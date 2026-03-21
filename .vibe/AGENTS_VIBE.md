# VIBE Workflow Contract

## Input requirements

The either a <COMPONENT ID> or <COMPONENT NAME> with the instruction sto draft a Stage & Checkpoint PLAN.d to implement this component (this is the VIBE-DRAFT). Or the ID of a specific checkpoint corresonding to a checkpoint in `.vibe/PLAN.md` (the VIBE-IMPLEMENT).

### VIBE-DRAFT: Draft stages & checkpoint to implement a specific component description 

If the input provided you with <Component ID> - <Component name>, refer to  `.components/COMPONENTS_DESCRIPTIONS.md`. Draft the PLAN.md for this mode. Establish relevant STAGES (e.g. closely related implementation steps) and checkpoints (smaller steps within a given stage). 

In that case, read these files for background & references only:
#### Instruction precedence & read order
1. As specified by `AGENTS.md`
2. This file
3. `.architecture/ARCHITECTURE_DESCRIPTION.md` (read-only, references)
4. `.component/COMPONENTS_DESCRIPTIONS.md` (read-only, references)
4. `.vibe/PLAN.md`
3. `.vibe/STATE.md`
5. `.vibe/HISTORY.md`
6. `.vibe/CONTEXT.md`

### VIBE-IMPLEMENT: Implement a specific checkpoint

If provided with a specific checkpoint (E.g "vibecode checkpoint 4.1"), then implement the given checkpoint.

Implement specific features based on the checkpoints described in `PLAN.md`. This further specifies `AGENTS.md` for this mode.

#### Instruction precedence & read order
1. As specified by `AGENTS.md`
2. This file
4. `.vibe/PLAN.md`
3. `.vibe/STATE.md`
5. `.vibe/HISTORY.md`
6. `.vibe/CONTEXT.md`


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
