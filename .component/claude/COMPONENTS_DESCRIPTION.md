# COMPONENTS DESCRIPTION

The response must provide one or more components for a single architectural element, adhering to this format.

## Source architectural element

- Element ID:
  - <10 | 20 | 30 | …>
- Element name:
  - <name as defined in `.architecture/ARCHITECTURE_DESCRIPTION.md`>
- Element purpose (summary):
  - <1–2 sentence restatement of the architectural element's purpose>

## Assumptions

- <any assumptions specific to this component breakdown, beyond what the architecture already states>

## Components

Repeat & fill this template for each component. Follow the numbering convention.

### <10>.1 — <Component name>

- Technology:
  - <primary technology, framework, or product (e.g. "Next.js 14", "PostgreSQL 16", "Keycloak 24", "Redis 7 pub/sub")>
- Supporting libraries / tools:
  - <additional libraries, SDKs, or tools this component depends on (e.g. "Prisma ORM", "passport-jwt", "pino logger")>
  - <use "none beyond the primary technology" if nothing extra is needed>
- Purpose:
  - <what this component does within the parent architectural element>
- Responsibilities:
  - <responsibility>
- Interfaces:
  - Incoming:
    - <requests / commands / events / data this component receives, and from whom (sibling component ID or external)>
  - Outgoing:
    - <responses / commands / events / data this component produces, and to whom>
- Data / state:
  - <what data or state this component owns, reads, writes, or exposes>
- Configuration / infrastructure:
  - <runtime, container, environment variables, secrets, ports, volumes, or cloud resources required>
- Dependencies:
  - <sibling component IDs within the same architectural element>
  - <cross-element component IDs if applicable (e.g. 20.3)>
- Constraints / notes:
  - <version pinning, licensing, performance considerations, known limitations>

## Component interaction summary

- Internal data / control flow:
  - <how the components within this element interact with each other>
- Cross-element touchpoints:
  - <where these components connect to components from other architectural elements, referencing element IDs>

## Technology choices rationale

- <component ID>: <1-2 sentences explaining why this technology was chosen over alternatives>

## Open questions

- <question requiring a component-level decision>