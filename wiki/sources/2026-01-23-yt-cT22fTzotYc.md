---
type: youtube-video
source_date: 2026-01-23
url: https://www.youtube.com/watch?v=cT22fTzotYc
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [ai-tools, cloud-devops, homelab-selfhosting]
tags: [claude-code, ai-agents, voip, automation, mcp]
---

# FREE Phone Calls with Claude Code

## Summary

Chuck builds a system that lets him place and receive **actual phone calls with Claude
Code** — Anthropic's agentic CLI — from any phone, including an old analog handset with
no internet. The video is nominally sponsored by **3CX** (their paid AI receptionist and
AI transcription features), but Chuck "takes it too far": instead of using 3CX's built-in
AI, he wires his own self-hosted **Claude Code phone system** into 3CX using only free/
open-source components.

The core insight is that Claude Code is where Chuck "lives" — it holds the context about
him and his business, his skills, and access to his stuff — so being able to phone it
from anywhere unlocks real superpowers (having servers call *him*, firing off tasks
hands-free, etc.).

The build connects old tech (phones / SIP / VoIP) to new (an agentic terminal). Rather
than pay for the commercial VoIP framework **Jambonz** ("Jam Bones") at ~$1,000/month,
Chuck discovered Jambonz is itself built on two free open-source projects — a SIP server
(**drachtio**, garbled as "Dr. Teo") and a media server (**FreeSWITCH**) — and rebuilt
the stack himself with a few Claude Code sessions. He calls the finished product his
"Claude phone."

**The stack:** phone/analog handset → **3CX** (phone system / PBX) → a small **API
server** on his Mac that does **voice activity detection**, uses **Whisper** for
speech-to-text and **ElevenLabs** for text-to-speech → **Claude Code** (the actual brain,
with skills). SIP/media handled by **drachtio + FreeSWITCH**. Crucially, because 3CX's
free SMB tier doesn't allow custom SIP trunks, he has Claude Code **register as a phone
(an extension)** — it shows up as a person with a ready status, can make and receive
calls. He demos multiple personas as separate extensions (Morpheus, ext. 9000, his
executive assistant; Stephanie, ext. 9002, his Ceph storage cluster; Dolores, the 3CX
built-in receptionist test), plus **n8n** as an orchestrator that polls his cluster and
triggers Claude to call him when a JSON `call_chuck` boolean flips true.

The video closes with Chuck's signature end-of-video prayer, this time centered on AI
anxiety, imposter syndrome, and fear of being left behind.

## Key claims (dated 2026-01-23)

- **The whole point is context, not just "an AI."** Claude Code already holds the context
  about Chuck and his business, his workflows, and his skills — so calling it by phone
  means access to all his real stuff (skills, tools, integrations), not a generic chatbot.
- **Claude Code registered as a phone extension, not a SIP trunk.** Because 3CX's free
  SMB tier forbids custom SIP trunks, he has Claude Code register with 3CX like a regular
  phone/extension (ready status, can call and be called) — this is what makes the calls
  free and unlimited internally.
- **Free open-source stack beats the $1,000/month product.** Jambonz (the VoIP framework
  all his research pointed to) costs ~$1,000/month for a single self-hosted node; it is
  built on open-source drachtio (SIP server) + FreeSWITCH (media server), so he rebuilt
  the equivalent for free.
- **SIP vs. media are two separate concerns.** SIP (Session Initiation Protocol) sets up
  the call; a media server handles the actual audio (voice, hold music). You need both to
  build VoIP.
- **The bridge is a small API server** on his Mac (Linux/Mac only — "I'm not supporting
  Windows") doing voice activity detection + Whisper (STT) + ElevenLabs (TTS), passing
  transcribed speech to Claude Code and Claude's replies back to the SIP side.
- **A persona = a few prompts + guardrails + scoped skills.** "Stephanie" is just Claude
  Code with a system prompt ("you are Stephanie") and access limited to storage skills;
  you can spin up an entire company of such agents on distinct extensions.
- **A "call skill" lets Claude phone the user** — fire-and-forget ("call ext 1000 and tell
  me I'm awesome"), a two-way conversation, or an autonomous "call me when you're done"
  after a long task (he references using this in his Mac Studio videos).
- **n8n as orchestrator for monitoring.** A simple n8n workflow hits the API server on a
  schedule, checks Ceph cluster health, and if a parsed JSON boolean `call_chuck` becomes
  true, Claude actually calls him — otherwise it stays silent. Servers monitoring
  themselves and phoning the human on trouble.
- **Connecting to the PSTN unlocks real numbers.** Internally everything is free unlimited
  3CX extension calls; wiring 3CX to the PSTN gives a real callable number and lets Claude
  call external numbers (he had it call his wife's cell, and tried — crudely — to have it
  phone a restaurant to check New Year's hours).
- **Explicitly a POC / "janky."** Chuck stresses this is a proof of concept, that he is
  "not a developer" but understands VoIP and "cobbled this together," and that the polished
  sponsor solution (3CX's own AI) is the non-janky option for real businesses.
- **Agentic-AI takeaway:** an agentic coding tool (Claude Code) is now capable enough that
  a self-described non-developer can, in a few sessions, stand up a novel SIP/VoIP
  application, glue Whisper + ElevenLabs + n8n + a PBX together, and treat the CLI agent
  itself as an addressable endpoint with skill access — Claude Code even drew his
  architecture diagrams.

## Notable verbatim quotes

> "I just called my server. My server has a phone number, but that's not the coolest part.
> By the end of this video, you're going to watch my server call me."

> "Cloud code is where I live nowadays. It's where I build my workflows and it contains a
> lot of the context about me and my business."

> "I could be in the middle of nowhere and all I can find is a payphone and I could still
> call and talk to the most advanced AI known to man."

> "So what if I gave Claude code the ability to sip? I could give him a phone number and
> three CX could communicate with him over sip."

> "I almost spent a thousand dollars a month to get this working. ... $1,000 a month for a
> single node self-hosted server. I was about to do it. I was reaching for my wallet."

> "I have Claude code ... registering with the three CX phone system like it's a phone,
> just a phone. It shows up as a person, it has a ready status, it can make calls and we
> can make calls to it."

> "The power here is not that I'm just talking to some AI. This is Claude code, my claw
> code, unlocking ridiculous things like skill access and access to all my stuff."

> "It's just a few prompts and a few guardrails. And the beauty of this is that you'll be
> able to create whoever you want to create ... You can create an entire company of these
> guys."

> "That's not me. I think it heard me say cloud and not Claude." *(on a botched thumbnail)*

> "I'm calling it my Claude phone now because I'm kind of a developer now. Everyone is."

> "Keeping in mind, I'm not a developer. I just cobbled this together because I understand
> VoIP technology and how it's supposed to work."

> "Claude code has been the thing that everyone's been talking about, and if you haven't
> played with it, you should, but be careful because it's very addicting and it can kind of
> consume you. The more you get into it, the more you feel left behind. And that's what I'm
> feeling, a ton of imposter syndrome, a ton of stress over all this."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: Claude Code agentic-coding project (AI-agents era) -->
