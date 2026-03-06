# COMPONENT Workflow Contract

## Purpose

Translate **one architectural component** into a **component-level design**.

This further specifies `AGENTS.md` for this mode.

## Instruction precedence & read order

1. As specified by `AGENTS.md`
2. This file
3. `.component/COMPONENTS_DESCRIPTION.md`
4. `.component/STATE.md`
5. `.component/PLAN.md`
6. `.component/HISTORY.md`

## Scope

This layer starts from **exactly one parent architectural component** from the architecture layer (for example `10`, `20`, `30`, ...), explicitly identified in the prompt.

This layer must:

- decompose that parent architectural component into the concrete internal components required to implement it
- define each internal component with enough specificity that implementation planning can begin
- make explicit technology choices for each components (libs, language, services, framework...)
- describe the important interfaces, dependencies, responsibilities, and ownership boundaries between those internal components
- capture key design assumptions, tradeoffs, and open questions

This layer must **not**:

- redesign the architecture
- decompose multiple parent architectural components unless explicitly requested
- break work down into feature-level tasks, checkpoints, stories, files, or code changes
- drift into endpoint-by-endpoint design, schema field design, list of db tables, etc.

## Parent anchoring rule

The target parent architectural component must be explicit.

Every component-layer output must start by naming:

- the parent architectural component ID
- the parent architectural component name

If the prompt does not clearly identify the parent architectural component, stop and ask.

## Core output

The deliverable is a markdown document that gives a **structured component design** for one parent architectural component.

The output must:

- identify all major internal components required to implement that parent
- assign each internal component a stable identifier linked to its parent (`10.1`, `10.2`, `20.1`, ...)
- describe the responsibility and boundaries of each internal component
- name concrete technology choices where appropriate (framework, runtime, database, queue, library, external service, etc.)
- explain the main interactions between the internal components
- conform to `.component/COMPONENTS_DESCRIPTION.md`

## Abstraction rule

Describe components at the **implementation-structure** level.

Use concrete choices when they matter, for example:

- frontend framework
- API framework
- worker runtime
- relational or document database choice
- object storage choice
- queue / event transport choice
- auth / session library
- major conversion engine or processing library

Do **not** drift into feature-layer detail such as:

- file paths
- function names
- internal class names
- endpoint-by-endpoint request bodies
- schema fields and migrations
- detailed ticket/checkpoint breakdown

## Component rule

Component-layer components must represent **real implementation building blocks**.
They should be small enough to be owned and built, but large enough to matter as design units.

Good examples include:

- browser frontend application
- API service
- auth/session adapter
- job orchestration service
- worker service
- capability registry
- relational metadata store
- artifact object store
- queue or event bus
- notification service
- observability pipeline

Do not create tiny pseudo-components that are only helper functions, DTOs, folders, or minor wrappers.

## Technology choice rule

Technology choices are required when they materially affect implementation.

For each internal component, specify:

- the selected technology or product
- why that choice fits the parent architectural component
- major constraints or consequences of that choice when relevant

Prefer one primary choice per component.
Only include an alternative when there is a close second option worth preserving.

## Boundary rule

A component-layer design may reference dependencies outside the parent scope, but must not fully decompose them unless explicitly requested.

For example, when designing component `20`, it is acceptable to reference dependencies on architectural components `50` or `60`, but the detailed subcomponents should remain focused on `20.x` only.

## Numbering rules

Use the parent architectural component ID as the prefix.

Examples:

- `10.1`, `10.2`, `10.3`
- `20.1`, `20.2`, `20.3`
- `30.1`, `30.2`, `30.3`

Rules:

- all internal component IDs for a draft must share the same parent prefix
- use increments of `0.1` (`10.1`, `10.2`, `10.3`, ...)
- do not renumber existing identifiers unless explicitly asked
- preserve gaps if needed to insert later components

## Component planning rule

Use `.component/PLAN.md` to track component-design questions that require clarification, investigation, or explicit decision.
Use `.component/STATE.md` to track the active parent architectural component, current design focus, blockers, and work log.
Use `.component/HISTORY.md` to archive resolved design questions, review rounds, and durable component-level decisions.

## Quality bar

A good component-layer output is:

- clearly anchored to one architectural parent
- specific enough that feature-level planning can follow
- concrete enough that meaningful tech choices are visible
- modular enough that ownership boundaries are understandable
- disciplined enough that it does not collapse into low-level implementation tasks
