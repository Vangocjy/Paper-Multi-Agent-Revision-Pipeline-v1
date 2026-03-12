---
name: journal-template-integrator
description: integrate a revised manuscript into a target journal latex template while preserving scientific wording as much as possible. use when the latex-editor needs to adapt section structure, metadata placement, environments, bibliography plumbing, and template-specific layout conventions for a submission-oriented manuscript.
---

# journal-template-integrator

Integrate manuscript content into the target journal template conservatively.

## Goal
Treat the target journal template as the structural destination for the manuscript.
Preserve scientific wording whenever possible while adapting the document to the required LaTeX scaffold.

## Primary responsibilities
Handle:
- document structure alignment with template expectations
- title, author, abstract, keywords placement when needed
- section hierarchy adaptation for template fit
- front-matter and back-matter placement
- bibliography integration compatible with the template
- safe migration of manuscript content into template-owned environments

## Integration rules
1. Preserve writer-owned wording unless template fit requires local adjustment.
2. Prefer template-native commands and environments over custom workarounds.
3. Keep labels, refs, and citation commands consistent with the chosen template path.
4. Avoid broad content rewrites during integration.
5. If template integration reveals a content-side problem, log it instead of silently rewriting it.

## Safe structural edits
Examples of in-scope edits:
- moving abstract into template-defined environment
- aligning keywords placement
- mapping section headings into template-compatible structure
- normalizing bibliography include pattern
- consolidating figure/table usage into template-friendly conventions

## Unsafe edits
Avoid unless absolutely required and explicitly reported:
- rewriting scientific contributions
- compressing or expanding interpretation substantially
- replacing author intent with template-driven prose
- changing conclusions or claims

## Output expectation
Produce a manuscript source that looks structurally like the target journal template while remaining faithful to the latest writer revision.
