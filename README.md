# madprojx-os

Single source of truth for madprojx — AI consulting for small businesses.

## Current Phase

**Phase 1: Foundation** — building the business operating system and foundational docs.

## Active Priorities

1. Finalize brand positioning and service offerings
2. Build out madprojx.com (Astro site in `madprojx-site/`)
3. Launch LinkedIn presence with 2-3 posts/week
4. Set up recurring content workflow via Cowork scheduled tasks

## Repo Structure

```
madprojx-os/
├── .claude/CLAUDE.md      # Business context for Claude Code sessions
├── brief.md               # Project brief — scope and definition of done
├── madprojx-site/         # Website codebase (Astro + Cloudflare Pages)
├── areas/
│   ├── brand/             # Positioning, voice guide, visual identity
│   ├── content/           # Strategy, calendar, ideas bank
│   ├── services/          # Offerings, pricing
│   └── operations/        # Tool stack, AI decision matrix, weekly review
├── resources/             # Reference material (competitors, tools, templates, research)
└── archives/              # Completed or inactive items
```

## Conventions

- **Folder naming:** kebab-case for all new folders and files
- **Areas vs Resources:** Areas are ongoing responsibilities (brand, content, services, operations). Resources are reference material with no action attached.
- **Archives rule:** Anything no longer active moves to `archives/`. Never delete, always archive.
- **Claude Code:** Open a session in this directory to auto-load business context from `.claude/CLAUDE.md`. Open a session in `madprojx-site/` to auto-load website build context.

## Key Docs

| Doc | Location | Purpose |
|-----|----------|---------|
| Project Brief | `brief.md` | What madprojx is, who it serves, definition of done |
| Brand Positioning | `areas/brand/positioning.md` | Who we serve, what we do, why us, brand voice |
| Service Offerings | `areas/services/offerings.md` | Assessment, Sprint, Retainer — scope and pricing |
| Content Strategy | `areas/content/strategy.md` | Platforms, cadence, pillars, weekly workflow |
| Content Ideas | `areas/content/ideas-bank.md` | Running backlog of content ideas |
| AI Decision Matrix | `areas/operations/ai-decision-matrix.md` | Which AI tool for which task |

## Environment

- **KITT (Ubuntu 24.04)** — canonical repo location, Claude Code, builds, deploys
- **Windows 11** — Obsidian vault (UI layer), Claude Cowork (business ops), VS Code SSH to KITT
- **Cloudflare** — hosts madprojx.com via Pages
- **Mobile** — DriveSync for Obsidian access on Android