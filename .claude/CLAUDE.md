madprojx — Business Context for Claude Code
You are working inside the madprojx-os repository — the single source of truth for madprojx, a one-person AI consulting brand.
What madprojx Is
AI consulting for small businesses — implemented securely, explained clearly. Founded by Kevin, 20+ years in cybersecurity (CISSP). We help small businesses understand, adopt, and secure AI in their operations.
Who We Serve
Small businesses (5-100 employees) that know they need AI but don't know where to start. Service businesses, retail, local firms, trades. Not tech companies.
Brand Voice

Direct, practical, security-aware. No hype. No jargon.
Lead with the business outcome, not the technology.
Use "implement" not "deploy." Use "protect" not "harden." Use "evaluate" not "audit."
Say what AI does in plain terms: "reads your invoices and flags errors" not "leverages NLP for document intelligence."
Never use "revolutionary," "game-changing," or "cutting-edge."
Never promise ROI you can't prove.
Never assume the reader knows what an LLM, API, or prompt is.

Service Offerings

AI Readiness Assessment — Fixed-price, 2-week engagement. Audit workflows, identify top 3 AI opportunities, assess security risks, deliver prioritized action plan.
AI Implementation Sprint — Project-based, 2-6 weeks. Build the top recommendation. Tool selection, configuration, security review, staff training.
Ongoing AI Advisory — Monthly retainer. Check-ins, priority support, quarterly security review.

Full details: areas/services/offerings.md
Differentiators

Security-first — every recommendation includes a risk assessment
Plain language — we explain AI in terms business owners understand
Vendor-neutral — we recommend the right tool, not the one that pays us
Solo practitioner — clients work directly with Kevin
Small business focus — recommendations fit real budget and staffing constraints

Content Pillars
All content maps to one of four themes:

AI Security for Small Business — data privacy, vendor risk, shadow AI, access controls
AI Made Simple — demystifying AI for non-technical business owners
Practical AI Use Cases — specific, real examples of AI helping small businesses
AI Mistakes to Avoid — what goes wrong without guidance

Repo Structure
madprojx-os/
├── .claude/CLAUDE.md          ← you are here
├── README.md
├── brief.md                   # Project brief — scope and definition of done
├── madprojx-site/             # Astro website codebase (has its own .claude/CLAUDE.md)
├── areas/
│   ├── brand/positioning.md   # Full positioning doc
│   ├── content/strategy.md    # Content strategy and weekly workflow
│   ├── content/ideas-bank.md  # Content idea backlog
│   ├── services/offerings.md  # Service definitions and pricing
│   └── operations/ai-decision-matrix.md  # Which AI tool for which task
├── resources/                 # Reference material (competitors, tools, templates, research)
└── archives/                  # Completed or inactive items
Key Rules

Read areas/brand/positioning.md before writing any client-facing or public content.
Read areas/content/strategy.md before creating content for any platform.
All content must connect to a business outcome, not just a technology feature.
Security angle should appear in at least 1 of every 3 pieces of content.
Never publish AI-generated content without human review. Claude drafts, Kevin publishes.
When suggesting tools or approaches, check areas/operations/ai-decision-matrix.md for which AI tool to recommend for which task.

Environment

Windows 11 PC — Claude Desktop (Cowork). i9-14900K, 32GB DDR5, 4060 Ti 8GB. Primary for business ops, content creation, scheduled tasks.
KITT (Ubuntu 24.04 LTS) — Claude Code. Ryzen 9 5950X, 64GB DDR4. Primary for development, builds, 24/7 automation.
Cloudflare — Hosts madprojx.com. Pages, Workers, KV, R2, D1 available.
Obsidian — Opens this repo as a vault on Windows. DriveSync for mobile access.

What NOT to Do

Don't create files outside the repo structure without asking.
Don't modify madprojx-site/ when working on business docs (and vice versa).
Don't use enterprise jargon in any content meant for small business audiences.
Don't recommend tools or vendors without noting security/privacy considerations.