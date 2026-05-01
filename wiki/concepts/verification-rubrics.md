---
type: concept
status: living
created: 2026-04-28
updated: 2026-05-01
sources:
  - "[[sumits-meeting-0-2026-02-20]]"
  - "[[sumits-meeting-1-2026-03-16]]"
tags:
  - concept
  - verification
  - rubrics
---

# Verification Rubrics

## Definition

A verification rubric is a user- or expert-provided set of checks that define what it means for an agent output to be acceptable.

## Forms

- Required subtasks that must be completed.
- Properties the output must have.
- Bad practices or error cases the output must avoid.
- Variations that are acceptable and should not be over-penalized.
- Must-haves versus nice-to-haves.

## Examples From Meetings

- For an itinerary: verify attraction opening hours, walking times, and age appropriateness.
- For a spreadsheet chart: verify that it pulls the right data, not only that it looks good.
- For a warehouse stock task: check implicit assumptions such as whether inflation or time horizon matters.

## Design Implications

Rubrics can drive views, preloaded questions, and verification prompts. They can also be used as a baseline, where users ask the agent to verify outputs against a rubric without the full research prototype.

## Imported Bridge Connections

- [[conversation-evaluation|Conversation evaluation]] generalizes verification rubrics into broader interaction-quality criteria.
- [[task-and-benchmark-datasets|Task and benchmark datasets]] points to datasets that can supply tasks, criteria, and correction traces.
- [[critical-review-and-counterargument|Critical review and counterargument]] adds the role of challenging assumptions rather than only checking completion.

## Related Pages

- [[spreadsheet-agent-verification]]
- [[unknown-unknowns]]
- [[views-into-agent-output]]
- [[participatory-design]]
- [[conversation-evaluation]]
- [[task-and-benchmark-datasets]]
- [[critical-review-and-counterargument]]
