---
type: source_summary
status: living
created: 2026-04-28
updated: 2026-04-28
source_date: 2026-02-20
raw_source: "raw/transcripts/Sumit's Meeting - Feb 20st, 2026.md"
sources:
  - "[[Sumit's Meeting - Feb 20st, 2026|Sumit's Meeting - Feb 20st, 2026]]"
tags:
  - source-summary
  - spreadsheet-agents
  - verification
---

# Sumit's Meeting 0 - 2026-02-20

## Source

- Raw file: [[Sumit's Meeting - Feb 20st, 2026|Sumit's Meeting - Feb 20st, 2026]]
- Date: 2026-02-20
- Participants named in transcript: [[sadra-sabouri|Sadra Sabouri]], [[sumit-gulwani|Sumit Gulwani]], [[sujay-maladi|Sujay Maladi]], [[athena-zeinabsadat-saghi|Athena]]
- Main topic: framing and evaluating a tool for validating, inspecting, and steering spreadsheet AI-agent outputs.

## One-Line Summary

The meeting reframed the project away from trust categories and toward helping users identify, understand, and fix issues in spreadsheet-agent outputs through verification methods, change touring, and steering mechanisms.

## Key Takeaways

- The system goal should be independent of whether users are low-trust or high-trust. The goal is to help users figure out where an agent output has issues and fix them.
- Satisfaction is broader than correctness. Users may care about preferences, aesthetics, layout, formatting, charts, and style as well as factual or computational correctness.
- Current spreadsheet-agent interfaces have fragmented explanations and limited interaction paths. This increases cognitive load during verification.
- A verification methodology can be a contribution even without a fully new tool feature. Users can ask an agent to check its own output, write a grading scheme, or use a second model as an independent checker.
- Verification rubrics may include must-haves and nice-to-haves, with the user specifying which aspects matter most for a task.
- The project may also apply to scalable oversight and expert data labeling, where paid domain experts judge agent outputs and trajectories.
- The tool may teach reusable methods. Sumit compares this to a divergent/convergent image-generation tool whose users later applied the method directly in ChatGPT.
- Implementation direction includes an Excel add-in path and a from-scratch prototype path. The add-in has more compatibility with Excel Agent; the scratch prototype gives more experimental control.
- OfficeJS is an important implementation surface. If chart or spreadsheet changes are represented as code, some edits can be mapped to direct code/object-model changes rather than full model calls.

## Decisions and Direction

- Prefer the framing of helping users get the job done correctly and to their satisfaction over measuring user trust as the central construct.
- Treat agent-verifies-itself or cross-model checking as a possible baseline or methodology.
- Keep the decision-tree/branching worksheet idea available, but recognize it may be a separate contribution from change touring.

## Action Items

- Clarify research questions around verification practices, change touring, and adaptive user intervention.
- Consider baselines that include agent-assisted verification.
- Decide which aspects of the prototype belong in the current paper and which are future work.
- Investigate whether Excel Agent can expose OfficeJS code for generated objects.

## Links

- [[spreadsheet-agent-verification]]
- [[verification-rubrics]]
- [[steerability]]
- [[views-into-agent-output]]
- [[participatory-design]]
