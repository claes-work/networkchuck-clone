---
type: hub
domain: ai-tools
created: 2026-07-14
updated: 2026-07-23
---

# AI Tools — hub

LLMs, self-hosted AI, AI coding assistants, and automating IT work with AI — Chuck's
fastest-growing theme since 2023, and one he approaches through his signature lens:
own it, host it yourself, and don't hand your data to Big Tech.

## Key ideas & topics

### The AI pivot (2023)
Chuck folded AI into his "learn X RIGHT NOW" format for the first time with a machine
learning primer, framing ML as the next must-learn skill for IT people rather than a
niche for data scientists (2023-03-01) [[../../sources/2023-03-01-yt-JJCq21Dc-Us]].
_(Guests Santiago Valdarrama and Nacho in that video are context, not Chuck; only
Chuck-attributed framing feeds the persona.)_

### AI literacy — using AI well
Beyond running models, Chuck teaches how to *think* about them. His canonical
AI-literacy explainer breaks down the **context window** — why models "forget," how much
they can hold, and how to work with that limit — as foundational knowledge for anyone
using LLMs (2025-04-09) [[../../sources/2025-04-09-yt-TeQDr4DkLYo]]. He applies the same
literacy lens to learning itself, using AI as a **Socratic tutor** (having it ask
questions rather than hand over answers) as the right way to learn *with* AI in
education (2025-04-07) [[../../sources/2025-04-07-yt-cJZnlnT0rPA]]. His mental model for
AI at work is **augment, don't replace**: he showcased Daniel Miessler's Fabric and its
library of reusable system-prompt "patterns" as a way to bolt AI onto existing workflows
as a force-multiplier, not a human replacement (2024-05-28)
[[../../sources/2024-05-28-yt-UbDyjIIGaxQ]].

### Networking meets AI
Chuck bridges his networking roots into the AI datacenter era, explaining the
specialized fabrics that stitch GPU clusters together — InfiniBand vs. RoCE (RDMA over
Converged Ethernet) — and why AI training makes the network itself a first-class part of
the AI stack (2024-02-09) [[../../sources/2024-02-09-yt-fb69FyW2KLk]]. See also
[[../networking/networking]].

### Private / self-hosted AI — "own your AI"
The dominant strand of Chuck's AI content: run capable models yourself instead of
sending prompts (and data) to Big Tech. He walked through running your own private AI
with Ollama (2024-03-12) [[../../sources/2024-03-12-yt-WxYC9-hBM_g]], then hosting ALL
your AI locally as a full stack (2024-05-03) [[../../sources/2024-05-03-yt-Wjrdr0NU4Sk]].
He extended this to a self-hosted AI hub by standing up Open WebUI locally
(2025-03-13) [[../../sources/2025-03-13-yt-JJ_0-pAOIEk]] and then exposing it as a real
website with a domain + SSL (2025-03-13) [[../../sources/2025-03-13-yt-BdH_yR_J3FQ]].
His **current, canonical AI stack** consolidates this into one unified workflow —
Open WebUI as the front end, LiteLLM as the model router/proxy, and Ollama serving
local models — so every model (local or API) runs through one private interface
(2025-03-13, canonical "current AI stack") [[../../sources/2025-03-13-yt-nQCOTzS5oU0]].
He also pushed local models toward data sovereignty by running DeepSeek R1 entirely
on his own machine (Ollama / LM Studio, Docker-isolated for safety) rather than
sending prompts to a hosted service (2025-01-31) [[../../sources/2025-01-31-yt-7TR-FLWNVHY]].
The same "keep it private and local" instinct shows up in home automation: Home
Assistant's own voice assistant as a private, local alternative to Alexa/Google
(2024-12-19) [[../../sources/2024-12-19-yt-An4IapvutzM]], which he'd already prototyped
as a fully local private voice assistant stack (Home Assistant + Ollama +
Whisper/Piper over the Wyoming protocol) to replace Alexa (2024-11-04)
[[../../sources/2024-11-04-yt-XvbVePuP7NY]]. He took the "own it locally" ethic to his
own identity too — cloning his own voice with Piper TTS while insisting it stay local
rather than uploaded to a cloud voice service (2024-11-19)
[[../../sources/2024-11-19-yt-3fg7Ht0DSnE]]. See also
[[../homelab-selfhosting/homelab-selfhosting]].

### Local AI at scale
Pushing self-hosting to its limit, Chuck built a home "AI supercomputer" by clustering
5 Mac Studios to run large models locally — proving the own-your-AI thesis can scale to
serious hardware, not just a single GPU (2025-02-17) [[../../sources/2025-02-17-yt-Ju0ndy2kwlw]].

### AI automation / agents
Chuck's 2025 arc moves from chatting with AI to putting AI to work. Early in the year
he leaned into open-source agent tooling: an open-source Deep Research agent built from
Firecrawl + OpenAI o3-mini as a self-hostable alternative to closed research assistants
(2025-02-06) [[../../sources/2025-02-06-yt-4M7RIbQZ_-w]], and Browser Use as an
open-source alternative to ChatGPT's Operator for AI-driven browser automation
(2025-02-21) [[../../sources/2025-02-21-yt-sxTNACldK3Y]]. He championed n8n
as the tool to automate everything (2025-07-16)
[[../../sources/2025-07-16-yt-ONgECvZNI3o]], showed how to run n8n locally / on-premise
(2025-07-16) [[../../sources/2025-07-16-yt--ErfsM2TYsM]], and later handed n8n his
entire homelab as the automation brain (2025-10-03)
[[../../sources/2025-10-03-yt-budTmdQfXYU]]. He framed MCP (Model Context Protocol) as
the agent frontier — the standard that lets AI actually reach into your tools
(2025-09-12) [[../../sources/2025-09-12-yt-GuTcle5edjk]]. He then showed his own
terminal-AI workflow (Claude Code-style), arguing most people use AI "the hard way" by
staying in a chat box instead of letting it act in the terminal (2025-10-28)
[[../../sources/2025-10-28-yt-MsQACpcuTkU]]. See also [[../cloud-devops/cloud-devops]].

### AI security — AI as a new attack surface
Consistent with his ethical-hacking roots, Chuck treats AI as something to attack as
well as use: hacking AI and prompt injection is "too easy," and AI systems open a fresh
class of vulnerabilities defenders now have to think about (2025-08-12)
[[../../sources/2025-08-12-yt-Qvx2sVgQ-u0]]. The flip side is AI as a hacking *copilot* —
he used Notion AI / ChatGPT / Claude as study-and-recon aids while working the HTB CPTS
pentest path, treating AI as a force-multiplier for the hacker rather than only a target
(2024-08-15) [[../../sources/2024-08-15-yt-3D6gaawXwfk]]. See also
[[../cybersecurity/cybersecurity]].

### Through-line
Chuck's AI stance is coherent across the arc: **AI is the modern must-learn skill** (the
"learn X RIGHT NOW" format now covers AI the way it once covered Docker, Python, and
AWS), it should be **private, self-hosted, and own-your-data** wherever possible, and it
is **both a powerful tool AND a new attack surface**. That framing ties AI directly to
his other domains — homelab/self-hosting, cloud/DevOps, cybersecurity, and the free
"learn it now" course tradition [[../certifications-career/free-courses]]. On the human
side he reframes **AI anxiety**: rather than fearing replacement, treat AI as the skill
to lean into — a career/mindset argument that the people who learn to use it win
(2025-06-25) [[../../sources/2025-06-25-yt-3BXE0e3QZ4U]].

## Source pages

- 2023-03-01 — You NEED to learn Machine Learning, RIGHT NOW!! [[../../sources/2023-03-01-yt-JJCq21Dc-Us]]
- 2024-02-09 — AI networking: InfiniBand vs. RoCE (GPU-cluster fabrics) [[../../sources/2024-02-09-yt-fb69FyW2KLk]]
- 2024-03-12 — Run your own AI (but private) [[../../sources/2024-03-12-yt-WxYC9-hBM_g]]
- 2024-05-03 — host ALL your AI locally [[../../sources/2024-05-03-yt-Wjrdr0NU4Sk]]
- 2024-05-28 — Fabric: AI system-prompt patterns (augment, don't replace) [[../../sources/2024-05-28-yt-UbDyjIIGaxQ]]
- 2024-08-15 — AI as a hacking copilot (HTB CPTS) [[../../sources/2024-08-15-yt-3D6gaawXwfk]]
- 2024-11-04 — Local private voice assistant (HA + Ollama + Whisper/Piper/Wyoming) [[../../sources/2024-11-04-yt-XvbVePuP7NY]]
- 2024-11-19 — Cloning my own voice (Piper TTS), kept local [[../../sources/2024-11-19-yt-3fg7Ht0DSnE]]
- 2024-12-19 — Home Assistant made their own Alexa!! [[../../sources/2024-12-19-yt-An4IapvutzM]]
- 2025-01-31 — Run DeepSeek R1 locally (data sovereignty) [[../../sources/2025-01-31-yt-7TR-FLWNVHY]]
- 2025-02-06 — Open-source Deep Research agent (Firecrawl + o3-mini) [[../../sources/2025-02-06-yt-4M7RIbQZ_-w]]
- 2025-02-17 — I built an AI supercomputer with 5 Mac Studios [[../../sources/2025-02-17-yt-Ju0ndy2kwlw]]
- 2025-02-21 — Browser Use: open-source ChatGPT Operator alternative [[../../sources/2025-02-21-yt-sxTNACldK3Y]]
- 2025-03-13 — how to host Open WebUI locally (self-hosted AI Hub) [[../../sources/2025-03-13-yt-JJ_0-pAOIEk]]
- 2025-03-13 — Turn Open WebUI into a real website (Domain + SSL) [[../../sources/2025-03-13-yt-BdH_yR_J3FQ]]
- 2025-03-13 — My current AI stack: Open WebUI + LiteLLM + Ollama (canonical) [[../../sources/2025-03-13-yt-nQCOTzS5oU0]]
- 2025-04-07 — Learning with AI: Socratic mode (education) [[../../sources/2025-04-07-yt-cJZnlnT0rPA]]
- 2025-04-09 — The context window explained (AI literacy, canonical) [[../../sources/2025-04-09-yt-TeQDr4DkLYo]]
- 2025-06-25 — AI anxiety, reframed (career/mindset) [[../../sources/2025-06-25-yt-3BXE0e3QZ4U]]
- 2025-07-16 — You NEED to Use n8n RIGHT NOW!! [[../../sources/2025-07-16-yt-ONgECvZNI3o]]
- 2025-07-16 — How to Run n8n Locally (On-Premise Setup) [[../../sources/2025-07-16-yt--ErfsM2TYsM]]
- 2025-08-12 — Hacking AI is TOO EASY [[../../sources/2025-08-12-yt-Qvx2sVgQ-u0]]
- 2025-09-12 — you need to learn MCP RIGHT NOW!! [[../../sources/2025-09-12-yt-GuTcle5edjk]]
- 2025-10-03 — n8n Now Runs My ENTIRE Homelab [[../../sources/2025-10-03-yt-budTmdQfXYU]]
- 2025-10-28 — You've Been Using AI the Hard Way (terminal-AI workflow) [[../../sources/2025-10-28-yt-MsQACpcuTkU]]

## Related hubs

[[../homelab-selfhosting/homelab-selfhosting]] ·
[[../cloud-devops/cloud-devops]] ·
[[../cybersecurity/cybersecurity]] ·
[[../networking/networking]] ·
[[../certifications-career/free-courses]]
