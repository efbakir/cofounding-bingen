# IndieHackers — H2

**Status**: draft (do NOT post until Week 1 recon confirms WTP signal on Reddit + Week 2 r/nosurf post gets engagement)
**Target community**: IndieHackers main feed (`Starting Up` / `Building` tag)
**Posting date target**: 2026-05-11 (Week 3, conditional on Weeks 1-2 surviving)
**CTA**: comment ("Anyone else seeing the block-bypass-rage cycle? I'd love to see your screen-time data")
**Sub rules**: IH allows builder pitches but rewards vulnerability + specifics. No marketing tone.

---

## We spent two weeks killing ideas before we wrote a line of code. Here's what survived.

Bingen and I are co-founding from 1,500km apart. He ships Eclipta (meditation app, live on the App Store, real breath/HRV engine). I ship Unit (gym app, near-launch, solo). The cofounding lab is the third thing — the project where Eclipta IP and my growth/product taste actually have to fuse to mean anything.

We started this month with seven hypotheses. Five are dead. Here's the audit, then the one we're sitting with.

**Killed**:
- **H1** — Long-distance "bro pair" for guys whose lift+work partner moved away. Pain-validator scored a median 0/27. Five distinct users wanted *matchmaking* (find me a partner) for every one who wanted *continuity* (my partner moved). Different products. The continuity wedge was our story, not the market's.
- **H3** — AI daily OS that stacks lift + cowork + meditation. The strongest WTP quotes ($65/mo coach.me churn, $300/mo trainer churn) actually validated a different shape: replace-the-human-coach. The lift+cowork+breath three-stack framing was ours, not the user's.
- **H4** — Paid 8-week men's depth cohort. Founder-fit kill. We're both engineers. If we don't light up on running cohorts vs shipping software, the operational load of community-as-product eats the unit economics.
- **H5 / H7** — Both validators still running, both on shaky WTP signal. Probably dead by Friday.

**Maybe-alive**: H2 — phone blocker + 60-second breath grounding in one loop, triggered at the bypass moment.

### Why H2 might be a thing

Pulled 15 verbatim HN quotes (Reddit was blocked at hunt time, that's its own caveat). The pattern that won't go away:

> "I set Screen Time blockers, it is fine for a day or two, then I need to lookup something on YouTube and it is blocked, I get mad, unblock everything, and scroll for hours." — u/lekker-kapsalon

> "I tried third-party blockers, like Opal and Clearspace. Those were just as easy to get around... it literally took me 5 seconds to instantly brick both apps." — u/skippyandfluff (the founder of Shutout, who registered `bit.ly/opaldoesntwork` because he was that done with it)

> "I had tried to block Reddit but I developed a muscle memory for just ignoring the block and overriding it." — u/iterateoften

The thesis: the block stops the behavior but leaves the nervous-system spike intact. So bypass is inevitable in 4 minutes. What's missing is a real reset between "block fires" and "user gives up." Bingen has shipped a real breath/meditation engine — not a 1-second one-sec delay, but the actual reset protocol. That's the integration: block → breath → return-or-don't.

### What almost killed it

**EvoCat already exists.** Founder anzerarkin shipped exactly the thesis ("scheduled blocking like Opal, mindful breathing like One Sec, gamification") in 2025. We checked: still on TestFlight 12 months later, two Show HN posts, 2 points / 0 comments each. Not a moat — a graveyard warning. Same idea, no pull. We have to know why before we ship.

**No verbatim "I'd pay for block + breath in one app" quote yet.** Closest is u/nosduhz on HN, who manually stacks paid Brick (~$60 hardware) + paid One Sec + Apple Watch — $60+ revealed WTP for a substitute stack. Implication, not assertion. Reddit recon next week is the real test.

### What we're doing next

- Week 1: 5 days lurking r/nosurf + r/digitalminimalism + Opal community forum + ScreenZen Discord, target ≥3 verbatim WTP quotes specifically tying block + reset together.
- If yes → soft post on r/nosurf, no product mention, just findings.
- If <3 quotes → kill H2, fold what we learned into Bingen's Eclipta roadmap and move on.

The competitor risk (EvoCat) plus the structural question — is this a third project, or does my solo Blocker product collapse into it? — both stay open until WTP signal lands.

### One ask

If you've shipped or used a phone blocker and you have your own bypass receipts: I want to see them. Specifically — how many times did you disable Opal/Brick/Screen Time last week? How many seconds between block-firing and bypass? Did anything actually ground you in that 30-second window, or did you just override?

Not collecting emails, not pitching, not running an "early access waitlist." Just trying to see if the block-bypass-rage pattern is real outside HN.

— Efe (Unit, solo) + Bingen (Eclipta, App Store)

---

## Quote sources used
- F1: u/skippyandfluff — [HN 42538466](https://news.ycombinator.com/item?id=42538466)
- F6: u/lekker-kapsalon — [HN 44023961](https://news.ycombinator.com/item?id=44023961)
- F8: u/iterateoften — [HN 42259960](https://news.ycombinator.com/item?id=42259960)
- F15: u/nosduhz — [HN 42257556](https://news.ycombinator.com/item?id=42257556)
- F3 (competitor): u/anzerarkin — [HN 43635873](https://news.ycombinator.com/item?id=43635873)

## Notes for posting
- **Sub rules check**: IH rewards transparent post-mortems. The "killed five hypotheses" intro is the social-proof move — shows we did the work, we're not pitching vapor.
- **Best time to post**: Mon/Tue morning EST. IH front page rewards early-week traction.
- **Follow-up plan**: Respond to every comment within first 6 hours. Specifically engage anyone who shares their own block-bypass count.
- **Tester capture**: Anyone who shares actual screen-time data → `notes/testers.md` as `interested`.
- **Cross-post check**: HN Show HN is NOT yet appropriate (no v0 to show). Defer Show HN to Week 4+ if a working artifact exists.
- **EvoCat call-out**: We name them. If anzerarkin sees the post, that's fine — public, founder-to-founder respect, no shade.
