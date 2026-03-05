# AGENTS.md — Minimal Markdown Workflow Contract

## Purpose

Keep collaboration simple:
- plan in markdown,
- execute small checkpoints,
- review at each step.

No Python workflow tooling is required in this repo.

## Precedence

1. User instructions in chat
2. This file
3. `.vibe/STATE.md`
4. `.vibe/PLAN.md`
5. `.vibe/HISTORY.md`

## Required read order (start of session)

1. `AGENTS.md`
2. `.vibe/STATE.md`
3. `.vibe/PLAN.md`
4. `.vibe/HISTORY.md` (optional)

## Working style

- Do one coherent checkpoint at a time.
- Keep diffs small and reviewable.
- Prefer concrete evidence over long narrative.

## Required checkpoint shape

Each checkpoint in `.vibe/PLAN.md` must include:
- Objective
- Deliverables
- Acceptance
- Demo commands
- Evidence

## Stop conditions

Stop and log an issue in `.vibe/STATE.md` if:
- required information is missing,
- instructions conflict,
- scope/architecture decision is needed,
- secrets or destructive actions are required,
- tests fail for reasons not clearly tied to your change.

## Active issue format (required)

```md
- [ ] ISSUE-123: Short title
  - Impact: QUESTION|MINOR|MAJOR|BLOCKER
  - Status: OPEN|IN_PROGRESS|BLOCKED|RESOLVED
  - Owner: agent|human
  - Unblock Condition: <what must be true to proceed>
  - Evidence Needed: <command/output/link proving resolution>
  - Notes: <optional context>
```

## Git rules

- Work on the current branch.
- Do not create/switch/delete branches unless explicitly asked.
- If you change tracked files, make a commit.
- Use commit messages prefixed with checkpoint ID, e.g. `3.1: Add API retry test`.
- Do not push or change remotes unless explicitly asked.
