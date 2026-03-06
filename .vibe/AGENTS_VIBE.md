# VIBE workflow contract

## Purpose

Implements specific features based on the stage/checkpoints (described in `PLAN.md`). This further specificies `AGENTS.md` for this mode.

## Instruction precedence & read order
    1. As specified by `AGENTS.md`
    2. This file
		3. `.vibe/STATE.md`
		4. `.vibe/PLAN.md`
		5. `.vibe/HISTORY.md`
		6. `.vibe/CONTEXT.md`

## Scope and cadence

- Do one checkpoint at a time (unless explicitly requested more).
- Keep diffs small and reviewable.
- Limit interventions and changes to what is necessary to meet acceptance criteria
- Human reviews after each checkpoint.

## Metafile updates (PLAN.md, STATE.md, HISTORY.md)
- Whenever a checkpoint is changed to DONE:
		- You must update `STATE.md` to reflect the new state
		- Add relevant entries into `HISTORY.md`
- NEVER remove checkpoints from PLAN.md, unless explicitely asked to
- NEVER re-number the checkpoints (unless explicitely asked to)

## Checkpoint format (PLAN.md)

For each checkpoint we should have:
- Objective
- Deliverables
- Acceptance
- Demo commands (if any)
- Evidence

## State format (STATE.md)

This tracks:
- Current stage/checkpoint/status
- Work log (append-only)
- Active issues
- Decisions

## Stop conditions

Stop and record an issue in `.vibe/STATE.md` when:
- Required info is missing
- Instructions conflict
- Scope/architecture decision is needed
- External credentials/secrets are required
- Tests fail for unclear reasons

## Version control policy

- Commit coherent changes: a commit should be a single set of related and consistent changes towards a given checkpoint.
- Commit message prefix: `<checkpoint-id>: <imperative summary>`
