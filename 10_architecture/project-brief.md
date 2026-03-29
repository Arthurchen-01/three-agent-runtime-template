# Project Brief

## Goal

Validate the shared three-agent pipeline with one minimal end-to-end task.

## Current Context

- The repository is already cloned on all three machines.
- Agent 1 is responsible for architecture and task creation.
- Agent 2 is expected to execute a tiny file-writing task.
- Agent 3 is expected to review the result and remove the task folder if approved.

## Technical Approach

- Keep the scope intentionally tiny.
- Do not modify bootstrap or system files for this test.
- Agent 2 should create exactly one execution artifact: `30_execution/hello.txt`.
- Agent 2 must also create or update `30_execution/HANDOFF.md`.
- Agent 3 should check the exact file content and whether the task stayed within scope.

## Risks

- Agent 2 may over-expand the task and edit unrelated files.
- Agent 3 may not remove the task folder after approval.
- Local runtime files may appear in worktrees but should not be committed.

## Task Breakdown

1. Agent 2 creates `30_execution/hello.txt` with the exact required content.
2. Agent 2 writes `30_execution/HANDOFF.md`.
3. Agent 3 reviews the result and deletes the task folder on pass.
