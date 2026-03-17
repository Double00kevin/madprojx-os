# madprojx-os

Single source of truth for madprojx — AI consulting for small businesses.

## Current Phase

**Phase 2: Presence + Layer 2 Launch** — website live, LinkedIn shifting to daily content, building thought leadership engine on top of consulting foundation.

## Active Priorities

1. LinkedIn daily content — framework documented, ramping from 2-3/week to daily
2. First blog article for madprojx.com
3. Build passive income roadmap alongside consulting services
4. Content pipeline architecture for KITT (Month 2-3)
5. Newsletter signup integration on madprojx.com
6. Client outreach planning

## Completed

1. Brand positioning and service offerings finalized
2. madprojx.com live on Cloudflare Pages (5 pages: Home, Services, About, Blog, Contact)
3. LinkedIn profile overhauled and first post published
4. madprojx-os repo is functioning single source of truth
5. Claude Desktop → Claude Code handoff workflow documented in CLAUDE.md

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
| LinkedIn Framework | `areas/content/linkedin-framework.md` | Daily posting framework, formats, engagement strategy |
| Passive Income Roadmap | `areas/strategy/passive-income-roadmap.md` | Two-layer model, monetization timeline, platform phases |

## Environment

- **KITT (Ubuntu 24.04)** — canonical repo location, Claude Code, builds, deploys
- **Windows 11** — Obsidian vault (UI layer), Claude Cowork (business ops), VS Code SSH to KITT
- **Cloudflare** — hosts madprojx.com via Pages
- **Mobile** — DriveSync for Obsidian access on Android