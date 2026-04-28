# Meeting Notes LLM Wiki

This folder is set up as an LLM-maintained wiki for meeting transcripts.

## Layout

- `AGENTS.md` - operating instructions for Codex or another LLM agent.
- `raw/transcripts/` - immutable raw transcript sources.
- `raw/assets/` - put downloaded images or attachments here.
- `wiki/index.md` - start here when browsing or querying the wiki.
- `wiki/log.md` - append-only history of ingests, queries, and lint passes.
- `wiki/sources/` - one summary page per raw source.
- `wiki/projects/`, `wiki/concepts/`, `wiki/people/`, `wiki/tasks/` - synthesized wiki pages.

## Workflow

To ingest a new transcript, put it in `raw/transcripts/` and ask:

```text
Ingest raw/transcripts/<file>.md into the wiki.
```

To ask a question, ask against the wiki:

```text
Using the wiki, what are the main open questions about the DAG feature?
```

To maintain the wiki, ask for a lint pass:

```text
Lint the wiki for stale claims, missing links, contradictions, and open concepts.
```

The raw sources should stay unchanged. The LLM should update only the generated wiki layer unless you explicitly ask for source cleanup or reorganization.
