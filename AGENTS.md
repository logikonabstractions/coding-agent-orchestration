# AGENTS.md — Lightweight Execution Contract

## Purpose

Use markdown files for planning and tracking. Keep execution small and supervised.

## Source of truth (priority)

1. User instructions in chat
2. `AGENTS.md`
3. `.vibe/STATE.md`
4. `.vibe/PLAN.md`
5. `.vibe/HISTORY.md`

## Session start read order

1. `AGENTS.md`
2. `.vibe/STATE.md`
3. `.vibe/PLAN.md`
4. `.vibe/HISTORY.md` (optional)

## Working style

- Do one checkpoint at a time.
- Keep diffs small and reviewable.
- Prefer direct markdown updates over extra process.
- Ask for input only when blocked by missing or conflicting requirements.

## Checkpoint minimum

Each checkpoint in `.vibe/PLAN.md` should have:
- Objective
- Deliverables
- Acceptance
- Demo commands
- Evidence

## Stop conditions

Stop and record an issue in `.vibe/STATE.md` if:
- acceptance cannot be evaluated,
- instructions conflict,
- scope would materially change,
- secrets/external side effects are required,
- tests fail for unclear reasons.

## Version control rules

- Work on current branch only.
- Do not switch/create/delete branches unless user asks.
- If you changed tracked files, commit them.
- Commit message format: `<checkpoint-id>: <imperative summary>`.
- Do not push or change remotes unless user asks.

## Issue format (in `.vibe/STATE.md`)

```md
- [ ] ISSUE-123: Short title
  - Impact: QUESTION|MINOR|MAJOR|BLOCKER
  - Status: OPEN|IN_PROGRESS|BLOCKED|RESOLVED
  - Owner: agent|human
  - Unblock Condition: <concrete condition>
  - Evidence Needed: <proof command/output>
  - Notes: <optional>
```
