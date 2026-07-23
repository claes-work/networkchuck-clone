---
type: youtube-video
source_date: 2026-05-20
url: https://www.youtube.com/watch?v=QQEgIo4Juxg
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [ai-tools]
tags: [hermes, openclaw, ai-agents, nous-research, agent-harness, agentic-memory, self-improvement, telegram, homelab, vps]
---

# you need to use Hermes RIGHT NOW!! (goodbye OpenClaw!!)

## Summary

Chuck announces he is switching all his agent setups from **OpenClaw** to **Hermes**, an AI agent harness built by **Nous Research**. Like OpenClaw, Hermes is a harness (a set of tools) that runs on top of whatever LLM you point it at (local via LM Studio/Qwen, or frontier via OpenRouter, OpenAI Codex/ChatGPT subscription, and — per a "Chuck from the future" insert — a Grok subscription). He frames Hermes as the fastest-growing GitHub project, having topped OpenClaw in OpenRouter token usage.

The video is a hands-on install tutorial (on a Hostinger VPS, the sponsor) plus an interview with Nous Research cofounder **Jeffrey Quesnelle (Jeff)**. Chuck builds an IT agent named "Ron Weasley" (a Hogwarts/IT-wizard themed troubleshooting agent) wired to Telegram, and demonstrates memory, self-built skills, Twingate network access, Home Assistant control, and UniFi management.

He gives five reasons for switching: (1) the vibe/mission of the company, (2) memory that is actively curated during sessions, (3) the people and origin story behind the tool, (4) the self-improvement loop / skill system (his favorite), and (5) it "just doesn't break" — it feels like a product, not a project. Origin note: Hermes actually predates OpenClaw — it started ~6-7 months earlier as an internal Nous Research tool for prototyping recursive self-improvement in model training. This is another instance of Chuck's fast tool-churn: he replaces a tool he heavily promoted (OpenClaw, 2026-03-30) roughly two months later.

## Key claims (paraphrase; dated 2026-05-20 unless noted)

- **What Hermes is:** an AI agent harness (a set of tools) from Nous Research that runs on top of any LLM you choose — local (LM Studio, especially Qwen) or frontier (OpenRouter, OpenAI Codex using a ChatGPT subscription, or a Grok subscription). Lightweight, built in Python, runnable almost anywhere; Windows-native support is said to be coming soon.
- **Nous Research** is the company behind Hermes — a group of AI researchers who train their own open-source models (also named Hermes; the Hermes *models* are separate from the Hermes *agent*). Origin: "a bunch of hacker nerds in a Discord" building open-source, humanistic, censorship-free, democratic AI.
- **Hermes predates OpenClaw:** it began ~6-7 months prior as an internal tool to prototype recursive self-improvement for model training. When OpenClaw launched, Nous found their internal tool less clunky, so they released their version.
- **Momentum:** described as the fastest-growing GitHub project; recently topped OpenClaw on OpenRouter token usage. Offers an OpenClaw migration path (user/memory files transfer over); the two can run side by side for testing.
- **Reason 1 — vibe/mission:** the site and branding reflect a company with a mission, not a "random lobster project"; the vibe alone sold him.
- **Reason 2 — memory:** Hermes maintains a `USER.md` (what it learns about you) and `MEMORY.md` (environment/technical context), auto-curated by the agent and loaded into the system prompt each new session. Differentiators vs OpenClaw: (a) **hard size limits** — user file capped at 1,375 characters, memory file at 2,200 — forcing the agent to distill and curate rather than bloat; (b) it **nudges roughly every 10 turns** to run a background agent that fact-checks/updates memory *during* the session, not just at compaction/new-session time.
- **Memory add-on (Honcho):** an optional peer service (local or cloud) that reasons over your messages, builds a "peer card" of your traits/preferences, and injects what the agent needs to know about you in the moment. Works better as a first-class citizen in Hermes than bolted onto OpenClaw. (Chuck flags this as a possible future standalone video.)
- **Reason 3 — the people/story:** Nous are AI researchers building their own models; Chuck values who makes AI tools and why (humanistic, censorship-free, democratic).
- **Reason 4 — self-improvement loop / skill system (his top pick):** Hermes agents **build their own skills** from your interactions (crystallizing repeated workflows), rather than downloading them from a marketplace. Demoed: Ron auto-created a "Twingate client operations" skill and a "UniFi network operation skill" without being told to. Ships a curated built-in skill library (e.g. a high-quality GitHub PR-review skill distilled from thousands of manual reviews). A new **"Curator"** background agent periodically reviews/prunes/improves skills, moving them through active/stale/archive states so self-generated skills don't pile up.
- **Security contrast:** OpenClaw is characterized as having had malware in community skill repos and multiple CVEs; Chuck says Hermes had no agent-related security incidents as of this video, crediting its simplicity and curated-skills philosophy.
- **Reason 5 — reliability:** OpenClaw "feels like a project" that degraded/broke over time (updates broke it, unresponsive); Hermes "feels like a product" and, after a month of use, gave him essentially no issues he didn't cause himself. Stable enough that he gave an agent to his wife (named "Honey") to help with homeschooling, diet planning, and managing the house for their six daughters.
- **Philosophy (from Jeff):** "get out of the way of the models" — models are smart enough to figure out what you want; the harness is the "haptic feedback," giving the model hands/feet to touch the world. Nous deliberately ships fewer messaging/integration options than OpenClaw, preferring a great experience with a few options over supporting everything.
- **Shipping features:** a Hermes dashboard (skills, plugins, multiple agents/profiles, auxiliary models for research/delegation), achievements ("agent autonomy" gamification), a **Kanban** task board (assign tasks to profiles; stops for human input; blocked by usage/rate limits in the demo), and a newly released **computer use** (still in preview).
- **Model context (dated):** references frontier models "Opus 4.7" and "GPT 5.5" as current/good, and speculates that if models stopped improving now, the field would still be near AGI — so the harness matters most.
- **Tool-churn / self-awareness:** Chuck jokes he is trying hard not to say "right now" this year (a nod to his catchphrase and to churning through tools), but insists Hermes is "something special" and worth the token spend. Note the pattern: he had promoted OpenClaw on 2026-03-30 and is replacing it ~7 weeks later.
- **Not sponsored by Nous:** Chuck states Hostinger sponsors the video, but he is not sponsored by Nous Research / Hermes — he's "kind of a fanboy" on his own.

## Notable verbatim quotes

> "I'm switching to Hermes. The vibe, the mission, that alone sold me. But the idea that the Hermes agent grows with you, that's gonna be better on day 30 than day one. That got me hooked."

> "Also because I'm tired of fixing my OpenClaw agents, and I'm not the only one. This is now the fastest growing GitHub project. It just topped OpenClaw on the OpenRouter token usage."

> "I've been using it for a month, and it's the only agent I felt comfortable enough with to give to my wife. She calls hers honey. It's her BFF."

> "Similar to OpenClaw, Hermes is a harness. It's a set of tools that would use whatever LLM you want."

> "The first thing it does is it has hard limits on the size of those files. The user file can only be 1,375 characters. The memory file, 2,200 characters. Now why does this matter? Well, it forces the agent to be very particular about what's gonna be loaded into its system prompt."

> "Ron just made his own skill. That's the power of Hermes. It makes its own skills."

> "With OpenClaw, it's all about finding skills in a marketplace, whereas Hermes is all about building skills, repeatable workflows based on your interactions with Hermes."

> "And that's how OpenClaw feels. It feels like a project, whereas Hermes feels more like a product."

> "So number five, in case you didn't realize it, was that Hermes just doesn't break."

> "AI is not meant to replace you. It's meant to make you be a better version of you every day."

> "I'm not sponsored by them, but I think they're really cool. Let me know what you think. Like, try Hermes, and you can run OpenClaw and Hermes side by side."

Jeff Quesnelle (Nous Research cofounder — context, NOT the subject):

> "So, actually, Hermes agent started out as an internal tool that we wrote started it almost six to seven months ago as a tool we were using internally to, like, prototype this recursive self improvement for model training."

> "Get get out of the way of, like, them and, like, let the models be smart, basically."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT). The video also contains interview clips from **Jeffrey Quesnelle ("Jeff")**, cofounder of Nous Research; his statements are quoted above under his own name and are context only (a non-subject entity), NOT persona training material for Chuck.
