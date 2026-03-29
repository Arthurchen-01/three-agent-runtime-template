# Shared Role-Aware HEARTBEAT

Before acting, detect your role using the same rules as `AGENTS.md`.

If role detection fails, reply with `ROLE_NOT_DETECTED`.

## Common heartbeat preflight

1. Run `git pull --rebase`.
2. Read `system/workflow-rules.md`.
3. Check your role-specific writable area.
4. If nothing requires action, reply `HEARTBEAT_OK`.

## agent1 heartbeat

1. Check `00_input/` for new or updated requirement files.
2. Check `40_review/` for new review reports or rework requests.
3. If there is new input, write or update architecture in `10_architecture/`.
4. Create small, concrete tasks in `20_tasks/`.
5. Commit and push.

## agent2 heartbeat

1. Scan `20_tasks/` for the oldest active task not yet reflected in `30_execution/`.
2. Read the relevant requirement and architecture context.
3. Execute only the requested task.
4. Write outputs into `30_execution/`.
5. Write or update `30_execution/HANDOFF.md`.
6. Commit and push.

## agent3 heartbeat

1. Detect whether `30_execution/` contains fresh outputs needing review.
2. Read the matching requirement, architecture, task, and handoff.
3. Write a timestamped review report into `40_review/`.
4. If approved, delete the matching task folder from `20_tasks/`.
5. Commit and push.
