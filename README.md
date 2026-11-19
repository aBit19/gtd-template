# GTD with Claude Code

A template for running David Allen's *Getting Things Done* as plain Markdown files, with [Claude Code](https://claude.com/claude-code) as your GTD assistant. Claude captures, clarifies, organizes, and guides your reviews through slash commands. You stay in control: every decision is yours, and everything is readable text you can edit by hand.

## Create your own instance

This repository is the **template** (system only, no personal data). Make one private copy per life domain, for example one for personal life and one for work.

**On GitHub:** click **Use this template** → create a **private** repository → clone it.

**Without GitHub's template feature:**
```bash
git clone <template-url> gtd-personal
cd gtd-personal
git remote rename origin upstream   # keep the template as upstream for updates
git remote add origin <your-private-repo-url>
git push -u origin main
```

Then open the folder in Claude Code and run `/mindsweep` to fill your inbox, followed by `/process`.

### Getting template updates

Improvements to the system live in `.claude/commands/`, `CLAUDE.md`, and this README. To pull them into an instance:
```bash
git remote add upstream <template-url>   # once, if not already set
git pull upstream main
```
Data files in the template stay as empty skeletons, so updates should not conflict with your data. If they do, keep your version of the data file.

## Daily and weekly rhythm

| When | What |
|------|------|
| Anytime | `/capture <thought>` — get it out of your head in seconds. |
| Daily | `/process` — empty the inbox. `/next` — choose what to do. `/done` — check things off. |
| Weekly | `/weekly-review` — get clear, get current, get creative. |
| As needed | `/mindsweep`, `/project`, `/waiting`, `/context`. |

## Commands

| Command | What it does |
|---------|-------------|
| `/capture <text>` | Appends to the inbox instantly, with no questions asked. |
| `/mindsweep [personal\|work\|all]` | Walks the GTD trigger list one category at a time to empty your head. |
| `/process [batch]` | Clarifies each inbox item with the GTD decision tree and files it. |
| `/next [@context] [30m] [low\|med\|high]` | Suggests the best 3–5 actions for your situation. |
| `/done <keywords>` | Completes an action, logs it, and asks for the project's next action. |
| `/project [name]` | Creates a project, or lists projects and flags stalled ones. |
| `/waiting [what — from whom]` | Adds a waiting-for item, or reviews overdue ones. |
| `/context [list\|add\|rename\|remove]` | Manages your contexts. |
| `/weekly-review` | Guided weekly review; writes notes to `reviews/`. |

## Files

| Path | Purpose |
|------|---------|
| `inbox.md` | Unprocessed captures. |
| `next-actions.md` | Next actions grouped by context. |
| `projects/` | One file per project; `projects/archive/` for finished ones. |
| `waiting-for.md` | Delegated items and things you expect from others. |
| `calendar.md` | Day- or time-specific items and ticklers. |
| `someday-maybe.md` | Ideas you are not committing to yet. |
| `contexts.md` | Your contexts. Add your own any time with `/context add`. |
| `horizons.md` | Purpose, vision, goals, and areas of focus. |
| `reference/` | Non-actionable information worth keeping. |
| `completed.md` | Log of what you finished. |
| `reviews/` | Weekly review notes. |
| `CLAUDE.md` | The rules and formats Claude follows. Edit it to change how the system behaves. |

## Line format at a glance

```
- [ ] Call Dr. Rossi's office to book a cleaning @phone +dental-checkup ~5m !low (added 2026-11-19)
```
`@context` where you can do it · `+project` which project it moves forward · `~time` estimate · `!energy` low, med, or high.
