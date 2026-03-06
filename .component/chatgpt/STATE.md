# STATE

This file keeps track of the active component-design session for one parent architectural component.

## Session read order

1. `AGENTS.md` (optional if already read this session)
2. `.component/AGENTS_COMPONENT.md`
3. `.component/STATE.md` (this file)
4. `.component/COMPONENTS_DESCRIPTION.md`
5. `.component/HISTORY.md` (optional)

## State management rules

- The parent architectural component should remain stable during a draft unless a human changes it.
- The status can be set to `DONE` only when the human reviewer has explicitly approved the result.
- Keep this file focused on current execution state. Put rollups and resolved items in `HISTORY.md`.

## Current focus

- Revision ID: Comp.0.1
- Status: NOT_STARTED  <!-- one of: NOT_STARTED | IN_PROGRESS | IN_REVIEW | DONE -->

## Parent architectural component

- Parent ID: <10 | 20 | 30 | ...>
- Parent name: <name from architecture layer>

## Objective (current draft)
<!-- 1 sentence. Keep aligned with `.component/COMPONENTS_DESCRIPTION.md`. -->

## Active assumptions / constraints
<!-- Keep only the assumptions or constraints that materially affect the current component draft. -->
- <assumption or constraint>

## Selected technology summary
<!-- Keep only the major choices that shape the current draft. -->
- <component id>: <technology choice>

## Work log (current session)
<!-- Append-only bullets for what changed and why. Prefer file/section references. -->
- YYYY-MM-DD: <change made and reason>

## Workflow state
<!-- Dispatcher flags. Checked = active/needed. Cleared once handled. -->
- [ ] PARENT_CONFIRMED
- [ ] DRAFT_CREATED
- [ ] HUMAN_REVIEW_REQUIRED
- [ ] DECISIONS_CAPTURED

## Active issues
<!-- Keep only active issues here. Move resolved items to HISTORY.md. -->
- [ ] Comp.0.1: <short title>
  - Impact: QUESTION <!-- QUESTION | MINOR | MAJOR | BLOCKER -->
  - Status: NOT_STARTED <!-- one of: NOT_STARTED | IN_PROGRESS | IN_REVIEW | DONE -->
  - Unblock condition: <what must be true to proceed>
  - Notes: <optional context>
