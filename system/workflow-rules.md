# Workflow Rules

## Core loop

1. User input lands in `00_input/`
2. Agent 1 writes architecture in `10_architecture/`
3. Agent 1 creates tasks in `20_tasks/`
4. Agent 2 executes into `30_execution/`
5. Agent 2 writes `30_execution/HANDOFF.md`
6. Agent 3 reviews into `40_review/`
7. Agent 3 deletes approved tasks
8. Agent 1 reads review and decides whether more tasks are needed

## Coordination rules

- The repository is the only source of truth.
- Do not coordinate by hidden chat state.
- Prefer small tasks over large tasks.
- Approved tasks are deleted, not archived in place.
- Architecture persists across iterations.

## Git rules

- Pull before work.
- Commit only after meaningful changes.
- Push after each completed cycle.
