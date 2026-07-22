---
type: youtube-video
source_date: 2025-10-03
url: https://www.youtube.com/watch?v=budTmdQfXYU
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [homelab-selfhosting, ai-tools, cloud-devops]
tags: [n8n, automation, homelab, self-hosting, ai, workflow]
---

# n8n Now Runs My ENTIRE Homelab

## Summary

Part two of Chuck's n8n AI-agent series. He builds an AI IT employee named "Terry" in
n8n that can monitor, troubleshoot, and (with human approval) fix things across a
homelab and network. The video is a hands-on build walking from a trivial "is this
website up?" check to a multi-tool agent wired into UniFi, Proxmox, Plex, and a NAS via
CLI/API.

The core idea: anything with a CLI or an API can be controlled by an n8n AI agent, and
the way you teach the agent is by reverse-engineering how *you* would monitor,
troubleshoot, and fix something, then handing the agent the same tools and process.
Chuck progressively escalates trust — read-only checks → running fixed commands →
letting the agent choose commands → letting it apply fixes → human-in-the-loop approval
gates — deliberately framing it as onboarding a junior hire you don't give root access
on day one.

He also demonstrates the failure modes honestly: the agent hits an iteration limit
(~10 tool calls), and at one point stops the very Traefik/n8n container running itself,
which motivates the human-in-the-loop approval flow. The video ends by teasing a part
three: sub-agents (Terry promoted to CTO managing a network engineer, storage engineer,
Linux admin), centralized network documentation for the agents, and an AI help desk /
ticketing system. Closes with Chuck praying over the viewer's career.

Concrete host stack shown: a self-hosted n8n instance on a Hostinger KVM2 VPS (sponsor),
with Twingate used as a headless client on the VPS to securely reach the home network
24/7 even when the homelab is down.

## Key claims (dated — the automations + idea)

All paraphrased from the 2025-10-03 video unless quoted.

- The central thesis: if a device or service has a CLI or an API, an n8n AI agent can
  monitor, troubleshoot, and fix it — you teach the agent by showing it the same
  process you would follow yourself. (2025-10-03)
- Recommends hosting the agent in the cloud (self-hosted n8n on a Hostinger VPS) rather
  than in the homelab, so the agent survives homelab outages and is immune to the
  owner's own tinkering. (2025-10-03)
- Uses Twingate as a headless client running on the VPS to securely connect the
  cloud-hosted agent back to the home/business network 24/7. (2025-10-03)
- Agent build blocks in n8n: an AI Agent node with a chat model (ChatGPT, GPT-4.1-mini
  for speed, later GPT-4.1 full for harder problems) plus Simple Memory keyed on a
  chat/session ID. (2025-10-03)
- Tools given to the agent: an HTTP Request tool ("website tool") to check a site is up;
  an SSH tool built by adding an SSH node, converting it to a sub-workflow, and calling
  it via the "Call n8n Workflow" tool so the agent can run arbitrary CLI commands
  ("docker tool" / later "CLI tool"). (2025-10-03)
- Monitoring automation: a Schedule trigger runs the agent every 5 minutes; a Set/Edit
  Fields node injects an artificial prompt and chat ID so the scheduled run has a user
  message and memory context. (2025-10-03)
- Alerting automation: a Telegram "send message" node reports results (Slack or Discord
  work equally). Structured output (a Structured Output Parser emitting JSON like
  `website_up: true/false` + a message) plus an IF node filters alerts so Chuck is only
  notified when something is actually wrong. (2025-10-03)
- Self-healing automation: changing only the agent's prompt lets it fix issues — e.g.
  run `docker start website`, then re-verify the site is up and report. (2025-10-03)
- Open-ended troubleshooting: giving the agent unrestricted CLI access plus context
  (which port, that it's a Docker container) let GPT-4.1 diagnose and resolve a port
  conflict it had never seen (found the rogue `python3 -m http.server` process on port
  8090 and killed it). GPT-4.1-mini failed the same task — model capability was
  inconsistent, motivating guardrails. (2025-10-03)
- Human-in-the-loop: a Telegram "send and wait for response" node with an approval
  response type gates system-modifying commands; the agent's prompt requires explicit
  approval before running anything that changes the system (read-only checks like
  `docker ps` or logs don't need approval). The approve response is looped back to the
  agent along with the chat ID so it retains context. (2025-10-03)
- A Switch node (replacing an IF) routes notifications on multiple conditions — notify
  when a fix was applied AND when the website is down. (2025-10-03)
- Real homelab integrations demonstrated via CLI/API: UniFi API (identify top 5
  bandwidth hogs — Chuck grabbed the API docs and had AI summarize them into the system
  prompt), Proxmox (SSH CLI + API — reported 3 running VMs: Home Assistant, a Docker
  host "Keith", and a FreeIPA/LDAP server), and Plex API (who is streaming — reported
  Chuck Keith watching "The Mummy" (1999)). NAS (TrueNAS/SETH on a 45Drives server, and
  a ZimaCube Pro at home) named as further CLI-controllable targets. (2025-10-03)
- Integration with existing monitoring: you don't have to replace SolarWinds or Uptime
  Kuma — have them fire a webhook to Terry, who then troubleshoots and fixes. (2025-10-03)
- Stated meta-benefit: building this forces you to reverse-engineer your own
  troubleshooting and document how your network is actually put together so you can
  describe it to the agent — making you better and more knowledgeable in the process.
  (2025-10-03)
- Teased next video: sub-agents (Terry as CTO managing specialized network/storage/Linux
  agents), centralized network documentation the agents read and maintain, and an AI
  help desk / ticketing system for users (editors, family). (2025-10-03)

## Notable verbatim quotes

> So, in this video, we're going to build your very own super intelligent AI agent, aka
> your new IT employee. It can monitor, it can troubleshoot, and even with your explicit
> permission, fix things in your network and home lab.

> Talking UniFi, Proxmox, Plex, your NAS. If it has a CLI or API, Terry can handle it.
> But hold on. We're going to treat Terry like a new hire. You don't give the new guy
> root access in the first day. You got to build that trust.

> The ability to actually connect to things in our home lab and network so it can
> monitor, troubleshoot, and yes, even fix stuff.

> You're going to think about how you would monitor something, how you would
> troubleshoot something, how you would even fix something, and then show Terry the same
> process.

> Giving our AI agent the ability to log into servers via CLI. That is so stinking
> powerful.

> That right there brings us to one of the main problems I have with letting AI do
> anything on my network. I would have stopped Terry from doing that, but I didn't know.
> But I still want him to try and troubleshoot things. I want him to work, but I want to
> be in the loop. And this is called human in the loop.

> We also set up approvals. Like, that's a pretty amazing thing. Putting yourself, the
> human, in the loop. That's people's biggest fears right now with AI. It's like, I
> don't know what it's doing, man. I can't control it. Like fine, put yourself in the
> middle. Put in guard rails.

> You're having to reverse engineer how you would troubleshoot things. You're having to
> think about how your lab or your network or your business network is actually put
> together so you can describe it properly to an AI agent.

> Anything you can do in the CLI, including creating virtual machines, deleting them,
> stopping them, restarting, whatever you got to do, you can have Terry do that.

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: canonical build of Chuck's n8n AI-agent-runs-the-homelab thread; concrete architecture (cloud n8n + Twingate, SSH-as-subworkflow tool, structured output, human-in-the-loop approvals) plus his "teach the agent your own troubleshooting process" and "onboard AI like a junior hire" frameworks — strong topic + beliefs/voice material. -->
