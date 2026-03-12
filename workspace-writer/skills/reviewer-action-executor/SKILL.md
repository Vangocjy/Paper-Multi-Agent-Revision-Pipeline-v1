---
name: reviewer-action-executor
description: convert reviewer feedback and writer action lists into a conservative writer execution plan for manuscript revision. use when the task is to interpret reviewer comments, triage requested changes, decide what the writer should revise, what should be deferred, and what should be handed off to latex-editor in a paper revision workflow.
---

# reviewer-action-executor

Transform reviewer feedback into a writer-side execution plan before revising the manuscript.

## Objective
Given:
- reviewer master review
- reviewer writer action list
- current manuscript

produce a structured execution plan that tells the writer:
- what must be revised now
- what should be revised if safe
- what cannot be revised safely without new evidence
- what belongs to latex-editor instead
- what should be recorded as unresolved

## Core rule
Do not jump directly from reviewer comments to free-form manuscript rewriting.
Always triage first.

## Triage categories
Every reviewer-requested item should be assigned to one of the following:

### 1. must-fix
Use for issues that materially affect:
- scientific clarity
- argument logic
- contribution framing
- interpretation correctness
- overclaim risk
- manuscript readability in key sections

### 2. should-fix
Use for useful but non-blocking improvements:
- clearer transitions
- tighter wording
- better paragraph flow
- terminology cleanup
- mild structural polishing

### 3. safe-local-edit
Use for revision items that can be handled with local prose edits without altering scientific meaning.

### 4. unsafe-without-evidence
Use when reviewer requests would require:
- new experiments
- new quantitative support
- new citations not available and not verified
- stronger claims than the current evidence supports
- new methodological details not grounded in source text

These items must not be force-implemented by the writer.

### 5. latex-owned
Use when the issue is primarily about:
- formatting
- template compliance
- equation layout
- figure/table environment handling
- caption formatting
- bibliography style
- cross-reference mechanics
- compile/presentation layer issues

These should be redirected to latex-editor.

### 6. defer-to-unresolved
Use when the issue is recognized but cannot be safely resolved in the current round.
Always include a reason.

## Execution logic
For each reviewer item:
1. identify the actual underlying problem,
2. determine whether it is content-owned or latex-owned,
3. estimate whether safe revision is possible from existing manuscript evidence,
4. assign a triage category,
5. propose a concrete writer action or deferral note.

## Reviewer item traceability rule

Preserve reviewer item traceability from triage through execution planning.

For each reviewer-requested item:
- keep the original reviewer item ID if available
- otherwise assign a stable local planning ID
- carry that ID into the writer execution plan
- ensure the same ID can later appear in the writer change log and unresolved issues

The execution plan should not lose reviewer-item identity during categorization.

This traceability is required so that later reviewer rounds can verify:
- what was implemented
- what was only partially handled
- what was deferred
- what was redirected to latex-editor

## Output

Generate a file equivalent in structure to:

- round summary
- triaged action table
- planned manuscript edits by section
- non-actions with reasons
- handoff notes to latex-editor
- unresolved candidates

The triaged action table should include:
\-  reviewer item ID
\-  category
\-  writer action
\-  target section
\-  notes

## Writer-side interpretation rules

### Abstract
Prefer:
- compression
- clearer objective/method/result/conclusion chain
- explicit but bounded novelty statement
Avoid:
- adding unsupported performance claims
- inflating application or practical impact

### Introduction
Prefer:
- sharper gap definition
- clearer motivation
- more explicit contribution framing
Avoid:
- exaggerated novelty rhetoric

### Methods
Prefer:
- clearer role explanation of components
- cleaner relation between inputs, modules, and outputs
Avoid:
- inventing mechanism details not in source

### Results/Discussion
Prefer:
- interpretation over mere restatement
- cautious significance wording
- explicit scope limits where needed
Avoid:
- overgeneralization
- causal language without basis

### Conclusion
Prefer:
- restrained takeaways
- boundary-aware implications
Avoid:
- broad deployment claims
- unqualified superiority claims

## Boundary rules
Do not rewrite LaTeX formatting policy.
Do not attempt to “fix” template-level issues here.
Do not silently discard reviewer requests.

## Deliverable style
Be operational, not reflective.
The execution plan should read like a work order for the writer.