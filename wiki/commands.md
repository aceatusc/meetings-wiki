---
type: command_reference
status: living
created: 2026-04-28
updated: 2026-04-28
tags:
  - commands
  - obsidian-cli
---

# LLM Wiki Commands

These are chat-level commands for this Codex session. They are backed by the workflow in [[AGENTS]] and should use Obsidian CLI when the Obsidian app is running.

Codex may intercept messages that start with `/`. Use the colon-form aliases below if the UI says a slash command is unrecognized.

## Commands

- `help:` - show available commands.
- `ingest: <raw-source-path>` - ingest a raw transcript or source into the wiki.
- `query: <question>` - answer a question using the wiki first, then raw sources if needed.
- `insight: [topic]` - produce one non-obvious insight and optionally file it.
- `missing: [topic]` - ask critical questions; treat user answers as commentary when updating the wiki.
- `lint:` - health-check unresolved links, orphan/dead-end pages, stale tasks, contradictions, and missing concepts.
- `open: <page-or-path>` - open/read a note.
- `map: [topic]` - map connections around a topic.
- `sources: [topic]` - list relevant sources for a topic.
- `tasks: [topic]` - extract or update action items.

## Obsidian CLI Backing

Common CLI calls:

```shell
obsidian files folder=wiki ext=md
obsidian search query="steerability" path=wiki
obsidian search:context query="unknown unknowns" path=wiki
obsidian read path="wiki/index.md"
obsidian append path="wiki/log.md" content="..."
obsidian unresolved counts verbose
obsidian orphans
obsidian deadends
obsidian backlinks path="wiki/concepts/steerability.md" counts
```

If Obsidian is not running, use direct filesystem tools with the same intent.
