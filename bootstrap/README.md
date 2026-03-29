# Bootstrap Area

This directory is for setup only.

The agents should treat it as read-only during normal work.

## Per-machine files

- `agent1/openclaw.json`
- `agent2/openclaw.json`
- `agent3/openclaw.json`

Copy the correct file to each machine's OpenClaw config location and fill in:

- model id
- Feishu app id
- Feishu app secret

## Launch helpers

- Windows architect: `agent1/launch.ps1`
- Linux executor: `agent2/launch.sh`
- Linux reviewer: `agent3/launch.sh`
