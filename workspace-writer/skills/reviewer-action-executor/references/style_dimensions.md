# Action Triage Dimensions

Use this reference to classify reviewer requests into writer-appropriate action categories.

## Primary triage question
For each reviewer request, determine:
1. what the underlying problem is,
2. whether it is content-owned or latex-owned,
3. whether the manuscript already contains enough support to revise safely,
4. whether the requested change is local or broad,
5. whether it should be implemented, deferred, or redirected.

## Triage dimensions

### 1. ownership
Classify each issue as one of:
- writer-owned content issue
- latex-owned presentation issue
- mixed issue requiring partial writer action and partial latex handoff

### 2. evidence safety
Ask whether the revision can be supported by the current manuscript.

Safe examples:
- clarifying a contribution statement
- tightening an abstract claim
- improving result interpretation wording
- standardizing terminology

Unsafe examples:
- adding a new citation not already verified
- asserting broader generalizability than shown
- inventing methodological rationale
- adding unreported experimental detail

### 3. revision scope
Estimate how invasive the change needs to be:
- local sentence edit
- paragraph repair
- section-level reframing
- unsafe broad rewrite

Prefer the smallest change that resolves the reviewer concern.

### 4. action category
Map the request to one of:
- `must-fix`
- `should-fix`
- `safe-local-edit`
- `unsafe-without-evidence`
- `latex-owned`
- `defer-to-unresolved`

## Decision cues

### must-fix
Use when the issue affects:
- scientific clarity
- contribution framing
- interpretation correctness
- overclaim risk
- major readability in key sections

### should-fix
Use when the issue improves quality but is not blocking.
Examples:
- smoother transitions
- cleaner paragraph flow
- wording compression
- terminology cleanup

### unsafe-without-evidence
Use when the reviewer request would require new support.
These items should not be force-implemented.

### latex-owned
Use when the issue is primarily about:
- formatting
- template compliance
- figure/table presentation
- equation layout
- caption policy
- bibliography style
- cross-reference mechanics

### defer-to-unresolved
Use when the issue is real but cannot be safely resolved in the current round.
Always include a reason.

## Output reminder
The execution plan should read like a work order, not like an essay.
For each item, record:
- reviewer concern summary
- triage category
- writer action or non-action
- brief reason
