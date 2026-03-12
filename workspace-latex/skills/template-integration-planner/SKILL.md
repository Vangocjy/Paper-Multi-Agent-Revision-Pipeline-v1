---
name: template-integration-planner
description: convert writer revision packets, reviewer latex action lists, and target journal template requirements into a conservative latex execution plan. use when the latex-editor needs to decide what template integration, formatting repair, reference cleanup, and compile-oriented tasks should be performed in the current round.
---

# template-integration-planner

Create a structured latex execution plan before editing files.

## Objective
Given:
- current manuscript source
- latest writer revision packet
- reviewer latex action list when available
- target journal template and style notes

produce a plan that tells the latex-editor:
- what must be integrated into the template now
- what formatting issues are in scope
- what compile-related fixes are highest priority
- what content-side issues should not be silently edited
- what should be recorded as unresolved if not safely fixable

## Planning categories
Classify each issue into one of the following:

### 1. must-fix-format
Use for items that materially affect:
- template compatibility
- compile stability
- broken labels or refs
- malformed floats or equations
- citation or bibliography plumbing
- submission-facing formatting blockers

### 2. should-fix-format
Use for useful but non-blocking cleanup:
- caption consistency
- float tidiness
- sectioning polish for template fit
- spacing or environment normalization

### 3. compile-risk
Use for issues likely to break or destabilize compilation.

### 4. content-owned
Use when the apparent issue is fundamentally about scientific wording, logic, interpretation, or claim strength.
Do not silently convert these into latex-editor rewrites.

### 5. defer-to-unresolved
Use when the issue is recognized but cannot be safely resolved in the current round.
Always include a reason.

## Additional triage category: figure-asset-missing

Use this category when:
- the manuscript references a figure
- a figure environment is absent or incomplete
- image files may exist outside the tex source
- path repair or figure insertion is needed

For such cases, route the issue to `figure-asset-integrator` before final format cleanup.

## Output
Generate a file equivalent in structure to:
- round summary
- triaged format and template tasks
- planned edits by area
- content-owned non-actions
- expected compile checks
- unresolved candidates

## Priority order
When planning, prioritize in this order:
1. compile stability
2. template compatibility
3. reference and cross-reference correctness
4. figure/table/equation environment cleanup
5. consistency polish

## Boundary rule
Do not turn content problems into formatting edits.
If minimal wording adjustment is required for template fit, keep the wording change local, conservative, and report it.
