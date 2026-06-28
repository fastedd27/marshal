# support-critical-fields (template)

> Replace every `[PLACEHOLDER]`. The test for every field: if the downstream party needs it to do
> their job, it is CRITICAL. If it is merely useful, it is nice-to-have.
> CRITICAL = if missing on a present item, the record cannot be ACCEPTED (return it to the author).
> Nice-to-have = note it, do not block.

## Front door (the gating prerequisite)

Define what must be documented for the downstream party to even begin. If this is missing, nothing
else matters and the record is returned regardless of how complete the rest is.

- `[the access path, identifier, or authorization the downstream party needs to act]`

## Per item

For each item that can appear in the record, list its support-critical fields.

### [ITEM 1 NAME]

**CRITICAL**
- `[must-have field]`
- `[must-have field]`

**Nice-to-have**
- `[useful but non-blocking field]`

### [ITEM 2 NAME]

**CRITICAL**
- `[must-have field]`

**Nice-to-have**
- `[useful but non-blocking field]`

*(repeat per item)*

## Always-present anchor (optional but powerful)

If your record has a section that is always filled, name it here. It becomes the reliable signal
for resolving whether other items are genuinely present or genuinely absent, so blanks are not
mistaken for gaps.

- `[the section your record always has]`
