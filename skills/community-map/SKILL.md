---
name: community-map
description: For a validated hypothesis (pain-validator returned GO), produce a concrete map of where the audience lives — exact subreddits with member counts, Discord servers with invite links, top-N influencers with handles + follower counts, newsletters, podcasts, and a 4-week posting calendar. Output is the distribution playbook used by build-in-public-writer.
---

# community-map

## Trigger
- User runs `/community-map H{N}` after pain-validator returns GO
- community-mapper agent invokes this skill
- Manual: "map the community for hypothesis 3"

## Inputs
- Hypothesis ID (H{N}) — required
- Validated discovery file `notes/discoveries/H{N}-*.md` must exist with verdict GO

## Process

### 1. Read the discovery file
Extract from validated findings:
- Every subreddit name where findings came from (count occurrences)
- Top 5 usernames by pain intensity
- Every tool/product mentioned (these have their own communities)
- Every company/person referenced (potential influencers)

### 2. Subreddit ranking
For each candidate sub:
- `WebFetch` on `https://www.reddit.com/r/{sub}/about.json` to get member count
- Note daily activity (look at /new for last 24h post count)
- Drop subs with <500 members or last post >3 months old

Output table sorted by relevance × size.

### 3. Discord / Slack hunt
For each tool/product mentioned:
- Search the tool's docs/website for "discord" / "community" / "slack"
- `WebFetch` on `https://www.google.com/search?q="{tool}"+discord+invite` for unofficial communities
- Note invite link only if it returns valid (don't fabricate)

### 4. Top user profiles
For each top-5 painful user:
- `WebFetch` `https://www.reddit.com/user/{username}.json` (last 25 posts)
- Extract OTHER subs they're active in — those subs are also candidate communities
- Note if their post history shows they're a builder, a buyer, or a complainer (different DM strategy each)

### 5. Influencer / account hunt
For each company/person referenced:
- Find their X/LinkedIn handle (WebFetch their website / Wikipedia)
- Note follower count band: <5k / 5-50k / 50k+
- Recent post relevance: did they post about this problem space in last 30 days?

If `persona-builder` skill is installed, optionally pass top-5 user data to it for richer persona output.

### 6. Newsletter / podcast hunt
- 1-2 targeted searches: "newsletter for {space}" on IH/HN/Substack
- "podcast about {space}" similarly
- Note reach if known, skip if unknown — don't fabricate

### 7. Posting calendar (4 weeks)

Generate concrete week-by-week plan:
- W1 — soft entry post in top sub ("seeing this problem, your stories?")
- W2 — IndieHackers post with first prototype/wireframe
- W3 — DM top 3 painful users (with prototype access offer)
- W4 — pitch newsletter / podcast / influencer

### 8. Write to discovery file

Append a section:

```markdown
---

## Community Map — {YYYY-MM-DD}

### Subreddits (top 5, by relevance × size)
| Sub | Members | Activity | Source findings |
|---|---|---|---|
| r/X | 12k | 5/day | F1, F3, F7 |
...

### Discord / Slack
| Server | Invite | Members | How found |
|---|---|---|---|
...

### Top users to engage (5 max)
| Username | Platform | Strongest finding | Tactic |
|---|---|---|---|
| u/X | Reddit | F2 — "...quote..." | DM after prototype, NOT before |

### Influencers
| Handle | Platform | Followers | Recent relevance |
|---|---|---|---|

### Newsletters / podcasts
| Name | URL | Reach | Why relevant |

### Posting calendar
- **Week 1**: ...
- **Week 2**: ...
- **Week 3**: ...
- **Week 4**: ...

### Subreddit rules / tone notes
- r/X — no self-promo days, weekly Show & Tell on Fridays only
- r/Y — DMs explicitly welcome, OP-friendly
```

## Output to caller
1-paragraph summary:
- Top 3 subs with member counts
- Top community to join (Discord if found)
- Top user to engage and when
- Recommended first-move next 7 days

## Rules
- **No fabricated metrics.** Member count, follower count, reach — verify or say "unknown".
- **Cite which findings led to which sub.** "r/X is in the map because F1, F3, F7 all came from it."
- **Respect community rules.** Always note self-promo policy. Default to "no self-promo allowed" unless verified otherwise.
- **No spam playbook.** We engage as humans. DM only after we have something to show, never cold for "feedback".
