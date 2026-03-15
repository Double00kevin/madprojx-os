# madprojx — Daily Workflow Guide

Quick reference for how to work on madprojx. Keep it simple.

---

## The One Rule

**Pull before you edit. Push after you commit.** That keeps KITT and Windows in sync. Everything else flows from this.

---

## Starting Your Day

1. Open Claude Desktop on Windows
2. Check the Scheduled section in the sidebar — your daily news digest is there (weekday mornings at 7:10am)
3. On Mondays, the weekly content brief is also there (8:01am)
4. Review both, note anything worth acting on
5. Open Obsidian — pull latest changes first:

```powershell
cd C:\ObsidianVaults\AllTheThings\projects\madprojx-os
git pull
```

---

## Editing Business Docs (Obsidian on Windows)

**When:** Updating positioning, services, content strategy, adding ideas, editing drafts.

1. `git pull` in PowerShell (always first)
2. Edit in Obsidian — navigate to `areas/` and open whatever you need
3. When done:

```powershell
cd C:\ObsidianVaults\AllTheThings\projects\madprojx-os
git add -A
git commit -m "short description of what changed"
git push
```

---

## Creating Content (Cowork on Windows)

**When:** Drafting LinkedIn posts, blog articles, proposals, presentations.

1. Open a new conversation in Claude Desktop
2. Tell Claude what you want to draft — reference your docs if needed:
   - "Draft a LinkedIn post based on my positioning in areas/brand/positioning.md"
   - "Write a blog article outline using my content strategy"
3. Claude drafts, you edit
4. Save final version to the appropriate folder in Obsidian
5. Commit and push

---

## Building the Website (Claude Code on KITT)

**When:** Writing code, building pages, deploying to Cloudflare.

1. SSH into KITT via VS Code
2. Pull latest:

```bash
cd ~/projects/madprojx-os
git pull
```

3. For website work — run Claude Code from the site directory:

```bash
cd ~/projects/madprojx-os/madprojx-site
claude
```

This loads the website-specific `.claude/CLAUDE.md`.

4. For website work that needs brand context (writing copy, etc.) — run Claude Code from the parent:

```bash
cd ~/projects/madprojx-os
claude
```

This loads the business-scoped `.claude/CLAUDE.md`.

5. After changes:

```bash
cd ~/projects/madprojx-os
git add -A
git commit -m "short description of what changed"
git push
```

6. On Windows, `git pull` next time you open Obsidian.

---

## Adding a New Content Idea

**When:** You think of something worth writing about.

1. Open Obsidian
2. Navigate to `areas/content/ideas-bank.md`
3. Add a line: `- [ ] Idea title — (Pillar) — brief note`
4. Commit and push when convenient (batch these — don't push every single idea)

---

## Weekly Routine

| Day | Activity |
|-----|----------|
| Monday | Review weekly content brief. Pick topics for the week. |
| Tues-Wed | Draft LinkedIn posts and blog article in Cowork. |
| Thursday | Edit, finalize, schedule posts. Publish blog article. |
| Friday | Engage on LinkedIn and X. Respond to comments. Find new conversations via SuperGrok. |

---

## When Something Goes Wrong

**Git conflict (both KITT and Windows edited the same file):**

```bash
git pull
# If conflict appears:
# Open the conflicted file, pick the version you want, save
git add -A
git commit -m "resolved merge conflict"
git push
```

**Forgot to pull before editing:**

```bash
git stash
git pull
git stash pop
# Resolve any conflicts, then commit and push
```

**Scheduled task didn't run:**
- Was your Windows PC asleep or Claude Desktop closed? Tasks only run when both are active.
- Check the Scheduled section in Claude Desktop sidebar for status.

---

## File Locations Cheat Sheet

| What | Where |
|------|-------|
| Brand positioning | `areas/brand/positioning.md` |
| Service offerings | `areas/services/offerings.md` |
| Content strategy | `areas/content/strategy.md` |
| Content ideas | `areas/content/ideas-bank.md` |
| AI tool decision matrix | `areas/operations/ai-decision-matrix.md` |
| Project brief | `brief.md` |
| Claude business context | `.claude/CLAUDE.md` |
| Website code | `madprojx-site/` |
| Repo index | `README.md` |
| Full operating plan | V2.1 doc (saved separately) |