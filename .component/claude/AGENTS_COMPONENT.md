# COMPONENT Workflow Contract

## Purpose

Translate **one architectural component** into a **component-level design**. This further specifies `AGENTS.md` for this mode.

## Instruction precedence & read order
1. As specified by `AGENTS.md`
2. This file
3. `.component/COMPONENTS_DESCRIPTION.md`
4. `.component/STATE.md`
5. `.component/PLAN.md`
6. `.component/HISTORY.md`
7. `.architecture/ARCHITECTURE_DESCRIPTION.md` (read-only reference)

## Scope

This layer receives **exactly one architectural element** (identified by its top-level number: 10, 20, 30…) and breaks it down into the concrete components required to implement it.

The input architectural element must be specified in the prompt. If it is not clear which element is being targeted, you MUST ask to confirm.

The output for this step must be formatted according to 

## Abstraction level for components

Describe components by **concrete role and technology** for a **buildable unit of work**, not by abstract architectural category.

The correct level of abstraction for a component (10.1, 10.2, ...) is one where:
- A specific technology (or set of technologies) can be identified to implement it
- The component has a clear objective and coherent set of responsabilities
- It maps to a recognizable delivrable (a service, a schema, a configured runtime, a UI module, ...)
- it remains large enough to likely require work on a few different features in order to deliver (e.g. it's more than 2-3 commits)

For example, a component could: "Authentication mechanism", with chosen technlogies (e.g. Oauth 2.0 implemented with Passport.js, hashing with bcrypt and a redis session store, etc.). It would not however go into details such as specifying the inputs fields required for the user form, the color theme for the page, the error messages to display in case of denied authentication etc.


## Numbering rules

Components are numbered as sub-elements of their main parent architectural element:

- Architectural element 10 → components 10.1, 10.2, 10.3 …
- Architectural element 20 → components 20.1, 20.2, 20.3 …

There is no fixed upper bound on component count — use as many as needed.

## Input requirements

The prompt must provide or reference:
- the target architectural element number (e.g. "element 10")
- access to the current `.architecture/ARCHITECTURE_DESCRIPTION.md` (or its relevant section)

If the architecture has not been reviewed/approved (status ≠ DONE in `.architecture/STATE.md`), log a warning in `.component/STATE.md` but proceed unless explicitly told to stop.

## Component planning rule

Use `.component/PLAN.md` to track component-level questions that require discussion, investigation, or explicit decision. Keep it for blocking technology or design choices.

Use `.component/STATE.md` to track the currently active component breakdown, current focus, active blockers, and work log.

Use `.component/HISTORY.md` to archive resolved questions and completed component reviews.
