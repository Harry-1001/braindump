# Personal Knowledge Vault

## Overview
Haruka's personal knowledge base — life, work, research, and writing all in one Obsidian vault.
Claude Code automates research and organization workflows.

## Structure
```
/
├── Inbox.md          # Topic words for research (one per line)
├── Work/             # Wanderlust internship notes, feedback, meetings
├── School/           # WASEDA class notes, assignments
├── Life/             # Journal, profile, personal thoughts
├── Topics/           # Deep research (curiosity-driven, cross-domain)
├── Writing/          # note.com articles (drafts & published)
├── People/           # Notes on specific individuals
├── Books/            # Reading notes
├── recruiting/       # Job hunting materials
├── Maps/             # Maps of Content (MOCs)
├── Templates/        # Obsidian templates
├── Archive/          # Paused or completed work
└── .claude/skills/   # Claude Code automation skills
```

## Domain Routing
When creating or saving notes, route by context:
- **Work/** — internship, clients, business tasks, feedback
- **School/** — lectures, assignments, academic research
- **Life/** — journal, goals, reflections, daily thoughts
- **Topics/** — deep research spanning domains or curiosity-driven
- **Writing/** — note.com article drafts and published pieces
- **People/** — notes on specific individuals
- **Books/** — reading notes and summaries
- **recruiting/** — job hunting, case prep, company research

## Global Conventions
- All files are Markdown (.md), Obsidian-compatible
- Use `[[wikilinks]]` for internal links
- Use YAML frontmatter for metadata (status, tags, dates)
- Prefer updating existing notes over creating duplicates
- Link related notes with `[[wikilinks]]` across domains freely

## Tag Taxonomy
- `#domain/work` — work/internship related
- `#domain/school` — academic/university related
- `#domain/life` — personal/life related
- `#thought` — free-form thought or reflection
- `#reference` — reference/source file

## Claude Code Skills
- `/ask <question>` — Quick Q&A, findings saved to vault
- `/deep-memo <words>` — Add topic words to Inbox.md
- `/deep-plan [topics]` — Create research plans
- `/deep-research [topics]` — Execute research
- `/deep-suggest [topics]` — Suggest follow-up directions
- `/dump [files]` — Organize thoughts with vault context
- `/todo [task]` — Record and update todo items
