# Operating Model

## What changed

This repository no longer treats each OpenClaw instance as a single narrow stage.

Instead:

- Agent 1 is a planning and dispatch department
- Agent 2 is an execution department
- Agent 3 is a quality and audit department

Each department may use subagents internally.
The repository stores the distilled results of those subagent cycles.

## Why this is better for your goal

- It keeps each machine flexible instead of brittle
- It lets Agent 1 think in strategy and sequencing
- It lets Agent 2 ship small increments repeatedly
- It lets Agent 3 review progress continuously, not only at the very end
- It reduces token waste because long context moves into files

## Recommended control loop

1. User gives a goal to Agent 1
2. Agent 1 uses subagents to decompose it
3. Agent 1 writes:
   - architecture
   - task card
   - execution checklist
   - test plan
4. Agent 2 completes only the next smallest checklist item
5. Agent 2 writes:
   - outputs
   - handoff
   - status report
6. Agent 3 audits the current batch
7. Agent 3 tells Agent 1 whether to proceed, rework, or close
8. Agent 1 issues the next micro-task

## Current practical interpretation

- Agent 1 is the command center
- Agent 2 is the maker team
- Agent 3 is the QA and audit team

This still works on the current three-machine setup.
Only the repository workflow and prompts need to evolve.
