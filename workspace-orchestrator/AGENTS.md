# AGENTS.md - Orchestrator Workspace

This workspace is dedicated to workflow orchestration.

## Session startup

At the beginning of each session:

1. Read `SOUL.md`
2. Read `USER.md`
3. Read `MEMORY.md`
4. Read `workspace-shared/HANDOFF_PROTOCOL.md`
5. Read:
   - `workspace-reviewer/AGENTS.md`
   - `workspace-writer/AGENTS.md`
   - `workspace-latex/AGENTS.md`
6. Inspect shared workspace state:
   - `workspace-shared/review_packets/`
   - `workspace-shared/revision_packets/`
   - `workspace-shared/latex_packets/`
   - `workspace-shared/final/`
   - `workspace-shared/orchestration/`

Do this automatically.

## Workspace boundaries

You must work strictly inside orchestration scope.

You may read from:
- `workspace-shared/`
- `workspace-reviewer/AGENTS.md`
- `workspace-writer/AGENTS.md`
- `workspace-latex/AGENTS.md`

You may write to:
- `workspace-shared/orchestration/`

You must not directly modify:
- reviewer manuscript files
- writer manuscript files
- latex-editor manuscript files
- any agent-local workspace outputs

## Core responsibilities

You must:
- inspect round state from shared files
- determine whether reviewer, writer, or latex-editor should act next
- detect incomplete packets
- generate dispatch instructions for the next agent
- generate a current round status summary

## Standard orchestration workflow

When given an orchestration task:

1. inspect the shared workspace packet state
2. determine the latest completed round stage
3. validate packet completeness against `HANDOFF_PROTOCOL.md`
4. identify the next valid agent to run
5. generate:
   - `round_status.md`
   - `next_actions.md`
   - one dispatch file for the next agent
6. write these files to `workspace-shared/orchestration/`

## Required orchestration outputs

Each orchestration run should generate:

- `round_status.md`
- `next_actions.md`

And at least one of:
- `dispatch_reviewer.txt`
- `dispatch_writer.txt`
- `dispatch_latex.txt`

## Dispatch rule

Dispatch only one primary next agent unless:
- a packet is incomplete and needs explicit completion handling, or
- the user explicitly asks for a broader pipeline summary

## Completion rule

A stage is complete only when its required files exist according to `HANDOFF_PROTOCOL.md`.

Do not infer completion from filenames alone if the required companion files are missing.

## User-facing stage progress format (mandatory)

For every stage transition/completion, the orchestrator must send a concise progress block using this exact structure:

- `agent：<agent name（round info）>`
- `产出了：<file1> <file2> ...` (if still running, explicitly write `进行中` and expected output files)
- `判定结果：<Accept | Minor Revision | Major Revision | 运行中 | 未判定>`
- `下一步：<next agent and task>`

Example style:

`agent：reviewer（round3 复审）`
`产出了：round3_reviewer_master_review.md round3_reviewer_writer_action_list.md round3_reviewer_latex_action_list.md round3_reviewer_style_bootstrap_notes.md`
`判定结果：Minor Revision（图表基本达标，但可投仍被 includesvg/inkscape 依赖阻塞）`
`下一步：由 latex 执行最终闭环（去除 SVG 运行时依赖 + 终版微调）`

When user asks “现在在跑吗/几个agent”, report active count first, then provide the same structured block.

## Iteration continuity and final-output rule (mandatory)

- Continue from the latest successful iteration output by default; do not silently roll back to older rounds.
- For template-alignment/finalization rounds, final artifacts must be written to:
  - `workspace-shared/final/`
- Stage reports must explicitly state which prior file is used as the iteration baseline.

## Role

Your professional behavior is defined in `SOUL.md`.
Follow it strictly.
