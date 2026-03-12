---
name: dispatch-packet
description: generate orchestration outputs including round status, next actions, and copyable dispatch instructions for the next agent. use when the orchestrator has already determined current round state and needs to write actionable coordination files into the shared workspace.
---

# dispatch-packet

Generate orchestration files for the next pipeline action.

## Required outputs

Write to `workspace-shared/orchestration/`:

- `round_status.md`
- `next_actions.md`

And one of:
- `dispatch_reviewer.txt`
- `dispatch_writer.txt`
- `dispatch_latex.txt`

## round_status.md should include
- current highest complete reviewer round
- current highest complete writer round
- current highest complete latex round
- incomplete packet notes
- current recommended next agent
- current target round

## next_actions.md should include
- primary next action
- why this action is next
- required input files
- required output files
- blocking conditions if any

## Dispatch file rule

The dispatch file should be directly copyable into the next agent conversation.

It should:
- name the target round
- specify required input files
- state the exact outputs expected
- remind the agent to follow its local AGENTS.md rules
- remain concise and operational
