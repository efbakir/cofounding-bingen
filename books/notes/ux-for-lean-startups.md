# UX for Lean Startups — Laura Klein

**Read**: in progress
**Pillar**: discovery + research method
**File**: `books/UX for Lean Startups by Laura Klein.pdf`

## TL;DR

Klein operationalizes Lean Startup methodology through a UX/research lens. She emphasizes two big traps: (1) not talking to real users before building, (2) when you do talk to them, asking the wrong questions and falling into the "compliment fishing" trap. **Behavioral signal is always more valuable than stated signal.** Concierge MVP, Wizard of Oz, listening tour — low-effort, high-learning techniques.

For cofounding-bingen: this book is the source of the philosophy behind `problem-hunter` and `pain-validator`. The "verbatim quote required, paraphrase forbidden" rule comes straight from Klein. The behavioral > stated preference discipline is the foundation of `pain-validator`'s WTP scoring.

## Core frameworks (for agents)

### 1. Listening tour (qualitative interviews before building)
Before the hypothesis is born: open-ended interviews with 8-12 target persona members. Don't ask "do you have this problem?" — ask "tell me how you did this workflow last week." Specific, past-tense, behavioral.

In cofounding-bingen, the listening tour = **reading verbatim pain posts on Reddit/HN**. Our "interviews" are asynchronous + scaled — the user has already written it in their own words; we find them and pull quotes. That's the primary job of the `problem-hunter` agent.

### 2. The 5 (or 8 or 12) rule
Klein's user-count practice: 5 users will catch the major usability issues. 8-12 will catch desire/motivation patterns. More than that = diminishing returns.

In cofounding-bingen: `pain-validator`'s frequency axis requires "monthly across multiple users" — the operational form of Klein's 8-12 rule. Don't extract a pattern from a single user; don't be sure with 3+ users — be sure with 8+.

### 3. Behavioral > stated preference
"Would you use this?" doesn't work because people give socially acceptable answers. Instead:
- "When you had this problem last week, what did you do?"
- "How much do you currently spend per month on this problem?"
- "Which tools have you tried for this in the last 6 months?"

All these questions look at **past behavior**.

In cofounding-bingen:
- The WTP axis in `pain-score`: 0 = no money signal at all; 3 = currently paying + complaining. Looks at **behavior**, not words.
- This is a direct ripple from the book.

### 4. Concierge MVP
Before building the product: **manually do the same job**, for a few customers, with your own hands. Customer fills out a form, you solve it by hand. This way:
- Your design decisions get tested against real edge cases
- You see whether the customer actually values it enough to pay
- No code yet

The cofounding-bingen analog: for a validated hypothesis, before "building" the product, run a **manual service pilot**. Example: if the hypothesis is "indie founders want Reddit pain mining," the first 5 customers get Efe + Bingen scanning Reddit by hand and emailing them a pain report. $200 per report. Anyone paying? Then write the code.

### 5. Wizard of Oz prototyping
Pretend the product back-end is built — the front-end looks real, but you're faking the automation by hand. The customer thinks "the AI is doing this," but it's actually you. Result: validate demand before building the AI feature.

In cofounding-bingen: a build-in-public post can say "we're using AI to mine Reddit pain points" while we manually fulfill it for the first testers. If 10 people show up, the engineering investment is justified.

### 6. The Mom Test influence
Klein predates Rob Fitzpatrick but lays the theoretical groundwork for the same discipline: users lie (not maliciously, just out of social politeness). The interviewer's job is to be the lie filter.

3 anti-patterns (Klein + Fitzpatrick combined):
1. **Compliment fishing** — "What do you think of this idea?" → user is polite
2. **Pitching the hypothesis** — explaining the idea and asking "good?" → confirmation bias
3. **Future commitments** — "Would you buy it if I built it?" → cheap promise

The only valid question: "What did you do in the past?" Past behavior doesn't lie.

In cofounding-bingen:
- The `idea-explorer` agent should **flag anti-patterns** when shaping a hypothesis (it doesn't yet — could be added)
- The `pain-validator` agent scores "I would pay" sentences as WTP=2 max; "I currently pay $X for Y and it sucks" sentences become WTP=3 → behavioral discount encoded into the rubric

### 7. Recruiting the right users
Recruiting users is harder than it looks. Klein's tactics:
- **Find users where they already are** — forum, sub, Discord. Don't bring them to a lab.
- **Incentive structure** — pay them, but not enough to distort the hypothesis ($25 reasonable, $200 distorts answers)
- **Avoid friends/family** — social bond drops the lie filter
- **Recruit by behavior, not demographics** — not "founders aged 30-40," but "founders who spent $500+ on tools last month"

In cofounding-bingen:
- The `community-mapper` skill operationalizes Klein's "find users where they are" — sub, Discord, influencer map
- The `tester-funnel` skill recruits-by-behavior — only people who comment on a pain post or DM us join the tester list
- There's no **incentive structure** field in the funnel yet. Could add: `Incentive offered: $X / free access / equity / nothing`

### 8. Rapid validation tests
- **Five-second test** — show the user a screen for 5 seconds, ask what they understood → first impression, value-prop clarity
- **Paper prototype** — test the flow on paper before building it
- **A/B headline tests** — try two headlines on a landing page, compare click rate

In cofounding-bingen: `build-in-public-writer` post drafts could mini-A/B — 2 different opening lines in 2 subs, which one drives more comments? Add to the post-launch plan.

## Quotes
_(verbatim quotes go here as you read, with page numbers)_

> "..."  — page N

## What this means for the repo

| Agent / skill | What it borrows from UX for Lean Startups |
|---|---|
| `idea-explorer` | Mom Test anti-pattern awareness — hypothesis must be shaped to "ask the right question" |
| `problem-hunter` | Listening tour = scanning Reddit/HN pain posts. Verbatim discipline comes from Klein. |
| `pain-validator` | Behavioral > stated. WTP axis is straight Klein. |
| `community-mapper` | Find users where they are. Don't bring them to a lab — go to their environment. |
| `build-in-public-writer` | Wizard of Oz mindset — say "we're building" then manually deliver the service first |
| `tester-funnel` | Recruit by behavior, mass over friends. Add an `incentive offered` field. |

## Concrete application: for the next hypothesis

When we get a validated H{N}, before moving to "build," try a **concierge pilot**:
1. Manually serve 3-5 interested testers (your own hands / with Bingen)
2. Charge — $50-200
3. After 2 weeks: anyone paying? How many came back?
4. Yes → write code. No → KILL or pivot.

This step could be added to the `notes/hypotheses.md` template: `Concierge pilot offer: $X for Y service`

## Anti-patterns Klein flags

1. **"Beautiful design first" trap** — pixel-perfect mockup before validation
2. **Asking opinions instead of behavior** — the "what do you think?" trap
3. **Lab effect** — putting users in an isolated environment (real behavior disappears)
4. **Recruiting from your network** — friends/family bias
5. **Stated preference scoring** — treating "I would pay" as behavior and writing code on top of it
6. **Skipping listening tour** — going straight to build
7. **Single-user pattern overconfidence** — extracting a pattern from 1-2 people
