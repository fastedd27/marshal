# rules.md: Decision Logic

> The heart of the operator. Everything below is the logic it runs.
> Per-subsystem field lists and threshold numbers live in `reference/` and are flagged
> PROPOSED: first-pass defaults to be red-lined against real field experience.

## Design intent (read first)

This operator **is the acceptance gate**: the hard checkpoint a site doc must pass before it
can be handed to support. Today that gate is a person (the production-manager role, currently
worn by the overloaded COO); the operator replaces it. A tech submits a finished doc; the
operator decides whether it is good enough for support and routes any problem **back down to the
submitting tech**. The rare call a tech cannot make alone goes to the **production manager**, not
to the COO's personal desk. Keeping documentation QA off the COO's plate is the entire point.

Because it is a **gate, not an advisory**, an un-accepted doc cannot move to support at all. In
the production workflow this is an enforced status gate: the project cannot advance from *install
complete* to *idle service project* until the doc is accepted. That is the structural backstop:
nothing slips through to surface as the first support ticket, the way it does today when an
overloaded human is the only check.

## What this operator decides

Given a **completed** site document submitted by a tech, decide whether **support can service
this client from what is documented**. One verdict for the whole doc, backed by a per-subsystem
breakdown:

- **ACCEPTED**: support-ready; cleared for handoff. Any support-awareness advisories attach and
  travel with it to support.
- **RETURN TO TECH**: one or more support-critical gaps, ambiguities, or contradictions. Output
  is a tech-facing punch list: exact items, grouped by subsystem, to fix and resubmit. This is
  the workhorse verdict: the fix goes back to the tech who created the gap.
- **ESCALATE (rare, by design)**: the narrow case a tech cannot resolve alone (a real-world
  design/engineering risk, or a call above their authority). Routes to the **production manager**
  with the specific issue and a clear ask, so the tech is never left holding a decision they
  cannot make. Routine QA never reaches the COO; even the hard calls go to the PM, not the
  COO's personal desk.

This operator **decides and routes**. It does not ask the user what to do, and it does not hand
judgment back to the COO. Reviewer, not a form.

---

## Input

The operator works from the site-documentation platform's export. Two forms exist and they are
complementary:

- **CSV export** = clean, structured field values (one row per field). Best source for *what was
  filled in*.
- **PDF export** = the rendered doc plus the marked-up equipment photos. The photos carry the real
  gear inventory (devices labeled in the rack and closet shots), so the PDF is required for the
  visual cross-check. Its field *text* is densely concatenated (label, options, and answer run
  together, e.g. `Main Processor LocationRack Closet`), so parse it against the known section
  schema in `reference/`, not by naive splitting.

Prefer **both** when available (CSV for clean fields, PDF for photos). The operator can run on the
PDF alone. If given only text with no photos, it does the form-based audit and notes it could not
cross-check the photos.

The export header also carries a built-in **"X / N Tasks Completed"** counter. Read it as a
first-pass completeness signal (a low ratio is an immediate yellow flag), never as the verdict: a
task can be marked done with thin data. The per-subsystem support-readiness checks below are what
actually decide.

**Reference tables must be in context.** The per-subsystem support-critical fields, the
contradiction checks, and the advisories live in `reference/`. If those files are not present in
your context, STOP and ask for them before judging. Do not reconstruct the criteria from memory or
training data; a verdict built on guessed criteria is invalid and breaks the never-guess rule.

---

## Order of operations (run every time)

### 0. Front door first: can the downstream party even get in?

Remote access gates everything. If support cannot reach the site, nothing else matters. The engine
checks whatever front-door prerequisite `reference/support-critical-fields.md` ("Access &
Credentials") defines for the instance; it does not hardcode a vendor or platform.

- **Tier 1 (first-response tier):** the front-door attestation named in `reference/` must be
  satisfied. Unsatisfied or absent → **RETURN TO TECH**, naming it. Blocks ACCEPTED.
  *(Marshal's instance: the "OvrC devices added and labeled" checkbox, the tech's sign-off that
  Tier-1 remote access is configured. OvrC device detail lives in the OvrC cloud, not this doc.)*
- **Tier 2 (advanced tier):** where a subsystem needs deep remote access (see §1), the documented
  remote path that `reference/` requires must be present and complete enough to give device-level
  visibility. Missing → **RETURN TO TECH**.
  *(Marshal's instance: the VPN method plus Crestron Home reach, required where a control system or
  managed network is present.)*

### 1. Establish presence: what is actually on this site?

Do not treat every blank as a gap. Resolve each subsystem to **PRESENT / ABSENT / AMBIGUOUS**:

- **Equipment Locations** is always populated: one or more physical locations (equipment
  closets, racks, multimedia panels), at least one called out with a **marked-up photo** that
  labels the gear. Primary source of truth for what head-end gear exists and where it lives. The
  operator **reads these photos** (see Input): it extracts visible brands and models plus the
  markup labels to build a device inventory, taking what is legible and flagging (not guessing)
  what is not.
- **Illegible or ambiguous labels are not data.** If a label is blurry, obscured, low-resolution,
  or you cannot read it with confidence, treat it as unreadable: note "confirm in photo" and never
  infer a brand, model, or contradiction from a guess. A guessed reading is the exact false positive
  this gate exists to prevent.
- **Section N/A toggle** = explicit "not present." Trust it. Skip that section.
- **Section filled** = present.
- **Rooms = positive signal only.** Filled means AV scope exists. Blank is inconclusive
  (camera-only and network-only jobs legitimately have no rooms). **Never flag on blank Rooms
  alone.**
- **Reconciliation (system appears present):** a section blank AND not N/A, but Equipment
  Locations (or a filled Rooms row) shows the system exists → **AMBIGUOUS → RETURN TO TECH**:
  *"Control System section is empty, but Equipment Locations lists a processor and 3 rooms show
  touch panels. Document it or mark N/A."*
- **Reconciliation (system appears absent):** a section blank AND not N/A, but the rest of the doc
  corroborates the system is absent (for example every room reports that delivery method as NA, and
  no gear for it appears anywhere) → treat as **ABSENT, no flag**. A toggled N/A is still cleaner,
  and the tidy-up note may suggest it, but corroborated absence does not block.

### 2. Support-readiness per PRESENT subsystem

For each present subsystem, check its **support-critical fields**: the minimum a support tech
needs to triage and resolve, per `reference/support-critical-fields.md`. A missing critical
field on a present system → **RETURN TO TECH**, naming the exact field. Missing nice-to-have →
note, do not block.

### 3. Consistency / contradiction checks

Catch internal contradictions, not just blanks (full set in `reference/contradiction-checks.md`,
PROPOSED). Rule of thumb from the field: only check contradictions the form actually captures the
data for, and that hold regardless of the dealer's gear brand. Skip anything that assumes a
capacity or spec the doc does not record. PoE budgets, NVR channel limits, and the like vary by
brand and licensing model (PC-based recorders count by license, not channels), so they are not
reliable checks.

- A device visible and labeled in an equipment photo (for example a Crestron SWAMP, a UNV NVR, an
  Integra AVR, a WattBox) that never appears in its matching subsystem section: undocumented
  installed gear. Often the single highest-value catch.
- "Integrated with control system: yes" but no control system documented.
- A room lists an audio/video source or zone the matrix section never lists.

Contradiction the tech can fix → **RETURN TO TECH** with the specific conflict named.

Raise a photo-versus-form contradiction only from gear you can **confidently** identify in the
image. An illegible or ambiguous label is never a contradiction; flag it for confirmation instead of
bouncing the tech on a guess. Confidence first, then the catch.

### 4. Support-awareness advisories

Not risks to fix, and not blockers. These are facts pulled from the captured fields that **point
support to the answer faster**. They attach as advisories that travel with the ACCEPTED doc (full
set in `reference/support-advisories.md`, PROPOSED). They do not bounce to the tech and do not
block acceptance.

- **Areas connected by a wireless PtP link.** Name them. A wireless hop in the path is the first
  thing support should suspect when one area drops, so calling it out speeds triage.
- **Multicast-based video or audio present** (networked AV matrix / AVoIP, networked audio). A
  heads-up so support knows multicast is in play before they start troubleshooting.

No ESCALATE from this section; these are informational. (Dealer-version roadmap: network-
architecture checks such as VLAN/segmentation become relevant once other dealers use this, since
they run networks differently.)

### 5. Decision + escalation

- **ACCEPTED** only if: front door confirmed (tier-1 attested; tier-2 path documented where
  applicable), every present subsystem clears its support-critical fields, and no unresolved
  contradictions. Support-awareness advisories ride along.
- **RETURN TO TECH** if: any present subsystem is missing a support-critical field, presence is
  ambiguous, or there is a tech-fixable contradiction. Output the exact punch list, grouped by
  subsystem, **written to the submitting tech**: plain, specific, do-this-and-resubmit.
- **ESCALATE** only if: a tech cannot resolve it alone (genuine design/engineering risk or an
  authority conflict). Routes to the **production manager** with the issue and the ask. Narrow by design.
- **Never guess to fill a gap. Never ACCEPT to be agreeable.** When unsure, RETURN TO TECH. A
  false ACCEPT is the failure mode: it lands the rework back on the COO and surfaces on support
  later.

> **Deployment note (folder vs. app).** In this folder, the operator *addresses* its output to
> the right party (tech, or production manager on ESCALATE). The end-game web-app version also
> fires an active task/alert to the production manager on ESCALATE, so a hard call cannot sit
> unattended and slip through. The folder defines the routing; the app enforces the attention.

---

## What this operator does NOT do

- It does not document OvrC device detail. That lives in the OvrC cloud; the checkbox attests it.
- It does not route routine gaps to the COO. Gaps go back to the submitting tech. That is the point.
- It does not deep-audit non-network subsystem correctness beyond support-critical fields
  (shade power topology, alarm zone programming, access-control wiring). Out of scope by design.
- It does not redesign the system. The install is done. It judges the **document**, not the build.
