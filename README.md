# Vibe Orchestration (Markdown-Only)

This repo is now intentionally minimal.

No Python control plane, no dispatcher, no automation requirements.
Just markdown files that a human and one or more agents update together.

## Core idea

Use only these files:

- `AGENTS.md` — collaboration rules
- `.vibe/PLAN.md` — checkpoints to execute
- `.vibe/STATE.md` — current checkpoint + status + active issues
- `.vibe/HISTORY.md` — completed summaries
- `.vibe/CONTEXT.md` — short handoff notes

## Lightweight workflow

1. Human defines or updates checkpoints in `.vibe/PLAN.md`.
2. Human sets active checkpoint/status in `.vibe/STATE.md`.
3. Agent implements **one checkpoint** (or two small ones if explicitly requested).
4. Agent updates `.vibe/STATE.md` with evidence and sets `IN_REVIEW`.
5. Human reviews and either:
   - marks `DONE` and advances to next checkpoint, or
   - sends back changes and status returns to `IN_PROGRESS`.
6. Add a short summary to `.vibe/HISTORY.md` when a stage is complete.

## Parallel work (simple mode)

If you want parallel work, assign explicit checkpoint IDs and owners in `.vibe/STATE.md`.
Keep each agent scoped to separate files/checkpoints, then merge after human review.

## Repo contents

- `templates/` provides markdown templates for AGENTS + `.vibe/*` files.
- `docs/` contains supporting guidance; prefer short docs over process-heavy machinery.

That’s it.
