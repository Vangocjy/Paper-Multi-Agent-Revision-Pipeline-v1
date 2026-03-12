---
name: claim-and-flow-editor
description: improve academic claim restraint, paragraph flow, contribution framing, and section-level coherence in a manuscript revision workflow. use when the writer needs to make the paper read more like a submission-ready academic manuscript by tightening abstracts, sharpening introductions, clarifying method narration, strengthening result interpretation, repairing transitions, reducing overclaim, and enforcing terminology consistency without inventing new evidence or expanding conclusions.
---

# claim-and-flow-editor

Improve manuscript prose at the level of claims, logic flow, and publication-facing academic style.

## Objective
Given a manuscript section or subsection, revise it so that it is:
- clearer
- more coherent
- more academically restrained
- better aligned with reviewer-facing expectations for a submission manuscript

This skill is for content refinement, not scientific invention and not LaTeX formatting.

## Core role
This skill helps the writer answer:
- Is the claim too strong?
- Is the contribution framed clearly enough?
- Does the paragraph sequence make sense?
- Is the method explained clearly without hype?
- Are results interpreted rather than merely restated?
- Does the conclusion stay within evidence bounds?
- Are terms used consistently?

## Non-negotiable constraints
Do not:
- invent results
- invent citations
- invent methodological details
- imply evidence that is not present
- convert tentative findings into broad claims
- introduce causal language without support
- turn formatting problems into prose edits
- rewrite for style alone when no clarity benefit exists

When uncertain, reduce claim strength rather than increase it.

## Scope gate
Use this skill only after revision scope has been triaged. Apply it only within writer-owned prose regions already approved for revision. Do not use it to introduce broader reframing, stronger novelty language, unsupported implications, or content outside the approved writer action scope.

## Editing priorities

### 1. claim restraint
Revise claims so they match the available evidence.

Prefer:
- “suggests”
- “is associated with”
- “shows improved performance under the evaluated setting”
- “demonstrates potential”
- “within the tested scenario”

Avoid unless fully supported:
- “proves”
- “guarantees”
- “is universally applicable”
- “significantly better” without explicit support
- “applicationly deployable” without clear evidence
- “robust in real-world settings” unless actually shown

### 2. contribution framing
Make the paper’s contribution easier to identify.

Prefer contribution statements that specify:
- what problem is addressed
- what gap is targeted
- what was proposed
- what is distinctive about the approach
- what evidence supports the contribution

Avoid vague novelty language such as:
- “for the first time”
- “novel and powerful”
- “highly innovative”
unless this is clearly justified and necessary.

### 3. paragraph flow
Improve local and section-level coherence.

Typical repairs:
- add topic sentences
- make the first sentence announce the paragraph’s role
- remove abrupt jumps
- add bridge phrases between problem, method, and result
- reorder sentences when needed for logic
- reduce repetition across adjacent paragraphs

Good paragraph behavior:
- first sentence frames purpose
- middle sentences provide support/explanation
- final sentence transitions or closes the point

### 4. abstract tightening
The abstract should form a compact chain:
- problem/context
- gap/challenge
- proposed approach
- evaluation setting
- key finding
- bounded implication

Prefer compression and information density.
Remove generic background filler.

### 5. introduction sharpening
The introduction should clearly move through:
- problem importance
- current limitation or gap
- why the gap matters
- what this paper does
- why that contribution matters

If contributions are diffuse, rewrite toward a cleaner gap-to-contribution line.

### 6. method narration
Clarify the role of each method component in prose.

Prefer:
- function-oriented explanations
- input-process-output narration
- relation between modules
- motivation for each component when already supported

Avoid:
- pseudo-mathematical hype
- repeating equations in prose without added meaning
- adding undocumented technical detail

### 7. results interpretation
Strengthen the writing around results.

Prefer:
- what the result indicates
- how it relates to the research question
- why it matters in the scope of the study
- what limitation remains

Avoid:
- pure score restatement with no interpretation
- sweeping real-world conclusions
- speculative mechanism claims not supported by evidence

### 8. conclusion restraint
The conclusion should:
- summarize contribution clearly
- restate findings conservatively
- acknowledge scope boundaries where needed
- avoid broad deployment or application impact claims unless warranted

## Section-specific guidance

## Abstract
Revise toward:
- concise motivation
- specific gap
- explicit method identity
- compact performance summary
- restrained significance statement

Do not:
- overload with background
- repeat introduction language
- claim general impact beyond evidence

## Introduction
Revise toward:
- precise problem framing
- clear literature or practice gap
- explicit rationale for the proposed approach
- recognizable contribution statement

Do not:
- let the section become a broad essay
- overuse generic motivation
- hide the contribution at the end of long paragraphs

## Methods
Revise toward:
- explain what each component does
- explain why components are included when supported
- maintain terminology consistency
- reduce ambiguity in procedural descriptions

Do not:
- fabricate design rationale
- add mathematical detail not present in source

## Results / Discussion
Revise toward:
- interpretive clarity
- comparison framing
- scope-aware takeaways
- connection back to the study objective

Do not:
- exaggerate practical significance
- generalize beyond evaluated data/settings
- present observed patterns as causal facts

## Conclusion
Revise toward:
- concise synthesis
- bounded takeaway
- realistic future-facing statement if needed

Do not:
- restate the entire paper
- broaden claims at the very end
- promise deployment readiness without support

## Terminology consistency
Standardize repeated technical terms within and across sections.

Prefer:
- one consistent name for the same concept
- stable naming for modules, tasks, datasets, and evaluation targets
- consistent singular/plural usage where it affects meaning

If two terms are used for the same concept, choose the manuscript’s dominant term unless reviewer guidance suggests otherwise.

## Typical transformations

### Overclaim reduction
Before:
- “Our method significantly improves general signal_value prediction and is highly suitable for application deployment.”

After:
- “Our method improves prediction performance in the evaluated setting and shows potential for future applicationly oriented refinement.”

### Contribution clarification
Before:
- “We propose a novel framework with several useful modules.”

After:
- “We propose a structured multi-mechanism framework for single-variable SensorSequence modeling, designed to better handle heterogeneous signal_value dynamics under distribution shift.”

### Result interpretation strengthening
Before:
- “The model achieved lower error than baselines.”

After:
- “The lower error suggests that the proposed representation better captures the evolving temporal patterns in the evaluated SensorSequence sequences, although validation remains limited to the tested setting.”

### Flow repair
Before:
- paragraph 1 ends with dataset statement
- paragraph 2 abruptly starts technical details

After:
- add a bridge sentence linking the identified challenge to the architectural choice

## Decision rules
When revising, prioritize in this order:
1. correctness of claim strength
2. clarity of logic
3. readability and flow
4. concision
5. stylistic polish

If a stylistic improvement risks altering scientific meaning, do not apply it.

## Handoff posture
This skill should produce prose that is easier for:
- reviewer to accept
- latex-editor to preserve
- downstream revision tracking to explain

The output should feel like a stronger submission draft, not like a different paper.