---
name: review-packet

description: generate structured review outputs for academic manuscript review. use when reviewing a manuscript tex file, evaluating a revised draft, or preparing reviewer handoff files for writer and latex-editor. produce a master review, a writer action list, and a latex action list.
---
# Review Packet

Generate a structured review handoff for an academic manuscript.

Use this skill when:
- reviewing a `.tex` manuscript
- reviewing a revised manuscript from the shared workspace
- converting reviewer judgments into actionable tasks for other agents
- preparing handoff files for writer and latex-editor

## Goal

Convert review findings into three clear outputs:

1. a master review report
2. a writer action list
3. a latex action list

The outputs must be specific, actionable, and separated by responsibility.

## Inputs

Review based on any relevant combination of:

- manuscript `.tex` files
- writer revision packets from the shared workspace
- latex packets from the shared workspace
- `journal_style.md`
- journal sample PDFs when needed

Ignore LaTeX noise unless it affects:
- structure
- readability
- figure or table communication
- equation presentation
- references
- journal fit

## Review dimensions

Evaluate the manuscript across these dimensions:

### Scientific and argumentative quality
- contribution clarity
- problem definition
- novelty positioning
- methodological soundness
- support for claims
- adequacy of experiments

### Communication quality
- logical flow
- section coherence
- paragraph clarity
- precision of writing
- overclaiming or unsupported statements

### Presentation quality
- figure clarity
- table readability
- caption quality
- equation readability
- reference and citation presentation
- overall journal style fit

## Severity labels

Label each issue as one of:

- Critical
- Major
- Minor

Definitions:

- **Critical**: threatens validity, contribution, or publishability
- **Major**: substantially weakens rigor, clarity, or journal fit
- **Minor**: improves readability, polish, or consistency

## Required outputs

Produce exactly these three files for each review round:

- `roundN_reviewer_master_review.md`
- `roundN_reviewer_writer_action_list.md`
- `roundN_reviewer_latex_action_list.md`

Replace `N` with the actual round number.

Use the templates in:

`references/output_templates.md`

## Output rules

Follow these rules strictly:

- be specific
- be actionable
- separate content issues from formatting issues
- do not rewrite the manuscript in full
- do not give vague criticism without a fix
- convert findings into executable downstream tasks

## Writer action list rules

Writer-facing tasks must:

- identify location
- describe the problem clearly
- define the revision goal
- preserve scientific meaning
- avoid fabrication
- avoid unnecessary rewriting outside the targeted scope

Examples of writer-facing tasks:

- Clarify the final paragraph of the Introduction and explicitly state the paper's main contribution.
- Rewrite the explanation of baseline selection in the Experiments section to justify why the chosen baselines are appropriate.
- Reduce overclaiming in the Conclusion and align wording with the actual evidence.

## Latex action list rules

Latex-facing tasks must focus on:

- figures
- tables
- equations
- citations
- references
- layout
- section presentation
- template consistency

Examples of latex-facing tasks:

- Reformat Table 2 to reduce line overflow and improve readability.
- Standardize figure captions so they are self-contained and consistent with journal style.
- Check whether Equation 5 should use a numbered equation environment.

Do not ask latex-editor to change scientific claims unless formatting clarity requires it.

## Save locations

Save outputs in both locations:

### Local archive
`D:\apps\openclaw\workspace-reviewer\reviews\`

### Shared handoff
`D:\apps\openclaw\workspace-shared\review_packets\`

## Collaboration model

These outputs are used by downstream agents:

- writer reads the writer action list
- latex-editor reads the latex action list
- the master review serves as the complete reviewer record

## Safety

You must not:

- fabricate references, methods, results, or claims
- rewrite the full manuscript
- directly edit other agents' workspaces
- post, upload, publish, or comment externally
- take any action that may harm the user
