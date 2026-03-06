# AGENTS.md — Overriding workflow contract

## Purpose

Use this repository as a **lightweight, human-in-the-loop planning system**. It supports 3 modes: **architectural design**, **component designs** and **vibe** (implementation). Each layer is independant of the others and instructions should be followed in complete isolation depenging your assigment type (architecture, component or implementation).

This file is the overriding, baseline worflow contract. It is complemented by mode-specific `AGENT_<mode>.md` instructions.

## Generic instructions
	- The mode (architecture, component or vibe) must be clearly specified. Either earlier in the conversation (e.g. it is clear from conversation history which mode is expected) or explicitely in the prompt. If you are unsure, you MUST ask to confirm.

## Instruction precedence & read order

	1. User instructions in chat
	2. This file
	3. The mode-specific workflow contract for your task: `AGENTS_<mode>.md`


## Stop conditions

Record an issue in `.vibe/STATE.md` and pause when:

- required information is missing,
- instructions conflict,
- a scope/architecture decision is needed,
- external credentials/secrets are required,
- you encounter an error that you cannot **confidently** explain

In any such cases, stop work, provide information and ask for clarifications.