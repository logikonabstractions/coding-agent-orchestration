# ARCHITECTURE Workflow Contract

## Purpose

Translate a product or problem statement into an **architectural design**. This further specificies `AGENTS.md` for this mode.

## Instruction precedence & read order
1. As specified by `AGENTS.md`
2. This file
3. `.architecture/ARCHITECTURE_OUTPUT_FORMAT.md`

## Scope

This layer must define the major architectural parts of the target system, the responsibility of each, how they interact, and the main system-wide concerns.

It must not define implementation strategies or concrete technology choices (for example: specific frameworks, databases, cloud products, or vendors).

## Core output

The deliverable is a markdown document that gives a **structured architectural breakdown** of the proposed solution.

The output must:

- describe the target system in plain language
- identify the major architectural components required
- describe each component at the **functional type** level
- define responsibilities for each component
- capture the important interfaces and interactions between components
- capture relevant system-wide concerns, assumptions, constraints, and open questions
- conform to `.architecture/ARCHITECTURE_OUTPUT_FORMAT.md`

## Abstraction rule

Describe components by **role**, not by implementation choice.

Use terms such as:

- web client
- mobile client
- API layer
- application service
- authentication provider
- relational database
- object storage
- message queue
- background job processor
- notification service

Do **not** use concrete product names.

## Component rule

Architectural components must represent **meaningful system capabilities**.
They must be large enough to matter at system-design level and small enough to have a clear responsibility.

Prefer examples such as:

- client application
- identity and access control
- catalog management
- order processing
- payment processing
- search and discovery
- notification delivery
- observability and operations

Do not model low-level implementation artifacts as architectural components.

## Numbering rules

Use top-level component numbering in increments of 10:

- 10
- 20
- 30
- 40
