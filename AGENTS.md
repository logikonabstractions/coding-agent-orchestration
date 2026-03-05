# AGENTS.md — Markdown-only workflow contract

## Purpose

Use this repository as a **lightweight, human-in-the-loop planning system**.
No Python orchestrator is required.

## Precedence

1. User instructions in chat
2. This file
3. `.vibe/STATE.md`
4. `.vibe/PLAN.md`
5. `.vibe/HISTORY.md`

## Required read order

1. `AGENTS.md`
2. `.vibe/STATE.md`
3. `.vibe/PLAN.md`
4. `.vibe/HISTORY.md` (optional)

## Scope and cadence

- Do one checkpoint at a time (or at most 2 if explicitly requested).
- Keep diffs small and reviewable.
- Human reviews after each checkpoint.
- Treat `.vibe/*.md` as source of truth.

## Checkpoint format (PLAN.md)

Each checkpoint must include:
- Objective
- Deliverables
- Acceptance
- Demo commands
- Evidence

## State format (STATE.md)

Track:
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

- Work on current branch only.
- Do not create/switch/delete branches unless user asks.
- Commit coherent changes.
- Commit message prefix: `<checkpoint-id>: <imperative summary>`

## Non-goals

- No autonomous long-running orchestration.
- No mandatory tooling runtime.
- No hidden state outside markdown and git history.
