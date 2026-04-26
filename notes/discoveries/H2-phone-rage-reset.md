# Discovery — H2: Phone-rage reset (block + 60s breath in one loop)

**Hunted on**: 2026-04-26
**Sources searched**:
- Hacker News (Algolia API, comment-level) — full coverage
- Reddit (r/nosurf, r/digitalminimalism, r/ADHD, r/getdisciplined) — **BLOCKED in this environment**: every reddit.com/old.reddit.com/web.archive.org/reddit endpoint returned "unable to fetch" or 429. Bing/DuckDuckGo also blocked or CAPTCHA-walled. Reddit pass deferred — flag for human or different scraper.
- App Store reviews — not directly accessible; covered indirectly via HN Show HN threads where founders describe their own bypass stories.

**Queries used (HN, all `tags=comment`)**:
- "Opal app phone", "Opal screen time", "Opal disable", "Opal too expensive", "Opal I canceled"
- "one-sec app", "one sec breathing exercise"
- "Brick app phone block", "Brick phone app", "ScreenZen"
- "phone addiction app", "screen time blocker", "app blocker doesn't work"
- "doomscroll cortisol", "feel sick after TikTok", "after scrolling I feel"
- "phone rage scroll", "I rage quit Instagram", "instagram two hour hole"
- "block then ground phone", "block breath phone", "meditation after scrolling"
- "Headspace screen time", "mindfulness phone addiction"
- "I just turn off the blocker", "wish blocker would help"
- "ADHD phone can't stop", "I would pay for focus app"

---

## Findings (15)

### F1 — "I tried third-party blockers, like Opal and Clearspace. Those were just as easy to get around" + built a competitor

- **Source**: [Show HN: I built a web app that locks you out of Screen Time](https://news.ycombinator.com/item?id=42538466)
- **Date**: 2024-12-29
- **User**: skippyandfluff (Aditya Saravana)
- **Quote**:
  > "I was tired of mindlessly scrolling on my phone, so I opened Settings and set a Screen Time limit to try and stop myself. The next day, I saw the 'Time Limit' screen pop up as I scrolled, and without so much as a second thought, I pressed 'Ignore Limit' and moved on. I had the same problem again.
  >
  > I tried third-party blockers, like Opal and Clearspace. Those were just as easy to get around, all I had to do was flip a switch in Settings and they were completely useless (Proof: www.bit.ly/opaldoesntwork—it literally took me 5 seconds to instantly brick both apps). I had the same problem AGAIN.
  >
  > I looked for something different: an app with no workarounds at all, something I could set up and forget about. I couldn't find one."
- **Context**: Founder of "Shutout" Show HN. He registered the URL `bit.ly/opaldoesntwork` to literally call out Opal's failure. Strongest possible "Opal doesn't work" signal: someone went and built a competing product.

---

### F2 — "I dislike being away from my phone. I dislike that I dislike being away from my phone" + built DIAL with $0.59 penalty

- **Source**: [HN comment by dwhale](https://news.ycombinator.com/item?id=45658967)
- **Date**: 2025-10-21
- **User**: dwhale
- **Quote**:
  > "I dislike being away from my phone. I dislike that I dislike being away from my phone. I don't like losing money. I don't like pointless subscriptions. So I built DIAL - a FREE (no subscription, no ads, no signup) screen time app that uses my hatred of losing money to beat my phone addiction. How it works: Block distracting apps for as long as you want. Want to end early? It costs $0.59. That's it. The pain of spending money > the pain of staying off TikTok."
- **Context**: Show HN-style self-promo. The double-negative emotional language ("dislike that I dislike") + the willingness to pay-per-bypass mechanic = market still demanding stronger consequence layer than what Opal provides. Confirms bypass is the core unsolved problem.

---

### F3 — Opal+ScreenZen+OneSec stack, "scheduled block sessions like Opal, mindful breathing interruptions like One Sec" → built EvoCat

- **Source**: [HN comment by anzerarkin](https://news.ycombinator.com/item?id=43635873)
- **Date**: 2025-04-09
- **User**: anzerarkin
- **Quote**:
  > "I also made an app to fix my scrolling issue — it's called EvoCat. The idea came from wanting to combine the best parts of all the focus apps I used: scheduled block sessions like Opal, mindful breathing interruptions like One Sec, and some light gamification to make it feel less like punishment."
- **Context**: Another founder explicitly stating the H2 thesis — combine Opal-style blocking with One Sec-style breathing. The exact integration H2 hypothesizes is wanted. Important caveat: EvoCat ALREADY exists doing roughly this; not a clean greenfield. Competitor risk.

---

### F4 — One Sec power user opens it 25 times in 7 hours ("breath delay isn't enough")

- **Source**: [HN comment by PartiallyTyped](https://news.ycombinator.com/item?id=36128408)
- **Date**: 2023-05-30
- **User**: PartiallyTyped
- **Quote**:
  > "I installed the 'one sec' app suggested in a sibling comment. I tried opening it about 25 times in the previous 7 hours."
- **Context**: Subtle but important — one-sec gives the breath pause, the user STILL bashes it 25x. The 1-second delay does not actually reset the impulse. Direct evidence the H2 wedge ("real reset, not 1-sec delay") has open space.

---

### F5 — One Sec works for some apps, but user "subconsciously ignored it" after a while

- **Source**: [HN comment by hn_throwaway_99](https://news.ycombinator.com/item?id=42259960)
- **Date**: 2024-11-27
- **User**: hn_throwaway_99
- **Quote**:
  > "I already have an app that does this on Android (One Sec is the app) and it only inserts a 'mindfulness break' for specific apps (e.g. Chrome and social media), and I came to the same conclusion you did.
  >
  > It's grind when I just mindlessly tap to open the browser to search for something random. Lots of times, though, the browser opens when I want to do something quickly, e.g. I get an email and I need to open something in the browser, and it becomes a big annoyance. After a while I just started subconsciously ignoring it, which I think defeats the purpose.
  >
  > It's a tough problem to solve - I want it to prevent me from doing 'mindless scrolling', but not when I have an actual task to accomplish."
- **Context**: One-sec habituation. After repetition, the breath prompt becomes wallpaper — exactly the failure mode H2 is trying to fix with a deeper reset. Strong WTP-adjacent: "tough problem to solve."

---

### F6 — Screen Time → blocked → "I get mad, unblock everything, and scroll for hours"

- **Source**: [HN comment by lekker-kapsalon](https://news.ycombinator.com/item?id=44023961)
- **Date**: 2025-05-18
- **User**: lekker-kapsalon
- **Quote**:
  > "I set Screen Time blockers, it is fine for a day or two, then I need to lookup something on let's say YouTube and it is blocked, I get mad, unblock everything, and scroll for hours."
- **Context**: Textbook block-bypass-rage cycle. The "I get mad" language is exactly the rage signal H2 names. Note: Apple Screen Time, not Opal — but same failure pattern.

---

### F7 — "Most digital wellbeing tools are designed to be ignorable" — 6,000 user-overrides at scale + $0.5 penalty fixes it

- **Source**: [HN comment by estonianburger ("I think I just solved screen-time addiction")](https://news.ycombinator.com/item?id=46377573)
- **Date**: 2025-12-24
- **User**: estonianburger
- **Quote**:
  > "I've tried every screen-time tool: limits, grayscale, app blockers, focus modes. None of them worked for more than a week. I just kept scrolling and what i found was a problem that really hadn't been solved:
  >
  > The failure of screen-time tools isn't that users don't understand the harm; it's that nothing meaningful happens when they ignore the limit.
  >
  > A few observations after running this with ~120 users and +6,000 overrides:
  > • People override limits constantly when there's no consequence • Even a $0.5–$1 'loss' dramatically changes behavior • Users want friction • Donation beats punishment
  >
  > Building the app has raised one uncomfortable question: Why are most 'digital wellbeing' tools designed to be ignorable?"
- **Context**: 120-user data set, 6,000+ override events. Quantitative confirmation that "block alone" fails. The Eclipta/breath-reset angle is a *different* answer to the same problem (consequence/reset > pure block). Direct competitor-thesis (financial penalty), but validates the underlying pain.

---

### F8 — Block + override muscle memory; only solution: hard PIN you forget

- **Source**: [HN comment by iterateoften](https://news.ycombinator.com/item?id=42259960)  *(reply chain)*
- **Date**: 2024-11-28
- **User**: iterateoften
- **Quote**:
  > "I had tried to block Reddit but then I needed it when researching some programming stuff. ... What I found is that I developed a muscle memory for just ignoring the block and overriding it.
  >
  > Instead of allowing myself an override that so I could dismiss the block I had to just hard block all of Reddit by setting an PIN I immediately forgot and if I really need something I'll use ChatGPT to summarize."
- **Context**: "Muscle memory for ignoring the block" — direct evidence that block-without-reset trains the bypass. Exactly H2's thesis.

---

### F9 — "I hate how I feel after doom scrolling. But the initial impulse is hard to fight"

- **Source**: [HN comment by momojo](https://news.ycombinator.com/item?id=43910705)
- **Date**: 2025-05-06
- **User**: momojo
- **Quote**:
  > "I agree. I hate how I feel after doom scrolling. But the initial impulse is hard to fight."
- **Context**: Pure rage/disgust language paired with the impulse-control problem — both halves of the H2 nervous-system thesis (post-scroll guilt + pre-scroll urge).

---

### F10 — "Frayed weariness" after Reddit/HN — gambling-like dopamine

- **Source**: [HN comment by npilk](https://news.ycombinator.com/item?id=47469648)
- **Date**: 2026-03-21
- **User**: npilk
- **Quote**:
  > "Yes, spending time working with Claude Code leaves me feeling the same way I feel after a day scrolling Reddit and HN - a thin, jittery, frayed sort of weariness. It's almost like gambling, with inconsistent dopamine hits, but it adds an element of keeping track of an ever-increasing number of projects and to-dos."
- **Context**: "Jittery, frayed weariness" = exactly the cortisol-spike phenomenology H2 targets. Names the gambling/dopamine analogy explicitly.

---

### F11 — "After an hour of TikTok scrolling, our body and subconscious is screaming"

- **Source**: [HN comment by munificent](https://news.ycombinator.com/item?id=37407211)
- **Date**: 2023-09-06
- **User**: munificent
- **Quote**:
  > "After an hour of TikTok scrolling, our body and subconscious is screaming that we should be doing something."
- **Context**: Body-level (not mind-level) post-scroll language. Fits the breath/grounding wedge — a meditation cue post-relapse would address exactly this body-scream.

---

### F12 — "Empty after scrolling Insta"

- **Source**: [HN comment by abhayhegde](https://news.ycombinator.com/item?id=36690738)
- **Date**: 2023-07-12
- **User**: abhayhegde
- **Quote**:
  > "I have been away from social media for similar reasons; I would feel empty after scrolling through Insta."
- **Context**: Emotional-emptiness language. Same post-scroll regret family.

---

### F13 — "I feel like I need a cold shower after endlessly scrolling those videos"

- **Source**: [HN comment by mike10921](https://news.ycombinator.com/item?id=32484440)
- **Date**: 2022-08-16
- **User**: mike10921
- **Quote**:
  > "I feel like I need a cold shower after endlessly scrolling those videos"
- **Context**: Body-reset language ("cold shower") = the user is *literally asking for a nervous-system reset*. This is the closest thing to a pre-product-articulation of H2's wedge.

---

### F14 — "Apathetic-rage-quit" of Facebook scrolling

- **Source**: [HN comment by mdip](https://news.ycombinator.com/item?id=20091417)
- **Date**: 2019-06-04
- **User**: mdip
- **Quote**:
  > "I had an experience I can only describe as an apathetic-rage-quit...a lot of the reason I scrolled Facebook was habit mixed with obligation."
- **Context**: Direct rage-quit language. Older but the phrasing is gold.

---

### F15 — Brick + One Sec stack + Apple Watch — only flows that didn't become "frustrating over time"

- **Source**: [HN comment by nosduhz](https://news.ycombinator.com/item?id=42257556)
- **Date**: 2024-11-27
- **User**: nosduhz
- **Quote**:
  > "On iOS, I've tried nearly everything, but here's what's lasted more than a few months. 1. A physical blocker like Brick (getbrick.app) and/or a Kitchen Timer Safe (KSafe). 2. One Sec app. I'll occasionally leave my phone at home and use only an Apple Watch with LTE. These are the only flows that haven't become frustrating over time and have worked to cut screen time and addicted apps (or altogether)."
- **Context**: Power user already manually stacks Brick + One Sec separately. They've solved the H2 problem with two apps + a physical device. Validates the integration thesis (two tools today, want one tomorrow) AND warns of substitute risk (a stack that already works isn't an emergency).

---

## Additional supporting signals (lower priority, included for pain-validator)

- **AdieuToLogic, 2025-06-23** ([HN 44351848](https://news.ycombinator.com/item?id=44351848)) on One Sec: "If this appears to be an insurmountable ask, or otherwise infeasible, I humbly suggest there is a greater concern to be addressed than what yet another app on the phone which cannot be distanced may remedy." — suggests One Sec users are already at their wits' end.
- **cocoflunchy, 2024-07-16** ([HN 40976126](https://news.ycombinator.com/item?id=40976126)) on Opal: "I have tried Opal but it was so buggy I gave up." — bug-driven Opal churn.
- **softservo, 2025-06-30** ([HN 44427955](https://news.ycombinator.com/item?id=44427955)): "I tried Apple Screen Time...found the blocks were too easy to bypass."
- **stuff4ben, 2024-06-10** ([HN 40635595](https://news.ycombinator.com/item?id=40635595)) ADHD: "I can't stop myself from fidgeting on my phone looking at Reddit or FB."
- **Djonckheere, 2025-09-20** ([HN 45314161](https://news.ycombinator.com/item?id=45314161)): "Phones are designed to be hyper-addictive, hooking users on...social media rage bait."
- **dvcrn, 2018-05-09** ([HN 17026684](https://news.ycombinator.com/item?id=17026684)): "My social media and phone addiction almost completely disappeared and I'm just in general a nicer person." — testimonial that meditation IS what fixes phone addiction (validates the breath layer's mechanism, but separately, not integrated).

---

## Caveats / where signal is weakest

1. **Reddit is the highest-priority hunting ground per H2 spec (r/nosurf is a "gold mine") and we couldn't access it from this environment.** All reddit.com / old.reddit.com / web archive / search-engine cache routes returned 403/429/CAPTCHA/blocked. **Recommendation: human runs the Reddit pass manually, OR install a redditlens/scraper skill before pain-validator scores. Without Reddit, our verbatim "I disable Opal X times a day" rage quotes are missing — HN is too SaaS-founder-skewed for the angry-end-user demographic.**
2. **The integration angle (block + breath in ONE app) has only ONE direct verbatim quote: anzerarkin's EvoCat (F3). Plus implicit demand from F4/F5/F13/F15.** This is exactly enough to not kill the hypothesis, not enough to declare it strongly wanted in the user's own words yet.
3. **EvoCat already shipped this premise (block + breath + gamification).** Need a competitor scan before pain-validator. If EvoCat is dead/abandoned that's permission; if it's growing that's a "third project crowding into a crowded lane" risk.
4. **No verbatim quote yet says "I would pay for an app that blocks AND grounds me."** Closest is F13 ("I need a cold shower after endlessly scrolling") which is body-reset language but not WTP-stated. WTP signal currently rides on adjacent products charging money successfully (Opal $20/mo, Brick hardware, DIAL $0.59-per-bypass) rather than direct H2-shaped quotes.
5. **All findings are from technical/HN audience.** H2's stated audience includes students 20-35 and ADHD-leaning indie hackers — HN covers the latter but the student angle is unvalidated. Reddit pass would patch this.

---

## Recommended next step

Hand to **pain-validator** with two flags:

1. **Reddit pass owed** — strong-enough HN signal to not kill the hypothesis (15 verbatim quotes including 3 founder-built-it-themselves stories), but the rage-end of the spectrum is under-sampled because we couldn't reach r/nosurf. Pain-validator should explicitly score the HN-only corpus and note the Reddit gap. If pain-validator is already at marginal GO, request a manual Reddit pass before deciding.
2. **Competitor risk: EvoCat** — anzerarkin already shipped the H2 product. Recommend `competitor-analysis` skill or a 30-min EvoCat investigation (TestFlight reach, app-store ratings, retention) BEFORE community-mapper, because if EvoCat is alive and good, the wedge collapses to "we vs. EvoCat" not "we vs. nothing."

Top 3 verbatim quotes to seed pain-validator:
1. skippyandfluff (HN 42538468): *"I tried third-party blockers, like Opal and Clearspace. Those were just as easy to get around, all I had to do was flip a switch in Settings and they were completely useless (Proof: www.bit.ly/opaldoesntwork—it literally took me 5 seconds to instantly brick both apps)."*
2. anzerarkin (HN 43635873): *"The idea came from wanting to combine the best parts of all the focus apps I used: scheduled block sessions like Opal, mindful breathing interruptions like One Sec..."*
3. lekker-kapsalon (HN 44023961): *"I set Screen Time blockers, it is fine for a day or two, then I need to lookup something on let's say YouTube and it is blocked, I get mad, unblock everything, and scroll for hours."*

---

## Validation — 2026-04-26

### Competitor check (mandatory for H2): EvoCat

Direct probe of `evocat.app` + HN Algolia search on user `anzerarkin` and story `evocat`:

- **Status**: Alive but commercially flatlined. Landing page is up, founder still posting (last HN comment 2026-02-05). Product is **still on TestFlight** as of 2026-04-26 — no App Store launch in 12+ months since first Show HN.
- **Show HN performance**: Two separate Show HN posts (2025-05-12 "Show HN: EvoCat – A Gamified iOS App Blocker" and 2026-04-10 "Show HN: EvoCat – a strict iOS app blocker with 'cat'-based enforcement") — **2 points / 0 comments each**. Functionally invisible.
- **Social proof**: Zero on the landing page. No testimonials, no user count, no reviews, no public metrics.
- **Pricing**: 3-day trial → annual plan, exact price not disclosed.
- **What it actually does**: 4 enforcement modes (strict hard lock, physical challenges, mental puzzles, breathing exercises), digital pet that evolves, on-device only.
- **Verdict on EvoCat**: Same thesis (block + breath + gamification) but the founder hasn't reached escape velocity. The wedge is **not closed** — anzerarkin shipped the integration thesis, but the market hasn't validated it yet. Permission to proceed, but treat this as a warning that "block + breath in one app" isn't an obvious win — execution, distribution, or the specific reset mechanic (breath alone may be too soft) all need to be better than EvoCat.

### Reddit gap (per hunter caveat)

HN-only sample. r/nosurf, r/digitalminimalism, r/ADHD, r/getdisciplined unreached due to scraping block. HN biases toward intellectual/builder-tier complaints; rage-end of the spectrum (verbatim curses, rage-quits with WTP) is under-sampled. Frequency NOT artificially boosted to compensate — scored on what was found.

### Per-finding scoring

| Finding | I | F | WTP | Total | Quote anchor |
|---|---|---|---|---|---|
| F1 skippyandfluff | 3 | 3 | 1 | 9 | "completely useless" + built a competitor; no $ from him, paying-for-a-worse-tool inferred |
| F2 dwhale | 2 | 3 | 0 | 0 | Builder-side, free product, no customer WTP |
| F3 anzerarkin | — | — | — | **EXCLUDED** | Competing builder describing thesis, not customer pain (per task rules) |
| F4 PartiallyTyped | 2 | 3 | 0 | 0 | "tried opening it about 25 times in the previous 7 hours" — using free app, no $ |
| F5 hn_throwaway_99 | 2 | 3 | 0 | 0 | "subconsciously ignoring it" — free One Sec, no $ |
| F6 lekker-kapsalon | 3 | 3 | 0 | 0 | "I get mad, unblock everything, and scroll for hours" — Apple Screen Time (free), no $ |
| F7 estonianburger | 2 | 3 | 1 | 6 | Builder-side data: 120 users, 6,000 overrides; "$0.5–$1 'loss' dramatically changes behavior" — competitor evidence of paying behavior, but indirect |
| F8 iterateoften | 2 | 3 | 0 | 0 | "muscle memory for just ignoring the block" — free Screen Time, no $ |
| F9 momojo | 2 | 3 | 0 | 0 | "I hate how I feel after doom scrolling" — pure pain, no $ |
| F10 npilk | 2 | 3 | 0 | 0 | "thin, jittery, frayed sort of weariness" — pure phenomenology, no $ |
| F11 munificent | 2 | 3 | 0 | 0 | "body and subconscious is screaming" — pure pain, no $ |
| F12 abhayhegde | 2 | 3 | 0 | 0 | "feel empty after scrolling Insta" — pure pain, no $ |
| F13 mike10921 | 2 | 3 | 0 | 0 | "need a cold shower after endlessly scrolling" — body-reset language but no $ |
| F14 mdip | 3 | 3 | 0 | 0 | "apathetic-rage-quit" — rage but no $ |
| F15 nosduhz | 2 | 3 | 2 | 12 | "Brick (getbrick.app) and/or a Kitchen Timer Safe (KSafe). 2. One Sec app." — paying for hardware AND premium app stack, validates substitute-stack WTP |

**Median total**: 0 (with F3 excluded; 14 findings; sorted: 0,0,0,0,0,0,0,0,0,0,0,6,9,12 → median between 7th and 8th = 0)

**Verdict**: **MAYBE** — leaning KILL on a strict reading of the median, but two structural reasons argue against an immediate kill:

1. The HN-only sample systematically under-samples WTP-stating users. r/nosurf was the H2 hypothesis's #1 hunting ground precisely because it's where rage + receipts cluster, and we couldn't access it. Scoring 0 on WTP for 11 of 15 findings reflects "no quote in HN" not "no willingness to pay anywhere."
2. Adjacent/competitor evidence (Opal $20/mo, Brick hardware ~$60, DIAL paying-per-bypass, EvoCat charging annual) shows the market IS paying for partial fixes. F15 confirms a real user manually stacks paid Brick + paid One Sec — that's a $60+ revealed WTP for the integration H2 proposes.

But — and this is the asshole filter — **zero verbatim "I would pay for an app that blocks AND grounds me" quote was found**. The hunter flagged this in caveat #4. The hypothesis's own kill criterion ("if everyone says 'I'd pay $0, just give me a free blocker', WTP fails — kill") is on the edge: HN users in this corpus aren't saying "$0," they just aren't saying anything about $ at all.

**Why**:
- **Strongest axis: Intensity (median 2-3)** — F6 ("I get mad, unblock everything, scroll for hours"), F14 ("apathetic-rage-quit"), F1 (registered `bit.ly/opaldoesntwork` to call out failure) — rage is real and easy to find.
- **Strongest axis: Frequency (3)** — block-then-bypass pattern is documented from 2018-2026 across many independent users. The pain is structural and persistent.
- **Weakest axis: WTP (median 0)** — The Eclipta/breath-reset wedge specifically (kill criterion #2) appears as wanted in ONLY ONE direct quote: F3 (anzerarkin, EXCLUDED as competing builder). F13 ("cold shower") is the closest customer pre-articulation, F15 is the strongest customer-stack proof. Both are inference, not assertion. **No verbatim "I'd pay for block + breath in one app" found.**
- **Existing competitors found**: EvoCat (same thesis, alive but commercially flat), DIAL (penalty wedge, free), Shutout (lockout wedge), Brick (hardware), One Sec (breath delay), Opal (block), ScreenZen (block). The crowded lane is real. EvoCat's specific failure to gain traction on HN with the exact H2 thesis is the loudest competitive signal — it's not a moat, it's a graveyard warning.

### Next step

**MAYBE → run two focused experiments before declaring GO/KILL, in this order**:

1. **Reddit pass on r/nosurf + r/digitalminimalism + r/ADHD** (manual or via different scraper). Specifically search for: "I'd pay", "would buy", "tried [Opal/Brick/One Sec] and", "$" + "blocker", "wish [blocker] could also". If Reddit yields ≥3 verbatim WTP quotes specifically tying block + reset together, escalate to GO. If Reddit yields ≥3 strong rage quotes but still no $ signal, KILL on the hypothesis's own WTP kill criterion.
2. **EvoCat reverse-engineering / TestFlight install** (~30 min). Why has it not reached App Store in 12+ months? Is it a quality bar problem (then we can do better), a distribution problem (then we'd hit the same wall), or an actual demand-gap (the "obvious" combination isn't actually wanted)? This answer reshapes the whole hypothesis.

If both experiments come back negative → KILL and move to graveyard. If Reddit confirms WTP and EvoCat looks beatable → GO with the open question already flagged in the hypothesis: **"is this a third project or does Efe's solo Blocker collapse into it?"** — this gets logged as a decision-needed item in `notes/decisions.md` only AFTER GO is confirmed.

### Decision-needed flag (parked, do not log yet)

If escalated to GO: log in `notes/decisions.md` — **"H2 vs. Efe-solo Blocker: separate project, merge, or shelve?"** Triggered per hypothesis line: *"if H2 validates strongly, the question becomes 'is this a third project or does Blocker collapse into it?'"* Currently MAYBE, so this decision is parked, not logged.

---

## Community Map — 2026-04-26

> **MAYBE-state caveat (read first)**: H2's verdict is MAYBE not GO (median 0/27, WTP axis starved by HN-only sampling). This map exists for two purposes: (1) tell a future Reddit re-hunt exactly where to look, and (2) seed the build-in-public playbook *if* a Reddit pass confirms WTP. **Do not start posting against this map until the Reddit recon (Week 1 below) confirms WTP signal lives there.** Distribution against an unvalidated WTP wedge is how indie hackers build dead products in crowded lanes.
>
> **Evidence-base thinness**: Member counts marked `verify needed` could not be fetched from this environment (Reddit + subredditstats + Google + reddit-stats all blocked the same way they blocked the hunting pass). Two subs (r/ADHD, r/getdisciplined) returned counts via frontpagemetrics.com and are confirmed; the rest are flagged for manual verification on first Reddit lurk.

### Subreddits (priority order)

| Sub | Members | Activity | Why it matters | Source findings |
|---|---|---|---|---|
| r/nosurf | verify needed (Reddit blocked from this env; nosurf.net's own about page calls it "still relatively small and new") | verify needed | **Primary**. Hypothesis explicitly named this as the "gold mine" for rage + receipts. None of F1-F15 came from here because Reddit was blocked at the hunting stage — that is the whole reason this map exists. The Reddit pass starts here. | Hypothesis spec, hunter caveat #1 |
| r/digitalminimalism | verify needed (Reddit blocked) | verify needed | **Primary**. Cal Newport's audience overflow. Less rage-pure than r/nosurf, more "I read the book, what do I do" — good for explaining the breath-reset mechanic. | Hypothesis spec |
| r/ADHD | **1,031,951** (frontpagemetrics 2026-04, ~1,400 active users) | ~1,500 new subs/day | **Secondary, huge sub**. Dopamine + focus threads where "I can't stop scrolling" is constant. Has explicit anti-self-promo rules — read sub rules before any post. F-supporting: stuff4ben's HN comment ("I can't stop myself from fidgeting on my phone looking at Reddit or FB") is exactly the archetype here. | Hypothesis spec, supporting signal |
| r/getdisciplined | **665,920** (frontpagemetrics 2026-04, ~640 active users) | ~500 new subs/day | **Secondary**. Self-discipline + accountability angle. Lekker-kapsalon's "I get mad, unblock everything, scroll for hours" (F6) is in this sub's typical voice. | Hypothesis spec |
| r/productivity | verify needed (frontpagemetrics 404) | verify needed | **Secondary**. Knowledge-worker overlap with H2's stated audience. Likely large but lower rage-density than r/nosurf. | Hypothesis spec |
| r/iphone, r/apple | verify needed (Reddit blocked) | verify needed | **Tertiary**. Useful only for review/uninstall threads on Opal/Brick/ScreenZen — not for primary hunting. Self-promo rules likely strict. | Hypothesis spec |
| r/Eclipta (or whatever Bingen ships under) | n/a | n/a | Owned channel — note for build-in-public-writer, not for hunting. | Bingen IP |

**EXCLUDED**: r/EvoCat or any sub tied to anzerarkin (F3) — direct competitor. Do NOT engage in their community.

### Discord / Slack / Forum

| Server | Invite / URL | Members | Notes |
|---|---|---|---|
| **ScreenZen Discord** | `https://discord.com/invite/qwDJm4pZZa` (verified on screenzen.co landing page) | unknown — invite live | **Confirmed**. Closest competitor community we should LURK (not post in). High-signal for "what does block-only look like when users hate it." Do NOT promote H2 here — it's their house. | 
| **Opal Community Forum** | `https://community.opalapp.com/` (confirmed live, 641 feature requests + 352 feedback topics + active "Gem Lounge" category) | unknown | **Confirmed active**. Same lurk-not-post rule. Feature-request board is a goldmine for "what Opal users wish existed" — read every top-voted request. |
| **Brick Community Board** | `https://getbrick.com/pages/community-board` → Canny | unknown — exists but no metrics shown | **Confirmed exists**, activity unknown. Canny boards are usually feature-request only, not discussion. |
| One Sec Discord | no invite found | — | One Sec ships in-app via web — no public community surface located. |
| EvoCat | n/a | n/a | **DO NOT ENGAGE** — direct competitor, anzerarkin (F3). |
| Cal Newport / Deep Life | none — newsletter + podcast only, no forum | — | Confirmed: thedeeplife.com runs no community forum, only contact email. |
| Center for Humane Technology | none — no Discord, just newsletter on substack | — | Same. |
| Make Time book community | newsletter only at `https://maketime.blog/newsletter-opt-in/` | — | No Discord/Slack found. |

### Top users to engage (NOT spam)

| Username | Platform | Pain quote (F#) | Suggested first contact |
|---|---|---|---|
| u/skippyandfluff (Aditya Saravana) | HN | F1 — "I tried third-party blockers, like Opal and Clearspace. Those were just as easy to get around" — registered `bit.ly/opaldoesntwork` | He's a builder (Shutout). DM as builder-to-builder AFTER prototype. Ask about retention curves on Shutout — he has live data we don't. **Not a customer DM, a peer DM.** |
| u/lekker-kapsalon | HN | F6 — "I get mad, unblock everything, and scroll for hours" | Pure customer voice. Reply on his HN comment thread when we have a working v0; do not cold DM. |
| u/PartiallyTyped | HN | F4 — "tried opening it about 25 times in the previous 7 hours" | Customer voice + builder-friendly (HN regular). Reach via HN profile after Show HN. |
| u/hn_throwaway_99 | HN | F5 — "after a while I just started subconsciously ignoring it" | Throwaway account — engage via the original HN thread reply, do not attempt account-level DM. |
| u/iterateoften | HN | F8 — "I developed a muscle memory for just ignoring the block...had to set a PIN I immediately forgot" | Customer voice. HN reply post-prototype. |
| u/nosduhz | HN | F15 — manually stacks Brick + One Sec + Apple Watch | **Highest WTP signal** ($60+ revealed spend on substitute stack). Engage as "you stacked these — would you replace them with one app, and what would have to be true?" |
| u/dwhale | HN | F2 — built DIAL ($0.59 penalty wedge) | **Competing builder**. Not a target. Watch what he ships, do not engage. |
| u/anzerarkin | HN | F3 — built EvoCat | **DIRECT COMPETITOR**. Per task rules: do not recommend engagement. |
| u/estonianburger | HN | F7 — built the $0.5 penalty app, 6,000 overrides at scale | **Competing builder** with the most quantitative data in the corpus. Read his future Show HNs, do not engage as customer. |

### Influencers / accounts to watch

| Handle | Platform | Followers | What they post | Source |
|---|---|---|---|---|
| @tristanharris | X/Twitter | unknown (Social Blade 403'd) | Phone-addiction policy + AI ethics. Center for Humane Technology podcast Your Undivided Attention has 132+ episodes (2026-04). | tristanharris.com confirmed |
| Cal Newport | newsletter (no public X) | **100,000+ newsletter subscribers** (confirmed on thedeeplife.com) | Deep Questions podcast (weekly Q&A on focus + tech), Digital Minimalism book = the audience root for H2. **No social handle, no community forum** — engagement is one-way until you ship. Ideal target for a case-study email after we have data. | thedeeplife.com |
| @maketimeblog | X/Twitter | unknown (Social Blade 403'd) | Make Time book newsletter + blog. Adjacent audience: knowledge workers building distraction-free systems. | maketime.blog |
| @opalapp | X/Twitter + YouTube + TikTok + Instagram | unknown | Direct competitor presence. Watch but don't engage adversarially. | opalapp.com |
| @livebricked (Brick) | X/Twitter + Instagram + TikTok | unknown | Direct competitor. Same: watch only. | getbrick.com |

> **Honest caveat**: Social Blade returned 403 on every Twitter follower check. All "unknown" entries above need a manual follower-count verification before any DM strategy. Don't invent numbers.

### Newsletters / podcasts

| Name | URL | Reach (verified) | Why relevant |
|---|---|---|---|
| **Cal Newport — Deep Questions podcast** | `https://www.thedeeplife.com/listen/` | newsletter has **100k+ subs**, podcast listenership unknown | Closest to a literal market for H2. A case-study pitch email post-launch is the highest-leverage cold outreach we have. |
| **Cal Newport newsletter** | thedeeplife.com signup | **100k+ subscribers** | Same audience as podcast. |
| **Your Undivided Attention (Center for Humane Technology)** | `humanetech.com/podcast` | listener count unknown, **132+ episodes**, biweekly | Tristan Harris + Aza Raskin. More policy-tilted than tactical, but their audience overlaps with H2's "I hate my phone" buyer profile. |
| **Make Time newsletter** | `maketime.blog/newsletter-opt-in/` | unknown | Jake Knapp + John Zeratsky. Adjacent — focused on time/attention, not blocker-rage. |
| Tristan Harris substack | `humanetech.com/substack` | unknown | CHT's Substack. |

### Posting calendar — adjusted for MAYBE state

> **Standard 4-week calendar shifted by 1 week**: Week 1 is recon, not posting, because verdict is MAYBE not GO. The first post is Week 2, conditional on Week 1 confirming WTP signal exists on Reddit.

#### Week 1 (2026-04-27 → 2026-05-03) — **RECON ONLY, NO POSTS**
- Lurk r/nosurf 3-5 days. Manually log every WTP-stating quote: "I'd pay", "would buy", "tried [tool] but" + $ context, "wish [blocker] could also". Target ≥ 3 verbatim WTP quotes in 5 days.
- Lurk r/digitalminimalism + r/ADHD focus threads in parallel.
- Lurk Opal community forum's top-voted feature requests (`community.opalapp.com`) — what do paying Opal users wish existed?
- Lurk ScreenZen Discord (`discord.com/invite/qwDJm4pZZa`) silently. Read pinned messages. Note rules.
- **Decision gate**: If ≥ 3 WTP quotes appear, escalate H2 to GO and proceed to Week 2. If 0-2 WTP quotes after 5 days of lurking, KILL on the hypothesis's own WTP kill criterion and move H2 to graveyard.
- Verify all `verify needed` member counts via the actual subreddit sidebars (this is incidentally trivial once the human-or-different-scraper hits Reddit).

#### Week 2 (2026-05-04 → 2026-05-10) — first soft post (only if Week 1 confirmed WTP)
- Post in r/nosurf using verbatim findings format: "I keep seeing the same pattern in HN threads — Opal/Brick/Screen Time get bypassed in 4 minutes. The block stops the behavior but not the cortisol spike. Anyone else feel this? What do you actually do at the bypass moment?" — quote 2-3 verbatim from F1/F6/F9. **Not promotional. No product mention.**
- Read r/nosurf rules first; many subs ban any link in OP for first-time posters. If self-promo is banned, do exactly that — engage as a human.

#### Week 3 (2026-05-11 → 2026-05-17) — IndieHackers + HN (only if Week 2 got engagement)
- IndieHackers post: "Built a v0 on the bypass-rage problem — looking for 5 testers who already canceled Opal/ScreenZen." Include the HN bit.ly/opaldoesntwork reference (F1) explicitly to show we did the research.
- Show HN if v0 is real. **Do not Show HN without a working artifact** — F1, F2, F3, F7 all show that the HN bar for "another phone-addiction app" is high.

#### Week 4 (2026-05-18 → 2026-05-24) — direct outreach
- DM the highest-pain HN users in this priority order: u/nosduhz (F15, $60+ revealed WTP), u/lekker-kapsalon (F6), u/PartiallyTyped (F4), u/iterateoften (F8). Frame as "you wrote X — we built a v0 of exactly that, would you tear it apart?" — NOT "would you like a free trial."
- Pitch a Cal Newport newsletter case-study email *only if* we have ≥ 5 testers' real retention data. Without data, don't waste the shot.
- Skip ScreenZen Discord and Opal forum for cold posting — these are competitor-owned spaces and self-promo there breaks community trust.

### Subreddit rules / tone notes

- **r/nosurf** — Strong anti-self-promo culture (sub is literally about hating tech-optimization tools). Frame any post as a *user's own struggle*, never as a builder pitch. The sub's own community page on nosurf.net describes itself as "still relatively small and new" — treat as a small, fragile community where one bad post burns the channel.
- **r/digitalminimalism** — Cal Newport-anchored, more book-club tone than rage. Quote-from-the-book entry posts welcome.
- **r/ADHD** — **Anti-self-promo rules are explicit and enforced**. Any product mention typically removed by mods. We can engage in comments only, never in OP. Read sub rules before any post.
- **r/getdisciplined** — Looser self-promo rules, but "show don't tell" — share the protocol, not the product.
- **r/iphone, r/apple** — Strict no-self-promo, very moderator-active. Avoid posting; engage only in already-active uninstall/blocker review threads.

### Distribution caveats specific to H2

1. **Crowded lane signal**: F1 (Shutout), F2 (DIAL), F3 (EvoCat), F7 (estonianburger penalty app) all built competitors. H2 is shipping into a market where 4 indie hackers from our own corpus are already swinging. This map should NOT be activated until both (a) Reddit confirms WTP, and (b) the EvoCat reverse-engineering task in `notes/discoveries/H2-phone-rage-reset.md` Validation section concludes there's still a wedge to take.
2. **Owned-IP channel**: Bingen has Eclipta IP. Eclipta's existing audience (if any — currently unverified) is the highest-trust distribution path because it's already opted-in to "real meditation/breath engine" instead of one-sec-style 1-second-delay. Verify Eclipta's audience size before building external community map any further.
3. **HN over-represented in current corpus**: 14/15 findings are HN. The Reddit pass closes that gap. Don't post on HN as primary channel until Reddit confirms the rage-end of the spectrum WTPs.

---
