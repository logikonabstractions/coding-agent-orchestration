# Lightweight Markdown Workflow

This repo is now intentionally simple.

## What changed

- No Python orchestration code.
- No CLI dispatcher.
- Workflow is driven only by markdown files.

## Files you use

- `AGENTS.md`: collaboration rules for human + agent.
- `.vibe/PLAN.md`: checkpoints backlog.
- `.vibe/STATE.md`: current checkpoint + status + evidence.
- `.vibe/HISTORY.md`: short archive after each checkpoint or stage.

## Minimal loop

1. Human writes or updates checkpoints in `.vibe/PLAN.md`.
2. Human sets active checkpoint in `.vibe/STATE.md`.
3. Agent implements **one checkpoint**.
4. Agent updates `.vibe/STATE.md` with:
   - what changed
   - commands run
   - pass/fail evidence
   - open issues
5. Human reviews and either:
   - marks checkpoint `DONE`, or
   - sends back revisions.
6. Repeat.

## Parallel work (simple)

If you want parallel agents, split work into independent checkpoints in the same stage:

- `2.1` Agent A
- `2.2` Agent B

Track each handoff in `.vibe/STATE.md` under the work log and merge once both are reviewed.

## Scope

This system is optimized for short supervised sessions (1–2 features), not long autonomous runs.
