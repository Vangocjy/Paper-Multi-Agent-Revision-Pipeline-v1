---
name: tex-format-fixer
description: repair latex-side manuscript presentation issues in tex files, including figures, tables, equations, captions, labels, refs, bibliography wiring, and local structural cleanup. use when the latex-editor needs to improve formatting quality and compile robustness without changing the paper's scientific meaning.
---

# tex-format-fixer

Repair LaTeX presentation and structure while preserving content meaning.

## Goal
Treat the `.tex` manuscript as a presentation-layer artifact that needs to be robust, consistent, and journal-facing.

## Primary responsibilities
Repair:
- figure and table environments
- caption consistency
- label and ref placement
- equation environments and numbering consistency
- bibliography and citation plumbing
- local structural inconsistencies that affect formatting or compile behavior

## Protected boundary
Do not use formatting repair as a reason to rewrite content.
If wording must change slightly to fit a caption, heading, or template requirement, keep the change minimal and report it.

## Figure insertion boundary

When a figure asset is available and the manuscript clearly requires it, you may normalize or finalize a figure environment after `figure-asset-integrator` has matched the asset.

Do not:
- guess image identity
- invent missing captions
- silently omit unresolved figure references
- treat absent assets as if the figure problem were solved

## Repair priorities
1. broken or risky environments
2. labels and cross-references
3. bibliography and citation compatibility
4. caption consistency
5. local normalization for journal-facing presentation

## Typical repairs
- normalize malformed figure or table environments
- attach captions and labels consistently
- simplify fragile float structures
- clean equation environment usage
- remove obvious duplication in labels
- align citation command usage with the template path
- preserve meaningful comments only when they help maintenance

## Avoid
- broad section rewriting
- changing scientific notation meaninglessly
- inventing missing reference entries
- cosmetic tweaks with no submission-facing benefit
