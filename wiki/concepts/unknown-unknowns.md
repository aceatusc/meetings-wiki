---
type: concept
status: living
created: 2026-04-28
updated: 2026-04-28
sources:
  - "[[sumits-meeting-1-2026-03-16]]"
tags:
  - concept
  - verification
  - prompting
---

# Unknown Unknowns

## Definition

Unknown unknowns are relevant assumptions, risks, checks, or alternatives that the user may not know to ask about.

## Role In The Project

Unknown unknowns are a possible verification-support feature. Instead of only offering edit suggestions or answerable questions, the system could ask what neither the user nor the agent has considered.

## Evidence From Meetings

The formative study surfaced some need for this kind of support, though not as frequently as rationale and alternatives. Sadra tested a warehouse stock task where a human-generated unknown unknown was inflation over the seven-day horizon. Early model outputs were reported as more surface-level.

## Research Direction

- Keep a diary of tasks where current models fail.
- Retry the diary when new models are released.
- Use stronger frontier models for this exploration.
- Create a meta-prompting agent whose job is to improve prompts for eliciting unknown unknowns.
- Compare edit/ask suggestions against a separate unknown-unknown prompt in a fresh context.

## Related Pages

- [[verification-rubrics]]
- [[spreadsheet-agent-verification]]
- [[views-into-agent-output]]

