# Schema — LLM Wiki Maintainer

This document defines how the wiki is structured, what conventions to follow, and what workflows to execute for ingest, query, and lint operations.

## Directory Structure

```
.
├── raw/                  # Immutable source documents (never modify)
│   └── assets/           # Downloaded images and media
├── wiki/                 # LLM-generated markdown files (LLM owns this)
│   ├── home.md           # Top-level synthesis and orientation
│   ├── index.md          # Content catalog — all pages listed with links and summaries
│   ├── log.md            # Append-only chronological activity log
│   ├── entities/         # Pages for people, organizations, products
│   ├── concepts/         # Pages for key ideas, frameworks, theories
│   ├── sources/          # Summary pages for each ingested source
│   ├── analyses/         # Pages generated from queries and explorations
│   └── topics/           # Cross-cutting topic pages
└── CLAUDE.md             # This file — wiki schema and conventions
```

## Page Conventions

- Each page starts with a `# Title` heading.
- Use YAML frontmatter when useful: `tags`, `date`, `sources`, `status`.
- Link liberally to other wiki pages using `[text](relative-path.md)`.
- When referencing a raw source, link to its file in `../raw/`.
- Keep pages focused — one entity/concept/source per page.
- When new information contradicts an existing page, update the page and note the contradiction.

## Ingest Workflow

1. Read the source document from `raw/`.
2. Discuss key takeaways with the user.
3. Write a summary page in `wiki/sources/`.
4. Create or update entity pages in `wiki/entities/`.
5. Create or update concept pages in `wiki/concepts/`.
6. Update `wiki/index.md` with all new/changed pages.
7. Append an entry to `wiki/log.md` in the format: `## [YYYY-MM-DD] ingest | Source Title`.
8. Update `wiki/home.md` if the overall synthesis changes.

## Query Workflow

1. Read `wiki/index.md` to find relevant pages.
2. Read the relevant pages.
3. Synthesize an answer with citations (links to wiki pages).
4. If the answer is substantial, file it as a new page in `wiki/analyses/` or the appropriate category.
5. Update `wiki/index.md` and `wiki/log.md` if a new page was created.

## Lint Workflow

1. Scan all wiki pages for:
   - Contradictions between pages
   - Stale claims superseded by newer sources
   - Orphan pages with no inbound links
   - Important concepts mentioned but lacking their own page
   - Missing cross-references
   - Data gaps that could be filled with a web search
2. Present findings to the user.
3. Fix issues with user approval.
4. Append an entry to `wiki/log.md`: `## [YYYY-MM-DD] lint | summary of fixes`.

## Log Format

```
## [YYYY-MM-DD] type | Title

- Brief description of what was done
- Pages created/updated
```

Types: `ingest`, `query`, `lint`.

## Tips

- A single source may touch 10-15 wiki pages — that's normal and good.
- Good query answers compound: file them back as new pages.
- The index is the LLM's primary navigation tool at moderate scale.
- Prefer staying involved in ingests one at a time rather than batch-processing.
