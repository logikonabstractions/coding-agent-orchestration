# VIBE workflow contract

## Purpose

Implement specific features by completing **one checkpoint at a time**. This file further specifies `AGENTS.md` for vibe mode.

## Instruction precedence & read order

1. As specified by `AGENTS.md`
2. This file
3. `.vibe/STATE.md`
4. `.vibe/PLAN.md`
5. `.vibe/HISTORY.md`
6. `.vibe/CONTEXT.md`
7. `.component/COMPONENTS_DESCRIPTIONS.md` (input reference when checkpoints are derived from component design)
8. `.architecture/ARCHITECTURE_DESCRIPTION.md` (high-level reference only when needed)

## Scope and cadence

- Do one checkpoint at a time unless explicitly asked to do more.
- Keep diffs small and reviewable.
- Limit changes to what is necessary to meet the active checkpoint's acceptance criteria.
- Expect human review after each checkpoint.

## Handoff contract

Vibe mode is the implementation layer of this workflow.

Whenever possible, each checkpoint should be traceable to:

- one implementation component in `.component/COMPONENTS_DESCRIPTIONS.md`, and
- by extension, one parent architectural element in `.architecture/ARCHITECTURE_DESCRIPTION.md`

If the active checkpoint cannot be tied back to an upstream design artifact, record that gap in `.vibe/STATE.md` before proceeding.

## Metafile updates (`PLAN.md`, `STATE.md`, `HISTORY.md`)

- Whenever a checkpoint changes to `DONE`:
  - update `.vibe/STATE.md` to reflect the new state
  - add relevant entries to `.vibe/HISTORY.md`
- NEVER remove checkpoints from `.vibe/PLAN.md` unless explicitly asked to do so
- NEVER renumber checkpoints unless explicitly asked to do so

## Checkpoint format (`PLAN.md`)

For each checkpoint, include:

- Objective
- Deliverables
- Acceptance
- Demo commands, if any
- Evidence

## State format (`STATE.md`)

Track:

- current checkpoint and status
- work log (append-only)
- active issues
- decisions

## Stop conditions

Stop and record an issue in `.vibe/STATE.md` when:

- required information is missing
- instructions conflict
- a scope or architecture decision is needed
- external credentials or secrets are required
- tests fail for unclear reasons

## Version control policy

- Commit coherent changes: a commit should be a single related set of changes toward a given checkpoint.
- Commit message prefix: `<checkpoint-id>: <imperative summary>`
- If you create a branch for vibe work, name it `codex/{feature}`.
