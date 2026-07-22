---
type: youtube-video
source_date: 2025-10-28
url: https://www.youtube.com/watch?v=MsQACpcuTkU
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [ai-tools]
tags: [ai, ai-agents, workflow, productivity, tools]
---

# You've Been Using AI the Hard Way (Use This Instead)

## Summary

Chuck argues that using AI through browser chat apps (ChatGPT, Claude, Gemini web
interfaces) is the "slow way," and that the real superpower is running AI **coding
CLIs in the terminal** — for everything, not just code. AI companies market these
tools to developers, but Chuck's thesis is that they work for research, writing,
project management, and any knowledge work. He demonstrates a full workflow across
several terminal AI tools and explains why the terminal beats the browser: you can
see and control your context window, the AI can read/write files and run scripts on
your own machine, everything lives in a local folder you own (no vendor lock-in), and
tools like Claude Code add sub-agents, output styles, and planning mode.

The video is itself the demo — Chuck reveals he wrote the script for this video using
this exact system, running Gemini CLI, Claude Code, and Codex simultaneously in the
same directory.

Tools covered:
- **Gemini CLI** — recommended starting point because of its generous **free tier**;
  install via one command (or `brew install gemini-cli` on Mac); log in with a regular
  free Gmail account; uses Gemini 2.5 Pro.
- **Claude Code** — Chuck's "daily driver" and favorite ("overpowered"); paid, but
  usable with a Claude Pro subscription (~$20/mo) instead of API keys. Standout
  feature: **sub-agents**.
- **Codex** — OpenAI's terminal tool, used for high-level analysis/review.
- **OpenCode** — open-source alternative; use any model (including **local models**
  via Ollama), free Grok access (grok-code-fast-1), Claude Pro login, session sharing,
  and a timeline/restore feature.

Core organizing idea: each tool reads a **context/instructions file** in the project
directory (`GEMINI.md`, `CLAUDE.md`, `AGENTS.md`) generated via `/init`. Keep those
files synced so all three AIs share the same context. Treat every project like code —
commit it to a **GitHub repo** so decisions and history are preserved. Sponsor segment:
Twingate (zero-trust network access), framed around the security risk of giving AI/
remote employees broad network access via traditional VPNs.

## Key claims (dated — the concept + approach)

All claims paraphrased from Chuck, 2025-10-28:

- Using AI in the browser is the slow way; running the same AI companies' **terminal
  (CLI) tools** makes him "10 times faster." AI companies market these as developer/
  coding tools but you can use them for everything, and it's better than their apps.
- The browser workflow degrades into chaos: many chats, lost context, ChatGPT losing
  context, cross-checking Claude/Gemini, and pasting into notes that never stays
  organized. The terminal fixes this.
- **Start with Gemini CLI** because of its generous free tier (free with a regular
  Gmail account); install with one command, or `brew install gemini-cli` on Mac.
- The terminal shows your **context window** (e.g. "99% context left") which the
  browser hides from you.
- The key advantage: terminal AI can **access your computer** — read and write files
  (e.g. create a `.md` document directly), read an Obsidian vault (notes are just files
  on disk), and run Bash/Python scripts. No copy-pasting.
- Running `/init` makes the tool analyze the project and generate a **context/
  instructions file** (`GEMINI.md` / `CLAUDE.md` / `AGENTS.md`) it loads on every
  launch, so new sessions pick up where you left off — no re-explaining, no scattered
  chats. You can ask the AI to keep this file updated with decisions and progress.
- **Claude Code is his default/favorite** ("overpowered"). It's paid, but a **Claude
  Pro subscription (~$20/mo)** logs you into the terminal — no API keys needed. If you
  can only pay for one AI subscription, Chuck would choose Claude Pro.
- Claude Code's game-changing feature is **sub-agents**: the main Claude delegates a
  task to another Claude instance with a **fresh 200,000-token context window**, which
  protects the main conversation's context from bloat and bias. He runs multiple agents
  in parallel (showed 7, actually 10, in one terminal).
- You create agents with `/agents`; they can be project-scoped or personal, given or
  restricted tool access, and assigned a model (he uses Sonnet). Reference files/agents
  with the `@` symbol.
- Chuck built purpose-specific agents: a **brutal critic** (three personalities/angles)
  that roasts his scripts against his own framework docs, and a **script session
  closer** that summarizes the day, updates all context files, and commits to GitHub.
- `--dangerously-skip-permissions` runs Claude "without training wheels" (bypasses
  permission prompts); `claude -r` resumes a previous conversation.
- Other Claude Code features: `/context` (see exact token usage), **output styles**
  (`/output-style` — changes the system prompt/persona; he made a script-writing style),
  **plan mode** (Shift+Tab to cycle modes), plus hooks, custom status lines, and pasting
  images into the terminal.
- Tools can run in **headless mode** (e.g. `gemini -p "<prompt>"`) so one AI can call
  another — he had a Claude agent use Gemini to do research.
- Run Claude, Gemini, and Codex in the **same directory** so they share context; keep
  `GEMINI.md`, `CLAUDE.md`, and `AGENTS.md` synced (AGENTS.md is the standard Codex uses,
  and they're trying to make it a cross-tool standard). Assign different roles: Codex/
  ChatGPT for high-level analysis, Gemini and Claude for the deep work.
- Because everything is a **local folder**, there's no vendor lock-in: copy the folder
  anywhere, switch tools/models freely, and adopt any better AI that comes out later.
- **OpenCode** (open source) may be the best of all: use any model, run **local models**
  (via Ollama, edit `opencode.jsonc`), free Grok (grok-code-fast-1), log in with Claude
  Pro, switch models mid-session, share sessions via URL, and a timeline to jump back /
  restore.
- He does the **writing himself** — AI is used to critique and keep him on track, not
  to write for him. The point is building personal, niche-specific software for your own
  use case.
- Security caveat (sponsor-framed): giving AI terminal access to your machine and files
  is powerful but risky, especially over traditional VPNs where remote access = full
  network access; he advocates zero-trust network access (Twingate).

## Notable verbatim quotes

> "If you're still using AI in the browser, you're doing it the slow way. You see each
> of these apps has a terminal version and they make me 10 times faster."

> "They're marketing these tools to developers for code, but here's what they're not
> telling you. You can use them for everything and it's way better than their apps."

> "once you see AI in the terminal, you're never going back to the browser"

> "This thing can do everything a browser can do, but it has a superpower. It can access
> your computer, it can read and write files."

> "It can access your obsidian vault, all your notes because those are just files
> sitting there on your hard drive."

> "What it just did there was create instructions for itself, context for what we're
> working on."

> "They're right here sitting on my hard drive mine, my precious."

> "I use cloud code, which is Claude in the terminal for pretty much everything. It's my
> default and here's why. It has a feature that changes the game agents."

> "if you can only pay for one AI subscription, cloud Pro is the one I would choose"

> "Claude was like, cool, I've got a task but it's not for me. I'm going to delegate
> this task to one of my employees... and this is another Claude instance."

> "That means the conversation we're having right now, me and the main CLA guy, it's
> protected. It doesn't get too bloated."

> "Nothing annoys me more than when Chad GBT tries to fence me in. Give me that vendor
> Lockin. So I can't leave. No, I reject that. I own my context."

> "If a new greater, better AI comes out, I'm ready for it because all my stuff is right
> here on my hard drive. I will use all ai, I'll use the best ai. No one could stop me."

> "I'm using all three right now to work on this video script."

> "I don't just use these AI terminal tools to help me create. I use them to critique me
> and make me better."

> "I want it to be hard to please so that when it did tell me I did a good job, I knew
> it. It was good."

> "It's not writing for me. I'm doing the writing because I like to keep that. I think
> that's important now with ai, but I do have AI roast me, help me stay on track."

> "I made this for me. This is my own personal software, exactly my use case. What can
> you build for you that's just for you and your niche."

> "I wake up every day feeling like I have superpowers. I want this for you."

> "don't let the terminal scare you... If you can get past that, this tool is for
> everyone. Everyone should be using this."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: Canonical statement of Chuck's personal AI workflow (terminal CLIs over browser; Claude Code as daily driver, sub-agents, context files, GitHub-tracked projects, AI-as-critic-not-writer) — high-value for persona/beliefs and an ai-tools topic hub. -->
