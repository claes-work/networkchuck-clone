---
type: youtube-video
source_date: 2024-05-03
url: https://www.youtube.com/watch?v=Wjrdr0NU4Sk
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [ai-tools, homelab-selfhosting]
tags: [local-ai, ollama, open-webui, self-hosting, private-ai, rag]
---

# host ALL your AI locally

## Summary

Chuck builds a full local, self-hosted AI stack — first for himself, then for his
daughters so they can use AI for school without cheating. The stack combines Ollama
(model runtime) + Open WebUI (a ChatGPT-like GUI in Docker) + Automatic1111 Stable
Diffusion (local image generation) + document upload/RAG, and an Obsidian integration.
The whole point is privacy and control: the AI runs on your own hardware, offline, with
no data leaving the machine. He stresses you don't need a monster rig — any Windows,
Mac, or Linux computer (better with a GPU) works, and demos the setup on a laptop —
while also showing off his purpose-built AI server "Terry" (dual RTX 4090s). Admin
controls in Open WebUI (user approval, model whitelisting, disabling chat deletion, and
custom model files with restrictive system prompts) let him put guardrails on what his
daughters' assistant will do.

## Key claims (dated — the stack + philosophy)

_All paraphrase unless quoted. Dated 2024-05-03._

The stack (four layers):
- **Ollama** is the foundation — the tool used to run AI models locally; installed on
  Linux with a single `curl` command (also works via WSL on Windows, and natively on
  Mac M1–M3 using the embedded GPU). Its API service runs on port `11434`.
- Models are pulled and run from the command line (`ollama pull llama2`,
  `ollama run llama2`); Chuck also uses code-focused (Code Gemma) and multimodal (LLaVA)
  models. On his server "Terry," Ollama uses both GPUs at once.
- **Open WebUI** is the GUI layer — a "ChatGPT-like" chat interface run in a Docker
  container (port `8080`) that connects to Ollama's local API. Chuck calls it the best
  of the many available web UIs; features include chat history, multiple models,
  editing/regenerating responses, text-to-speech, file upload, and @-mentioning models
  into a conversation.
- **Automatic1111 / Stable Diffusion** is the local image-generation layer (port `7860`),
  installed after prereqs including pyenv + Python 3.10. It must be launched with the
  `--listen` and `--api` flags to integrate into Open WebUI, after which images can be
  generated inline from a chat prompt.
- **Documents/RAG**: Open WebUI's Documents section lets you add a file and query it in
  chat via a `#` reference (e.g. "give me five bullet points about this").

Admin / control features:
- The first account to sign up automatically becomes the admin; new users land in a
  pending state until the admin approves them, and can connect from anywhere with the
  host's IP address.
- Admin can whitelist which models users may access, disable chat deletion (to monitor
  what his daughters do), and create custom **model files** — a `FROM <model>` line plus
  a triple-quoted system prompt — to build restricted assistants.
- He built a restricted assistant named "Deborah" (from Llama 2, later mixtral) for his
  daughter Chloe that refuses to write papers and instead acts as a guide, to prevent
  cheating.

Hardware — "Terry," the AI server (overkill, by his own admission):
- Lian Li O11 Dynamic EVO XL case, ASUS X670E ProArt Creator motherboard, AMD Ryzen 9
  7950X (16 cores, 4.2 GHz), 128 GB DDR5-6000 (G.Skill Trident Z5 Neo), two liquid-cooled
  MSI RTX 4090s (24 GB each), two 2 TB Samsung 990 Pro SSDs, Corsair AX1600i 1600 W PSU.
- Ubuntu refused to install; he used **Pop!_OS by System76** instead (its image ships
  with Nvidia drivers built in) and it worked first try.

Philosophy:
- The recurring theme is local, private, self-owned AI: it's fast, customizable, offline,
  and — crucially — under your own control, which is what makes it safe to hand to his
  kids. Privacy is a stated primary concern.
- Extra integration: the Obsidian notes app (via the BMO Chatbot community plugin) can
  connect to a local Ollama instance ("Terry") to give an in-note, private local GPT that
  can reference the current note.

## Notable verbatim quotes

> I built an AI server for my daughters. Well, first it was more for me. I wanted to run all of my AI locally.

> And again, it's local, it's private. I control it, which is important because I'm getting it to my daughters.

> I want them to be able to use AI to help with school, but I don't want them to cheat or do anything else weird. But because I have control, I can put in special model files that restrict what they can do.

> Really all you'll need is a computer. That's it. It can be any computer running Windows, Mac or Linux. And if you have a GPU, you'll have a much better time.

> We're about to interact with a chat GPT, like AI right here, no internet required. It's all just happening in that five gigabyte file.

> This I think for me is just scratching the surface of running local AI private in your home on your own hardware. This is seriously so powerful.

> I think AI is just the coolest thing, but also privacy is a big concern for me. So to be able to run AI locally and play with it this way is just the best thing ever.

> Do you not feel like a wizard when you're installing stuff like this and the fact that you're installing AI right now? Come on.

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: full local AI stack — self-hosted/private-AI ethos deepens -->
