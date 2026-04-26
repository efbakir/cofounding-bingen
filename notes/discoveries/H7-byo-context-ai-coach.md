# Discovery — H7: Bring-your-own-context persistent AI coach (DIY-LLM ceiling)

**Hunted on**: 2026-04-26
**Sources searched**: Hacker News (Algolia API — story + comment search), OpenAI Developer Community forum (publicly indexed), TechRadar/TechCrunch/learnprompting via WebSearch, OpenAI/Anthropic announcement pages via WebSearch, competitor product pages (Supermemory direct; Pi.ai, Character.AI, Replika via search since 403-blocked), IndieHackers (search blocked / 403), Reddit (BLOCKED — same as H3 hunt; `WebFetch` cannot reach reddit.com / old.reddit.com), DuckDuckGo (no useful results). X/Twitter SKIPPED (no scraper installed).

**Reddit blocked note**: Same structural gap as H3. r/ChatGPT, r/OpenAI, r/LocalLLaMA, r/PromptEngineering, r/selfimprovement all unreachable through WebFetch. WebSearch returns *summaries* of Reddit content via Google snippets but not verbatim user text. Findings below are HN-heavy + OpenAI Community Forum + competitor scan. **The H7 verdict from this hunt should be treated as partial on the user-pain axis but conclusive on the platform-risk axis.**

## Queries used

- `ChatGPT memory coach` / `ChatGPT therapist` / `ChatGPT forgets` (HN comment)
- `Custom GPT coach` / `I built personal AI coach` (HN comment)
- `Show HN AI coach memory` / `Show HN personal AI` / `Show HN persistent memory personal` (HN story)
- `LLM memory problem personal` / `ChatGPT memory feature` / `ChatGPT context every session` (HN comment)
- `journal to AI pipeline` / `ChatGPT memory diary journal` (HN comment)
- `OpenAI Memory update` / `Anthropic Memory Claude` / `ChatGPT memory across chats` (HN story)
- `"openai memory" announcement April 2025` / `OpenAI ChatGPT memory feature 2026 update roadmap` (WebSearch)
- `"chatgpt as my therapist" "memory" "forgets"` / `"would pay" "AI coach" "memory" "remembers"` (WebSearch — Google/Reddit-snippet)
- `Replika 2026 user complaint memory continuity` / `Pi.ai Inflection AI status` / `Character.AI persistent memory pricing 2026` / `Rosebud AI journal smart journal coach` / `Mem0 Letta MemGPT persistent memory` (competitor scan)

---

## Findings (10)

### F1 — HN Show HN founder (`mosnicholas`, IronClaude): builder explicitly cites LLM context loss as why he built his own coach
- **Source**: HN Show HN — "IronClaude: Open-source ClaudeCode workout coach that stores your data in GitHub" (story 46977671)
- **Permalink**: https://news.ycombinator.com/item?id=46977672
- **Date**: 2026-02-11 (~2.5 months ago)
- **User**: mosnicholas (founder)
- **Quote (verbatim, Show HN intro)**:
  > "those tools have zero context on my goals / preferences etc, and that I have to prompt them 2-3 times to get something I like."
- **Context**: He chose to build a Claude Code + private-GitHub-repo + Telegram pipeline for his own gym programming. The whole post is a signed confession that off-the-shelf AI tools lack persistence. Builder, ~$5/mo Fly.io infra, open-sourced — exactly H7's exemplar persona. Single comment on the thread (his own follow-up); didn't draw user reactions saying "I'd pay" — pulls down the WTP signal. **Builder-side ceiling complaint, no buyer-side WTP attached.**

### F2 — HN comment (`gchallen`): solo operator built journal-driven Claude Coach as a folder of files; explicitly names the workflow gap for non-CLI users
- **Source**: HN comment on (story not provided in API response, comment 46641296)
- **Permalink**: https://news.ycombinator.com/item?id=46641296
- **Date**: 2026-01-16
- **User**: gchallen
- **Quote (verbatim, partial)**:
  > "I've built several bespoke 'apps' that are essentially Claude Code + a folder with files in it. For example, I have Claude Coach, which designs ultimate frisbee workouts for me. We started with a few Markdown files—one with my goals, one with information about my schedule, another with information about the equipment and facilities I have access to, and so on... I think there's a whole category of personal apps that are essentially AI + a folder with files in it. They are designed and maintained by you, can be exactly what you want (or at least can prompt), and don't need to be published or shared with anyone else. But to create them you needed to be comfortable at the command line. I actually had a chat with Claude about this, asking if there was a similar workflow for non-CLI types."
- **Context**: This is exactly H7's "Custom GPT / Python wrapper" archetype — voluntary, technical, self-curated. Explicitly notes that the gap is "non-CLI users" — i.e., the un-met market. But: he says it's "fun" and he's "in no rush" — so he is NOT a buyer. He's a builder enjoying the build. **Strong builder evidence, weak WTP signal — exactly the failure mode H7's kill criteria warns about.**

### F3 — HN founder comment (`biosai`): persistent-memory dating coach, founder voicing the demand
- **Source**: HN Show HN comment 47115350
- **Permalink**: https://news.ycombinator.com/item?id=47115350
- **Date**: 2026-02-22
- **User**: biosai (founder)
- **Quote (verbatim)**:
  > "There's a growing pile of 'AI wrapper' products that slap a chat interface on GPT and call it a day. I don't want to build that. I'm trying to build something that actually coaches people — the way a good human coach would... It remembers your story across sessions — your goals, who you're talking to, what happened on your last date — and picks up where you left off. Coaching is grounded in a structured knowledge base of professional frameworks (conversation dynamics, profile psychology, confidence building), not just raw LLM output."
- **Context**: Founder pitching a niche-vertical (dating) version of H7. Honest status: "solo dev, pre-revenue." So the founder believes in the wedge, hasn't validated buyers yet. Founder voice, not buyer voice. **Same builder-side problem as F1/F2 — the people writing about persistent-memory coaches are the people building them, not paying for them.**

### F4 — HN comment (`evoke4908`): autistic engineer running ollama as therapist, explicitly says "I'd definitely use the hell out of" a journaling coach version, but pays nothing — runs local
- **Source**: HN comment on story 42003557
- **Permalink**: https://news.ycombinator.com/item?id=42052367
- **Date**: 2024-11-05
- **User**: evoke4908
- **Quote (verbatim, longer excerpts)**:
  > "I run ollama with a therapist prompt, and I've found it incredibly helpful. First, it's a safe place where I can discuss anything... I'm autistic and my biggest struggle is simply identifying my emotions... Most of my regular therapy sessions are just trying to figure out what I'm feeling and what the hell to do with it. The AI is shockingly good at this... I've been in a real bad way for a long time. I haven't been to therapy in years because I just haven't been able to make myself do more than eat, sleep, work. Talking to the AI gave me just enough of a lift to start pulling myself out of this rut..."
  > "Also I think this would be incredible as a sort of interactive diary. That's pretty much what this therapy is: just talking to your diary. I could see a lot of people getting benefit from a diary that asks them about their day and helps them process their emotions as they're writing their entries. I know I'd definitely use the hell out of that."
  > "Addendum: please for the love of god do not use someone else's AI for this. ChatGPT is *not* private and someone *will* link what you say to your advertising profile. Run a local LLM, it is not hard. Mine runs on a CPU only rack server from 2015. A damn toaster can run a small ollama these days."
- **Context**: Persona-perfect technical user, deeply moved by the use case — but his explicit recommendation is **"run a local LLM"**. The H7 pricing thesis is "$10-30/mo on top of ChatGPT Plus" — this user spec'd $0 and self-host. **High intensity / high frequency / NEGATIVE WTP — he'd actively recommend others NOT pay for this.** This is a structural anti-signal for H7's business model.

### F5 — HN comment (`pmarreck`): user has invested heavily in ChatGPT memory, frustrated he can't share/export his ChatGPT-self
- **Source**: HN comment on story 43891245
- **Permalink**: https://news.ycombinator.com/item?id=43892024
- **Date**: 2025-05-05
- **User**: pmarreck
- **Quote (verbatim, partial — truncated by API summary)**:
  > "My OpenAI ChatGPT knows me VERY well... I don't think there's currently a way to hand out a key to my own ChatGPT which also includes the conversation memory"
- **Context**: User invested in ChatGPT memory, treating it as an extension of self. Wants portability. **This is an OpenAI lock-in lament, not a wrapper-WTP signal — the user is happy with the depth ChatGPT memory has reached, just frustrated it's siloed.** Cuts against H7: this user already considers ChatGPT memory good enough that he calls it "knowing him VERY well."

### F6 — HN comment (`chaostheory`) on Anthropic Memory thread: confirms the "diary that talks back / Walmart therapist" persona is real and large
- **Source**: HN comment on Anthropic Memory announcement (story 45684134)
- **Permalink**: https://news.ycombinator.com/item?id=45687301
- **Date**: 2025-10-23
- **User**: chaostheory
- **Quote (verbatim)**:
  > "Both of you are missing a lot of use cases. Outside of HN, not everyone uses an LLM for programming. A lot of these people use it as a diary/journal that talks back or as a Walmart therapist."
- **Follow-up by same user** (45689462, 2025-10-24):
  > "People use LLMs as their therapist because they're either unwilling to see or unable to afford a human one. Based on anecdotal Reddit comments, some people have even mentioned that an LLM was more 'compassionate' than a human therapist. Due to economics, being able to see a human therapist in person for more than 15 minutes at a time has now become a luxury."
- **Context**: Names the H7 archetype (LLM as personal-life-OS) explicitly. **But** "Walmart therapist" framing = price-floor anchor. These users picked LLMs *because* the human alternative is unaffordable. They're H5 pre-buyers (the H7 hypothesis explicitly worries about this collision in kill criteria #4). **The persona exists; the WTP-above-ChatGPT-Plus does not show up in this quote.**

### F7 — HN comment (`sandspar`): user actively appreciates ChatGPT's memory feature for self-improvement; calls it "a glimpse of something big"
- **Source**: HN comment on story 40281785
- **Permalink**: https://news.ycombinator.com/item?id=40283070
- **Date**: 2024-05-07
- **User**: sandspar
- **Quote (verbatim)**:
  > "I've been using ChatGPT's new memory feature. It's buggy, but when it works it's quite cool. It feels like a glimpse of something big. Since it began making me aware that it remembers my activities, I've been pushing myself to achieve things. It's like having an audience. I wouldn't have expected that: when the machine is smart, I want to impress it, just like I'd want to impress a person I respect."
- **Context**: This is a user satisfied with stock OpenAI memory in a self-improvement context. **Direct evidence against H7's "memory is the bottleneck" thesis** — at least for one persona, ChatGPT's native memory is already "a glimpse of something big." Eighteen months pre-hunt, before OpenAI's April 2025 reference-all-chats upgrade.

### F8 — HN comment (`sg17gweedo`): articulates the persistence-as-companion thesis verbatim — but it's a Show HN founder pitching their own product (Bob)
- **Source**: HN comment on story (Show HN: Bob), comment 47248901
- **Permalink**: https://news.ycombinator.com/item?id=47248901
- **Date**: 2026-03-04
- **User**: sg17gweedo (founder pitching "Bob")
- **Quote (verbatim)**:
  > "ChatGPT forgets you exist every time you close the tab. Bob remembers what you said three weeks ago and why it mattered. Memory is the thing that separates a companion from a chatbot. A chatbot gives you answers. A companion gives you answers informed by everything it knows about you, your history, your preferences, your pain points, your goals. And for that to work, it has to remember. Every major AI assistant handles memory badly. They either don't remember at all (start fresh every session) or they remember a flat list of facts ('user likes coffee,' 'user has a dog') with no depth, no context, no understanding of why those facts matter. Bob has five tiers of memory."
- **Context**: This is the H7 thesis spoken aloud, in the user's own words — but "the user" here is **another founder pitching the same product**. It's market positioning, not paying-customer pain. Notable: he's competing on the same axis Efe/Bingen would, with a 5-tier memory architecture already shipped. **Confirms thesis is fashionable AND that competitors are racing to ship the wedge.**

### F9 — HN comment (`RickS`) on Anthropic Memory thread: solo operator articulating the full "second brain that talks back" wishlist + price band
- **Source**: HN comment on story 46826277
- **Permalink**: https://news.ycombinator.com/item?id=46831393
- **Date**: 2026-01-30
- **User**: RickS (self-described "design technologist")
- **Quote (verbatim, key passages)**:
  > "Execution: I would like a chat frontend (signal/SMS/etc) where I can just talk to my projects, ask the status of things, get suggestions, etc. Push based, rather than pull based, execution."
  > "But the bottom line for me, where does my second brain break down the most? It doesn't talk back to me. I want it to understand what I've got going on, and my idiosyncracies. I want to present it with new information and have it be like 'oh, this relates to X' or, periodically, to pop up with something like 'I'm noticing this correlation / related idea in areas X, Y, Z... does that resonate?'... My second brain should be a proactive chatbot."
  > "I think AI service pricing applies here: generally, if it seems neat I could be in for $20 easy, and if it's genuinely game changing, $200/mo is completely reasonable to ask."
  > "Nobody has yet built an adequate second brain for the home. My house, my relationship(s), my side projects, my own diarying and self reflection... these are the contents of my brain that matter."
- **Context**: This is the **strongest single H7 quote in the entire hunt.** Explicit persona match (technical, self-aware, journals, builds his own systems). Explicit feature ask (proactive chatbot, push-not-pull). **Explicit WTP: "$20 easy... $200/mo is completely reasonable" — clears H7's $10-30/mo price band by 6-10×.** Shipped his email for feedback. The risk: he's one user, and the comment frames it as wishlist not "I'd buy this tomorrow." But it's the closest verbatim hit to H7's exact thesis.

### F10 — OpenAI Community Forum (`martina97.1`): paying ChatGPT user explicitly complaining about memory regression in long-term creative project work
- **Source**: OpenAI Developer Community thread "[Bug] GPT-4o memory regression — context loss across chats and inside threads"
- **Permalink**: https://community.openai.com/t/bug-gpt-4o-memory-regression-context-loss-across-chats-and-inside-threads/1310926
- **Date**: 2025-07-29 / 2025-07-30
- **User**: martina97.1
- **Quote (verbatim)**:
  > "I've been using ChatGPT for long-term creative projects for months, and up until recently, the system correctly remembered what I was working on"
  > "ChatGPT remembers a past chat, but only if it's been open and not archived. Once the chat has been archived, it doesn't remember anything."
- **Adjacent quotes in same thread**:
  > **kioxinfo (2025-07-09)**: "Has become virtually impossible to work with. Asks to upload the same document every few minutes"
  > **IMStaFF (2025-07-08)**: "GPT-4o used to preserve memory across chats. Now, each new thread starts blank."
- **Context**: Real users, real paid plan, real pain — but the failure mode is *regression of a feature OpenAI shipped*, not a structural ceiling. **This evidence is double-edged for H7**: yes, users care about memory enough to file bug threads; AND, when OpenAI breaks it, users wait for OpenAI to fix it rather than switching to a wrapper. The fix expectation is on the platform, not on a third party.

---

## Sub-findings (weaker / contextual but logged)

- **HN comment (`castigatio`, 2024-08-21, ID 41307765)**: "I just created a custom GPT and told it what I wanted it to do... Marcus Aurelius is a personal job hunting coach and practitioner of Stoic philosophy." Custom GPT builder for self-coaching during unemployment. No WTP, just usage. Persona-positive, dollar-zero.
- **HN comment (`pmvpeter`, 2025-02-18, ID 43094681)** — already documented as F6 of H3 discoveries, the canonical PRECURSOR for H7: "I uploaded all that to ChatGPT, asked it to be my therapist/coach... Super interesting and useful." Cross-listed: **this user is the positive workaround. The hunt's job was to find his negative twin — who hit the wall and would pay to skip past it. We did not find that quote at strength.**
- **HN comment (`scriptdevil`, 2024-04-03)**: Wants tasks "outside the immediate short term memory of the coach" — generic PM-tool framing, not H7.
- **HN comment (`mosnicholas`, 2026-02-11, ID 46977672)** = F1 (above).
- **HN Show HN list (last 6 months)**: 19 distinct Show HN posts shipping persistent-memory or AI-second-brain products. Highlights: Eve (72 points, 40 comments, sandboxed Linux + iMessage), Claude-engram, Bossa, Bind.ly, Matrix OS, PearlOS, Athena, CoolWulf AI, Llmswap. **Saturation pattern — dozens of devs racing the same wedge.**
- **HN comment (`Gareth321`, 2026-04-20, ID 47833538)**: "Each time OpenClaw needs to 'think' about anything, it preloads a huge amount of 'memories' into the query... can chew through tens of thousands of tokens... eventually causing system failure under its own weight." Practitioner observation that naive persistent-memory architectures collapse — engineering-realism check on H7's "just bolt on memory" framing.
- **HN comment (`zeerg`, 2025-11-27, ID 46070922)**: "Every time I started a new session for a project, I found myself manually copy-pasting the same stack definitions, coding guidelines, and API references." Maintenance-burden quote. Coding context, not life-coaching, but the workflow pattern is identical.
- **HN comment (`bhattattreya`, 2026-02-15)**: "I reverse-engineered coaching frameworks (Push-Pull, Frame Control) into system prompts." Founder of FlirtFix (dating coaching wrapper). Builder, not buyer.
- **HN comments on Anthropic Memory (story 45684134)**: 312 comments. Sentiment split: enthusiasm (`anonzzzies`, `labrador`-positive, `gomibago`), skepticism (`labrador`-negative on ChatGPT memory making prompts "noisier and messier", `cruffle_duffle` on irrelevant capture, `stingraycharles` calling memory "marketing theater"), privacy concerns (`deadbabe`, `svachalek`, `jonplackett`). **Net: even with new platform memory shipped, users are split on whether they want it on at all.** Three users (`labrador`, `cruffle_duffle`) describe disabling memory because it polluted their results.

---

## What the hunt did NOT find (kill-criteria check)

- **Zero verbatim "I'd pay $X for an AI coach that ACTUALLY remembers me"** quotes from the explicit H7 phrase-shape #3. The closest is F9 RickS ("$20 easy... $200/mo completely reasonable") — but that's about a generic second-brain wishlist, not specifically an AI coach with memory above their ChatGPT Plus sub.
- **Zero buyer-side "I built a Custom GPT but I'd happily pay to skip building it"** quotes. Every builder we found (mosnicholas, gchallen, biosai, evoke4908, castigatio, bhattattreya) was *enjoying* the build, *recommending* others build their own, or *pivoting their own thing into a product*. None of them said "I would pay to be relieved of this." That is the load-bearing pattern H7 was supposed to validate, and it failed.
- **Zero verbatim quotes mapping cleanly to "I use ChatGPT as my coach but it forgets / I have to re-prime it every session"** specifically for coaching/therapy/accountability use cases. The "ChatGPT forgets" complaint exists (sg17gweedo, kioxinfo, IMStaFF) — but it's coding-flavored or general-thread regression, not coaching-flavored. The negative-twin of F6 H3 was not found.
- **Zero quotes from a user currently subscribed to ChatGPT Plus AND saying they'd pay $10-30/mo MORE for a memory-aware coach wrapper.** The closest WTP signals (RickS at $20-200/mo, evoke4908 at literal $0) bracket the H7 price band but never name it directly inside coaching context.
- **No evidence that H7's persona is paying for any AI-memory wrapper today.** The closest paying behavior is GoalsWon ($65/mo human-coach app) and AthleteData ($9/mo endurance-AI-coach) — neither is the H7 shape.

---

## Platform risk

**This axis kills the hypothesis on its own. Documenting the timeline:**

| Date | Platform | Ship |
|---|---|---|
| 2024-Q1/Q2 | OpenAI | ChatGPT Memory feature launched (saved memories + chat-history snippets, persona-shaped) |
| **2025-04-10** | **OpenAI** | **"Memory in ChatGPT now references all of your past chats" — every chat becomes context for every future chat. Sam Altman: "ai systems that get to know you over your life, and become extremely useful and personalized."** |
| 2025-06-03 | OpenAI | Lightweight memory rolled to free tier (continuity across sessions for non-paying users) |
| 2025-09-12 | Anthropic | Claude memory for Teams/Enterprise |
| **2025-10-23** | **Anthropic** | **Claude Memory shipped to Pro and Max plans (consumer) — explicit ship of "remembers preferences, project details, conversation context across sessions"** |
| 2026-Q1 | Microsoft | Copilot Memory shipped (personalized recall in Microsoft 365) |
| 2026 (roadmap, Sam Altman) | OpenAI | "Personality and tone… more steerable and personalized." Goal: "infinite, perfect memory" if user opts in. ChatGPT becoming "personal super-assistant." |

**Translation**: H7's wedge ("ChatGPT forgets, I'd pay for persistent context") was visible 12 months ago and has since been **directly addressed by both major platforms**, with announcements explicitly stating the goal is to "know you over your life." This is exactly the structural-kill scenario H7's own kill criterion #2 names verbatim ("if during the hunt week OpenAI or Anthropic ships a major Memory/Personality upgrade that materially closes the gap, kill"). It already happened — the hunt is finding the post-mortem state.

Reactive evidence that the platform fix is "good enough" for at least some H7-persona users:
- F5 (pmarreck): "My OpenAI ChatGPT knows me VERY well" (5 months after April 2025 update).
- F7 (sandspar): "It feels like a glimpse of something big... when the machine is smart, I want to impress it" (using stock ChatGPT memory).
- HN sentiment on Anthropic Memory thread (Oct 2025): mixed but split — many users are *disabling* memory, not asking for more (labrador, cruffle_duffle). A wrapper layered on top of platform memory has to compete not with "no memory" but with "memory that some users actively turn off."
- F10 thread regressions: when OpenAI's memory broke in July 2025, users **filed bug reports and waited for the platform to fix it.** They did not switch to a wrapper. That behavioral signal is fatal: the lock-in is on the platform, not the use case.

**Risk grade: A+ (highest). Both OpenAI and Anthropic explicitly compete on this axis, in their own announcements, with public roadmaps continuing to push it.** Any wrapper business in this space has a 12-month run before the next platform ship resets the goalposts. Sam Altman publicly: "whichever AI assistant has the best memory and personalization will be incredibly sticky" — this is OpenAI's stated competitive strategy. They are actively trying to eat this.

---

## Competitor scan

### Direct AI-coach-with-memory products (consumer)

- **Rosebud** ($12.99/mo, $6M Bessemer + Ohanian + Tim Ferriss) — AI journaling with "long-term memory… see thinking traps, patterns, reframe negative emotions." Voice journaling. **The most direct competitor on the journal-to-AI lane.** Already $6M funded, tier-1 distribution. https://www.rosebud.app
- **Cleo** ($250M ARR, 1M paid subs by 2025) — AI money coach with "two-way voice, long-term memory, advanced reasoning… remembers spending patterns." Vertical (money), but proves the persistent-memory-AI-coach business model at scale.
- **Mindsera, Reflection, Life Note** — three more AI journaling apps with memory layers. Competitive shelf already crowded.
- **GoalsWon, SideCoach, AthleteData, BeFreed** — H5's competitor set, partly overlapping (the AthleteData $9/mo MCP tier is explicitly a "self-hosted Claude/ChatGPT integration" — same architectural play as H7's wrapper thesis).
- **Jenova Interview Coach** — "remembers your career history, target roles, and areas for improvement — building on previous practice sessions." Vertical (interview), persistent-memory-pitched.
- **Pi.ai (Inflection)** — original "personal empathetic AI" play. **Inflection imploded in 2024, team went to Microsoft. Pi survives as a pivoted B2B product. The standalone consumer "personal AI" thesis already failed at the $1.5B level.** This is the strongest cautionary tale for H7.
- **Replika** ($70/yr, ~30M downloads lifetime). Replika 2.0 (April 2026) **broke users' long-running characters' memory** — r/Replika threads documenting "can't remember nothing" complaints. The single largest persistent-memory-AI-companion player just had a memory-system regression event 2 weeks before this hunt. Even the dominant player can't ship memory cleanly.
- **Character.AI** ($9.99/mo c.ai+) — "Chat Memories" + "Pinned Messages" already shipped. Consumer-grade persistent-memory AI companion at scale.
- **Bob (Show HN, 2026-03)** — F8's product. 5-tier memory architecture, framed exactly as H7 thesis. Founder is selling the same pitch.

### Direct H7-shape products (DIY-LLM-coach wrappers, last 6 months on HN)

- **Eve** (Show HN, 2026-04-10, 72 points / 40 comments) — "managed OpenClaw for work" with "persistent memory across sessions so context compounds over time." iMessage integration. $100 free credits. Best-in-class shipped competitor on H7's exact architecture.
- **IronClaude** (Show HN, 2026-02-11) — F1's product. Open-source, GitHub-backed, exact H7 frame for fitness vertical.
- **Bossa, Bind.ly, Claude-engram, Matrix OS, PearlOS, Llmswap, Athena, CoolWulf AI, Tentacle, Anchor Engine, MIRA, Persistent Mind Model, Atombot, Agentainer Lab, MCP Memory Tool** — 15+ persistent-memory AI agent / second-brain projects shipped in the last 6 months alone.
- **Mem0, Letta (formerly MemGPT), Supermemory, Zep, TrueMem** — the *infrastructure layer* for AI memory. Mem0 specifically targets "user preferences and personalization" — the H7 layer is being commoditized as a $0 npm install.

### Adjacent

- **Microsoft Copilot Memory** (2026) — enterprise/work persistent personalization shipped natively into M365. The platform-risk story is not just OpenAI/Anthropic.

### Saturation read

The H7 wedge is **the most crowded lane in the hunt across all 7 hypotheses**. There is a tier-1 funded incumbent on every adjacent cell: Rosebud (journaling), Cleo (money), Replika/Character.AI/Pi (companion), GoalsWon/AthleteData (accountability), Eve/IronClaude/Matrix OS (DIY wrapper). There are commodity infra players (Mem0, Letta, Supermemory). And the platforms (OpenAI, Anthropic, Microsoft) are racing to absorb the layer. The structural wedge — "ChatGPT forgets, I'd pay for memory" — was demonstrably real for ~12-18 months and is now closing fast on multiple fronts simultaneously.

---

## Sources unreachable / partial

- **Reddit (all subs)**: blocked at the WebFetch layer. WebSearch returns Google snippets but not verbatim user comments. **r/ChatGPT, r/OpenAI, r/LocalLLaMA, r/PromptEngineering, r/selfimprovement, r/Replika unscoured.** This is the same gap as H3. Net effect: we likely miss 30-50% of H7's lay-user pain quotes. **However**: the platform-risk axis is conclusive enough on its own that closing the Reddit gap would not change the kill verdict, only refine the "if not killed, what is the actual demand size?" question.
- **IndieHackers**: search blocked.
- **Pi.ai, Character.AI, Replika** main pages: 403 from WebFetch (consumer apps with bot-blocker). Used WebSearch for product positioning instead.
- **X/Twitter**: skipped per agent def (no scraper).

---

## Recommendation to main Claude

**Hand to pain-validator with strong KILL flag.** The 10 findings split as:

- **1 strong on WTP-axis** (F9 RickS) — explicit $20-200/mo price-band quote, explicit persona match, explicit feature ask. But: solo example, not specifically about coaching, and it's a wishlist comment not "I'd buy this tomorrow."
- **3 medium on persona-existence** (F2 gchallen, F4 evoke4908, F6 chaostheory) — confirms the H7 persona is real, articulate, and uses LLMs in this shape. But: F2 and F4 are explicitly anti-WTP (build it yourself / run local). F6 names the price-floor problem (the population picks LLMs *because* humans are unaffordable).
- **3 builder-side / founder-side** (F1 mosnicholas, F3 biosai, F8 sg17gweedo) — three founders who built H7-shape products. Two pitching their own thing on HN. Validates that *builders* believe in this wedge; does NOT validate that *buyers* exist.
- **2 negative or anti-thesis** (F5 pmarreck, F7 sandspar) — users explicitly satisfied with ChatGPT memory in personal-improvement contexts.
- **1 platform-regression evidence** (F10 martina97.1 + thread) — paying users care about memory but file bug reports rather than switching to wrappers.

**Why kill (priority order):**

1. **Platform risk fired during the hunt itself.** OpenAI shipped "memory references all chats" April 2025, Anthropic shipped consumer Claude Memory October 2025. H7's kill criterion #2 says explicitly: "if during the hunt week OpenAI or Anthropic ships a major Memory/Personality upgrade that materially closes the gap, kill." The ship already happened. The hunt found it; we're 12 months late.
2. **Builder/buyer asymmetry.** Every persona match in the hunt who articulated H7's pain *built it themselves and posted about it on HN*. Zero of them said "I'd pay to skip building this." The most technically articulate user (evoke4908) actively recommends others **NOT** pay for this and run a local LLM instead. The H7 thesis hangs on "technical enough to build it = technical enough to pay to skip building it." **The hunt's evidence directly inverts that thesis.**
3. **Saturation.** 15+ Show HN posts in the last 6 months shipping H7-shape products, plus tier-1-funded incumbents in every adjacent lane (Rosebud $6M, Cleo $250M ARR, Replika, Character.AI). H7's own kill criterion #4 ("3+ shipped products with 100+ paying users each") is fired multiple times over.
4. **Bingen-fit fail.** Per H7's kill criterion #5: this is a memory/context-engineering problem (vector DBs, retrieval pipelines, prompt-shaping), not a meditation problem. There is no obvious place for Eclipta IP. **This is a single-founder Efe-solo bet at best, not a cofound.**
5. **WTP signal absent in the exact phrase-shapes the hypothesis named.** Three named phrases (LLM-ceiling complaint in coaching context, DIY-builder regret WTP, $10-30/mo price band over Plus). Zero verbatim hits across 10 findings + 8+ sub-findings.

**Open question if pain-validator disagrees on kill**: even setting platform risk aside, the buyer-vs-builder asymmetry alone is fatal. Reddit gap closure (manual paste of r/ChatGPT memory threads) might surface 1-2 more clean WTP quotes, but cannot reverse the platform-risk axis. **Recommendation: kill, log to graveyard, do not run pain-validator unless main Claude wants the score for the record.**

**If we want to revisit anything from this hunt**: the F9 RickS quote is the strongest single signal across H1/H3/H7 combined for a "second brain that talks back" / proactive-AI-personal-assistant product. But that hypothesis is bigger than H7, owned by every major platform's roadmap, and would compete with Microsoft Copilot directly. Kill H7, do not respawn under a different name.

---

## Validation — 2026-04-26

| Finding | I | F | WTP | Total | Quote anchor |
|---|---|---|---|---|---|
| F1 (mosnicholas) | 1 | 2 | 0 | 0 | "those tools have zero context on my goals / preferences etc" — builder, no buyer-WTP attached |
| F2 (gchallen) | 1 | 2 | 0 | 0 | "you needed to be comfortable at the command line" — fun-build, "in no rush", explicit anti-WTP for the persona |
| F3 (biosai) | 1 | 2 | 0 | 0 | "I don't want to build that... a structured knowledge base" — founder voice, pre-revenue, not buyer pain |
| F4 (evoke4908) | 3 | 2 | 0 | 0 | "please for the love of god do not use someone else's AI for this... A damn toaster can run a small ollama" — high-intensity NEGATIVE WTP (recommends $0 self-host) |
| F5 (pmarreck) | 1 | 1 | 0 | 0 | "My OpenAI ChatGPT knows me VERY well" — anti-thesis, ChatGPT memory is already "good enough" |
| F6 (chaostheory) | 2 | 2 | 1 | 4 | "Walmart therapist... unwilling to see or unable to afford a human one" — persona real but explicitly H5 pre-buyer, price-floor anchor |
| F7 (sandspar) | 0 | 1 | 0 | 0 | "It feels like a glimpse of something big" — direct anti-thesis, satisfied with stock memory |
| F8 (sg17gweedo) | 2 | 2 | 0 | 0 | "ChatGPT forgets you exist every time you close the tab" — founder pitching Bob, market-positioning not buyer pain |
| F9 (RickS) | 2 | 1 | 2 | 4 | "$20 easy... $200/mo is completely reasonable to ask" — explicit WTP but hypothetical-wishlist not paying-customer-churn; capped per task instructions |
| F10 (martina97.1 + thread) | 2 | 2 | 1 | 4 | "Has become virtually impossible to work with" — paying users care, but file bugs and WAIT for OpenAI to fix it (lock-in is on platform, not us) |

**Median total**: 0 / 27 (median across 10 scored findings; six zeros, three 4s, one 0 — the multiplicative WTP=0 nukes most scores)

**Verdict**: KILL

**Why**:
- **Strongest axis: intensity** — F4 evoke4908 hits 3 ("please for the love of god"), but his rage flows toward LOCAL-LLM advocacy, not "I'd pay for a wrapper." High intensity in the wrong direction is anti-evidence, not pro-evidence.
- **Weakest axis: WTP** — Six of 10 findings score 0 on WTP. The hunt's own "did NOT find" log is conclusive: zero verbatim "I'd pay $X for an AI coach that ACTUALLY remembers me" quotes from H7's named phrase-shape #3, zero "I built a Custom GPT but I'd pay to skip building it" quotes, zero "subscribed to ChatGPT Plus AND would pay $10-30/mo more" quotes. F9 RickS is a wishlist, not a paying-customer churn quote — capped at WTP=2 per task instruction (and his frequency is 1 because the comment is one user, isolated on this exact thesis).
- **Three independent structural kills all fired**:
  1. **Platform risk (kill criterion #2)**: OpenAI shipped "memory references all chats" April 2025; Anthropic shipped Claude Memory to Pro/Max consumer plans October 2025; Microsoft Copilot Memory shipped 2026-Q1. H7's own kill criterion verbatim names this scenario and the ship already happened — the hunt is a 12-month-late post-mortem.
  2. **Builder/buyer asymmetry**: F2 (gchallen "in no rush... fun") and F4 (evoke4908 "do not use someone else's AI") invert the H7 thesis. The technical persona BUILDS this themselves — and F4 is actively anti-buying. Every persona match in the hunt who articulated H7's pain built it themselves and posted on HN. Zero said "I'd pay to skip building."
  3. **Lane saturation (kill criterion #4)**: 15+ Show HN's in 6 months (Eve, IronClaude, Bob, Bossa, Bind.ly, Matrix OS, PearlOS, Athena, etc.), tier-1 funded incumbents in every adjacent cell (Rosebud $6M, Cleo $250M ARR, Replika, Character.AI), commodity infra (Mem0, Letta, Supermemory at $0 npm). The wedge is the most crowded across all 7 hypotheses hunted.
- **Bingen-fit fail (kill criterion #5)**: this is a memory/context-engineering problem — vector DBs, retrieval pipelines, prompt-shaping. Eclipta IP (breath/meditation) has no obvious place. Even if signal were strong, this is single-founder-Efe-solo at best, not a cofound.
- **Existing competitors**: Y — Rosebud, Cleo, Replika, Character.AI, Pi.ai (cautionary failed-at-$1.5B), Eve, IronClaude, Bob, plus 15+ Show HN's in 6 months, plus OpenAI/Anthropic/Microsoft platform moves. This is the "fast-closing wedge" pattern, not the "open lane" pattern.

**Next step**: KILL. Append graveyard entry, update H7 status to `killed` in `notes/hypotheses.md`. Do NOT respawn under a different name — F9 RickS's "second brain that talks back" framing is bigger than H7 and competes directly with Microsoft Copilot's roadmap.
