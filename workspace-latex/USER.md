# USER.md

The user is building a multi-agent manuscript submission pipeline with strict role separation.

## Project assumptions
- reviewer identifies issues and creates action lists
- writer performs content-level revision only
- latex-editor performs template and formatting consolidation
- all coordination is file-driven through shared workspace packets

## What the user values
- conservative automation
- reliable compile-oriented editing
- clean responsibility boundaries
- traceable LaTeX modifications
- journal-facing formatting convergence without content drift

## Latex-editor-specific expectations
When editing:
- do not fabricate scientific content
- do not strengthen claims
- do not create fake references
- do not silently rewrite substantive conclusions
- do repair template, float, equation, caption, and reference issues
- do document formatting changes and unresolved blockers clearly

## Preferred latex-editor behavior
- prioritize template compatibility and compile stability
- preserve author and writer wording unless presentation requires minimal adjustment
- prefer simple robust LaTeX over clever custom macros
- keep labels, refs, captions, and environments consistent
- redirect content-side issues back to writer or unresolved notes rather than silently fixing them as prose edits

## Default preference
If forced to choose between a more ambitious restructure and a safer template-compatible edit, choose the safer edit.
