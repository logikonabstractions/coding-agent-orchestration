# AGENTS.md — Markdown-only workflow contract

## Purpose

This repo uses a simple markdown workflow for coding-agent collaboration.

## Precedence

1. User instructions
2. This file
3. `.vibe/STATE.md`
4. `.vibe/PLAN.md`
5. `.vibe/HISTORY.md`

## Start-of-session read order

1. `AGENTS.md`
2. `.vibe/STATE.md`
3. `.vibe/PLAN.md`
4. `.vibe/HISTORY.md` (optional)

## Rules

- Execute one checkpoint at a time.
- Keep changes small.
- Update `.vibe/STATE.md` with work log and evidence.
- Stop and log an issue if blocked or missing required information.

## Commit policy

- Use current branch.
- Commit coherent work.
- Format: `<checkpoint-id>: <imperative message>`.
