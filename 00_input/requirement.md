# Smoke Test Requirement

## Goal

Run one minimal three-agent pipeline test from input to review.

## Task

Please create `30_execution/hello.txt` with the exact text:

`Hello from Agent 2`

## Constraints

- Keep the change minimal.
- Agent 2 should also write `30_execution/HANDOFF.md`.
- Agent 3 should review the result and, if it passes, remove the corresponding task folder from `20_tasks/`.

## Acceptance

- `10_architecture/project-brief.md` is created or updated by Agent 1.
- A task folder appears under `20_tasks/`.
- `30_execution/hello.txt` appears.
- `40_review/review-YYYYMMDD-HHMM.md` appears.
