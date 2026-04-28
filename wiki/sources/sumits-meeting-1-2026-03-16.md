---
type: source_summary
status: living
created: 2026-04-28
updated: 2026-04-28
source_date: 2026-03-16
raw_source: "raw/transcripts/Sumit's Meeting - March 16st, 2026.md"
sources:
  - "[[Sumit's Meeting - March 16st, 2026|Sumit's Meeting - March 16st, 2026]]"
tags:
  - source-summary
  - spreadsheet-agents
  - dag
  - steerability
---

# Sumit's Meeting 1 - 2026-03-16

## Source

- Raw file: [[Sumit's Meeting - March 16st, 2026|Sumit's Meeting - March 16st, 2026]]
- Date: 2026-03-16
- Participants named in transcript: [[sadra-sabouri|Sadra Sabouri]], [[sumit-gulwani|Sumit Gulwani]], [[souti-rini-chattopadhyay|Souti Chattopadhyay (Rini)]], [[sujay-maladi|Sujay Maladi]], [[athena-zeinabsadat-saghi|Zeinabsadat Saghi / Athena]]
- Main topic: broadening the spreadsheet-agent project around views, steerability, DAGs, unknown unknowns, and prototype/video scope.

## One-Line Summary

The meeting identified the larger contribution as giving users different views into agent outputs and ways to steer the process, with DAGs, rubrics, unknown unknowns, and graph repair as major design directions.

## Key Takeaways

- Rename or reframe "granular feedback" as [[steerability|steerability]] because users are trying to accomplish and direct a task, not only label an output.
- The big idea is [[views-into-agent-output|different views into the output of an agent]]. Step-by-step reveal is one manifestation, not the full contribution.
- Candidate views include step-by-step reveal, a DAG of the agent's computation, formula-only or correctness-focused views, Q&A views, and views filtered by user intent.
- Views should support steering, not only post-hoc understanding. The process may still be underway when users inspect it.
- The formative/participatory study had already run 8 sessions by this meeting. Users liked step-by-step reveal and felt edit mechanisms gave more precise control.
- User feedback surfaced rationale questions, alternatives, and some need for [[unknown-unknowns|unknown unknowns]] or rubrics.
- Unknown unknowns may require better models and better prompts. Sumit recommended maintaining a diary of hard tasks and retrying them when stronger models are released.
- There may be a role for a meta-prompting agent whose job is to improve prompts for surfacing unknown unknowns.
- Functional versus aesthetic focus can become a UI toggle for edit and ask modes.
- A demo video should show a convincing task story where the user finds a bug or steers the output in an interesting direction, not just a feature tour.
- The DAG may be especially novel. It should represent computational dependencies, not merely the linear order in which the agent wrote or executed steps.
- DAG edges may store code and/or a spec. Saved states enable deterministic backtracking; rerunning code or regenerating from specs enables forward changes.
- Steering raises hard issues: propagating edits across dependent paths, refactoring code, pruning obsolete paths, repairing downstream steps, and merging useful parts from different branches.
- Guardrails are necessary because exploratory agent behavior can make users feel out of control.
- Preloaded questions can help address the Gulf of Envisioning by showing users the space of useful questions and model capabilities.

## Decisions and Direction

- Keep the current paper focused enough to finish, but claim the broader space of views plus steering.
- Use the best available model for frontier design exploration unless the research question is explicitly about latency, cost, or smaller models.
- Include the DAG in the video or prototype story if possible because it may be the clearest differentiator.
- Treat dependency propagation, refactoring, repair, pruning, and merging as important future or adjacent work unless they can be handled within current scope.

## Action Items

- Complete the research prototype and prepare the summative study.
- Prepare a video for Microsoft/internal sharing that includes the DAG and a strong motivating example.
- Maintain a diary of tasks where current models fail to surface good unknown unknowns.
- Experiment with prompts and agents for eliciting unknown unknowns.
- Decide what graph/DAG semantics are in scope for the paper.

## Links

- [[spreadsheet-agent-verification]]
- [[views-into-agent-output]]
- [[steerability]]
- [[dag-of-agent-computation]]
- [[unknown-unknowns]]
- [[verification-rubrics]]
