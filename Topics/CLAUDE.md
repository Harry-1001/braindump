# Topics — Research Workflow

## Structure
- Single `.md` file for shallow topics
- Folder only when content grows beyond one file:
  ```
  <topic>/
    _index.md     # Overview, status, key questions
    notes/        # Research findings
    references/   # Source summaries and links
  ```
- Folder names: lowercase, hyphens (e.g., `machine-learning`)
- Note filenames: descriptive, lowercase, hyphens

## Frontmatter
```yaml
---
tags: [topic/<name>, status/planned]
---
```

## Status Tags
- `#status/planned` — plan created, research pending
- `#status/active` — research in progress
- `#status/paused` — paused
- `#status/done` — completed

## Workflow
1. `/deep-memo <words>` — adds to Inbox.md
2. `/deep-plan` — creates folder structure and _index.md
3. `/deep-research` — fills in notes/ and references/
4. `/deep-suggest` — suggests follow-up directions (read-only)

## Rules
- Use the topic template in `Templates/` when creating new topics
- Always link to related topics with `[[wikilinks]]`
- Inbox.md entries can be minimal — just a word or phrase
