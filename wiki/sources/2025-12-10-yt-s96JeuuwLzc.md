---
type: youtube-video
source_date: 2025-12-10
url: https://www.youtube.com/watch?v=s96JeuuwLzc
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [ai-tools, cloud-devops, homelab-selfhosting]
tags: [n8n, automation, ai-agents, workflow]
---

# I'll never use n8n the same...... (2025-12-10)

## Summary

Chuck demonstrates the technique that changed how he uses n8n: connecting n8n to an
AI terminal agent (Claude Code, or alternatively Gemini CLI / Codex) so n8n workflows
can execute Claude Code commands, agents, and skills. The connection method is
deliberately simple — an **SSH node** in n8n that logs into a Linux server where the
AI terminal tool is installed and runs `claude` commands in headless mode (`claude -p`).

n8n becomes the **orchestrator** while the complexity (context, skills, multi-agent
spawning, Python scripts, markdown environment descriptions) lives inside Claude Code.
Chuck argues this is far more powerful than n8n's native AI agent nodes because Claude
Code carries local file/directory context, can deploy multiple sub-agents on the fly,
and handles context better than n8n. He also shows how to **resume a session** by
generating a UUID in a code node and passing it via `--session-id` / `-r`, enabling
multi-turn conversations — culminating in a Slack-driven workflow that lets him talk
to Claude Code from his phone until he marks the conversation done.

The video is sponsored by hosting.com (VPS for self-hosting n8n) and plugs two new
Network Chuck Academy courses (n8n; Claude Code coming soon). Ends with his usual
closing prayer.

## Key claims (dated — technique + workflow)

All dated 2025-12-10 (paraphrase unless quoted):

- The core technique: n8n can drive an AI terminal agent, so n8n workflows execute
  Claude Code commands, agents, and skills — Chuck says this "changed forever" how he
  uses n8n.
- Three things are needed: an n8n instance, an AI terminal tool, and coffee. For the
  AI terminal tool he recommends Claude Code (requires a paid/Pro subscription);
  Gemini CLI is free with limits; Codex is described as "kind of janky."
- The AI terminal tool can be installed on any Linux-based machine (including Mac, or
  Windows via WSL) — alongside n8n on a VPS, on a Raspberry Pi, or (his setup) on an
  Ubuntu server in his Network Chuck Studios server room so Claude Code sits next to
  his files.
- The connection method is n8n's **SSH node** with the "execute command" action —
  n8n SSHes into the server and runs `claude` commands. Chuck says he first tried a
  more complicated custom HTTP wrapper (which worked) but SSH was the simplest, most
  elegant solution.
- Setup: create an SSH credential (password or private key) pointing at the server's
  IP; test with a known command (`hostname`) then `claude --version` to confirm the
  install works.
- Run Claude in headless mode with `claude -p` ("print"), so you can ask it something
  and walk away.
- Reason 1 it's powerful — **context**: chaining `cd <dir> && claude -p "..."` gives
  Claude the local directory's files as context (e.g. asking whether the current
  video script "is going to be any good"). He likens it to connecting n8n to the GUI
  ChatGPT with all your memories, but more powerful — and the tokens are already
  covered by his subscription.
- Reason 2 — **skills and agents**: running Claude with a custom "unified skill" (a
  skill on his server that tells Claude how to access his unified environment) let him
  deploy three sub-agents at once to check WiFi, network performance, and security,
  writing results to a dashboard. n8n is "just the orchestrator"; the complexity
  (markdown files, Python scripts, multi-agent spawning) lives in Claude Code. This
  surfaced a real finding — high memory on his switch and UDM Pro he didn't know about.
- Reason 3 — **resumable sessions**: AI terminal tools operate off session IDs. Generate
  a UUID in an n8n JavaScript code node, pass it with `--session-id` on the first call,
  then continue with `-r <session-id>` on later calls so follow-up prompts keep context
  ("why is one of them down?").
- The showcase workflow: a Slack + n8n loop that lets him talk to Claude Code from his
  phone anywhere. Slack sends a message, Claude Code responds (kept under 2000
  characters), and a true/false dropdown feeds an IF node — false loops back with
  another `-r` same-session command to keep the conversation going, true ends the
  workflow. Demo: deploying two agents to debate Nano vs Neovim.
- You can still use n8n's native AI agents — they can call Claude Code and develop
  prompts on the fly. The killer differentiator is that Claude Code can deploy multiple
  agents on the fly, whereas n8n is limited to the agents hard-wired into the workflow.
- Chuck's next-video plan: build an "IT department" with n8n as orchestrator and Claude
  Code + Gemini CLI + Codex as the workers.

## Notable verbatim quotes

> "How I use NAN [n8n] has changed forever because now I'm using NAN with Claude Code."

> "I almost stopped using NAN because while it's good, Claude code is more powerful. ...
> but when I realized I could combine the two, oh my gosh, I unlocked a superpower."

> "You need three things. You'll need an innate N [n8n] instance, an AI terminal tool and coffee."

> "Here's how they connect you ready for SSH? That's it. We're going to use the SSH node
> on N eight N to log into our server and run Claude Commands."

> "I tried to make it more complicated. I created my own HTTP wrapper and it worked, but
> still, SSH was the simplest, most elegant solution."

> "And what I love about this is that N eight N, he's now just the orchestrator. Things
> are simple here. The complexity lives here in claw code [Claude Code]."

> "Giving N eight N access to cloud code [Claude Code] gives NAN access to a super
> powerful context filled agent."

> "We just gave NAN and freaking pot of coffee. This is so overpowering. We have context.
> We've got the power of the terminal Claude skills."

> "The killer part about Claude Code is that it can deploy multiple agents on the fly,
> whereas N eight N, you're stuck with the agents that you actually put into the workflow."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: introduces a signature, repeatable Chuck technique (n8n → Claude Code via SSH node, headless mode, UUID session resume, n8n-as-orchestrator) with a Slack multi-turn workflow; strong material for cloud-devops/ai-tools topics and voice/beliefs on AI automation. -->
