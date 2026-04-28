# LLM Wiki Maintainer

This workspace is an LLM-maintained personal research wiki for meeting transcripts and related notes. The user curates sources and asks questions. The LLM maintains the wiki.

## Repository Roles

- Raw sources are immutable. Read them, cite them, and never edit them during wiki work.
- Transcript sources live in `raw/transcripts/`, with attachments in `raw/assets/`.
- Generated wiki pages live in `wiki/`. The LLM owns this layer and may create, revise, link, reorganize, and lint pages there.
- `wiki/index.md` is the content map. Update it after every ingest or major wiki edit.
- `wiki/log.md` is append-only chronological history. Add a dated entry after every ingest, substantial query, or lint pass.

## Wiki Conventions

Use Obsidian-style wikilinks for internal links.

Every generated page should start with YAML frontmatter:

```yaml
---
type: concept
status: living
created: 2026-04-28
updated: 2026-04-28
sources:
  - "[[Source Page]]"
tags:
  - example-tag
---
```

Common `type` values:

- `overview`
- `index`
- `log`
- `source_summary`
- `project`
- `concept`
- `person`
- `task`
- `template`

Status values:

- `living`: expected to evolve.
- `seed`: incomplete first pass.
- `stable`: mature synthesis.
- `needs_review`: likely important but uncertain.

## Citation and Evidence Rules

- Keep source claims traceable. Prefer linking to a source summary and the raw source file.
- Distinguish what the transcript says from what the LLM infers.
- Do not identify anonymized speakers unless the transcript itself does so clearly.
- For meeting transcripts, preserve uncertainty around names, deadlines, and speaker roles.
- When a source contains a relative date, record the source date and convert only when the inference is clear.
- Do not over-clean transcripts in the raw layer. Clean and synthesize only in the wiki.

## Ingest Workflow

When the user asks to ingest a new transcript or source:

1. Read the raw source completely.
2. Create or update a page under `wiki/sources/`.
3. Extract:
   - meeting date
   - participants or speaker labels
   - topic
   - decisions
   - action items
   - open questions
   - useful quotes or terms, paraphrased unless exact wording matters
4. Update relevant pages under `wiki/projects/`, `wiki/concepts/`, `wiki/people/`, and `wiki/tasks/`.
5. Add missing cross-links in both directions where useful.
6. Update `wiki/index.md`.
7. Append to `wiki/log.md` using:

```markdown
## [YYYY-MM-DD] ingest | Source title
```

## Query Workflow

When answering a question against the wiki:

1. Read `wiki/index.md` first.
2. Open the most relevant wiki pages and source summaries.
3. If needed, search raw transcripts with `rg`.
4. Answer with citations to wiki pages and raw sources.
5. If the answer produces reusable synthesis, ask whether to file it or, if the user requested compounding/wiki maintenance, create a new page and update the index/log.

## Obsidian CLI Usage

Prefer Obsidian CLI for vault navigation and wiki maintenance when the app is running. If `obsidian` reports that it cannot find Obsidian, fall back to direct filesystem tools such as `rg`, `sed`, and `apply_patch`.

Useful Obsidian CLI commands for this vault:

- `obsidian files folder=wiki ext=md` - list wiki pages.
- `obsidian search query="<term>" path=wiki` - find relevant wiki pages.
- `obsidian search:context query="<term>" path=wiki` - search with matching line context.
- `obsidian read path="<path>"` - read a note.
- `obsidian create path="<path>" content="<markdown>"` - create a note.
- `obsidian append path="wiki/log.md" content="<entry>"` - append to the log.
- `obsidian backlinks path="<path>" counts` - inspect inbound links.
- `obsidian links path="<path>"` - inspect outgoing links.
- `obsidian unresolved counts verbose` - find unresolved wikilinks.
- `obsidian orphans` - find pages with no incoming links.
- `obsidian deadends` - find pages with no outgoing links.
- `obsidian tags counts` and `obsidian properties counts` - inspect wiki metadata.

## Session Commands

The user may call these commands as plain chat messages. The Codex UI may intercept messages that begin with `/`, so support both slash-form commands and colon-form aliases. Prefer documenting colon-form aliases to the user.

### `/help` or `help:`

Show the available LLM Wiki commands and their expected arguments.

### `/ingest <raw-source-path>` or `ingest: <raw-source-path>`

Run the full ingest workflow on one raw source. Use Obsidian CLI to search/read/create/append when available. Update the source summary, relevant project/concept/person/task pages, `wiki/index.md`, and `wiki/log.md`.

If the argument is omitted, inspect `raw/transcripts/` for raw sources that do not have matching source summaries and ask the user which to ingest only if more than one plausible target exists.

### `/query <question>` or `query: <question>`

Run the query workflow. Read `wiki/index.md`, use Obsidian CLI search/context over `wiki/` and `raw/transcripts/`, synthesize an answer with source links, and avoid filing new pages unless the user asks or the answer is clearly reusable.

### `/insight [topic]` or `insight: [topic]`

Generate one non-obvious, useful insight from the wiki. It should connect at least two existing pages or sources, state why it matters, and suggest one concrete implication. If the insight should be preserved, file it under `wiki/insights/`, update `wiki/index.md`, and append to `wiki/log.md`.

### `/missing [topic]` or `missing: [topic]`

Ask critical questions that would add meaningful new connections to the wiki. Treat the user's answers as commentary, not raw source evidence. If the user answers, create or update a commentary page under `wiki/commentary/`, link it to relevant source-backed pages, and mark the provenance clearly as user commentary.

### `/lint` or `lint:`

Run the lint workflow. Use Obsidian CLI checks such as `unresolved`, `orphans`, `deadends`, `tags`, and `properties` when available. Create a dated lint report in `wiki/tasks/`, update `wiki/index.md` if needed, and append to `wiki/log.md`.

### `/open <page-or-path>` or `open: <page-or-path>`

Open or read a wiki note. Prefer `obsidian open file=<name>` or `obsidian open path=<path>` if Obsidian is running; otherwise read the file directly.

### `/map [topic]` or `map: [topic]`

Create a compact connection map for a topic: central pages, linked concepts, source evidence, open questions, and weak or missing links. File durable maps under `wiki/maps/` only when the user asks to keep them or when they materially improve navigation.

### `/sources [topic]` or `sources: [topic]`

List the most relevant raw sources and source summary pages for a topic, with short notes on what each contributes.

### `/tasks [topic]` or `tasks: [topic]`

Extract or update action items related to a topic. Use `wiki/tasks/action-items.md` as the canonical task page unless a project-specific task page is warranted.

## Lint Workflow

Periodically check for:

- orphan pages with no inbound links
- concepts mentioned repeatedly but missing pages
- stale project pages after new meetings
- conflicting claims between pages
- vague source provenance
- action items without owners or dates
- raw sources that have not been ingested

Record lint results in `wiki/tasks/` and append an entry to `wiki/log.md`.

## Domain Priorities

This wiki currently focuses on research meetings around:

- spreadsheet or worksheet AI agents
- verification, oversight, and user agency
- views into agent output and steerability
- DAGs or graphs of agent computation
- rubrics, unknown unknowns, and model-assisted checking
- LLM effects on creativity, creative agency, and programming
- participatory design, formative studies, and summative evaluation planning

Keep terminology precise:

- Use `spreadsheet` for the whole Excel document.
- Use `worksheet` for a sheet/tab inside a spreadsheet.
- Use `steerability` when the user is actively directing an output, and `feedback` when someone is rating or labeling output quality.
