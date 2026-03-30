# Workflow Rules

## Core operating model

This repository uses a department-style orchestration model:

1. User input lands in `00_input/`
2. Agent 1 acts as the command center
3. Agent 1 uses internal subagents to analyze and decompose
4. Agent 1 records architecture, task cards, execution checklists, and test plans
5. Agent 2 acts as the delivery department
6. Agent 2 executes only the current smallest dispatched unit
7. Agent 2 records outputs plus a status report back to Agent 1
8. Agent 3 acts as quality and audit
9. Agent 3 reviews the current batch and tells Agent 1 what should happen next
10. Agent 1 issues the next micro-task until the milestone is done

## File flow

- User requirements: `00_input/`
- Strategy and decomposition: `10_architecture/`
- Active dispatch packets: `20_tasks/`
- Execution outputs and reports: `30_execution/`
- Audit and review outputs: `40_review/`
- Persistent knowledge: `memory/`

## Dispatch packet rule

Every active task packet under `20_tasks/` should contain:

- `task-card.md`
- `execution-checklist.md`
- `test-plan.md`

This keeps the next action explicit without forcing long chat context.

## Execution loop

1. Agent 1 writes a task packet
2. Agent 2 completes the first smallest unchecked item
3. Agent 2 updates `30_execution/STATUS-REPORT.md`
4. Agent 3 reviews the batch or step
5. Agent 1 decides the next smallest dispatch

## Coordination rules

- The repository is the only source of truth.
- Do not coordinate by hidden chat state.
- Prefer micro-tasks over large tasks.
- Prefer iterative dispatch over one massive specification.
- Architecture persists across iterations.
- Review should inform the next dispatch, not just produce pass/fail.

## Memory rules

Each agent keeps three layers:

- short-term: immediate notes, current day, current step
- mid-term: current task, milestone, rolling summary
- long-term: stable lessons, project structure, recurring rules

If a fact will matter again, move it upward from short-term to mid-term or long-term instead of repeating it in chat.

## Git rules

- Pull before work.
- Commit only after meaningful changes.
- Push after each completed cycle.
