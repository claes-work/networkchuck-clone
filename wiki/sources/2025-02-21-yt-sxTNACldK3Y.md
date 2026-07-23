---
type: youtube-video
source_date: 2025-02-21
url: https://www.youtube.com/watch?v=sxTNACldK3Y
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [ai-tools, homelab-selfhosting]
tags: [ai-agent, browser-agent, open-source-ai, operator, self-hosted]
---

# ChatGPT Operator is expensive....use this instead (FREE + Open Source)

## Summary

Chuck presents **Browser Use** (specifically its **Web UI** companion project) as a
free, open-source alternative to OpenAI's **ChatGPT Operator** — a browser-controlling
AI agent that you give a natural-language task ("find me a Japanese VCR that supports
TBC on eBay and add it to my cart") and it opens a browser and does it. His framing is
his recurring one: Operator is a research preview locked behind OpenAI's $200/month Pro
tier, while Browser Use is open source, self-hostable, and can run entirely on your own
hardware — including with **local AI** via Ollama, so "Sam Altman" isn't tracking what
you do.

The bulk of the video is a hands-on Windows/WSL install walkthrough of the Web UI, plus
a series of live demos and a head-to-head "competition" between Browser Use and ChatGPT
Operator (buying a VPS from the sponsor's hosting, buying a Japanese VCR on eBay, and
solving a CAPTCHA). Chuck's key practical finding: local model choice matters a lot —
small models (Qwen, Llama 2) are "dumb" and fail the agentic browsing task, while
DeepSeek-R1 14B works locally and cloud models (Claude 3.5 Sonnet, GPT via API) are
fastest and smartest. Browser Use's standout advantage over Operator is that it can
drive **your own browser** with your logged-in sessions and password manager, and you
can interrupt/take control mid-task. He closes by noting the "scary" hacking
ramifications of automating browser tasks this easily.

Install/how-to (Windows via WSL Ubuntu 22.04):
1. Ensure Python 3.11+ (he uses `pyenv install 3.11` / `pyenv global 3.11`).
2. `git clone` the Web UI repo, `cd web-ui`.
3. Create/activate a venv (`python3 -m venv .venv`, `source .venv/bin/activate`).
4. `pip install -r requirements.txt`.
5. Install **Playwright** (headless-browser tooling).
6. `cp .env.example .env`, then `nano .env` to add API keys (OpenAI/Anthropic) and/or an
   Ollama endpoint (localhost, or a remote Ollama server — his is "Terry," a dual-RTX-4090
   AI server).
7. Run the `webui.py` script, open `localhost:7788` in a browser, pick an LLM provider +
   model in the LLM configuration, and run the agent. A Docker option exists but he finds
   local setup easier.

## Key claims (dated — tool + framing)

All 2025-02-21, paraphrase unless quoted:

- The recommended open-source tool is **Browser Use** ("Enable AI to control your
  browser"), a Y Combinator-backed project; the specific piece demoed is its **Web UI**
  companion project, which gives a GUI-friendly, no-code way to try it.
- ChatGPT Operator is a research preview, is janky, and is only available to OpenAI Pro
  users at $200/month; Browser Use is free and open source and can be self-hosted.
- Browser Use also has a paid hosted version (Y Combinator backed) that claims to be 2%
  better than Operator at $30/month — but the open-source, self-hosted path is what Chuck
  cares about.
- You can run the agent with completely local, free AI via **Ollama** — no cloud, nothing
  tracked. Cloud models (OpenAI/Anthropic via API key) are more performant because they
  have more resources.
- Model capability is decisive: Qwen and Llama 2 are too "dumb" to complete the browsing
  task; **DeepSeek-R1 14B** is the local model he recommends as a minimum; **Claude 3.5
  Sonnet** and GPT (via API) are fast and accurate.
- Browser Use's big edge over Operator: it can use **your own browser** with existing
  logged-in sessions, password manager, and settings, and you can take control mid-task.
  Operator uses its own isolated browser.
- Requirements: a Mac/Windows/Linux machine; on Windows it runs under **WSL**; Python
  3.11+; Ollama for local AI or an API key for cloud AI. Playwright is installed for the
  headless/browser automation.
- Reinforces the recurring framing: prefer open-source, self-hosted tools over expensive
  SaaS. "Anything we can run open source local is amazing."
- Notes a security angle: if ordinary users can automate browser tasks this easily,
  hackers can automate their processes too — "it's kind of scary."
- Demo caveats observed live: the agent over-ordered VPS servers (11, and nearly 20) when
  instructions weren't specific about quantity; CAPTCHA-solving was inconsistent; some
  runs gave up. Being specific in the prompt (exact server count, step-by-step CAPTCHA
  instructions) improved behavior.

## Notable verbatim quotes

> "It's like giving a task to an assistant and you can go about your day."

> "But I found an open source alternative. It's like this. It'll open up a browser, do the whole thing. Actually, I think it's kind of better. It's free open source."

> "The project is called Browser Use. Enable AI to control your browser."

> "But anyways, open source is what we care about. We can host this ourselves, use our own local stuff, even local AI."

> "One tool you can use that's completely free, completely local, completely awesome is Ollama."

> "Now we'll say if you're doing Qwen or Llama 2, they're dumb. They have a really hard time doing this. I normally want to do it with DeepSeek-R1 14B at least."

> "And locally too, it feels like magic."

> "The one big limitation with ChatGPT Operator is that it's using this random browser that it operates... with Browser Use, we can actually use our own browser with our own settings. Everything's still logged in. Our password manager and our AI can handle it for us. That's so powerful, dude."

> "I'll tell you one thing, even though mine might be a bit slower, it still wins out because of this little tagline right here: Sam Altman's tracking what you're doing."

> "Anything we can run open source local is amazing."

> "Also think about this, the hacking ramifications. If you and I can get access to this like that... think about hackers, how they can automate their processes. It's kind of scary."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
