---
type: youtube-video
source_date: 2025-03-13
url: https://www.youtube.com/watch?v=nQCOTzS5oU0
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [ai-tools, homelab-selfhosting]
tags: [open-webui, litellm, self-hosted-ai, ai-workflow, llm-router]
---

# I'm changing how I use AI (Open WebUI + LiteLLM)

## Summary

Chuck walks through his current, unified way of using AI: a single self-hosted
web interface — **Open WebUI** — that he connects to every model he cares about
through **LiteLLM**, an OpenAI-compatible proxy/gateway that routes to 100+ AIs
(local and cloud). Open WebUI is the front-end (a ChatGPT-like chat UI); LiteLLM
is the router that sits alongside it and lets him plug in providers Open WebUI
can't natively connect to (Anthropic/Claude, Gemini, Grok, DeepSeek via Groq,
etc.). Local models run via **Ollama** (e.g. Llama 3.2) on the same box.

He deploys the whole stack on a VPS (the video's sponsor is Hostinger; KVM 2
plan, AMD EPYC / 8 GB RAM), installing Open WebUI + Ollama from an app template
on Ubuntu 24.04, then adding LiteLLM by `git clone`-ing the LiteLLM repo and
running it via `docker compose up -d`. On-prem (laptop, NAS, Raspberry Pi) is
presented as the alternative to the cloud VPS.

The *why* is the heart of the video: instead of paying for many separate AI
plans, he wants **one interface, own-your-data, and control**. API/pay-as-you-go
access gives him the newest models the day they release (no waiting for the
$200/month tier) and lets him provision accounts for his family and employees.
Through Open WebUI's groups/permissions plus LiteLLM **virtual keys**, he sets
per-person model access, monthly **budgets**, and system prompts (e.g. a "school
helper" prompt for his kids that won't do their homework), and he can review his
kids' chat logs. He's explicit that saving money is *not* the primary goal — the
big "asterisk" is token-based API pricing, which can get expensive for power
users like him.

## Key claims (dated — stack + why)

All dated 2025-03-13 (publication), paraphrase unless quoted:

**The stack**
- His current AI setup is **Open WebUI** (open-source, self-hosted web interface
  for AI) as the single front-end for every LLM he uses.
- Open WebUI runs both cloud models (ChatGPT, Claude) and local self-hosted
  models via **Ollama** — he names Llama 3, Mistral, and DeepSeek, and often runs
  two to four models side by side.
- Open WebUI natively only offers two connection types: OpenAI-compatible API
  and Ollama API — so it can't directly connect to Claude/Anthropic, Gemini, etc.
- To solve that, he adds **LiteLLM**, "a proxy for AI or a gateway" that connects
  to 100+ AIs. Open WebUI connects only to LiteLLM (LiteLLM exposes an
  OpenAI-compatible API), and LiteLLM connects out to everything else: OpenAI,
  Anthropic (Claude), Gemini, Grok (xAI), DeepSeek (American-hosted via Groq).
- LiteLLM installs alongside Open WebUI via Docker: `git clone` the LiteLLM repo,
  edit the `.env` file to add `LITELLM_MASTER_KEY` and `LITELLM_SALT_KEY`
  (randomly generated `sk-...` values; the salt key encrypts/decrypts stored API
  key credentials), then `docker compose up -d`. LiteLLM admin UI runs on port
  4000; Open WebUI on port 8080.
- Deployment target in the demo is a Hostinger VPS (KVM 2 plan, AMD EPYC CPU,
  8 GB RAM, NVMe), chosen as a "home lab" that can host more than just Open WebUI;
  on-prem (laptop/NAS/Raspberry Pi) is the alternative.
- In Open WebUI he pastes the LiteLLM virtual key under the OpenAI API connection
  with base URL `http://localhost:4000` (both run on the same server).

**Why he changed**
- He wants **one interface / one place to go** rather than paying for and managing
  15+ separate AI plans.
- **Control**: via Open WebUI groups/permissions and LiteLLM virtual keys he sets
  which models each person (kids, wife, employees) can access, gives them system
  prompts, and caps them with per-person monthly **budgets** (e.g. $20).
- **Own-your-data / privacy / security**: "my data's a bit more safe"; he can
  review his kids' AI chats (and chooses not to monitor employees').
- **Newest models immediately**: API access exposes all of a provider's models —
  including just-released ones — with no waiting for expensive normie tiers.
- **Saving money is explicitly NOT the primary goal**: API pricing is token-based
  and can be expensive; as a heavy user of the best models (GPT-4.5, o1, o3) with
  long, context-heavy conversations, his cost would be well above $20/month.

## Notable verbatim quotes

> "I found a way to access every ai. I'm talking chat, GBT, Claude Gemini Grok
> from one self-hosted interface, and no, I'm not paying for any of these plans."

> "It's better security. My data's a bit more safe and oh my gosh, the amount of
> features it has, I'm addicted. This might be the better way to use ai."

> "This is where a tool I fell in love with comes in. It's called light. LLM.
> LiteLLM is a proxy for AI or a gateway."

> "The whole point of this was to try everything."

> "Can this save you money? Maybe, but I wouldn't do this as the primary goal to
> save money. For me, it's more about I want to give my family myself and my
> employees access to all the ai and I don't want to pay for 15 million plans and
> have to manage all these different things. I want one interface, one place to
> go and I want control."

> "You can put a budget in per person so they don't go over... If you use that
> 4.5 all day, you're done, buddy. You're talking to Ollama for the rest of the
> day."

> "This is now my AI hub and this is where I'll control the budget."

> "You should be looking at your kids' AI chats if you're letting them have AI —
> and you should let them have AI, hot take, but I think kids need to learn how to
> use it because that's kind of the future."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: current self-hosted AI workflow (Open WebUI + LiteLLM router) -->
