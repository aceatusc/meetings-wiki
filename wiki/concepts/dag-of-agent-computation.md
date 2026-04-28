---
type: concept
status: living
created: 2026-04-28
updated: 2026-04-28
sources:
  - "[[sumits-meeting-1-2026-03-16]]"
tags:
  - concept
  - dag
  - computation
  - agents
---

# DAG of Agent Computation

## Definition

A DAG of agent computation represents what the agent did as dependencies between steps or states, rather than as a purely linear transcript. The transcript argues that even if the model produced actions in a sequence, the meaningful structure may be parallel or dependency-based.

## Possible Semantics

The DAG could represent:

- actual computation dependencies
- saved spreadsheet states
- code snippets that transform one state into another
- specs for what each step intended to do
- user-created branches from edits
- alternate paths that remain relevant after a user decision

These meanings should not be conflated without an explicit design choice.

## Technical Ideas

- Save states for deterministic backtracking.
- Store code on edges so steps can be rerun.
- Store specs on edges so a model can regenerate code with the same intent.
- Use repair when a user edit invalidates downstream steps.
- Use refactoring to propagate shared constants or style decisions.
- Prune obsolete paths when a user decision makes them irrelevant.
- Treat some edits like merge operations between branches.

## Risks

- Downstream code may include hard-coded constants or assumptions.
- Adding a column can invalidate later column indices.
- Layout/style changes may need to propagate across charts.
- Showing unexplored or obsolete paths can confuse users.
- Full dependency repair may be out of scope for the current paper.

## Related Pages

- [[spreadsheet-agent-verification]]
- [[views-into-agent-output]]
- [[steerability]]
- [[open-questions]]

