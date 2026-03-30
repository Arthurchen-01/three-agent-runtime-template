# Test Plan

## Task Id

TASK-001

## What To Verify

- `30_execution/hello.txt` exists
- its content is exactly `Hello from Agent 2`
- `30_execution/HANDOFF.md` exists
- no unrelated file outside `30_execution/` was modified by Agent 2 for this step

## Manual Checks

- [x] Open `30_execution/hello.txt`
- [x] Open `30_execution/HANDOFF.md`
- [ ] Confirm `30_execution/STATUS-REPORT.md` is present
- [ ] Confirm Agent 3 writes a review report in `40_review/`

## Optional Command Checks

- command: `cat 30_execution/hello.txt`
- expected result: `Hello from Agent 2`

## Review Focus

Agent 3 should focus on scope discipline and whether Agent 2 stayed within the smallest requested batch.
