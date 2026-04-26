# cofounding-bingen

Startup ideation lab for Bingen + Efe. Hypothesis → real "ready-to-pay" complaint signals from Reddit/HN/X/IndieHackers → build in public → tester funnel.

Structure follows [selmakcby/claude-agents-skills](https://github.com/selmakcby/claude-agents-skills); agents and skills are written specifically for this repo.

---

## Core thesis

> A paying customer = someone who complains with high frequency × high intensity × clear willingness to pay, is already trying something to fix it, and the ticket size is meaningful.

The repo operationalizes this thesis:

1. **Discover** — give a problem hypothesis, agents find people complaining about it on Reddit/HN/X/IH.
2. **Map** — where do these people hang out? Which subreddits, Discords, influencers do they follow?
3. **Score** — rank findings by pain intensity × frequency × WTP signal.
4. **Build in public** — turn findings into Reddit/IH/X posts in the format "we're building a thing that solves X, want to test it?"
5. **Funnel** — track everyone who shows interest in `notes/testers.md`.

---

## Folders

| Folder | Contents |
|---|---|
| `agents/` | 5 subagent definitions — copy into `~/.claude/agents/` or `.claude/agents/` |
| `skills/` | 5 skill definitions — copy into `~/.claude/skills/` or `.claude/skills/` |
| `books/` | Startup-shaping books (PDF, EPUB, markdown notes) |
| `ideas/` | Pre-existing opportunity briefs and seed thinking |
| `notes/` | Active ideation: hypotheses, validation logs, tester funnel |
| `CLAUDE.md` | Repo-level rules (the context Claude uses while working with Bingen) |

---

## Setup

### 1. Clone
```bash
git clone git@github.com:efbakir/cofounding-bingen.git
cd cofounding-bingen
```

### 2. Install agents + skills at the project level
So they auto-load when Claude Code is opened inside this repo:
```bash
mkdir -p .claude/agents .claude/skills
cp agents/*.md .claude/agents/
cp -r skills/* .claude/skills/
```

Or globally (available across every project):
```bash
cp agents/*.md ~/.claude/agents/
cp -r skills/* ~/.claude/skills/
```

### 3. (Optional) Community skills
The skills below pair directly with our flow; if installed, our agents will prefer them automatically:

| Skill | Repo | What it does |
|---|---|---|
| `redditlens` | [0xMassi/redditlens](https://github.com/0xMassi/redditlens) | Reddit pain-point clustering. **Drop-in.** Requires a Serper API key. |
| `reddit-skill` | [brisyramshere/reddit-skill](https://github.com/brisyramshere/reddit-skill) | Official Reddit OAuth — search, comment-tree extraction. Free. |
| `mine-calls` | [maxionmain321/claude-code-skills](https://github.com/maxionmain321/claude-code-skills/tree/main/skills/mine-calls) | Pain → exact quote → channel-angle mapping schema |
| `persona-builder` | Anthropic skills (already in env) | Voice-of-customer → segment |
| `competitor-analysis` | Anthropic skills (already in env) | "Has this already been solved?" check |

---

## Typical flow

When working through a new hypothesis:

```
1. Add the hypothesis to notes/hypotheses.md (use the template at the top of that file)
2. In Claude Code: "invoke the problem-hunter agent on H{N}"
   → agent searches Reddit/HN/X, writes raw findings to notes/discoveries/H{N}-*.md
3. "have pain-validator score the findings"
   → each finding gets an intensity × frequency × WTP score
4. "have community-mapper map where these people live"
5. "have build-in-public-writer draft posts for IH and Reddit from these findings"
6. Publish a post → log everyone who shows interest in notes/testers.md
```

In an ideation session you only invoke **idea-explorer** first; it narrows raw ideas down to 3-4 sharp hypotheses, then the chain runs.

---

## Cofounding with Bingen

This repo is public and part of a build-in-public strategy. While Bingen and Efe work together:

- Open a PR for each hypothesis; review the validation log together
- `notes/decisions.md` captures every decision made jointly
- Conflict → write the position to `notes/conflicts.md`, wait 24 hours, then talk

---

## License

MIT
