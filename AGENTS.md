# AGENTS.md — Overriding workflow contract

## Purpose

Use this repository as a **lightweight, human-in-the-loop planning system**. It supports 3 modes: **architecture**, **component** and **vibe**. Each mode is independent of the others and instructions should be followed in complete isolation depending on your assignment type.

This file is the overriding, baseline workflow contract. Each mode-specific `AGENTS_<mode>.md` file extends this contract with mode-specific rules.

The three modes form a refinement chain: an **architectural element** (from architecture mode) feeds into **component** mode, and a **component** feeds into **vibe** mode. Example numbering: Element 10 → Component 10.2 → Stage 10.2.1 → Checkpoint 10.2.1.1.

## Generic instructions
	- The mode (**architecture**, **component** or **vibe**) must be clearly specified. Either earlier in the conversation (e.g. it is clear from conversation history which mode is expected) or explicitly in the prompt. If you are unsure, you MUST ask to confirm.
	- Treat repository paths as **repo-root relative** unless a document says otherwise.

## Instruction precedence & read order

	1. User instructions in chat
	2. This file
	3. The mode-specific workflow contract for your task will detail the rest: `AGENTS_<mode>.md`

**Important**: you only need to read & consider this file and the files contained in your workflow's folder (`.vibe`, `.component`, `.architecture`). Ignore the rest unless specifically mentioned. (For instance, a **component** may refer to a specific **architectural element** from `.architecture`)

## History management

For all modes, `.<mode>/HISTORY.md` tracks advancement of the task. Append an entry when:
	- A status moves to `DONE`
	- A review round is completed
	- An important decision is made

Do **not** remove or rewrite earlier entries — HISTORY.md is append-only.

## State management

For all modes, `.<mode>/STATE.md` tracks current focus, active blockers, and work in progress. Update it whenever focus shifts or a blocker is added/resolved.

## Meta-templates

All templates are found under `/meta_templates`. When inserting new sections (checkpoints, components, architectural element descriptions, history points, etc.) always start from the corresponding template for the mode of operation (e.g. `/meta_templates/.component` for component mode). Each mode file lists its specific templates.