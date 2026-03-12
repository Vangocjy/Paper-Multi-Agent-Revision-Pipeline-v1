---
name: revision-packet
description: package writer-side manuscript revisions into a standard revision packet with revised tex, change log, and unresolved issues for downstream latex editing and reviewer re-check. use when the writer has finished a manuscript revision round and needs to hand off a traceable revision package.
---

# revision-packet

Package the writer’s revision outputs into a consistent, auditable handoff.

## Required outputs
For each round, produce:

1. `roundN_writer_revised.tex`
2. `roundN_writer_change_log.md`

Optional when needed:
3. `roundN_writer_unresolved_issues.md`
4. `roundN_writer_execution_plan.md`

## Purpose of each file

### revised manuscript
The actual writer-revised content manuscript for downstream use.

### change log
Explains:
- which reviewer concerns were addressed
- what sections were changed
- what kind of revision was made
- where the change was conservative or partial

### unresolved issues
Explains:
- which reviewer requests were not fully implemented
- why they were not safely actionable
- whether they require new evidence, author input, or latex-editor action

### execution plan
Internal or shareable planning artifact that records the writer’s triage before revision.

## Change log requirements
The change log should be organized by reviewer request or by manuscript section.
Each item should include:
- issue summary
- action taken
- affected section(s)
- notes on scope or limits when relevant

Do not write vague statements like:
- “improved wording throughout”
- “fixed several issues”
Be specific.

## Reviewer action mapping rule

The writer change log should map implemented or deferred changes back to reviewer action items whenever possible.

### Preferred mapping rule
- If the reviewer action list already provides stable item IDs, reuse those IDs directly.
- If the reviewer action list does not provide IDs, generate stable local writer mapping IDs based on section and order, such as:
  - `INTRO-1`
  - `METHOD-2`
  - `RESULT-1`

### Change log expectation
Each substantive change log entry should include:
- reviewer action item ID or local mapping ID
- issue summary
- action taken
- affected section(s)
- status
- notes on limits or partial handling when relevant

### Allowed statuses
Use one of the following:
- `implemented`
- `partially-implemented`
- `deferred`
- `redirected-to-latex`
- `unresolved`

### Mapping discipline
Do not write a change log that only says:
- “improved wording”
- “revised the introduction”
- “addressed reviewer concerns”

Instead, make it possible for the next reviewer round to trace:
- which reviewer request was addressed
- how it was addressed
- whether it was fully handled
- whether it was deferred or redirected

### If one reviewer item causes multiple edits
A single reviewer action item may correspond to multiple manuscript edits.
In that case:
- reuse the same reviewer item ID across multiple change log entries, or
- create subentries such as `R3.a`, `R3.b` if needed

### If multiple reviewer items are addressed together
If several reviewer items are resolved by one integrated revision, note all relevant reviewer IDs in the same entry and explain the merged handling briefly.



## Unresolved issue requirements
Each unresolved item should include:
- issue summary
- why unresolved
- whether it is evidence-limited, scope-limited, or latex-owned
- recommended next owner if applicable

## Output style
Be concise, factual, and audit-friendly.
Avoid self-praise or generic commentary.