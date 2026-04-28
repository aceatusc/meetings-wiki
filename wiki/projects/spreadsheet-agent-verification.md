---
type: project
status: living
created: 2026-04-28
updated: 2026-04-28
sources:
  - "[[sumits-meeting-0-2026-02-20]]"
  - "[[ace-weekly-1-2026-03-11]]"
  - "[[sumits-meeting-1-2026-03-16]]"
tags:
  - spreadsheet-agents
  - verification
  - steerability
---

# Spreadsheet Agent Verification

## Summary

This project studies how users can inspect, verify, and steer the outputs of spreadsheet AI agents. The core direction is not merely to increase user trust, but to help users find issues, understand changes, and request targeted fixes until the output satisfies the task.

The strongest current framing is: provide [[views-into-agent-output|views into agent output]] and [[steerability|steerability]]. Step-by-step reveal is one view. A [[dag-of-agent-computation|DAG of agent computation]], formula-only checks, Q&A, functional/aesthetic filters, and [[verification-rubrics|rubric]] views are other candidates.

## Problem Framing

Spreadsheet-agent outputs are data-first artifacts. Users often verify at the level of cells, rows, formulas, charts, and layout rather than by reading a program. This makes verification cognitively demanding when the agent's changes are large, disconnected, or poorly explained.

The project should focus on task success and satisfaction:

- Can users understand what changed?
- Can they detect errors or questionable assumptions?
- Can they distinguish functional correctness from aesthetic preference?
- Can they steer the output at the right granularity?
- Can they specify what matters most for verification?

## Current Prototype Features

- Step-by-step reveal or change touring.
- Contextual edit on a specific step or output object.
- Ask/Q&A support for rationale and explanation.
- Preloaded questions to show users useful question types.
- Possible DAG view of the agent's computation.
- Possible focus toggle for functional, aesthetic, or both.
- Possible rubrics or unknown-unknown prompts.

## Study Plan

The formative/participatory design phase had run 8 sessions by [[sumits-meeting-1-2026-03-16]]. Participants reportedly liked step-by-step reveal and felt edit controls gave more precise control.

The summative study should evaluate the tool's effect on:

- speed of verification
- accuracy of issue detection
- understanding of changes
- agency and satisfaction
- possibly ability to state or use task-specific rubrics

The study should avoid framing the dependent variable as agent quality. The target is user verification and steering.

## Baseline Candidates

- Existing spreadsheet-agent interface without the research prototype.
- Manual inspection of output.
- Agent self-verification through a second prompt.
- Cross-model verification, where a different model checks the first model's output.
- User-provided rubric without the full tool.

## Implementation Notes

- Use `spreadsheet` for the entire Excel document and `worksheet` for a tab.
- Excel Agent likely uses OfficeJS to manipulate Excel's object model. If code is exposed, some edits may map directly to code or object-model parameters.
- A DAG edge can store code, a spec, or both.
- Backtracking can use saved states for determinism and efficiency.
- Forward changes can rerun code, regenerate code from specs, or ask an agent to repair affected downstream steps.
- Dependency propagation, refactoring, pruning obsolete branches, and merging alternate branches are hard but important.

## Scope Risks

- The project can sprawl into many separate papers. Current work needs one solid contribution.
- Branching worksheets/spreadsheets may be separate from change touring unless tightly integrated.
- Unknown unknowns may underperform with weaker models or weak prompts.
- DAG semantics need to be clear: actual computation dependencies, user-explored alternatives, speculative alternatives, or some combination.

## Related Pages

- [[views-into-agent-output]]
- [[steerability]]
- [[verification-rubrics]]
- [[dag-of-agent-computation]]
- [[unknown-unknowns]]
- [[participatory-design]]
- [[action-items]]
- [[open-questions]]

