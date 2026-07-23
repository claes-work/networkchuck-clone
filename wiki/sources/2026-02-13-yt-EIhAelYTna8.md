---
type: youtube-video
source_date: 2026-02-13
url: https://www.youtube.com/watch?v=EIhAelYTna8
channel: "@networkchuck_v2"
ingested: 2026-07-22
tier: L2
domains: [ai-tools, homelab-selfhosting, cloud-devops]
tags: [claude, 3cx, voip, tutorial, ai-agents]
---

# Talk to Claude on 3CX Phone System Tutorial (Full Setup)

## Summary

The step-by-step how-to companion to Chuck's main-channel showcase "FREE Phone Calls
with Claude Code" (2026-01-23). Where the main-channel video demoed the idea — calling
Claude Code on a real phone and having it answer with a voice — this second-channel
video walks through the actual build end to end using his own "Claudphone" GitHub repo.
Chuck opens by stressing he is "not a developer" but is "pretending to be now with
Claude Code," and that the repo plus this walkthrough fill in gaps the documentation
doesn't cover.

The build has two halves. First, a free 3CX cloud phone system (hosted, up to 10 users)
that gives you business-style extensions and free VoIP calls between phones. Second,
"Claude phone" itself, which is two services: a voice server (handles the VoIP / SIP
call audio, runs Docker containers FreeSWITCH + DRACHTIO) and an API server (a wrapper
around Claude Code that converts phone-call audio into messages Claude Code can receive
and respond to). The voice server also doubles as a 3CX SBC (session border controller)
that bridges home-network devices to the 3CX cloud. Chuck installs the voice server on a
Raspberry Pi 5 and the API server on a Linux VM, though he notes both could in theory
run on one device (untested at recording time). For AI voice he uses ElevenLabs (TTS,
paid) and OpenAI Whisper (STT, pay-as-you-go). He demos creating user "Susie Claude"
(an extension that IS Claude Code), calls her, gets a weather answer, then adds a second
personality "Stewart Ross" with a different voice (Oliver) and a dad-joke help-desk
system prompt — illustrating that you can spin up multiple voiced Claude agents and even
point one at a homelab task (e.g. a skill to troubleshoot a NAS or Proxmox). Closes with
his second-channel prayer for the audience.

Companion how-to to the main-channel showcase; concept already established there.

## Key claims (dated — stack + steps)

Stack (2026-02-13):
- **3CX Cloud** — free hosted PBX for up to 10 users; provides extensions and free
  VoIP calls; setup takes ~30 seconds. (paraphrase)
- **3CX SBC (Session Border Controller)** — free; runs on the voice-server device inside
  the home network; acts as middleman letting local devices/phones register with the
  3CX cloud. (paraphrase)
- **Voice server** — handles VoIP / SIP call audio; runs Docker containers FreeSWITCH
  and DRACHTIO; installed here on a Raspberry Pi 5. (paraphrase)
- **API server** — wrapper around Claude Code that translates phone audio to/from Claude
  Code messages; must run on the same machine as Claude Code (Mac, Linux server, VPS, or
  Raspberry Pi all work); installed here on a Linux VM; default port 3333. (paraphrase)
- **ElevenLabs** — TTS to give Claude a voice; paid; chosen for quality and multiple
  selectable voices/personalities. Requires an API key + voice ID. (paraphrase)
- **OpenAI Whisper** — STT to transcribe caller speech for Claude; pay-as-you-go.
  Requires an OpenAI API key. (paraphrase)
- Hardware: best case two servers (any mix of Linux boxes / Raspberry Pis / a Mac
  desktop for the API server), or in theory a single Linux device. (paraphrase)

Steps (2026-02-13):
1. **Set up 3CX Cloud** — go to 3cx.com, log in (Google works), My Systems → Add System,
   choose the "less than 10 users" free cloud-hosted option; save the returned login
   info; download the 3CX mobile app and scan the QR code to register your first phone.
   (paraphrase)
2. **Flash Raspberry Pi OS for the voice server** — use Raspberry Pi Imager; do NOT use
   the latest OS — the 3CX SBC doesn't support it yet. Choose Raspberry Pi OS (other) →
   Bookworm → Raspberry Pi OS Legacy 64-bit Lite (command-line). (paraphrase)
3. **Add the SBC in 3CX** — admin cog → Voice and Chat → Add SBC → choose Linux/Raspberry
   Pi → run the provided install command on the Pi; when prompted, paste the provisioning
   URL (the `*.cx.cloud` portal address) and the authentication key. Verify it shows green
   / "up" under Voice and Chat statistics. (paraphrase)
4. **Install the API server** — on the Claude Code machine, run the repo's one-line
   installer (checks prereqs: Docker, Node.js, Claude installed), then `claude phone
   setup`, select "API server," accept default port 3333, and `claude phone start`;
   verify the port is listening (`ss -tulpn | grep 3333`) and that `claude` is installed.
   (paraphrase)
5. **Install the voice server on the Pi** — run the same one-line installer; if needed
   run `newgrp docker` so Docker works; run `claude phone setup`, choose "voice server"
   (it auto-detects the installed SBC), give it the API server's IP + port 3333, and
   paste the ElevenLabs API key, voice ID, and OpenAI API key. (paraphrase)
6. **Create the Claude user in 3CX** — Users → add user (e.g. "Susie Claude") → IP Phone
   → "I will configure a phone myself" → connect via the SBC → Add Phone; paste the
   `*.cx.cloud` hostname, extension, SIP auth ID, and SIP auth password; optionally set a
   system prompt; confirm the Pi's IP is used for audio/VoIP/HTTP. (paraphrase)
7. **Start and test** — `claude phone start` brings up the FreeSWITCH/DRACHTIO Docker
   containers (`docker ps` to confirm healthy); call the Claude user's extension from a
   3CX phone and talk. (paraphrase)
8. **Add more personalities** — create additional users (e.g. "Stewart Ross"), add them
   as Claude phone devices with their own extension/SIP creds, pick a different voice
   (e.g. Oliver), and give each its own system prompt; restart Claude phone. (paraphrase)

Notes:
- A failed first weather test ("Sorry, something went wrong") was NOT a software bug — it
  was an exhausted OpenAI account needing billing added. (paraphrase)
- No hold music is bundled yet because Chuck's own track is copyrighted; he plans to add
  free hold music to the automatic setup later. (paraphrase)
- Chuck says he may later add local/open-source model support, and invites forks; he also
  warns he won't support the project forever. (paraphrase)

## Notable verbatim quotes

- "Claude phone. You can call Claude with your phone and Claude can call you on your
  phone."
- "Disclaimer, I'm not a developer, but I'm pretending to be now with Claude Code."
- "Now, if you watched the previous video, you'll know this is going to involve the 3CX
  phone system somehow. And don't worry, what we're doing with 3CX is going to be
  completely free because we're going to be deploying a phone system in the cloud. And
  this seriously takes about 30 seconds."
- "This API server ... all it's doing is converting the phone call stuff to messages that
  Claude Code can ... receive and then respond to."
- "In theory, we should be able to do everything on a Raspberry Pi, including Claude
  Code."
- "To make Claude talk, to give him a voice, we have to use TTS ... For that, we're going
  to [use] ElevenLabs. This is not a free service. It is paid, but I chose this because
  it's amazing."
- "Don't you dare try to write the latest OS to this card because the 3CX SBC does not
  like it right now."
- "So you can call and talk to your Proxmox server. You can say like you are a Proxmox
  server. This is your stinking job. This is all you do. That's cool. At least I think it
  is."
- "The issue wasn't with my software. The issue was that I ... needed to add some billing
  to my Open AI."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
