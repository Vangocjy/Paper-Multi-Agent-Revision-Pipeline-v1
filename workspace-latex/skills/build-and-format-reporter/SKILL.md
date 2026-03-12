---
name: build-and-format-reporter
description: summarize latex build status, formatting actions, unresolved blockers, and content-boundary notes into standard latex packet reports. use when the latex-editor has completed a formatting round and needs to hand off a traceable build report and format report.
---

# build-and-format-reporter

Package the latex-editor round into clear, audit-friendly reports.

## Required outputs
For each round, produce:
1. `roundN_latex_formatted.tex`
2. `roundN_latex_build_status.md`
3. `roundN_latex_format_report.md`

Optional when needed:
4. `roundN_latex_unresolved_issues.md`
5. `roundN_latex_execution_plan.md`

## Build status requirements
The build status report should state:
- whether compilation is confirmed, estimated, or not verified
- the major build blockers if any
- likely source locations or categories of issues
- whether refs/citations/floats appear stable, degraded, or unknown

Do not pretend a build succeeded if it was not actually verified.

## Format report requirements
The format report should explain:
- which template integration actions were taken
- which figure/table/equation/ref issues were repaired
- any local wording adjustments required for formatting reasons
- what remains unresolved
- which issues are content-owned rather than latex-owned

## Figure asset status section

Every format/build report should include a figure asset status section covering:
- figures referenced in manuscript
- figures already present before this round
- figures inserted this round
- image paths repaired
- figures moved to appendix
- unresolved figure references
- asset format issues such as svg-only availability without processed pdf

## Reporting style
Be factual, concise, and audit-friendly.
Avoid vague claims like “formatting improved throughout”.
Be specific about classes of changes and remaining blockers.
