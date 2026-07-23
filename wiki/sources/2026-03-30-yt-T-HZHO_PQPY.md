---
type: youtube-video
source_date: 2026-03-30
url: https://www.youtube.com/watch?v=T-HZHO_PQPY
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [ai-tools]
tags: [openclaw, ai-agents, personal-ai, agentic-ai, self-hosted, vps, telegram, security, prompt-injection, cron, memory, homelab]
---

# OpenClaw......RIGHT NOW??? (it's not what you think)

## Summary

Chuck walks through OpenClaw, an open-source "gateway" for personal AI agents that had exploded in popularity (he cites 308,000 GitHub stars, "beating React and the Linux kernel," and says its creator "Peter" was acqui-hired by OpenAI). Breaking his own "YouTube rule," he sets up a working agent live at the top of the video: spin up a Hostinger VPS (the sponsor), SSH in, run OpenClaw's one-line installer, pick an AI model (he uses an OpenAI ChatGPT subscription via OAuth), connect a Telegram bot via BotFather, and give the agent an identity ("Terry Crews," a chaotic NetworkChuck fan) written to its `soul.md`.

The core thesis — the "not what you think" twist — is that **OpenClaw is not an AI itself; it's a harness/gateway**, a Node.js service running 24/7 that wires together four things: (1) any AI model you choose (OpenAI, Anthropic, or local via Ollama), (2) **channels** (it comes to you on Telegram/Discord/Slack instead of making you visit a platform), (3) **memory** (markdown files — `soul.md`, `identity`, `memory`, a daily journal directory — living on your own VPS), and (4) **tools** on the host machine (bash, cron, heartbeats, a headless browser, skills, subagents). He demos it one-shotting a news-briefing dashboard and an IT-monitoring dashboard — tasks he'd previously built laboriously in n8n.

Chuck is openly ambivalent: he finds it fun and impressive but "kind of hates it" and stresses that it is **not groundbreaking** — the tooling already existed; OpenClaw's achievement was packaging it into one clean install that made agentic AI feel accessible ("a collective light bulb"). A large security segment warns that a fresh install makes you "a walking, talking CVE" (prompt injection, malware in ClawHub skills — he cites 12% of skills found with malware) and walks through the `openclaw security audit`, firewall/loopback binding, SSH tunnel to the web UI, tool profiles (`coding` vs `full`), exec security modes, and agents.md "redlines/yellowlines." Verdict: for serious work he still prefers Claude Code; OpenClaw he uses for purpose-built personal agents (an IT team, a Japanese-speaking assistant, a fitness coach). Ends with his signature prayer for the audience about finding identity beyond their job in an AI-shaped world.

> Note: A later NetworkChuck video (2026-05-20) says "goodbye OpenClaw" in favor of Hermes — so this tool was subsequently superseded. This page captures the 2026-03-30 video faithfully.

## Key claims (paraphrase, dated 2026-03-30)

- OpenClaw is **not an AI** — it is a gateway/harness, a layer that sits on top of whatever AI model you choose; it's a Node.js app running 24/7 on your machine (visible via `ps aux | grep claw`).
- It connects roughly four pillars: (1) **your choice of model** (OpenAI, Anthropic, or local models — Ollama is now officially supported), (2) **channels** — the AI comes to you on Telegram/Discord/Slack rather than requiring you to visit a platform, (3) **memory** — plain markdown files (`soul.md`, `identity`, `memory`, plus a daily-journal `memory/` directory) stored on your own VPS, and (4) **tools/permissions** on the host (bash, cron, heartbeats, browser, skills, subagents).
- It was extremely popular at the time: ~308,000 GitHub stars ("beating React and the Linux kernel"), and its creator (referred to as "Peter") was acqui-hired by OpenAI.
- It is **not groundbreaking**; comparable tooling already existed and some software does parts better. What made people "freak out" was that it packaged everything into one clean install and made agentic AI feel accessible — plus the viral framing of buying a Mac mini and onboarding an AI as a "new employee" with its own computer.
- Setup is fast and can be done anywhere you can install the gateway; Chuck demos it on a Hostinger VPS (KVM 2), installs via the one-line command from `openclaw.ai`, authenticates a model, and connects a Telegram bot created through BotFather.
- You configure OpenClaw by talking to it — the identity you type in the TUI is written to the agent's `soul.md`; Peter separates `identity` from `soul` (Chuck finds that "creepy" for a chatbot).
- **Heartbeats and crons** are what make the agent feel "alive": crons are real scheduled tasks on your server (e.g., a 6 a.m. daily news briefing); heartbeats let the agent check in periodically. Chuck says OpenClaw does this better than competitors right now, who are copying it.
- **Skills** come from a directory called **ClawHub** (npm-installable; `clawhub install`) with 33,000+ skills — but it's a major security risk: he cites that 12% of skills were found with malware, and notes a VirusTotal partnership. Vet everything.
- **Security**: a fresh install is dangerous ("you're a walking, talking CVE" — prompt injection, malware in skills). Mitigations shown: `openclaw security audit` (`--deep`, `--fix`), ensuring the web UI is not internet-exposed (bound to loopback `127.0.0.1`, port `18789`, reached via SSH tunnel), enabling the host firewall (allow only SSH/22), tool profiles (`tools.profile` = `coding` vs `full`), exec security modes (`tools.exec.security` = full / allowlist / deny; `tools.exec.ask`), and **redlines/yellowlines** in `agents.md` (instructions the agent should obey — but "just a prompt," nothing deterministic enforces them).
- Industry validation: Jensen Huang called OpenClaw "the operating system for personal AI"; Nvidia built its own version, "Nemo Claw" (reportedly very insecure); Anthropic is reportedly building its own; the intro also notes Anthropic "dropped channels and dispatch" the prior week.
- **Verdict**: For serious work (research, scripting, some coding) Chuck normally uses **Claude Code**, which he says has better tooling and overall experience. He uses OpenClaw for purpose-built personal agents: an IT team (a CTO plus network/storage/systems engineers running his home lab), a personal assistant ("Hermione") that checks his email and makes Japanese restaurant reservations by phone while he's in Japan, and a fitness coach ("Arnold Schwarzenegger"). He considers himself in "dabble mode" and plans an OpenClaw series.

## Notable verbatim quotes

> "you may not have known this, but Open Claw is not itself an AI. It's a harness. It's a layer sitting on top of other AI."

> "OpenClaw it's simply a gateway. It's a gateway that connects a few things together."

> "Most AI companies say, 'Hey, if you want to talk to our AI, come to our platform. Come to us.' OpenClaw is like, 'No. Whatever you're using, we'll come to you. Telegram, Discord, Slack, we'll do it.'"

> "You just configured Open Claw, one of the most insecure things out there. Prompt injection, malware hidden in the skills. You're a walking, talking CVE."

> "it does feel like magic but it's just a stinking scheduled task on your server. Genius for how simple that is."

> "Now, is this groundbreaking? No. No, it's not. A lot of this has already been done... What this did though, and this is the reason everyone freaked out, is it made everything seem accessible. It packaged everything together in one clean install."

> "Jensen Huang called Open Claw the operating system for personal AI."

> "12% of skills were found with malware. I mean, ooh, be very careful. Vet everything."

> "Open Claw is really fun. But, for serious work, I am normally going to be using Claude code... I think it has better tooling and an overall better experience for things that I do, which is like research and scripting, a little bit of coding here and there."

> "essentially, I have a bunch of very purpose-built agents I use. And I know I haven't fully unlocked the power because... You have to spend a lot of time to think about that and figure it out. So, I'm kind of in dabble mode."

> "This software is the reason AI has been stressing me out so much... you can't ignore it even though I want to, even though I kind of hate it. It's here."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: Defines OpenClaw's "gateway/harness not an AI" framing and Chuck's four-pillar model of personal AI agents (model + channels + memory + tools); states his working preference (Claude Code for serious work, OpenClaw for purpose-built personal agents) and his agentic-AI security stance — durable persona/beliefs material, and the anchor of an announced OpenClaw series later superseded by Hermes (2026-05-20). -->
