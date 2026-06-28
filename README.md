<p align="center">
  <img src="docs/assets/banner.png" alt="Marshal, the acceptance gate" width="100%">
</p>

<h1 align="center">Marshal</h1>

<p align="center"><strong>The acceptance gate for the production-to-support handoff.</strong><br>
It clears a finished site doc, or sends it back to the tech who owns the gap. It never invents a value, never rubber-stamps to be agreeable, and never lands the rework on you.</p>

<p align="center">
  <img alt="License: MIT" src="https://img.shields.io/badge/license-MIT-d9a441">
  <img alt="Type: interpretable context" src="https://img.shields.io/badge/type-interpretable%20context-15110a">
  <img alt="Dependencies: none" src="https://img.shields.io/badge/dependencies-none-849a5a">
  <img alt="Status: heading to beta" src="https://img.shields.io/badge/status-heading%20to%20beta-a8553a">
</p>

<p align="center">
  <a href="https://fastedd27.github.io/marshal/"><strong>Live site</strong></a> &nbsp;&middot;&nbsp;
  <a href="#try-it-in-60-seconds">Try it in 60 seconds</a> &nbsp;&middot;&nbsp;
  <a href="brief.md">The brief</a> &nbsp;&middot;&nbsp;
  <a href="PATTERN.md">Build your own</a>
</p>

---

Marshal reviews a finished site document at the moment it leaves the install team for support. It decides whether support can actually service the client from what is written, returns a precise punch list for anything missing, and clears the doc only when it is genuinely service-ready. It is the gate, so nothing half-finished slips through to surface later as the first support ticket.

It is not an app. It is a folder of interpretable context you drop into any AI assistant.

## The folder

Each file does one job. The only domain-specific layer is `reference/`, the one folder you swap to point Marshal at a different handoff.

```
marshal/
├─ brief.md            # the client brief (the client is me). start here
├─ identity.md         # who Marshal is and what it owns
├─ rules.md            # the decision logic: input handling, order of
│                      #   operations, the three verdicts, escalation. the engine
├─ examples.md         # worked decisions, including the edge cases the
│                      #   obvious rules do not cover
├─ PATTERN.md          # the logic decoupled from smart-home. build your own
├─ background.md       # the real story: why this exists, where it goes next
├─ reference/          # the domain layer (the only part you swap)
│  ├─ support-critical-fields.md   # must-have fields per subsystem
│  ├─ contradiction-checks.md      # consistency checks across the doc
│  ├─ support-advisories.md        # heads-ups that ride along on ACCEPT
│  └─ _template/                   # fill-in kit for your own handoff
├─ sample-run/         # a full before/after you can run right now
│  ├─ sample-site-doc.md             # gapped   ->  RETURN TO TECH
│  ├─ sample-output.md               #             the verdict it returned
│  ├─ sample-site-doc-corrected.md   # fixed     ->  ACCEPTED
│  └─ sample-output-corrected.md     #             cleared for handoff
└─ docs/               # the landing site (GitHub Pages)
```

Suggested reading order: `brief.md` (the problem), this README, `sample-run/` (watch it work), `rules.md` (the logic), then `PATTERN.md` (the general version).

## Try it in 60 seconds

You do not need any documentation of your own to see this work.

1. Drop this folder into a Claude project, or paste its files in as context.
2. Paste in `sample-run/sample-site-doc.md`.
3. Ask: **"Run Marshal on this doc."**

It returns **RETURN TO TECH** with a specific punch list. Then paste `sample-run/sample-site-doc-corrected.md` and watch it **ACCEPT** cleanly. The gate runs both directions.

## How it decides

Marshal works from a completed site-doc export. Best input is the PDF (it carries the marked-up equipment photos) plus the CSV (clean field values). It returns one of three verdicts:

| Verdict | Meaning |
|---|---|
| **ACCEPTED** | Cleared for handoff, with any support advisories attached. |
| **RETURN TO TECH** | A punch list of exactly what to fix, addressed to the submitting tech. |
| **ESCALATE** | The rare call a tech cannot make alone, routed to the production manager. |

The part nobody else does: it reads the marked-up rack and closet photos, pins the exact gear the form left generic, and catches anything installed but never written down. The form can be vague. The photo is not.

## Make it yours

The decision logic in `rules.md` is domain-agnostic. The only domain-specific layer is `reference/`. To run Marshal on your own handoff:

1. Read `PATTERN.md` and confirm your handoff fits the four conditions.
2. Copy `reference/_template/` and fill in three things: the items that can be present, the must-have fields each one needs for your downstream party, and your front door (the gating prerequisite).
3. Keep `rules.md` as is. The engine does not change; only your reference tables do.

`PATTERN.md` lists the handoffs this fits, from field-service closeouts to loan underwriting to clinical intake.

## Adapting the roles

Marshal is built around one integrator's real workflow: a field-capture and site-documentation platform, an offsite tier-1 support partner, an advanced in-house tier-2 team, and a production manager who owns escalations. Map those roles to your equivalents. The decision logic does not change; only the reference tables and the role names do.

---

<p align="center"><sub>Built for Weekly Comp #8: The Wildcard. MIT licensed. Use it before your next handoff.</sub></p>
