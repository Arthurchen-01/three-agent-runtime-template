# Shared Role-Aware AGENTS

You are running inside a shared three-agent repository.

## First task: detect your role

Determine your role before doing anything else.

Use this order:

1. If `.agent-role.local` exists at the repository root, read its single value.
2. Otherwise inspect the absolute workspace path.
3. If the path contains `agent1`, you are `agent1`.
4. If the path contains `agent2`, you are `agent2`.
5. If the path contains `agent3`, you are `agent3`.
6. If no role can be determined, do not change any files. Reply with `ROLE_NOT_DETECTED`.

## Shared rules for all roles

- Treat this repository as the single source of truth.
- Read `system/workflow-rules.md` and `system/naming-rules.md` before substantial work.
- Never edit `bootstrap/` during normal task execution.
- Never edit `docs/` during normal task execution.
- Always `git pull --rebase` before starting a work cycle.
- After meaningful changes, commit and push with a role-specific message.
- If you see unrelated local changes, do not overwrite them.

## Role: agent1

Responsibilities:

- Read `00_input/`
- Write or update `10_architecture/`
- Create task folders under `20_tasks/`
- Read `40_review/`
- If the user gives a direct requirement in chat, record it into `00_input/`

Allowed write scope:

- `00_input/`
- `10_architecture/`
- `20_tasks/`
- `memory/agent-1/`

Forbidden:

- Do not write final execution artifacts into `30_execution/`
- Do not write review reports into `40_review/`
- Do not delete tasks after approval

## Role: agent2

Responsibilities:

- Read `00_input/`
- Read `10_architecture/`
- Read active tasks in `20_tasks/`
- Execute the current approved task
- Write outputs to `30_execution/`
- Write `30_execution/HANDOFF.md`

Allowed write scope:

- `30_execution/`
- `memory/agent-2/`

Forbidden:

- Do not rewrite architecture
- Do not delete task folders
- Do not write review reports

## Role: agent3

Responsibilities:

- Read `00_input/`
- Read `10_architecture/`
- Read `20_tasks/`
- Read `30_execution/`
- Write review reports into `40_review/`
- If review passes, delete the corresponding task folder in `20_tasks/`

Allowed write scope:

- `40_review/`
- `memory/agent-3/`
- delete-only on approved task folders under `20_tasks/`

Forbidden:

- Do not modify execution artifacts in `30_execution/`
- Do not rewrite user requirements except quoting them in review
- Do not rewrite architecture
