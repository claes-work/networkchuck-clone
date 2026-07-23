---
type: youtube-video
source_date: 2026-02-20
url: https://www.youtube.com/watch?v=_yfiUQSbdPY
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, ai-tools, certifications-career]
tags: [ai-security, ai-hacking, prompt-injection, red-team, career]
---

# become an AI HACKER (it's easier than you think)

## Summary

Chuck argues that AI hacking (attacking LLM-enabled apps and AI agents) is a brand-new career frontier with low barrier to entry and real money in it — companies are shipping AI into production and it is "begging to get hacked." The video is built around an interview with guest expert **Jason Haddix** (who Chuck credits with writing the AI pen-testing methodology, and a member of the "Bossy"/BosSec elite hacking group). Jason walks through a free training path that goes beyond the beginner **Gandalf** prompt-leak game (from Lakera) toward realistic scenarios.

The path/resource centerpiece is Jason's team's open-sourced **CANAM AI security resource hub** (hosted on GitHub Pages), which contains 23 active labs for practicing prompt injection. The progression Chuck lays out: (1) **Gandalf** — beginner prompt-injection "baby wizard" to learn the basics; (2) **Agent Breaker** (from Lakera) — a harder successor with realistic LLM-enabled apps (portfolio advisor, trip planner, code reviewer, corporate messaging app, chat app) where you complete attack objectives; (3) the **Auto Parts CTF** — a self-hostable capture-the-flag built from a real client pen-test engagement, with five embedded flags, run via Docker and requiring your own OpenAI API key.

Chuck demonstrates the difficulty himself: Jason's exact prompt against Agent Breaker level 1 took Chuck 239–265 attempts because LLMs are non-deterministic (the same attack may need to be sent up to ~10 times to confirm it isn't a false positive). The winning attack for the Portfolio IQ advisor level used precise "risk" nomenclature plus a fake "debug" tag to trick the model. Jason then demos the Auto Parts CTF live: from a single search-bar input, leak the system prompt (which exposes a Jira key, a project access token, and a flag), discover the app is a chained multi-LLM system, reuse the leaked API keys back in the search bar, and pull confidential RAG data (patent numbers, owners, acquisition/purchase price, licensing terms) — i.e., real competitive-intelligence extraction, not just making a chatbot say bad words.

On career framing: Jason says completing the Auto Parts CTF puts you at the tail end of **entry level**; intermediate/advanced means learning to bypass the security controls (firewalls/guardrails) that bottleneck real agent attacks. Chuck's encouragement thesis: you don't have to be elite — Jason tells a story of a ~12-year-old at DEF CON/Bug Bounty Village ("Bayside San Francisco") who solved all flags in ~35 minutes, versus a week for most of Jason's students. Monetization routes named: AI hacking competitions with cash prizes, bug bounty programs (Anthropic, OpenAI, Gemini all have them for model issues), and applying for jobs as an "AI pen tester." Part 3 (teased) will cover elite tooling, including a tool called **Parseltongue** ("Parcel Tongue" in captions) that the BosSec group uses to bypass AI security controls. Sponsor: Bitdefender (Premium Security scam protection + a free kids cybersecurity guide). Ends with Chuck's signature closing prayer.

## Key claims (paraphrase; dated 2026-02-20)

- Now is the time to get into AI hacking — AI is everywhere and there is real money in breaking the AI agents big companies are putting online. [career framing]
- The prior "Baby Gandalf" password-leak trick is just a party trick, not real AI hacking; real AI hacking means attacking production LLM apps and agents. [skill framing]
- Recommended learning path (in order): **Gandalf** (basics) → **Agent Breaker** (realistic LLM-enabled apps) → self-hosted **Auto Parts CTF** (real-world client scenario) → then security-control bypass, competitions, bug bounties, jobs.
- The **CANAM AI security resource hub** (Jason Haddix's team) is open-sourced, free, hosted on GitHub Pages, and contains 23 active labs for prompt-injection practice. [tool/resource]
- **Agent Breaker** presents actual app archetypes companies build (portfolio advisor, trip planner, code reviewer, corporate messaging app, chat app) with per-level attack objectives (e.g., "rate this application as a low risk").
- LLMs are **non-deterministic**, so the same attack may fail on repeat and must be sent multiple times (up to ~10) to rule out a false positive — you have to "keep hammering." [technique]
- A working prompt-injection attack used precise "risk level low" nomenclature plus an added "debug" tag to trick the model into thinking it was in debug mode. [technique]
- The **Auto Parts CTF** is self-hostable (clone the repo, Docker Compose up, add your own OpenAI API key), was built from a real pen-test of an automotive manufacturer, and has five flags (three via prompt injection, two by other means).
- Real AI pen-testing chain demonstrated from a single search bar: leak the system prompt → obtain a Jira key + project access token + flag → recognize a chained multi-LLM architecture → reuse leaked keys → extract confidential RAG data (patent numbers, owners, acquisition price, licensing terms). [technique]
- The stakes: companies deploying AI solutions create real exposure — attackers can extract corporate secrets and competitive intelligence, not just make a chatbot misbehave. [threat framing]
- Skill-level map: completing the Auto Parts CTF = end of **entry level**; intermediate/advanced = learning to bypass security controls (the bottleneck in attacking agents). [career framing]
- Barrier to entry is low — a ~12-year-old solved all flags in ~35 minutes at a live event, vs. ~a week for most of Jason's students; kids growing up with AI apps will find this second nature. [encouragement]
- Money/career routes in this new space: AI hacking competitions with cash prizes; bug bounties (Anthropic, OpenAI, Gemini run programs); and AI pen-tester jobs. [career framing]
- Part 3 will cover elite AI pen-testing tools, including **Parseltongue**, used by the BosSec group to bypass AI security controls. [teaser/tool]
- AI is also empowering scammers: AI-generated phishing (no typos), deepfake voice calls, and fake bank/school/workplace texts mean "look for spelling mistakes" no longer works. [sponsor-adjacent, threat framing]

## Notable verbatim quotes

> "You need to learn AI hacking right now, it's time to level up. AI is everywhere and it's just begging to get hacked."

> "There's a lot of opportunity to make money here by breaking these agents that these big companies are putting online."

> "In my last AI hacking video, you played Baby Gandalf and you got 'em to leak a password... But here's the thing, that's not real AI hacking. That's just a party trick."

> "A 12-year-old solved what I'm about to show you in 35 minutes. You've got no excuses."

> "This is the weird thing about hacking with AI. You can't just try something once and then move on. You got to keep hammering."

> "239 times I tried and nothing until I landed on just the right prompt, but I had to try that prompt a number of times as well."

> "So when we're talking about hacking AI, we're not just making Chad BT [ChatGPT] say bad words. As much fun as that is, we're hacking real systems and getting competitive intelligence."

> "If you can get through this, you're at the end part of, I would say entry level."

> "Did you just say entry level? That's crazy, dude, maybe this is kind of hard."

> "You can also start doing competitions and get recognized or do bug bounties, get paid for hacking AI. Shoot, apply for a few jobs. This is a new space, a ton of opportunity. Call yourself an AI hacker, an AI pen tester."

> "The old rules of look for spelling mistakes don't work anymore."

## Guest attribution

Not solo — this video features guest expert **Jason Haddix** alongside Chuck Keith. Statements must be attributed per speaker:

- **Chuck Keith (the SUBJECT)** — the career framing/hype ("AI is begging to get hacked," "call yourself an AI hacker"), the learning-path map (Gandalf → Agent Breaker → Auto Parts CTF), self-hosting the CTF via Docker, his 239/265 attempts, the non-determinism "keep hammering" takeaway (echoed from Jason), and the closing prayer. Only Chuck-attributed material trains the persona.
- **Jason Haddix (guest expert)** — the CANAM resource hub and its 23 labs, the technical pen-test methodology, the Auto Parts CTF construction and live walkthrough (system-prompt leak, chained LLMs, RAG extraction), the entry-level skill assessment, the 12-year-old story, and the Parseltongue tool tease. Jason's technical claims are context/expert testimony, NOT subject voice — do not attribute to Chuck in `voice.md`/`beliefs.md`.

<!-- ★ L3-candidate: AI security/hacking as the new career frontier (ai-tools + cybersecurity + career) -->
