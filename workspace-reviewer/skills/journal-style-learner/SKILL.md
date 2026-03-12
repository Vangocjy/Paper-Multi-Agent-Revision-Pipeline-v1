---
name: journal-style-learner

description: learn and maintain target journal style expectations for manuscript review. use when reviewer needs to judge journal fit, update journal_style.md, compare a manuscript against target-journal conventions, infer style patterns from journal sample papers, or bootstrap a practical journal baseline before the first formal review round.
---

# Journal Style Learner

Learn, refine, and maintain the target journal style baseline used by the reviewer.

Use this skill when:
- `journal_style.md` is missing
- `journal_style.md` is incomplete, weak, placeholder-heavy, or outdated
- reviewer needs stronger evidence for a journal-fit judgment
- reviewer must compare the manuscript against target-journal conventions
- reviewer needs to infer style patterns from sample papers
- round 1 requires a practical style baseline before formal review

## Goal

Produce or refine a reusable journal-style summary that helps the reviewer judge:

- structure
- tone
- citation pattern
- figure and table presentation
- methodological detail level
- expected experiment density
- discussion and conclusion style
- overall fit with the target journal

The main output of this skill is an improved `journal_style.md`.

## First-round bootstrap rule

If `journal_style.md` is incomplete, placeholder-heavy, or insufficient for journal-fit judgment, generate a practical first-pass style guide before continuing formal review.

This is especially important in round 1, where the reviewer should not rely on generic academic expectations when the target journal style has not yet been operationalized.

## Bootstrap mode

In bootstrap mode:

1. inspect the current `journal_style.md`
2. identify missing or weak sections
3. read representative journal sample PDFs selectively
4. extract only review-relevant style evidence
5. update `journal_style.md` into a minimally usable journal baseline
6. optionally record evidence and confidence in `round1_reviewer_style_bootstrap_notes.md`

Do not attempt a full journal survey.
Aim for a practical review baseline that improves manuscript judgment immediately.

## Primary sources

Use sources in this order:

1. existing `journal_style.md`
2. journal sample papers in `journal_samples/`
3. target journal template artifacts when helpful
4. official public author guidelines when necessary

Prefer local sources first.

## Working principle

Do not imitate surface wording from papers.

Instead, infer stable editorial patterns such as:
- what sections typically appear
- how detailed methods usually are
- how claims are phrased
- how figures and tables are used
- how dense references are
- how conclusions are scoped

Focus on patterns that help manuscript review.

## When to read sample papers

Read sample papers only when needed.

Examples:
- `journal_style.md` does not exist
- `journal_style.md` lacks enough detail for a decision
- the current manuscript raises a specific style question
- the reviewer needs evidence for a journal-fit judgment
- round 1 requires first-pass style bootstrap

Do not read all papers blindly. Sample strategically.

## Sampling strategy

When consulting `journal_samples/`, prefer a targeted sample:

- 2 to 4 representative papers first
- add more only if style evidence is inconsistent
- prioritize papers closest in topic, structure, or method to the target manuscript

Use `references/style_dimensions.md` to guide what to observe.

## Minimum viable output standard

A first-pass `journal_style.md` is usable only if it provides actionable guidance for:
- abstract style
- introduction and contribution framing
- methods density and exposition
- result presentation and figure/table expectations
- discussion and conclusion restraint
- language tone and claim strength
- likely journal-fit review blockers

If these areas are not covered, continue extracting evidence until they are.

## Output file

Maintain or create:

`D:\apps\openclaw\workspace-reviewer\journal_style.md`

This file should be concise, reusable, and review-oriented.

## Output requirements

The journal style summary should include:

- journal identity or venue note
- typical section structure
- abstract style
- introduction style
- related work treatment
- methods detail expectations
- experiment structure expectations
- figure and table conventions
- citation density and style tendencies
- discussion and conclusion tendencies
- language and claim style
- review implications

Do not turn `journal_style.md` into a long literature review.

Keep it focused on patterns that matter for review.

## Review-facing orientation

The purpose of journal-style learning is to improve later review decisions.

Every extracted style point should help answer at least one of these questions:
- does the manuscript sound like a submission to the target journal?
- is the contribution framed in a journal-appropriate way?
- are methods, figures, and results presented with the expected level of clarity and density?
- are discussion and conclusion claims sufficiently bounded?
- which issues should be sent to writer versus latex-editor?

## Evidence use rule

Prefer extracting:
- recurring rhetorical patterns
- section-level expectations
- figure/table presentation norms
- claim restraint patterns
- contribution framing style
- density and tone of methods/results writing

Avoid filling `journal_style.md` with:
- generic publication advice
- historical journal background
- non-actionable observations
- long article summaries

## Confidence rule

When evidence is weak or sample coverage is limited, state the inference conservatively in `journal_style.md`.

Prefer wording such as:
- "appears to favor"
- "often presents"
- "typically emphasizes"
- "tends to use"

Do not overstate stylistic certainty from one or two examples.

## Trigger for forced refresh

Refresh `journal_style.md` before formal review when any of the following is true:
- the file still contains placeholder text
- most sections are empty or generic
- the target journal or template has changed
- the reviewer cannot make journal-fit judgments confidently from the current file

## Review usage

When reviewer evaluates journal fit, use `journal_style.md` as the default reference.

Only fall back to sample papers when:
- the summary is insufficient
- a style judgment is uncertain
- a specific formatting or rhetorical question needs confirmation

## Safety and boundaries

You must not:
- fabricate journal requirements
- pretend a weak inference is a hard rule
- overgeneralize from one paper
- copy long passages from sample papers
- perform external actions beyond information retrieval