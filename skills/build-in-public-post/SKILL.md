---
name: build-in-public-post
description: Draft platform-specific build-in-public posts (Reddit, IndieHackers, X, LinkedIn) for a validated hypothesis with a community map. Each draft uses verbatim pain quotes from validated findings, sounds like a human builder not marketing copy, and asks for ONE thing per post. Used by build-in-public-writer agent and callable directly via /build-in-public-post H{N} <platform>.
---

# build-in-public-post

## Trigger
- User runs `/build-in-public-post H{N} reddit` (or `indiehackers`, `x`, `linkedin`)
- build-in-public-writer agent invokes this skill
- After community-map skill has produced the distribution playbook

## Inputs
- Hypothesis ID (H{N}) — required
- Platform — required (one of: `reddit`, `indiehackers`, `x`, `linkedin`)
- Optional: `--ask` flag to override the default ask (default = recruit testers)

## Process

### 1. Read context
- `notes/hypotheses.md` — H{N} block
- `notes/discoveries/H{N}-*.md` — findings, validation verdict, community map
- `notes/testers.md` (if exists) — current funnel

### 2. Pick the strongest pain quote
From the validated findings, pick 1-2 quotes that:
- Are verbatim and contain the validated pain language
- Have a public username (better social proof) — anonymize if needed
- Are recent (last 6 months preferred)

### 3. Write platform-specific draft

#### Reddit
- 150-300 words
- Opening: question or observation, not announcement
- Hook patterns:
  - "I've been seeing X come up a lot — am I crazy or is this widespread?"
  - "Curious if anyone here has dealt with {problem}. Been digging for 2 weeks and..."
- Include 1 verbatim quote (with credit if user is public): "Saw this from u/X recently: '...'"
- Reveal what you're building in 1 sentence — mid-post, not the headline
- ONE ask at the end (testers / 15-min call / "your worst story")
- Tone: deferential, asking-not-telling, builder-among-builders

#### IndieHackers
- 300-500 words
- Opening: vulnerability hook
  - "We almost built the wrong thing. Here's what we learned in 2 weeks of validation."
  - "Sharing what we found before we write a line of code."
- Structure:
  - The hypothesis (1 paragraph)
  - What we did to validate (3-5 bullets)
  - What we found (2-3 verbatim quotes from findings)
  - What we're building (1 paragraph, concrete)
  - The ask (1 paragraph — tester signup or DM)
- Include co-founder names: "Bingen and I are..."

#### X / Twitter (thread)
- 4-7 tweets, 280 chars each
- Tweet 1: punchy claim or finding ("Most {persona} have this problem and don't realize it.")
- Tweet 2-3: verbatim quote(s) from findings, attributed
- Tweet 4-5: what we're building, in plain English
- Tweet 6-7: the ask + link
- One thought per tweet. No threading-cliché overuse.

#### LinkedIn
- 200-400 words
- Story arc: setup → tension → reveal → ask
- Tone: professional but human. No emoji-stacking. No corporate-speak.
- Hook patterns:
  - "Spent 2 weeks talking to {persona} before writing a single line of code. Here's what changed our mind."
  - "{N} pain points. {N} subreddits. One pattern."
- Mention you're building openly + co-founder context
- ONE ask, often "comment if this is your problem too" since LinkedIn rewards engagement

### 4. Write to file
`notes/posts/H{N}-{platform}-{YYYY-MM-DD}.md`:

```markdown
# {Platform} draft — H{N}

**Status**: draft
**Target community**: r/{sub} or #{tag} or self-feed
**Posting date target**: YYYY-MM-DD
**CTA**: comment / DM / signup-link / 15-min call
**Sub rules**: {self-promo policy, day restrictions, etc. — from community map}

---

{The post, ready to copy-paste}

---

## Quote sources used
- F{n}: u/{name} — [thread]({url})

## Post-launch plan
- Respond to every comment in first 6h
- Tester capture: anyone who says "I want to try" → notes/testers.md within 1h
- Cross-post check: any other communities where this would be welcome?
```

### 5. (Optional) Read 3 reference posts
Before finalizing, if posting to Reddit/IH, `WebFetch` 3 top recent posts in the target sub and check tone/length match. Adjust if mismatch.

## Output to caller
- Draft file path
- Strongest 1-line hook from the post
- Suggested posting time (with time zone) based on sub/platform norms

## Rules

### Banned words (rewrite if found)
revolutionize, disrupt, next-generation, AI-powered (unless literally the topic), synergy, leverage, cutting-edge, game-changer, paradigm shift, world-class, best-in-class, innovative, seamless, frictionless

### Required ingredients
- ONE verbatim pain quote with attribution
- ONE concrete sentence describing what we're building
- ONE specific ask (not three)
- Both names (Efe + Bingen) when contextually right — we co-found

### Tone calibration
- Sound like a builder talking to other builders
- No vague benefits ("save time", "boost productivity") — replace with the specific outcome from the discovery quote
- Acknowledge uncertainty: "we think", "early hunch", "still validating"
- If sub explicitly bans self-promo: write a non-promotional findings-share variant + plan the promo-allowed version for week 3
