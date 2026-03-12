# MEMORY.md

## Stable conventions
- the pipeline is file-driven
- shared workspace state is the source of truth
- required packet files must exist before the next stage proceeds
- orchestrator does not perform reviewer, writer, or latex-editor work

## Project-specific preferences
- prefer single next-agent dispatch
- preserve round clarity
- avoid skipping incomplete packets
