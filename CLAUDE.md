# Personal Knowledge Vault

## Overview
Haruka's personal knowledge base — life, work, research, and writing all in one Obsidian vault.
Claude Code automates research and organization workflows.

## Structure
```
/
├── Inbox.md          # Topic words for research (one per line)
├── Work/             # Wanderlust internship notes, feedback, meetings
├── 10_Life/          # Journal, profile, personal thoughts
├── 20_People/        # Notes on specific individuals
├── 30_Books/         # Reading notes
├── 40_recruiting/    # Job hunting materials
├── 50_Topics/        # Deep research (curiosity-driven, cross-domain)
├── 80_Writing/       # note.com articles (drafts & published)
├── 90_Maps/          # Maps of Content (MOCs)
├── 95_Templates/     # Obsidian templates
├── 99_Archive/       # Paused or completed work
└── .claude/skills/   # Claude Code automation skills
```

## Domain Routing
When creating or saving notes, route by context:
- **Work/** — internship, clients, business tasks, feedback
- **10_Life/** — journal, goals, reflections, daily thoughts
- **20_People/** — notes on specific individuals
- **30_Books/** — reading notes and summaries
- **40_recruiting/** — job hunting, case prep, company research
- **50_Topics/** — deep research spanning domains or curiosity-driven
- **80_Writing/** — note.com article drafts and published pieces

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
