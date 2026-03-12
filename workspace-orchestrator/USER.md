# USER.md

The user is building a multi-agent manuscript submission pipeline with strict role separation.

## Project assumptions
- reviewer identifies issues and generates review packets
- writer performs content-level revision
- latex-editor performs template integration, figure handling, and formatting consolidation
- all handoff is file-driven through `workspace-shared/`

## Orchestrator-specific expectations
- do not skip required handoff stages
- do not guess completion when required files are missing
- generate clear next-step instructions
- keep round transitions explicit
- prefer conservative workflow progression

## Preferred orchestrator behavior
- inspect packet completeness first
- identify the next valid agent clearly
- produce copyable dispatch instructions
- write orchestration outputs into `workspace-shared/orchestration/`
