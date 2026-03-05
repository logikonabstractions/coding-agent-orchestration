# STATE

## Session read order
1) `AGENTS.md`
2) `.vibe/STATE.md`
3) `.vibe/PLAN.md`
4) `.vibe/HISTORY.md` (optional)

## Current focus
- Stage: 1
- Checkpoint: 1.2
- Status: DONE  <!-- NOT_STARTED | IN_PROGRESS | IN_REVIEW | BLOCKED | DONE -->

## Objective (current checkpoint)
Provide minimal markdown guidance for a human-in-the-loop workflow.

## Deliverables (current checkpoint)
- Update `README.md`, `AGENTS.md`, and `VIBE.md` with simple instructions.
- Keep planning and execution centered on `.vibe/*.md` files.

## Acceptance (current checkpoint)
- Docs describe a low-fluff plan -> implement -> review loop.
- No dependency on Python tooling for workflow operation.

## Work log (current session)
- Replaced orchestration docs with markdown-only guidance.
- Removed all tracked Python files from repo.
- Simplified `.vibe/PLAN.md` to two practical checkpoints.

## Evidence
- `rg --files -g '*.py'` returns no files.
- Top-level docs now define manual markdown workflow.

## Active issues
- None.

## Decisions
- 2026-03-05: Keep workflow intentionally manual and human-reviewed at each checkpoint.
