---
type: overview
status: living
created: 2026-04-28
updated: 2026-05-01
sources:
  - "[[sumits-meeting-0-2026-02-20]]"
  - "[[ace-weekly-0-2026-03-04]]"
  - "[[ace-weekly-1-2026-03-11]]"
  - "[[sumits-meeting-1-2026-03-16]]"
  - "[[agent-workflows]]"
  - "[[conversation-evaluation]]"
  - "[[llm-behavior-and-biases]]"
tags:
  - synthesis
---

# Overview

The wiki now captures two connected meeting-derived research threads plus an imported `sadra-vault` research-note layer. The meeting threads are [[spreadsheet-agent-verification|spreadsheet-agent verification and steering]] and [[llm-creativity-programming-study|LLM effects on creative programming]]. The imported layer adds notes on [[agent-workflows|agent workflows]], [[conversation-evaluation|conversation evaluation]], [[llm-behavior-and-biases|LLM behavior and biases]], [[human-oversight|human oversight]], [[task-and-benchmark-datasets|task datasets]], [[second-brain-and-organizational-memory|second brains]], and related artifact-generation work.

Across both layers, the broader question is: how can AI systems preserve or improve human agency instead of only producing faster outputs?

## Current Synthesis

The spreadsheet-agent work is converging on a larger framing than "step-by-step reveal." The durable claim is that users need different [[views-into-agent-output|views into agent output]] and mechanisms for [[steerability|steering]] the output. Step-by-step change touring is one view. Other candidate views include DAGs, formula-only views, Q&A views, functional versus aesthetic views, and rubric-oriented verification views.

The strongest phrasing from the meetings is: users should not merely gain confidence that the agent was correct; they should be able to identify what matters, inspect the right parts of the output, and request precise changes. This shifts the project away from trust as a personality trait and toward task success, verification, correction, and satisfaction.

The creativity study provides a parallel agency story. LLM assistance appears to increase productivity-like outcomes such as correctness and completeness under a limited session, but it may reduce ideation time, creative moments, and perceived creative ownership. The suggested framing is a [[productivity-creativity-tradeoff|productivity-creativity tradeoff]] grounded in [[creative-agency|creative agency]].

The imported `sadra-vault` layer broadens the same agency problem from meeting-specific projects into reusable design and evaluation vocabulary. [[agent-workflows]] and [[human-oversight]] emphasize controlled autonomy and explicit moments where the system should ask the user. [[conversation-evaluation]] and [[verification-rubrics]] connect rubric-driven evaluation to interaction quality. [[llm-behavior-and-biases]] strengthens the case for critical review by collecting failure modes such as sycophancy, framing effects, anchoring, and sticky early concepts.

## Active Research Threads

- [[spreadsheet-agent-verification|Spreadsheet Agent Verification]] - Design and evaluate views, edit/ask controls, DAGs, rubrics, and steering workflows for spreadsheet AI agents.
- [[llm-creativity-programming-study|LLM Creativity Programming Study]] - Present and refine results on how LLMs affect creative programming behavior.
- [[participatory-design|Participatory Design]] - Use lightweight expert review and co-design to validate design goals and refine prototype features.
- [[unknown-unknowns|Unknown Unknowns]] - Explore whether models can surface implicit assumptions and missing checks that users may not think to ask.
- [[dag-of-agent-computation|DAG of Agent Computation]] - Treat agent work as a dependency graph that supports inspection, backtracking, repair, rerun, and merge-like steering.
- [[agent-workflows|Agent Workflows]] - Imported research-note cluster on controlled autonomy, test-and-patch loops, human oversight, and reviewable agent work.
- [[conversation-evaluation|Conversation Evaluation]] - Imported cluster on rubrics, user experience, correction traces, and conversational quality.
- [[llm-behavior-and-biases|LLM Behavior And Biases]] - Imported cluster on sycophancy, anchoring, framing effects, and critical review.
- [[second-brain-and-organizational-memory|Second Brain And Organizational Memory]] - Imported cluster connecting this wiki pattern to personal and organizational memory systems.

## Main Open Tensions

- Scope: the project has many promising ideas. The current paper needs one tight contribution, while the broader space should still be claimed.
- Terminology: use `spreadsheet` for the whole Excel document and `worksheet` for a tab.
- Baselines: possible baselines include manual verification, existing agent UI, agent self-verification, and cross-model checking.
- DAG semantics: decide whether the DAG represents actual computation dependencies, user-explored alternatives, or both.
- Model quality: several ideas depend on using frontier models rather than smaller models, especially unknown unknowns and decision/property extraction.
- Integration: decide whether imported source notes should remain a separate `sadra-vault` layer or be further synthesized into the meeting-derived project pages.

## Navigation

Start with [[spreadsheet-agent-verification]] for the main current project. Use [[action-items]] for work planning and [[open-questions]] for unresolved meeting-derived design and study decisions. Use [[sadra-vault-merge-diff-2026-05-01]] to inspect the imported nodes and bridge edges from the `sadra-vault` merge.
