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
