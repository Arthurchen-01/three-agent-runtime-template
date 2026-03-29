# Deploy Commands

Repository URL:

- `https://github.com/Arthurchen-01/three-agent-runtime-template.git`

Before running the commands below, replace the placeholder values inside the copied `openclaw.json`:

- `REPLACE_WITH_YOUR_MODEL`
- `YOUR_APP_ID`
- `YOUR_APP_SECRET`

## Machine 1: Windows architect

```powershell
mkdir C:\Users\25472\.openclaw\workspace-agent1 -Force
git clone https://github.com/Arthurchen-01/three-agent-runtime-template.git C:\Users\25472\.openclaw\workspace-agent1
Copy-Item C:\Users\25472\.openclaw\workspace-agent1\bootstrap\agent1\openclaw.json C:\Users\25472\.openclaw\openclaw.json -Force
notepad C:\Users\25472\.openclaw\openclaw.json
powershell -ExecutionPolicy Bypass -File C:\Users\25472\.openclaw\workspace-agent1\bootstrap\agent1\launch.ps1
```

## Machine 2: Linux executor

```bash
mkdir -p /root/.openclaw
git clone https://github.com/Arthurchen-01/three-agent-runtime-template.git /root/.openclaw/workspace-agent2
cp /root/.openclaw/workspace-agent2/bootstrap/agent2/openclaw.json /root/.openclaw/openclaw.json
nano /root/.openclaw/openclaw.json
bash /root/.openclaw/workspace-agent2/bootstrap/agent2/launch.sh
```

## Machine 3: Linux reviewer

```bash
mkdir -p /root/.openclaw
git clone https://github.com/Arthurchen-01/three-agent-runtime-template.git /root/.openclaw/workspace-agent3
cp /root/.openclaw/workspace-agent3/bootstrap/agent3/openclaw.json /root/.openclaw/openclaw.json
nano /root/.openclaw/openclaw.json
bash /root/.openclaw/workspace-agent3/bootstrap/agent3/launch.sh
```

## Optional git identity on each machine

```bash
git config --global user.name "agent-x"
git config --global user.email "agent-x@example.com"
```

## First smoke test

On any machine with push access, create:

- `00_input/requirement.md`

Suggested content:

`Please create 30_execution/hello.txt with the text "Hello from Agent 2".`
