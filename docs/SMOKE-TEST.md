# Smoke Test

## Goal

Verify that the three-machine loop can move one tiny task through the full pipeline.

## Step 1

Create `00_input/requirement.md` with:

`Please create 30_execution/hello.txt with the text "Hello from Agent 2".`

## Step 2

Wait for Agent 1 heartbeat.

Expected:

- `10_architecture/project-brief.md`
- `20_tasks/TASK-001/task-card.md`

## Step 3

Wait for Agent 2 heartbeat.

Expected:

- `30_execution/hello.txt`
- `30_execution/HANDOFF.md`

## Step 4

Wait for Agent 3 heartbeat.

Expected:

- `40_review/review-YYYYMMDD-HHMM.md`
- `20_tasks/TASK-001/` removed if approved
