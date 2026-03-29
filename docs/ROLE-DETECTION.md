# Role Detection

This repository uses one shared `AGENTS.md` and one shared `HEARTBEAT.md`.

That is different from the stricter "one workspace, one hardcoded role file" pattern.
It is intentionally chosen here so that one repository can be cloned and used immediately on three machines.

## Detection order

1. local override file `.agent-role.local`
2. workspace path contains `agent1`
3. workspace path contains `agent2`
4. workspace path contains `agent3`

## Recommended clone paths

- `.../workspace-agent1`
- `.../workspace-agent2`
- `.../workspace-agent3`

## Local override

You may create a non-committed file named `.agent-role.local` with one line:

- `agent1`
- `agent2`
- `agent3`

This file is ignored by `.gitignore`.
