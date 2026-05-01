---
type: concept
status: living
created: 2026-04-28
updated: 2026-05-01
sources:
  - "[[sumits-meeting-1-2026-03-16]]"
tags:
  - concept
  - views
  - agents
---

# Views Into Agent Output

## Definition

A view is a structured representation of what an agent did or produced, tailored to what a user needs to understand, verify, or steer. The analogy in the meeting was close to a database view: the underlying artifact stays the same, but users see a purposeful slice or transformation of it.

## Examples

- Step-by-step reveal or change touring.
- DAG of computation dependencies.
- Formula-only or correctness-focused view.
- Q&A view.
- Functional-only, aesthetic-only, or combined view.
- Rubric view focused on must-haves and nice-to-haves.
- Unknown-unknown view focused on missing assumptions and hidden risks.

## Why It Matters

The larger contribution of the spreadsheet-agent project may be views into agent output, with step-by-step reveal as only one implementation. Views reduce cognitive load and make agent work actionable.

## Imported Bridge Connections

- [[agent-workflows|Agent workflows]] adds a workflow-level reason for views: users need review surfaces before they can intervene.
- [[human-oversight|Human oversight]] connects views to the moment when an agent should expose uncertainty or request input.
- [[second-brain-and-organizational-memory|Second brain and organizational memory]] connects views to persistent knowledge artifacts rather than one-off explanations.

## Related Pages

- [[spreadsheet-agent-verification]]
- [[steerability]]
- [[dag-of-agent-computation]]
- [[verification-rubrics]]
- [[agent-workflows]]
- [[human-oversight]]
- [[second-brain-and-organizational-memory]]
