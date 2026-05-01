---
type: task
status: living
created: 2026-04-28
updated: 2026-05-01
sources:
  - "[[sumits-meeting-0-2026-02-20]]"
  - "[[ace-weekly-0-2026-03-04]]"
  - "[[ace-weekly-1-2026-03-11]]"
  - "[[sumits-meeting-1-2026-03-16]]"
tags:
  - tasks
  - open-questions
---

# Open Questions

## Spreadsheet-Agent Verification

- What is the tight paper contribution: step-by-step reveal, views into agent output, steerability, DAGs, or a combination?
- What baseline is most defensible?
- Should cross-model verification be framed as a baseline, methodology, or future work?
- How should user-provided rubrics enter the study?
- How should must-haves and nice-to-haves be represented in the UI?
- What aspects should be considered functional versus aesthetic?
- Does the current task produce a convincing enough motivating example?
- Should unknown unknowns be a feature in this paper or a future direction?

## DAG / Graph

- Does the DAG represent computation dependencies, user-explored alternatives, speculative alternatives, or all three?
- Should unseen paths be displayed?
- When should obsolete paths be pruned?
- Should edges store code, specs, saved states, or multiple artifacts?
- When a user edits one node, should downstream nodes be rerun, repaired, regenerated, or marked stale?
- How should changes propagate across sibling branches, charts, or shared constants?
- Is merge-like branch combination in scope?

## Creativity Study

- What is the best term for the broader issue: cognitive alignment, cognitive misalignment, control, orchestration, or mixed initiative?
- Which code characteristics should be presented as baseline differences rather than creativity measures?
- How should collaboration modes be renamed to avoid confusion with product names like Copilot?
- How should the final talk connect the creativity study back to the broader thesis?

## Sources and Wiki

- Are Athena and Zeinabsadat Saghi the same person?
- Can anonymized ACE weekly speakers be mapped to real people, or should the wiki keep them anonymous?
- Should exact line-level citations be added to source summaries for stronger traceability?

## Imported Sadra Vault Questions

- See [[sadra-vault-open-questions|Sadra Vault Open Questions]] for open questions imported from the `sadra-vault` wiki layer.
- Should the imported `sadra-vault` concepts remain a separate research-note cluster, or should the strongest links be synthesized directly into project pages such as [[spreadsheet-agent-verification]] and [[llm-creativity-programming-study]]?
