# AGENTS.md — Overriding workflow contract

## Purpose

Use this repository as a **lightweight, human-in-the-loop planning system**. It supports 3 modes: **architectural design**, **component design** and **vibe** (implementation). Each mode is independent of the others and instructions should be followed in complete isolation depending on your assignment type (architecture, component or implementation).

This file is the overriding, baseline workflow contract. It is complemented by mode-specific `AGENTS_<mode>.md` instructions.

## Generic instructions
	- The mode (architecture, component or vibe) must be clearly specified. Either earlier in the conversation (e.g. it is clear from conversation history which mode is expected) or explicitly in the prompt. If you are unsure, you MUST ask to confirm.
	- Treat repository paths as **repo-root relative** unless a document says otherwise.

## Instruction precedence & read order

	1. User instructions in chat
	2. This file
	3. The mode-specific workflow contract for your task will detail the rest: `AGENTS_<mode>.md`

**Important**: you must ONLY read & consider this file and the files contained in your workflow's folder (`.vibe`, `.component`, `.architecture`). Ignore the rest unless explicitly told otherwise.

## History management

For all modes, `.<mode>/HISTORY.md` tracks advancement of the task. Append an entry when:
	- A status moves to `DONE`
	- A review round is completed
	- An important decision is made

Do **not** remove or rewrite earlier entries — HISTORY.md is append-only.

## Meta-templates

Each mode relies on a set of markdown files. Refer to the mode-specific contract for the authoritative list. The common files across all modes are:

| File | Role |
|------|------|
| `AGENTS_<mode>.md` | Workflow contract for the mode |
| `STATE.md` | Current focus, active blockers, work log |
| `PLAN.md` | Mode-specific planning tracker |
| `HISTORY.md` | Append-only log of completed work and decisions |

