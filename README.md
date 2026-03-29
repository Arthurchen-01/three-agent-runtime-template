# Three-Agent Runtime Template

This repository is designed to be both:

1. the shared working repository that all three machines clone; and
2. the template/bootstrap source for OpenClaw role configs.

The working area is the repository root:

- `00_input/`
- `10_architecture/`
- `20_tasks/`
- `30_execution/`
- `40_review/`
- `memory/`
- `system/`

The support area is read-only during normal task flow:

- `bootstrap/`
- `docs/`

## Role detection

The root `AGENTS.md` and `HEARTBEAT.md` are role-aware.

Each machine should clone this repository into one of these paths:

- `C:/Users/<you>/.openclaw/workspace-agent1`
- `/root/.openclaw/workspace-agent2`
- `/root/.openclaw/workspace-agent3`

Role detection order:

1. read `.agent-role.local` if present;
2. otherwise infer from the workspace path containing `agent1`, `agent2`, or `agent3`;
3. otherwise stop and report `ROLE_NOT_DETECTED`.

## Immediate run goal

If OpenClaw is installed, a model is configured, Feishu is connected, and the machine clones this repository into the expected role path, the workspace should be theoretically runnable without extra repository edits.

## Important note

This repository is the shared work area.

You do not need a second "non-work" repository for the main loop.
The only non-work area here is `bootstrap/`, which stores setup templates and launch helpers.
