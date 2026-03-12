---
name: academic-tex-reviser
description: revise academic manuscript prose inside tex files while ignoring latex noise and respecting writer-only boundaries. use when the manuscript is in .tex format and content-level revision is needed without taking over template, layout, bibliography, or formatting responsibilities.
---

# academic-tex-reviser

Revise prose inside `.tex` manuscripts while preserving LaTeX structure and staying within writer scope.

## Goal
Treat the `.tex` file as a manuscript container, not as a layout engineering target.

## Primary responsibilities
Revise:
- abstract text
- section prose
- paragraph transitions
- contribution statements
- method explanation prose
- result interpretation prose
- discussion, limitation, conclusion wording
- terminology consistency
- text surrounding figures/tables when the issue is explanatory rather than formatting-related

## Protected zones
Do not actively rewrite unless unavoidable:
- preamble
- documentclass and package lines
- macro definitions
- bibliography configuration
- float placement logic
- equation layout environments
- table formatting structure
- figure/table environment mechanics
- label/ref mechanics unless text-adjacent cleanup is trivial

## Zone model
When reading `.tex`, classify regions as:

### prose-dominant zones
Safe to revise directly.
Examples:
- abstract body
- normal paragraphs under sections
- discussion text
- conclusion text

### mixed zones
Revise cautiously.
Examples:
- captions with substantive prose
- paragraphs containing inline math or refs
- itemized contribution lists

### layout-sensitive zones
Prefer not to edit except minimal wording cleanup.
Examples:
- complex tables
- aligned equations
- figure environments
- custom macros inside content blocks

### protected zones
Do not edit.
Examples:
- preamble
- package imports
- global formatting setup

## Revision rules
1. Preserve valid LaTeX syntax.
2. Prefer sentence-level or paragraph-level edits over structural tex surgery.
3. Avoid changing commands unless required for text integrity.
4. If an issue is mostly presentational, flag it for latex-editor instead.
5. If text revision risks compile breakage, choose the simpler edit.

## Academic editing priorities
- clarity
- coherence
- restraint
- section fit
- terminology consistency
- evidence-bounded claims

## Do not
- redesign manuscript structure globally unless explicitly required and safe
- rewire references/citations mechanically
- change equation notation for stylistic reasons alone
- alter formatting policies

## Output expectation
Produce a revised `.tex` manuscript that improves prose while remaining downstream-friendly for latex-editor.