# Marshal

**The acceptance gate for smart-home site documentation. It clears the doc, or sends it back to the
tech who owns the gap. It never invents a value, never rubber-stamps to be agreeable, and never
lands the rework on you.**

Marshal reviews a finished site document at the moment it leaves the install team for support. It
decides whether support can actually service the client from what is written, returns a precise
punch list for anything missing, and clears the doc only when it is genuinely service-ready. It is
the gate, so nothing half-finished slips through to surface later as the first support ticket.

## Try it in 60 seconds

You do not need any documentation of your own to see this work.

1. Drop this folder into a Claude project, or paste its files in as context.
2. Paste in `sample-run/sample-site-doc.md`.
3. Ask: "Run Marshal on this doc."

It returns a verdict (RETURN TO TECH) with a specific punch list. Then paste
`sample-run/sample-site-doc-corrected.md` and watch it ACCEPT cleanly. The gate runs both directions.

## The folder (the methodology)

The interpretable-context structure, each file doing one job:

- `identity.md` : who Marshal is and what it owns.
- `rules.md` : the decision logic. Input handling, the order of operations, the three verdicts, the
  escalation rules. The heart.
- `examples.md` : worked decisions, including the edge case the obvious rules do not cover.
- `reference/` : the field-level detail. Support-critical fields per subsystem, the consistency
  checks, the support advisories.
- `README.md` : this file.

## Also in here

Context and reusability, signposted so they help rather than clutter:

- `brief.md` : the client brief. The client is me. Start here.
- `background.md` : the real story. Why this exists, and where it goes next.
- `PATTERN.md` : the logic decoupled from smart-home. What kinds of handoffs the gate works for, and
  how to build your own.
- `sample-run/` : a full before-and-after. A gapped doc that bounces, and the same doc fixed that
  clears, each with the verdict Marshal returned. Drop in and watch it work.
- `reference/_template/` : a fill-in skeleton to point Marshal at your own handoff.

Suggested order: `brief.md` (the problem), then this README, then `sample-run/` (watch it work),
then `rules.md` (the logic), then `PATTERN.md` (the general version).

## Input

Marshal works from a completed site-doc export. Best input is the PDF (it carries the marked-up
equipment photos) plus the CSV (clean field values). The PDF alone works; a text-only export works
with reduced photo cross-checking. It returns one of three verdicts:

- **ACCEPTED** : cleared for handoff, with any support advisories attached.
- **RETURN TO TECH** : a punch list of exactly what to fix, addressed to the submitting tech.
- **ESCALATE** : the rare call a tech cannot make alone, routed to the production manager.

## Make it yours

You do not need smart-home docs to use this. The decision logic in `rules.md` is domain-agnostic;
the only domain-specific layer is `reference/`. To run Marshal on your own handoff:

1. Read `PATTERN.md` and confirm your handoff fits the four conditions.
2. Copy `reference/_template/` and fill in three things: the items that can be present, the
   must-have fields each one needs for your downstream party, and your front door (the gating
   prerequisite).
3. Keep `rules.md` as is. The engine does not change; only your reference tables do.

`PATTERN.md` lists the handoffs this fits, from field-service closeouts to loan underwriting to
clinical intake.

## Adapting the roles

Marshal is built around one integrator's real workflow: a field-capture and site-documentation
platform, an offsite tier-1 support partner, an advanced in-house tier-2 team, and a production
manager who owns escalations. Map those roles to your equivalents. The decision logic does not
change; only the reference tables and the role names do.
