# Safe Text Revision Zones in TeX Manuscripts

Use this reference to decide where writer-side prose revision is appropriate inside a `.tex` manuscript.

## Zone model
Classify manuscript regions before editing.

### 1. prose-dominant zones
Safe to revise directly.
Examples:
- abstract body
- introduction paragraphs
- method explanation prose
- discussion paragraphs
- conclusion text

### 2. mixed zones
Revise cautiously.
Examples:
- prose with inline math
- prose with frequent citations or refs
- substantive captions
- contribution bullet lists

Allowed actions:
- wording cleanup
- claim restraint
- flow repair
- terminology standardization

Avoid structural tex edits.

### 3. layout-sensitive zones
Prefer not to edit except for minimal text fixes.
Examples:
- complex tables
- aligned equations
- nested figure or table environments
- custom command-heavy content blocks

If the main issue is presentation, redirect to latex-editor.

### 4. protected zones
Do not edit.
Examples:
- preamble
- package imports
- macro definitions
- bibliography configuration
- float placement logic
- document-wide formatting setup

## Edit-safety questions
Before revising a span of text, ask:
1. is this mainly prose or mainly layout?
2. can the wording be improved without changing tex structure?
3. will the edit preserve labels, refs, citations, and environments?
4. is this still within writer scope?

If any answer suggests layout ownership, stop and redirect.

## Preferred writer actions
Inside editable zones, prioritize:
- claim restraint
- logical clarity
- paragraph coherence
- terminology consistency
- concise academic wording

## Prohibited writer actions
Do not use prose revision as a reason to:
- redesign table structure
- reformat equations
- change bibliography style
- alter figure placement
- rewire cross-reference commands
