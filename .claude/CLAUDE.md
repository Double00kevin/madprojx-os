# madprojx — Business Context for Claude Code
> Last updated: 2026-03-18

You are working inside the madprojx-os repository — the single source of truth for madprojx, a one-person AI consulting brand.

## What madprojx Is

AI consulting for small businesses — implemented securely, explained clearly. Founded by Kevin, 20+ years in cybersecurity (CISSP). We help small businesses understand, adopt, and secure AI in their operations.

## Who We Serve

Small businesses (5-100 employees) that know they need AI but don't know where to start. Service businesses, retail, local firms, trades. Not tech companies.

## Business Model: Two Layers

**Layer 1 — Consulting (Active Income):** AI Readiness Assessments, Implementation Sprints, Advisory retainers. This is the revenue foundation and credibility engine.

**Layer 2 — Thought Leadership (Passive Income):** Daily content across expanding platforms builds audience. Monetization unlocks over time: affiliate revenue → digital products → sponsorships → courses. Every consulting engagement feeds content. Every piece of content drives consulting leads.

Kevin is the voice and filter. AI handles production scaling. Nothing auto-publishes.

## Differentiators

- Security-first — every recommendation includes a risk assessment
- Plain language — we explain AI in terms business owners understand
- Vendor-neutral — we recommend the right tool, not the one that pays us
- Solo practitioner — clients work directly with Kevin
- Small business focus — recommendations fit real budget and staffing constraints

## Model & Settings Guidance
Default model for ALL work: Opus 4.6
- Use Opus 4.6 on every single turn, every subagent, every agent team.
- I will change the model myself in the Desktop/Code tab dropdown if I ever want something different.
- Never suggest or switch to Sonnet, Haiku, or any other model.
- Effort level: high (default). Use "ultrathink" keyword only when I explicitly type it.

## Repo Structure

```
madprojx-os/
├── .claude/
│   ├── CLAUDE.md              ← you are here
│   └── rules/                 ← modular rules (brand voice, content, guardrails)
├── README.md
├── brief.md                   # Project brief — scope and definition of done
├── madprojx-site/             # Astro website codebase (has its own .claude/CLAUDE.md)
├── areas/
│   ├── brand/positioning.md   # Full positioning doc
│   ├── content/strategy.md    # Content strategy and weekly workflow
│   ├── content/ideas-bank.md  # Content idea backlog
│   ├── services/offerings.md  # Service definitions and pricing
│   └── operations/
│       ├── ai-decision-matrix.md  # Which AI tool for which task
│       ├── workflow-guide.md      # madprojx-specific daily workflow
│       └── operating-plan-v2.md   # Full operating plan V2.1
├── resources/                 # Reference material (competitors, tools, templates, research)
└── archives/                  # Completed or inactive items
```

## Workflow: Claude Desktop → Claude Code Handoff

Content strategy, brand decisions, copy drafting, and planning happen in Claude Desktop (Cowork/Project chat). Claude Desktop does NOT build files or write code for the repo.

When a task is ready for implementation, Claude Desktop provides a detailed prompt for Claude Code. Kevin copies that prompt to a Claude Code session on KITT, where the actual repo work happens.

- Claude Desktop's job: decide what to build and why.
- Claude Code's job: build it, test it, deploy it.

## Key References

- Full positioning: `areas/brand/positioning.md`
- Content strategy: `areas/content/strategy.md`
- Service definitions: `areas/services/offerings.md`
- AI tool decisions: `areas/operations/ai-decision-matrix.md`
- Passive income roadmap: `areas/strategy/passive-income-roadmap.md`
- Daily content framework: `areas/content/linkedin-framework.md`

## Close The Loop

When I type "close the loop":
1. Update this file's "Last updated" date + any changed sections

## Rules

See `.claude/rules/` for modular rules on brand voice, content pillars, service offerings, and guardrails.

All files in `.claude/rules/` are automatically loaded at the same priority as this file and must be followed at all times.
