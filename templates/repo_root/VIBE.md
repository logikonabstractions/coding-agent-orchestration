# VIBE

This project uses a markdown-only workflow.

## Read order
1. `AGENTS.md`
2. `.vibe/STATE.md`
3. `.vibe/PLAN.md`
4. `.vibe/HISTORY.md` (optional)

## Working files
- `.vibe/PLAN.md` — backlog of checkpoints
- `.vibe/STATE.md` — current checkpoint/status/evidence/issues
- `.vibe/HISTORY.md` — completed summaries
- `.vibe/CONTEXT.md` — short handoff notes

## Manual loop
1. Pick the active checkpoint from `.vibe/PLAN.md`.
2. Implement the deliverables.
3. Run demo commands listed in the checkpoint.
4. Record evidence in `.vibe/STATE.md` and set `IN_REVIEW`.
5. Human reviews and marks `DONE` or sends back to `IN_PROGRESS`.

## Parallel option
Run multiple agents only on independent checkpoints. Record owner + scope in `.vibe/STATE.md`.
