# STATE

This file keeps track of component design sessions. Use it when technology choices need discussion, when trade-offs need human input, or when cross-element dependencies surface.

## Session read order

1. `AGENTS.md` (optional if already read this session)
2. `.component/AGENTS_COMPONENT.md`
3. `.component/STATE.md` (this file)
4. `.component/COMPONENTS_DESCRIPTION.md`
5. `.component/HISTORY.md` (optional)
6. `.architecture/ARCHITECTURE_DESCRIPTION.md` (read-only reference)

## State management rules

- Each session targets a single architectural element. Do not mix elements in one session.
- The status can be set to `DONE` only when the human reviewer has explicitly approved the result.
- Keep this file focused on current execution state. Put rollups and resolved items in `HISTORY.md`.

## Current focus

- Target element: <10 | 20 | 30 | …>
- Revision ID: Comp.<element>.0.1
- Status: NOT_STARTED  <!-- one of: NOT_STARTED | IN_PROGRESS | IN_REVIEW | DONE -->

## Objective (current breakdown)
<!-- 1 sentence. Keep aligned with the target element in `.architecture/ARCHITECTURE_DESCRIPTION.md`. -->

## Active assumptions / constraints
<!-- Keep only the assumptions or constraints that materially affect the current component breakdown. -->
- <assumption or constraint>

## Work log (current session)
<!-- Append-only bullets for what changed and why. Prefer file/section references. -->
- YYYY-MM-DD: <change made and reason>

## Workflow state
<!-- Dispatcher flags. Checked = active/needed. Cleared once handled. -->
- [ ] ARCHITECTURE_REVIEWED
- [ ] DRAFT_CREATED
- [ ] HUMAN_REVIEW_REQUIRED
- [ ] DECISIONS_CAPTURED

## Active issues
<!-- Keep only active issues here. Move resolved items to HISTORY.md. -->
- [ ] Comp.<element>.0.1: <short title>
  - Impact: QUESTION <!-- QUESTION | MINOR | MAJOR | BLOCKER -->
  - Status: NOT_STARTED <!-- one of: NOT_STARTED | IN_PROGRESS | IN_REVIEW | DONE -->
  - Unblock condition: <what must be true to proceed>
  - Notes: <optional context>
