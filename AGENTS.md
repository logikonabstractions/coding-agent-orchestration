# AGENTS.md — Minimal Markdown Workflow

## Scope

This repo uses a markdown-first workflow with manual human checkpoints.

## Source of truth (priority)

1. User instructions in chat
2. `AGENTS.md`
3. `.vibe/STATE.md`
4. `.vibe/PLAN.md`
5. `.vibe/HISTORY.md`

## Required startup read order

1. `AGENTS.md`
2. `.vibe/STATE.md`
3. `.vibe/PLAN.md`
4. `.vibe/HISTORY.md` (optional)

## How to work

- Implement one coherent checkpoint at a time.
- Keep diffs small and reviewable.
- Update `.vibe/STATE.md` after each implementation pass.
- Use `.vibe/HISTORY.md` only for completed summaries.
- Prefer plain markdown updates over extra tooling.

## Checkpoint template (required)

Each checkpoint in `.vibe/PLAN.md` must include:

- Objective
- Deliverables
- Acceptance
- Demo commands
- Evidence

## Status values

Use only:

- `NOT_STARTED`
- `IN_PROGRESS`
- `IN_REVIEW`
- `BLOCKED`
- `DONE`

## Issues (lightweight)

Track only active issues in `.vibe/STATE.md` with this schema:

- [ ] ISSUE-123: Short title
  - Impact: QUESTION|MINOR|MAJOR|BLOCKER
  - Status: OPEN|IN_PROGRESS|BLOCKED|RESOLVED
  - Owner: agent|human
  - Unblock Condition: <concrete condition>
  - Evidence Needed: <what proves resolution>
  - Notes: <optional>

## Parallel work

Parallel work is allowed when checkpoints are independent.
Record owner + scope explicitly in `.vibe/STATE.md` before starting.

## Version control

- Work on the current branch only.
- Do not create/switch/delete branches unless user asks.
- If you change tracked files, commit them.
- Commit message format: `<checkpoint-id>: <imperative summary>`.

## Stop conditions

Stop and ask for input (via issue in `.vibe/STATE.md`) if:

- required information is missing,
- instructions conflict,
- scope/architecture decisions become unclear,
- external secrets/credentials/destructive actions are required,
- tests fail for unclear reasons.
