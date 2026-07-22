---
type: youtube-video
source_date: 2025-03-13
url: https://www.youtube.com/watch?v=JJ_0-pAOIEk
channel: "@networkchuck_v2"
ingested: 2026-07-22
tier: L2
domains: [ai-tools, homelab-selfhosting]
tags: [open-webui, ollama, local-ai, self-hosting, private-ai]
---

# how to host Open WebUI locally (self-hosted AI Hub)

## Summary

A short, focused tutorial on Chuck's second channel walking through how to self-host
[[../entities/open-webui|Open WebUI]] on-premises — a self-hosted, open-source web
interface for running whatever AI you want, framed as a "ChatGPT but you call the shots"
private AI hub. Chuck stresses repeatedly that Open WebUI is *only* the web interface and
ships with no AI models baked in; you must connect AI to it separately — either local
models via [[../entities/ollama|Ollama]] running on-prem, or cloud models (ChatGPT,
Claude, Grok, Gemini) plugged in via API. The install runs on Linux (native, Mac, or
Windows via WSL) using Docker and Docker Compose. The video reinforces his private /
self-hosted AI ethos: run your own AI stack, own your data, control your own
configuration.

## Key claims (dated — setup + concept)

Concept (2025-03-13):
- Open WebUI is a self-hosted, open-source interface for whatever AI you want to host —
  "think of it like ChatGPT but you call the shots," and it is very powerful. (paraphrase)
- Open WebUI is *only* the web interface — it contains no AI models on its own; you have
  to connect AI into it separately. Chuck repeats this warning several times so viewers
  don't have inflated expectations. (paraphrase)
- To run everything fully on-prem, you connect AI via Ollama, which he calls a great way
  to run local AI models inside a ChatGPT-like interface. (paraphrase)
- Alternatively (and he says he's very excited about this) you can plug in cloud-based
  models — ChatGPT, Claude, Grok, or Gemini — but they don't come baked in. (paraphrase)

Setup (2025-03-13):
- Requirement: Linux, because this runs as a web server accessed through a browser. Linux
  can be native Linux, a Mac, Windows running WSL (Windows Subsystem for Linux), or
  something lightweight like a Raspberry Pi — the workload is not heavy. (paraphrase)
- Prerequisites are Docker and Docker Compose; he doesn't cover installing them in this
  video and points to a separate video for that. (paraphrase)
- Steps: launch a Linux terminal (he uses his Ubuntu WSL instance), `mkdir open-webui`,
  `cd` into it, create `docker-compose.yml` with Nano, and paste in the provided config.
  (paraphrase)
- The Compose config pulls the Open WebUI image, maps a volume so data/configuration
  persist even when the container is removed, and maps ports — Open WebUI uses port 8080
  by default, remapped to 3000 for access. (paraphrase)
- Launch with a single command: `docker compose up -d`; the build is very fast. Verify
  with `docker ps`, then open a browser to `localhost:3000`. (paraphrase)
- On first load you create an account and you're in — still with no models. To add models,
  go to top-right → Settings → Admin Settings → Connections, where you can add cloud models
  (OpenAI, Claude, Gemini, Grok) or point it at an Ollama server. Chuck notes he has an
  Ollama server running on another machine. (paraphrase)

## Notable verbatim quotes

> "which if you don't know is a self-hosted open source interface for whatever AI you want
> to host think of it like [ChatGPT] but you call the shots and it is crazy powerful"

> "I'm showing you how to install open web UI just the web interface the web interface
> itself will not contain AI you'll have to connect AI into it"

> "[Ollama] is a great way to run local AI models and you can use them in a very [ChatGPT]
> like interface inside open web UI"

> "another one that I am very excited about is hooking up [ChatGPT] cloud-based models also
> Claude or [Grok] or Gemini you can plug those in but they won't come baked in"

> "now with one command we'll have this bad boy up and running Docker compose up- D just
> like this hit enter and it's building it's done that was so fast"

> "this is my second Channel if you're not subscribed you're crazy"

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
