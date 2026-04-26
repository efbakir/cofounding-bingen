# Agents

Five subagents. Each does one thing in the chain and returns output to the main Claude.

| Agent | Model | Responsibility |
|---|---|---|
| `idea-explorer` | opus | Reduces raw ideas to 3-4 testable hypotheses |
| `problem-hunter` | opus | Takes a hypothesis and finds real evidence of the problem on Reddit/HN/X/IH |
| `pain-validator` | opus | Scores findings on intensity × frequency × WTP |
| `community-mapper` | opus | Identifies where these users live (subs, Discord, who they follow) |
| `build-in-public-writer` | opus | Drafts platform-specific build-in-public posts to recruit testers |

## Typical chain

```
idea-explorer  →  problem-hunter  →  pain-validator
                                       ↓
            build-in-public-writer  ←  community-mapper
```

## Why are all of them on opus?

This repo wins on **decision quality**, not speed. A single false positive ("these people will pay") leads to weeks of building the wrong thing. Sonnet would be enough for some agents, but the default is opus. Each agent's frontmatter has a `model:` line if you want to override.

## Setup

Copy these files into `~/.claude/agents/` (global) or `.claude/agents/` (project-only). See the root README for details.
