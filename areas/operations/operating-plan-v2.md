**Prepared for:** Kevin (00Kevin) — Solo Founder, madprojx **Date:** March 14, 2026 **Status:** VERIFIED **Version:** 2.1 (FINAL) — Incorporates discovery answers, platform research, and Docs-as-Code operating model

---

## What Changed Since V1

Your discovery answers and the research into current Claude Desktop/Cowork capabilities significantly shift the recommendation. The hybrid approach is still correct, but **Claude Cowork on your Windows 11 machine is now the centerpiece**, not just a supporting tool. Here's why:

Since V1, Anthropic has shipped Cowork with scheduled tasks, a plugin marketplace, 12+ MCP connectors (Gmail, Google Calendar, Google Drive, WordPress, and more), cross-app workflows, and the Cloudflare MCP connector — which you already have connected in this session. This means your Windows 11 dev machine running Claude Desktop is no longer just a chat interface. It's a business operations hub that can draft content, manage your calendar, read your email, interact with your Cloudflare infrastructure, and run recurring tasks on a schedule.

Combined with Claude Code on KITT for development work and your existing Obsidian + DriveSync setup for knowledge management, you have a stack that covers every requirement you listed — without adding a single new tool.

---

## Revised Hybrid Stack for madprojx

### Layer 1: Claude Cowork (Windows 11) — Command Center

**Role:** Daily business operations, content creation, research, scheduling, client communications.

**What you get right now:**

- **Scheduled Tasks** — Set recurring content drafting, competitor monitoring, industry news digests, and social media post prep on autopilot. Tasks run when your PC is awake and Claude Desktop is open. Your i9-14900K machine is presumably on most of the day, making this viable.
- **Gmail Connector** — Read, search, and draft emails directly from Cowork. When you're doing outreach to small businesses, Claude can draft personalized emails, follow-ups, and proposals without leaving the conversation.
- **Google Calendar Connector** — Schedule discovery calls, block content creation time, and review your week. A scheduled task could generate a daily briefing of what's on your plate.
- **Google Drive Connector** — Read and search files in Drive. Since you're using DriveSync with Obsidian, this creates a bridge between your knowledge base and Claude.
- **Cloudflare Connector** — Already active in this session. You can manage Workers, Pages, KV, R2, and D1 databases directly through Cowork. When it's time to build out madprojx.com, Claude can deploy directly.
- **WordPress Connector** — If you decide to run a blog on WordPress (or headless WP as a CMS for Cloudflare Pages), this is ready.
- **Skills & Plugins** — You have access to the full plugin marketplace. Document creation (docx, pptx, pdf, xlsx), data analysis, and specialized workflows are available as skills.

**Limitation to know:** Scheduled tasks only run when your PC is awake and Claude Desktop is open. Not a 24/7 automation server. For always-on automation, you'd use KITT.

---

### Layer 2: Claude Code on KITT (Ubuntu 24.04) — Build Engine

**Role:** Website development, automation scripts, tool building, and any code-heavy work.

**What it handles:**

- Building and deploying madprojx.com via Cloudflare Pages (your `projects/madprojx-site` folder is already there)
- Running GSD when you need structured development sprints for client tools or internal software
- Hosting MCP servers or custom automations that need to run 24/7 (KITT doesn't sleep)
- Git operations, CI/CD, and anything that benefits from a persistent Linux environment

**The `.claude/CLAUDE.md` inside `madprojx-os/`** provides repo-scoped context. Any `claude` session opened in that directory automatically inherits the full madprojx business context — brand voice, positioning, content templates, operational constraints — without touching your global CLAUDE.md. Your global CLAUDE.md stays focused on your cross-project SOP and environment specs.

---

### Layer 3: `madprojx-os` Git Repo + Obsidian — Knowledge Base & Single Source of Truth

**Role:** Internal documentation, knowledge management, decision logs, content drafts, brand context, and the canonical source of truth for the entire business.

**Operating Model: Hybrid Docs-as-Code**

Everything is a flat Markdown file. Brand positioning, website copy, service definitions, content drafts, SOPs, and operational context all live in a single Git-backed directory structure (`madprojx-os`). Git provides version history, branching, and traceability. Obsidian provides the reading/editing UI. Claude Code operates directly on the repo.

**Architecture:**

- **Git repo on KITT** (`~/projects/madprojx-os/`) — the canonical source. All changes are committed and tracked. Claude Code reads and writes to this directly.
- **Obsidian on Windows** (`C:\ObsidianVaults\AllTheThings\`) — the main vault, local only (no cloud sync). `madprojx-os` is cloned from GitHub into the vault's `projects/` folder. Obsidian is the UI, not the system of record. Git is the only sync engine between KITT and Windows.
- **Mobile access** — Tailscale RDP into Windows PC on the rare occasion phone access is needed. No DriveSync dependency.
- **`.claude/CLAUDE.md` inside the repo** — scoped project context. Any Claude Code session opened in `madprojx-os/` automatically inherits the full business context (brand voice, positioning, service definitions, content templates, operational constraints) without manual prompting.

**Directory Structure (PARA-inspired, flat Markdown):**

```
madprojx-os/
├── .claude/
│   └── CLAUDE.md              # Repo-scoped Claude context (brand voice, SOPs, templates)
├── README.md                  # Index — current state, active priorities, quick links
├── madprojx-site/             # Website codebase (Astro) — already exists
│   ├── .claude/
│   │   └── CLAUDE.md          # Website-specific build instructions
│   ├── src/
│   ├── public/
│   ├── astro.config.mjs
│   └── ...
├── areas/                     # Ongoing responsibilities, no end date
│   ├── brand/
│   │   ├── positioning.md     # Who we serve, what we do, why us
│   │   ├── voice-guide.md     # Tone, vocabulary, do/don't
│   │   └── visual-identity.md # Colors, fonts, logo usage
│   ├── content/
│   │   ├── strategy.md        # Platform priorities, cadence, formats
│   │   ├── calendar.md        # Rolling content calendar (Markdown table)
│   │   └── ideas-bank.md      # Running list of content ideas
│   ├── services/
│   │   ├── offerings.md       # Assessment, Sprint, Retainer definitions
│   │   └── pricing.md         # Pricing structure and rationale
│   └── operations/
│       ├── tool-stack.md      # What tools, what each does, costs
│       ├── ai-decision-matrix.md  # Which AI for which task
│       └── weekly-review.md   # Template for weekly self-review
├── resources/                 # Reference material, not action items
│   ├── competitors/           # Notes on competing consultancies
│   ├── ai-tools/              # Tool evaluations, bookmarks, notes
│   ├── templates/             # Reusable templates (proposals, posts, emails)
│   └── research/              # Industry data, market research, saved articles
└── archives/                  # Completed or inactive — moved here, never deleted
```

**Note:** `madprojx-site/` is the Astro website codebase that already exists. It lives inside `madprojx-os` as one project alongside the business docs. The root `.claude/CLAUDE.md` covers business context; the `madprojx-site/.claude/CLAUDE.md` covers website build instructions. Future projects (e.g., `linkedin-launch/`, `first-client/`) get created as sibling folders at the same level when needed.

**Why this approach:**

- **Simplicity & Clarity** — Everything is a flat Markdown file. No databases, no proprietary formats, no SaaS lock-in.
- **Solo-Founder Usability** — Operates within tools you already use (Obsidian, VS Code, Git, Claude Code) without adding new software.
- **Low Overhead** — No complex systems to manage. `git add`, `git commit`, done.
- **Long-Term Usefulness** — As madprojx scales, this repo is the single source of truth. Feed the entire folder to Claude Desktop as project context, and the AI understands your brand voice, goals, and constraints without manual prompting.
- **AI-Native by Design** — Claude Code on KITT reads/writes directly to the repo. The `.claude/CLAUDE.md` inside means every session starts fully primed. Branching lets you experiment ("what if we pivot to healthcare?") without destroying what works.
- **PARA Discipline** — The archive rule is enforced: anything not active moves to `archives/`. This prevents the directory from becoming a junk drawer over time.

---

## Your AI Tool Roles (Multi-AI Strategy)

You have four AI subscriptions. Each has a distinct strength. Using the wrong one for a task wastes time and money.

### Claude (Pro/Max — Cowork + Code)

**Best for:** Execution. Content drafting, document creation, code generation, business operations, scheduled tasks, file manipulation, multi-step workflows. Claude is your primary workhorse — it does things, not just answers things.

### Perplexity Pro ($20/mo)

**Best for:** Research with citations. Competitor analysis, market research, fact-checking, finding current pricing/statistics, industry reports. Perplexity's Deep Research mode auto-selects models and produces cited reports. Use it when you need sourced, verifiable information — not when you need to create or build something.

### Gemini 2.5 Pro ($20/mo)

**Best for:** Long-context analysis. With a 1M token context window, Gemini handles massive document review, codebase analysis, and processing large datasets. If a client hands you 200 pages of internal docs and says "tell me where AI fits," Gemini is the tool. Also strong at multimodal analysis (images, video, audio). Emerging TTS/audio capabilities could be useful for video content narration.

### SuperGrok (X Premium+)

**Best for:** Real-time X/Twitter intelligence. DeepSearch across X gives you live sentiment, trending topics, and what small business owners are actually saying about AI right now. Use it for social listening, X content research, and understanding what's resonating on the platform. The X-native data access is something no other AI has.

### Decision Matrix

|Task|Primary Tool|Why|
|---|---|---|
|Draft LinkedIn post|Claude Cowork|Execution + brand voice in context|
|Research competitor pricing|Perplexity Pro|Cited, current web sources|
|Analyze client's 100-page ops manual|Gemini 2.5 Pro|1M token context handles it|
|Find trending AI topics on X|SuperGrok|Native X data access|
|Build website page|Claude Code (KITT)|Code generation + Cloudflare deploy|
|Weekly content calendar|Claude Cowork (scheduled)|Recurring automated task|
|Draft client proposal|Claude Cowork|docx skill + brand context|
|Fact-check a blog post|Perplexity Pro|Citation-backed verification|
|Create presentation|Claude Cowork|pptx skill|
|Monitor industry news daily|Claude Cowork (scheduled)|Automated daily briefing|

---

## madprojx Positioning: Clarified

Based on your answers, here's the positioning distilled:

**Who you serve:** Small businesses that know they need AI but don't know where to start, who to trust, or how to avoid getting burned.

**What you do:** You bridge the gap between "we should use AI" and "here's exactly how, what it costs, and what it does for your business" — with a security-first mindset that protects them from the usual pitfalls.

**Why you:** 20+ years in cybersecurity (CISSP). You don't just implement AI — you implement it safely. Small businesses are terrified of data leaks, vendor lock-in, and AI hallucinating their way into liability. Your background is the differentiator.

**First 90-day service offering (keep it tight):**

1. **AI Readiness Assessment** — A fixed-price, 2-week engagement where you audit a small business's workflows, identify the top 3 AI opportunities, assess security/privacy risks, and deliver a prioritized action plan. Productized, repeatable, easy to sell.
2. **AI Implementation Sprint** — A project-based engagement where you build the top recommendation from the assessment. Could be workflow automation, a chatbot, document processing, whatever scored highest. Scoped, delivered, done.
3. **Ongoing AI Advisory** — Monthly retainer for businesses that completed an assessment or sprint. You're on call for questions, new opportunities, and keeping their AI usage secure and effective.

This gives you a natural funnel: Assessment → Sprint → Retainer. Each stage is independently valuable and leads to the next.

---

## Content Strategy: Practical Plan

**Platforms (in priority order):**

1. **LinkedIn** — Primary. This is where small business owners and decision-makers live. 2-3 posts per week. Mix of educational content ("5 things to check before giving an AI tool access to your customer data"), personal takes ("I've been in cybersecurity for 20 years — here's what scares me about how small businesses are adopting AI"), and case-study style posts (anonymized or hypothetical until you have real clients).
2. **Blog on madprojx.com** — 1 long-form article per week. SEO-targeted. "How small businesses can use AI without risking their customer data." "AI tools for [industry] in 2026: what actually works." These become LinkedIn content source material and establish domain authority.
3. **X (Twitter)** — Shorter, punchier takes. Repurpose LinkedIn content. Use SuperGrok to find conversations about small business + AI and engage authentically.
4. **Instagram** — Visual tips, infographics, short reels about AI security basics. Lower priority but good for credibility.
5. **YouTube** — Animated explainer videos. "What is AI doing with your business data?" "3 AI tools every small business should know about." Keep them under 5 minutes. This is a longer-term play — start after LinkedIn and blog are running.

**Scheduled Task Opportunity:** Set up a weekly Claude Cowork task that generates a content brief for the upcoming week: 3 LinkedIn posts, 1 blog article outline, and 2-3 X posts, based on trending topics from your industry and recent news. You review, edit, and post.

---

## Implementation Roadmap

### Phase 1: Foundation (Week 1-2)

**Expand `madprojx-os` Repo (KITT) — repo and `madprojx-site` already exist:**

- SSH into KITT, `cd ~/projects/madprojx-os/`
- Create the business doc structure alongside the existing `madprojx-site/`:

bash

```bash
  mkdir -p areas/{brand,content,services,operations} resources/{competitors,ai-tools,templates,research} archives .claude
```

- Create `README.md` as the repo index (current state, active priorities, quick links to key docs)
- Create `.claude/CLAUDE.md` at the repo root — include brand voice, positioning summary, content templates, multi-AI decision matrix, and operational constraints. This is the file that makes every Claude Code session in this directory business-aware from the first prompt. (The existing `.claude/CLAUDE.md` inside `madprojx-site/` stays focused on website build instructions.)
- Commit and push to a private GitHub repo (or Gitea if you're self-hosting on KITT)

**Write Foundational Docs (in the repo):**

- `areas/brand/positioning.md` — Use the positioning section from this plan as the starting draft
- `areas/services/offerings.md` — Assessment, Sprint, Retainer definitions with scope and pricing
- `areas/content/strategy.md` — Platform priorities, cadence, and format preferences
- `areas/content/ideas-bank.md` — Running list, even if it starts with 5 ideas
- `areas/operations/ai-decision-matrix.md` — Which AI tool for which task (from the matrix in this doc)

**Connect Obsidian (Windows 11):**

- Obsidian vault is at `C:\ObsidianVaults\AllTheThings\` (local, no cloud sync)
- Push `madprojx-os` to a private GitHub repo from KITT
- Clone into the vault's `projects/madprojx-os/` folder on Windows
- Git is the only sync engine — push from KITT, pull on Windows (and vice versa)
- Mobile access via Tailscale RDP into Windows if ever needed

**Cowork Scheduled Tasks (Windows 11):**

- Set up a daily industry news digest (pulls from web, summarizes AI news relevant to small businesses)
- Set up a weekly content brief generator

### Phase 2: Presence (Week 3-4)

**Website (madprojx.com):**

- Use Claude Code on KITT to build out the site from `~/projects/madprojx-os/madprojx-site/` (Astro project already exists)
- Deploy via Cloudflare Pages (you already have the domain and hosting)
- Pages needed: Home (positioning + CTA), Services (the 3 offerings), About (your background), Blog (start empty, populate in Phase 3), Contact
- Content for each page is sourced directly from your `areas/` docs (positioning.md → Home, offerings.md → Services)

**Social Accounts:**

- Set up or claim LinkedIn company page, X account, Instagram account for madprojx
- Write bios using your positioning doc
- First 5 LinkedIn posts drafted in Claude Cowork

### Phase 3: Content Engine (Week 5+)

- Start publishing: 2-3 LinkedIn posts/week, 1 blog article/week
- Use the scheduled content brief task to stay consistent
- Repurpose blog content to X and Instagram
- Begin engaging on X using SuperGrok-identified conversations
- Track what resonates, double down on it

### Phase 4: Development (When Needed)

- Install GSD on KITT when you have a specific software project (client tool, internal automation, etc.)
- Use Claude Code for all development work
- This phase starts when a client engagement or internal need demands it — not before

---

## Updated Risk Review

All five risks from V1 still apply. Two additional risks based on your answers:

### Risk 6: Spreading Across Too Many Platforms Too Fast

You listed LinkedIn, blog, X, Instagram, and YouTube. That's five channels. For a solo founder, starting all five simultaneously is a recipe for inconsistency. Start with LinkedIn + blog. Add X in week 3-4. Instagram and YouTube are Phase 3+ at the earliest. Consistency on two platforms beats sporadic presence on five.

### Risk 7: Tool Subscription Creep

You're currently paying for Claude (Pro or Max), Gemini Pro, Perplexity Pro, and SuperGrok (X Premium+). That's $60-$240+/month in AI subscriptions alone depending on tiers. Each tool should justify its cost monthly. If you're not using Gemini's long-context capability or SuperGrok's X intelligence regularly, they're overhead. Audit quarterly.