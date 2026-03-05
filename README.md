# Vibe (Markdown-only)

This repo is now a **minimal markdown workflow** for coding sessions.

No Python tooling, no dispatch engine, no automation loops.
Just keep planning and progress in markdown so humans and agents can collaborate in short, reviewable steps.

## What to use

- `AGENTS.md` — rules of engagement for agent sessions.
- `.vibe/PLAN.md` — backlog of checkpoints.
- `.vibe/STATE.md` — current checkpoint and status.
- `.vibe/HISTORY.md` — archived summaries.
- `.vibe/CONTEXT.md` — short handoff notes.

## Lightweight operating model

1. Define checkpoints in `.vibe/PLAN.md`.
2. Pick one checkpoint in `.vibe/STATE.md`.
3. Agent implements one scoped change.
4. Human reviews.
5. Mark checkpoint `DONE` or add issues.
6. Move to the next checkpoint.

That’s it.

## Checkpoint format (keep it simple)

Each checkpoint should include:

- Objective
- Deliverables
- Acceptance
- Demo commands
- Evidence

## Status values

Use one of:

- `NOT_STARTED`
- `IN_PROGRESS`
- `IN_REVIEW`
- `BLOCKED`
- `DONE`

## Notes

- Prefer small checkpoints that can be reviewed quickly.
- If blocked, record one issue with clear unblock condition.
- Keep churn low: update only PLAN/STATE/HISTORY/CONTEXT as needed.
