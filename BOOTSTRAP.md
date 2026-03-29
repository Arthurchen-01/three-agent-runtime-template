# Bootstrap

This file is for humans, not for the agents' day-to-day loop.

## Clone targets

- Windows architect machine: clone into `C:/Users/<you>/.openclaw/workspace-agent1`
- Linux executor machine: clone into `/root/.openclaw/workspace-agent2`
- Linux reviewer machine: clone into `/root/.openclaw/workspace-agent3`

## Why one repo is enough

The repository root is the shared work area.
All three machines sync through Git.
The only support-only area is `bootstrap/`.

## What still depends on the environment

- OpenClaw must be installed
- model credentials must exist on each machine
- Feishu credentials must be filled into each machine's OpenClaw config
- Git push credentials must be configured

## Minimal first test

Create `00_input/requirement.md` with:

`Please create 30_execution/hello.txt with the text "Hello from Agent 2".`

Then let the three heartbeats run in order.
