---
name: round-state-inspector
description: inspect shared packet files and determine the current round state of the manuscript pipeline. use when the orchestrator needs to understand which stages are complete, which packets are missing, and what the latest valid reviewer, writer, and latex-editor outputs are.
---

# round-state-inspector

Inspect the shared workspace and determine pipeline state conservatively.

## Goal

Given:
- `workspace-shared/review_packets/`
- `workspace-shared/revision_packets/`
- `workspace-shared/latex_packets/`
- `workspace-shared/HANDOFF_PROTOCOL.md`

determine:
- the latest reviewer packet state
- the latest writer packet state
- the latest latex packet state
- which round is currently active
- whether any required files are missing

## Required checks

For reviewer packets, check:
- `roundN_reviewer_master_review.md`
- `roundN_reviewer_writer_action_list.md`
- `roundN_reviewer_latex_action_list.md`

For writer packets, check:
- `roundN_writer_revised.tex`
- `roundN_writer_change_log.md`

For latex packets, check:
- `roundN_latex_formatted.tex`
- `roundN_latex_build_status.md`
- `roundN_latex_format_report.md`

## State rules

- A packet is complete only if all required files for that stage exist.
- If a later-stage file exists but required earlier-stage files are missing, treat the workflow as inconsistent and report it.
- Prefer the highest complete stage, not merely the highest-numbered file.

## Output expectation

Produce a structured state summary that includes:
- latest complete reviewer round
- latest complete writer round
- latest complete latex round
- incomplete packets if any
- recommended next stage candidate
