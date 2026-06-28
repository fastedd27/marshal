# The Acceptance-Gate Pattern

Marshal is one instance of a reusable pattern. This guide is the pattern itself: what it is, when
it fits, the engine that runs it, and how to build your own. If you came for the smart-home tool,
that is the worked example. The thing worth taking is the logic.

## What it is

An acceptance gate sits at a handoff. An author finishes a record; a downstream party depends on
it. Before the record is accepted, the gate decides whether that downstream party can actually do
their job from what is written. It clears the record, or it sends it back to the author with a
specific list of what to fix. The rare call the author cannot make routes to a supervisor. Routine
gaps go back to the author, never up the chain.

The logic is domain-agnostic. Marshal applies it to smart-home site documentation, but only one
layer is domain-specific: the `reference/` tables (what can be present, what fields are required,
what the front door is). Swap those and the same engine runs your handoff.

## When the pattern fits

All four of these have to be true:

1. An **author** produces a record (a document, a form, a package).
2. A **downstream party** cannot do their job well if the record is incomplete or inconsistent.
3. Today a **bottleneck person** hand-checks it, or no one does and the gaps surface downstream as cost.
4. **"Complete enough" is conditional**: not every blank is a gap, and what is required depends on what is present.

If all four hold, the pattern fits. If they do not, it probably is not the right tool (see the
boundary below).

## The engine (six steps, every time)

- **0. Front door.** Can the downstream party even act? Check the gating prerequisite first. If it
  fails, nothing else matters.
- **1. Presence.** Resolve what is actually in scope versus legitimately absent. Do not treat every
  blank as a gap; an item the record shows is not there is not a gap.
- **2. Per-item completeness.** For each item that is present, are the must-have fields there for
  the downstream party to act on?
- **3. Consistency.** Catch internal contradictions, not just blanks. Only check what the record
  actually captures, and only checks that hold regardless of brand, tool, or vendor.
- **4. Advisories.** Non-blocking heads-ups that ride along to the downstream party so they start
  closer to the answer.
- **5. Decide and route.** Accept (cleared for handoff), return to author (a specific punch list,
  addressed to whoever made the gap), or escalate the rare call to a supervisor.

Three disciplines keep it honest:

- **Never invent a value.** If the record does not capture something, that is a gap to flag, not a
  number to guess.
- **Never accept to be agreeable.** A false accept is the failure mode: it puts the work back on
  the bottleneck and surfaces downstream as cost.
- **Route accountability to the author.** The gate exists to take routine QA off one overloaded
  desk, not to become a new one.

## What it works for

Anywhere the four conditions hold. A partial list:

- Field-service closeouts &rarr; support **(Marshal)**
- IT asset and employee-onboarding handoffs &rarr; operations
- Patient or client intake &rarr; the clinician or caseworker
- Inspection and compliance reports &rarr; the reviewer
- Loan and mortgage application packages &rarr; underwriting
- Insurance claims &rarr; the adjuster
- Construction submittals and RFIs &rarr; the general contractor
- Grant and proposal packets &rarr; the review committee
- QA and test reports &rarr; release management
- Legal intake and discovery &rarr; the attorney

Different records, same engine. Only the reference tables change.

## What it is NOT (the honest boundary)

A readiness gate, not a correctness oracle. It checks whether the record has what the downstream
party needs and whether it contradicts itself. It does not judge whether the underlying work is
good, and it does not check anything the record never captured. It tells you the handoff is
complete and consistent. It does not tell you the install, the diagnosis, or the deal was right.

## Build your own

1. **Read this pattern.** Confirm your handoff meets the four conditions.
2. **Copy `reference/_template/`.** Fill in three things: the items that can be present, the
   must-have fields each one needs for your downstream party, and your front door (the gating
   prerequisite).
3. **Keep `rules.md` as is.** The engine does not change; only your reference tables do.
4. **Use Marshal as your worked example.** Its `reference/` and `sample-run/` show exactly what a
   filled-in, stress-tested instance looks like.

That is the whole move: the logic is fixed, the reference is yours.
