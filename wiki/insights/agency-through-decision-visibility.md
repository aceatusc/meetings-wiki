---
type: insight
status: living
created: 2026-04-28
updated: 2026-04-28
sources:
  - "[[overview]]"
  - "[[llm-creativity-programming-study]]"
  - "[[spreadsheet-agent-verification]]"
  - "[[views-into-agent-output]]"
  - "[[creative-agency]]"
tags:
  - insight
  - agency
  - steerability
  - creativity
---

# Agency Through Decision Visibility

## Insight

The creativity study and spreadsheet-agent verification project are not just adjacent examples of human-AI interaction. They may be studying the same deeper mechanism: **users lose agency when the agent collapses meaningful decision points into a polished output**.

In the creativity study, LLMs may reduce ideation time, aha moments, and creative ownership even when outputs become more complete. In the spreadsheet-agent project, users need views, DAGs, rubrics, and step-level controls because the agent's work is otherwise hard to inspect or steer.

The shared construct is decision visibility. Users need to see where consequential choices were made, which alternatives were possible, and which parts they can still change.

## Why It Matters

This reframes the contribution from "help users verify outputs" or "measure creativity loss" to a broader design principle:

> Human agency in AI workflows depends on making consequential decision points visible, revisable, and attributable.

That principle can unify creative workflows, spreadsheet agents, coding agents, and other long-running agentic systems.

## Concrete Implication

For a creative workflow user study, do not only measure final artifact quality or self-reported creativity. Also instrument:

- which decision points the user saw
- which decision points the user changed
- which decisions were attributed to the user versus the agent
- whether the user discovered alternatives after seeing the agent's path
- whether the user could explain why the final artifact took its current form

This would connect [[creative-agency]] directly to [[views-into-agent-output]] and [[steerability]].

## Related Pages

- [[creative-agency]]
- [[views-into-agent-output]]
- [[steerability]]
- [[productivity-creativity-tradeoff]]
- [[dag-of-agent-computation]]

