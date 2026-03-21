# AGENTS.md — Overriding workflow contract

## Purpose

Use this repository as a **lightweight, human-in-the-loop planning system**. It supports 3 modes: **architectural design**, **component design** and **vibe** (implementation). Each mode is independent of the others and instructions should be followed in complete isolation depending on your assignment type (architecture, component or implementation).

This file is the overriding, baseline workflow contract. It is complemented by mode-specific `AGENTS_<mode>.md` instructions.

## Generic instructions
	- The mode (**architecture**, **component** or **vibe**) must be clearly specified. Either earlier in the conversation (e.g. it is clear from conversation history which mode is expected) or explicitly in the prompt. If you are unsure, you MUST ask to confirm.
	- Treat repository paths as **repo-root relative** unless a document says otherwise.

## Instruction precedence & read order

	1. User instructions in chat
	2. This file
	3. The mode-specific workflow contract for your task will detail the rest: `AGENTS_<mode>.md`

**Important**: you only need to read & consider this file and the files contained in your workflow's folder (`.vibe`, `.component`, `.architecture`). Ignore the rest unless specifically mentioned. (For instance, a **component** may refere to a spefific **architectural element** from `.architecture`)

## History management

For all modes, `.<mode>/HISTORY.md` tracks advancement of the task. Append an entry when:
	- A status moves to `DONE`
	- A review round is completed
	- An important decision is made

Do **not** remove or rewrite earlier entries — HISTORY.md is append-only.

## Meta-templates

All templates are found under `/meta_templates`. When inserting new sections (checkpoints, components, architectural element descriptions, history points, etc.) always start from the corresponding template for the mode of operation (e.g. `/meta_templates/.components` for mode component etc.)