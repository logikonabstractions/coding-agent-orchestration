# VIBE Workflow Contract

## Purpose

Implement specific features based on the checkpoints described in `PLAN.md`. This further specifies `AGENTS.md` for this mode.

## Instruction precedence & read order
1. As specified by `AGENTS.md`
2. This file
3. `.vibe/STATE.md`
4. `.vibe/PLAN.md`
5. `.vibe/HISTORY.md`
6. `.vibe/CONTEXT.md`

## Meta-templates

| File | Role |
|------|------|
| `STATE.md` | Current checkpoint, status, work log, active issues, decisions |
| `PLAN.md` | Ordered list of checkpoints with objectives and acceptance criteria |
| `HISTORY.md` | Completed checkpoints and decisions |
| `CONTEXT.md` | Shared context: architecture notes, key decisions, gotchas, hot files |

## Scope and cadence

- Do one checkpoint at a time (unless explicitly requested more).
- Keep diffs small and reviewable.
- Limit changes to what is necessary to meet acceptance criteria.
- Human reviews after each checkpoint.

## Metafile updates
- Whenever a checkpoint moves to DONE:
	- Update `STATE.md` to reflect the new state
- NEVER remove checkpoints from PLAN.md, unless explicitly asked to
- NEVER re-number the checkpoints (unless explicitly asked to)

## Checkpoint format (PLAN.md)

For each checkpoint we should have:
- Objective
- Deliverables
- Acceptance
- Demo commands (if any)
- Evidence

## State format (STATE.md)

This tracks:
- Current checkpoint and status
- Work log (append-only)
- Active issues
- Decisions

## Version control policy

- Commit coherent changes: a commit should be a single set of related and consistent changes towards a given checkpoint.
- Commit message prefix: `<checkpoint-id>: <imperative summary>`
