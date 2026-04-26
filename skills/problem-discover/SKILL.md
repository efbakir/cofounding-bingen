---
name: problem-discover
description: Given a hypothesis from notes/hypotheses.md (by H{N} ID), generate targeted search queries and run them across Reddit, Hacker News, IndieHackers, and (if scraper installed) Twitter/X. Returns verbatim findings with source URLs to notes/discoveries/H{N}-*.md. Used by the problem-hunter agent but also callable directly via /problem-discover H{N}.
---

# problem-discover

## Trigger
- User runs `/problem-discover H3` (or another hypothesis ID)
- problem-hunter agent invokes this skill mid-chain
- Anyone says "let's hunt for evidence on hypothesis X"

## Inputs
- Hypothesis ID (H{N}) — required
- Optional: extra keywords to add to the search set
- Optional: source restriction (e.g., "reddit only", "no twitter")

## Process

### 1. Read the hypothesis
Open `notes/hypotheses.md`, find the H{N} block. Extract:
- problem statement
- persona
- WTP signal target
- starting communities (`Where to hunt`)

### 2. Build query set (8-12 queries)

For each problem, generate queries in 4 categories:

**A. Direct pain**
- `"{problem} sucks"` / `"hate {tool}"` / `"{problem} is broken"`
- `"frustrated with {tool/workflow}"`
- `"why is {workflow} so {hard|slow|expensive}"`

**B. Workaround leakage**
- `"how do you guys {do problem}"` / `"any tool for {problem}"`
- `"alternatives to {dominant_tool}"` (use the tool the persona currently uses)
- `"is there a {category} that {specific feature}"`

**C. WTP leakage**
- `"would pay for {something that solves problem}"`
- `"too expensive" "{tool}"` (price complaints about existing solutions)
- `"willing to pay" + {keywords}`

**D. Negative experience**
- `"wasted hours on {problem}"`
- `"{tool} ruined my {workflow}"`
- `"tried {tool} and it doesn't even {expected feature}"`

### 3. Run queries across sources

Priority order — STOP early if you hit 15+ findings:

**Reddit** (highest signal-to-noise for B2B/SMB/indie problems)
- If `redditlens` skill is installed → invoke it with the query set
- Else: `WebFetch` on `https://www.reddit.com/search.json?q={query}&sort=new&type=link` (no auth needed for read)
- For specific subs from the hypothesis: `https://www.reddit.com/r/{sub}/search.json?q={query}&restrict_sr=1`

**Hacker News** (high signal for dev tools / tech audiences)
- Algolia API, no auth: `https://hn.algolia.com/api/v1/search?query={q}&tags=(story,comment)`
- Comments often have richer pain language than stories — search both

**IndieHackers** (high signal for SaaS/maker problems)
- No public API. `WebFetch` on `https://www.indiehackers.com/search?q={query}` then drill into top 3 results
- Posts in /forum/main are most likely to contain pain language

**Twitter/X** (high signal but only if scraper installed)
- If `x-twitter-scraper` or `xquik-dev/x-twitter-scraper` skill is installed → use it
- Else: skip and note "X skipped — no scraper installed"

**App Store / G2 / Capterra** (only if competitor product is named in hypothesis)
- WebFetch the 1-3 star reviews specifically — that's where pain lives

### 4. Filter findings

Drop a finding if:
- Quote is < 1 sentence (not enough signal)
- Post is > 18 months old (unless frequency search is the goal)
- It's a self-promo post (someone announcing their tool, not complaining)
- Username is clearly a bot (suspicious karma/post pattern)

Keep at most 20 findings. Quality > quantity.

### 5. Write to discovery file

Append-only write to `notes/discoveries/H{N}-{date}.md`:

```markdown
# Discovery — H{N}: {hypothesis short name}
**Date**: YYYY-MM-DD
**Skill**: problem-discover
**Sources searched**: Reddit, HN, IH ({skipped: ...})
**Queries run**: {count} — full list at bottom

## Findings ({N})

### F1 — {one-line pain summary}
- **Source**: [{thread title}]({url})
- **Date**: YYYY-MM-DD
- **User**: u/{name} (or anonymous)
- **Quote**:
  > {verbatim, can be multi-line}
- **Context**: {what was the thread about, sub/forum, what tool was discussed}

...

---

## Queries used
1. ...
2. ...

## Sources skipped
- X — no scraper installed
```

## Output to caller
1-paragraph summary:
- N findings written to `notes/discoveries/H{N}-YYYY-MM-DD.md`
- Top 3 strongest verbatim quotes (with URLs)
- Recommended next: `/pain-score H{N}` or "ready for pain-validator agent"

## Rules
- **Never paraphrase quotes**. If you can't get the verbatim text, drop the finding.
- **Always include URL**. No URL = no finding.
- **Mark skipped sources explicitly** so the caller knows what coverage gaps exist.
- **No fabrication**. If 0-2 findings, return "weak signal — recommend killing H{N}" rather than padding.
- Respect rate limits. If a source returns 429 or stops responding, note it and move on.
