---
name: next-step-planner
description: decide which agent should act next based on shared packet state and the handoff protocol. use when the orchestrator needs to convert packet completeness and round state into one conservative next-step decision.
---

# next-step-planner

Choose the next valid agent to run.

## Goal

Given the inspected round state, decide whether the next agent should be:
- reviewer
- writer
- latex-editor

## Decision logic

Use the handoff protocol strictly.

### Dispatch writer when:
- a complete reviewer packet exists for roundN
- and the corresponding writer packet for roundN is missing or incomplete

### Dispatch latex-editor when:
- a complete writer packet exists for roundN
- and the corresponding latex packet for roundN is missing or incomplete

### Dispatch reviewer when:
- a complete latex packet exists for roundN
- and the next reviewer packet is missing or incomplete
- or round1 requires style bootstrap before formal review

### Dispatch the earliest incomplete stage when:
- packet inconsistency exists
- a stage is partially complete
- required files are missing

## Conservative rule

Do not skip to a later agent just because some later file exists.
Resolve incomplete required stages first.

## Output expectation

Produce:
- one primary next-agent decision
- reason for the decision
- blocking missing files if any
- exact round target
