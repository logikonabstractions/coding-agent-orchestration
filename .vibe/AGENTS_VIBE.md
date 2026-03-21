# VIBE Workflow Contract

## Purpose

Depending on input provided to you:

### VIBE-DRAFT: Draft stages & checkpoints for a specific component

The input must provide a **component ID** from `.component/COMPONENTS_DESCRIPTIONS.md` (e.g. `10.2 — Auth Service`). Draft the `PLAN.md` for this mode. Establish relevant **stages** (groups of closely related implementation steps) and **checkpoints** (smaller steps within a given stage).

### VIBE-IMPLEMENT: Implement a specific checkpoint

The input must provide a specific **checkpoint** from `.vibe/PLAN.md` (e.g. "checkpoint 1.2"). Implement the given checkpoint.

### Instruction precedence & read order

1. As specified by `AGENTS.md`
2. This file
3. `.vibe/PLAN.md`
4. `.vibe/STATE.md`
5. `.vibe/HISTORY.md`
6. `.vibe/CONTEXT.md`
7. `.architecture/ARCHITECTURE_DESCRIPTION.md` (read-only reference, VIBE-DRAFT only)
8. `.component/COMPONENTS_DESCRIPTIONS.md` (read-only reference, VIBE-DRAFT only)


## Meta-templates

Under `../meta_templates/.vibe`

| File | Role |
|------|------|
| `state_tplt.md` | Current checkpoint, status, work log, active issues, decisions |
| `plan_tplt.md` | Ordered list of checkpoints with objectives and acceptance criteria |
| `history_tplt.md` | Completed checkpoints and decisions |
| `context_tplt.md` | Shared context: architecture notes, key decisions, gotchas, hot files |

## Scope and cadence
- A `STAGE` should include a few related implementation steps
- A `CHECKPOINT` should be a small and reviewable diff, at most a few commits.
- Limit changes to what is necessary to meet acceptance criteria.

## Metafile updates
- Whenever a checkpoint moves to DONE:
	- Update `STATE.md` to reflect the new state
- NEVER remove checkpoints from PLAN.md, unless explicitly asked to
- NEVER re-number the checkpoints (unless explicitly asked to)

## Version control policy

- Commit coherent changes: a commit should be a single set of related and consistent changes towards a given checkpoint.
- Commit message prefix: `<checkpoint-id>: <imperative summary>`
