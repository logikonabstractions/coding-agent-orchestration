# AGENTS.md — Minimal Markdown Workflow

## Priority
1. User instructions
2. This file
3. `.vibe/STATE.md`
4. `.vibe/PLAN.md`
5. `.vibe/HISTORY.md`

## Read order
1. `AGENTS.md`
2. `.vibe/STATE.md`
3. `.vibe/PLAN.md`
4. `.vibe/HISTORY.md` (optional)

## Operating rules
- One checkpoint at a time.
- Keep diffs small.
- Update `.vibe/STATE.md` every pass.
- Use markdown files as the control plane (no extra orchestration required).

## Checkpoint shape
Every checkpoint in `.vibe/PLAN.md` includes:
- Objective
- Deliverables
- Acceptance
- Demo commands
- Evidence

## Status values
`NOT_STARTED | IN_PROGRESS | IN_REVIEW | BLOCKED | DONE`

## Parallel mode
Allowed for independent checkpoints; record owner/scope in `.vibe/STATE.md`.

## Git rules
- Stay on current branch unless user says otherwise.
- Commit all tracked changes you make.
- Commit message: `<checkpoint-id>: <imperative summary>`.
