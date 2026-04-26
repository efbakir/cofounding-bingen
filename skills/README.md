# Skills

Five skills, each one operational layer for a step in the agent chain. Skills differ from agents: agents decide, skills execute.

| Skill | Slash | Invoking agent | What it does |
|---|---|---|---|
| `problem-discover` | `/problem-discover` | problem-hunter | Takes a hypothesis, generates search queries, runs them across Reddit/HN/IH/X |
| `community-map` | `/community-map` | community-mapper | Builds a sub/Discord/influencer map for a validated hypothesis |
| `pain-score` | `/pain-score` | pain-validator | Scores a finding on intensity × frequency × WTP |
| `build-in-public-post` | `/build-in-public-post` | build-in-public-writer | Drafts a platform-specific post |
| `tester-funnel` | `/tester-funnel` | (manual) | Tracks interested testers across funnel stages |

## Community skill integration

These skills call community-built skills via "use if installed" pattern:

| Skill | Repo | Used by |
|---|---|---|
| `redditlens` | [0xMassi/redditlens](https://github.com/0xMassi/redditlens) | `problem-discover` (preferred for Reddit) |
| `reddit-skill` | [brisyramshere/reddit-skill](https://github.com/brisyramshere/reddit-skill) | `problem-discover` (fallback) |
| `mine-calls` | [maxionmain321/claude-code-skills](https://github.com/maxionmain321/claude-code-skills) | `pain-score` (cluster schema reference) |
| `persona-builder` | Anthropic | `community-map` (persona extraction) |
| `competitor-analysis` | Anthropic | `pain-score` ("already solved?" check) |

If they're not installed, the skills fall back to no-auth sources (Reddit JSON endpoint, HN Algolia API).

## Setup

```bash
cp -r skills/* .claude/skills/      # project-only
# or
cp -r skills/* ~/.claude/skills/    # global
```

## API keys

Put these in a `.env` file (gitignored):

```
SERPER_API_KEY=...      # for redditlens (optional)
REDDIT_CLIENT_ID=...    # for reddit-skill (optional)
REDDIT_CLIENT_SECRET=...
XQUIK_API_KEY=...       # for x-twitter-scraper (optional)
```

Without any of these, the skills run with HN Algolia + Reddit public JSON only — still useful, just narrower coverage.
