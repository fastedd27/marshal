# reference/_template

The build-your-own-gatekeeper skeleton. The decision logic in `../../rules.md` does not change.
You replace the three reference files below with your own domain, and the same engine runs your
handoff.

## How to use it

1. Read `../../PATTERN.md` and confirm your handoff meets the four conditions.
2. Copy these files up into `reference/` (replacing the smart-home ones), and fill in every
   `[PLACEHOLDER]`.
3. Leave `rules.md` alone. Only your reference tables change.

## The three files

- `support-critical-fields.md` : your front door, plus the must-have fields each item needs for
  your downstream party. This is the heaviest one and the most important.
- `contradiction-checks.md` : the internal inconsistencies worth catching.
- `support-advisories.md` : the non-blocking heads-ups that ride along to the downstream party.

Marshal's own `reference/` (one level up) is a fully worked, stress-tested example. Copy its shape.
