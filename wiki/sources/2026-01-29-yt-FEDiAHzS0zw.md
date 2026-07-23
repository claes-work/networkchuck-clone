---
type: youtube-video
source_date: 2026-01-29
url: https://www.youtube.com/watch?v=FEDiAHzS0zw
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [ai-tools, linux-terminal, cloud-devops]
tags: [claude-code, mobile, termux, ssh, ai-agents]
---

# Claude Code on your phone in 10 minutes

## Summary

A tutorial for running Claude Code (Anthropic's terminal-based agentic coding CLI) from a phone, so you can "code and hack from anywhere." Chuck's framing: Claude Code is a terminal app, and phones don't have a terminal — so the trick is to remote into a terminal running Claude Code on an always-on remote machine.

The method has two goals: (1) get a terminal on your phone, and (2) set up a remote terminal that "will never, ever go down" — his "forever terminal." His build:

1. **Provision a cloud VPS** — the "forever terminal." He uses Hostinger (sponsor; go to hostinger.com/networkchuck), specifically the KVM 2 plan, and selects a pre-built OS template that ships with Claude Code pre-installed. After setting a password you can open a browser terminal, type `claude`, and log in.
2. **Harden the Linux VPS** (since it is exposed to the public internet) with three steps: install and run **Fail2Ban** (blocks brute-force attacks) via `sudo apt install fail2ban -y` / `systemctl status fail2ban`; enable the **UFW firewall** allowing only port 22 (SSH) via `sudo ufw allow 22 && sudo ufw enable`; and later disable password authentication.
3. **Install a phone terminal/SSH client** — **Termux** on the phone (note: the transcript's captions render the terminal/SSH app as "Terminus"; Chuck states he is not sponsored by that app, only by Hostinger). No account needed. Create a host pointing at the VPS DNS name or public IP, username `root`, and the VPS password, then connect — `claude` runs.
4. **Switch to SSH key auth** — generate an SSH key inside the app, export/share it to the host, remove the saved password, then disable password authentication on the server (edits the SSH config in two files, including a Hostinger override file, and restarts SSH). Password logins are then denied ("public key denied" from a plain client), but the phone with the key still gets in.
5. **Add tmux for persistent sessions** — install `tmux` (`apt install tmux`, often pre-installed). Because Claude Code sessions otherwise vanish when the phone locks, loses signal, or a plane takes off, tmux (a terminal multiplexer) keeps sessions alive. Start a session with `tmux`, launch Claude, detach with `Ctrl+B D`, and reattach after reconnecting with `tmux a` (last session) or `tmux a -t <name>` (named session). One fix: scrolling doesn't work with the phone client out of the box, so add a one-line mouse quality-of-life setting to the tmux config file.

Takeaway: with a hardened, always-on VPS plus a phone SSH client plus tmux, you can run Claude Code — and build/run whole projects like a website on the host itself — "from literally anywhere." The video closes with Chuck's signature prayer for the audience.

## Key claims

- (2026-01-29) Claude Code is a terminal app; because phones lack a terminal, you can't run Claude Code directly on a phone — the workaround is to remote (SSH) into a terminal running Claude Code on a remote machine. [paraphrase]
- (2026-01-29) The recommended setup is an always-on cloud VPS (his "forever terminal"); he uses Hostinger's KVM 2 plan with an OS template that has Claude Code pre-installed. [paraphrase]
- (2026-01-29) A public VPS must be hardened: install Fail2Ban (auto-blocks brute-force attacks), enable the UFW firewall allowing only port 22 for SSH, and disable password authentication in favor of SSH key auth. [paraphrase]
- (2026-01-29) On the phone he uses a mobile SSH/terminal app (captions say "Terminus"; he is not sponsored by it) to connect to the VPS via DNS name or public IP as root. [paraphrase]
- (2026-01-29) SSH key authentication replaces the password: generate a key in the app, export it to the host, remove the saved password, then disable password auth server-side by editing the SSH config (two files, one a Hostinger override) and restarting SSH. [paraphrase]
- (2026-01-29) tmux keeps Claude Code sessions persistent so they survive phone lock, lost signal, or disconnects — detach with `Ctrl+B D` and reattach with `tmux a` / `tmux a -t <name>`. [paraphrase]
- (2026-01-29) tmux mouse scrolling doesn't work with the phone client until you add one line to the tmux config file. [paraphrase]
- (2026-01-29) Overall takeaway: this setup lets you "code and hack from anywhere," and you can build and run whole projects (e.g. a website with Claude) directly on the host. [paraphrase]

## Notable verbatim quotes

> Claude code has been blowing up. There are actually articles about Claude Code Addiction. I believe it. I've got it. Do you have it?

> What if you could use Claude code at the airport on the couch, in the shower, on the toilet? I want to give you that freedom.

> Claude code is a terminal app. That's what I love about it. ... Our phones most of us, so we can't use cloud code on our phones. But what if using our phones we could remote into a terminal running cloud code?

> We have actually two goals in our mission. Number one, get a terminal on our phone. And number two, set up a remote terminal that will never, ever go down. ... We'll call it our forever terminal.

> Is this thing even secure? This is accessible to the entire world. We got to make sure you protect it. We got to harden this Linux machine.

> What happens when I don't know, your phone locks or you lose signal or your plane's taking off? What happens to that cloud code session? ... There's a way to fix that. It's called tmux.

> Now you can code and hack from anywhere and with hosting your As your VPS, you can do a bunch of things like build a website with Claude and it runs the website and it builds it right there on the stinking host.

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: canonical hands-on method for running Claude Code from a phone (VPS + SSH-key hardening + tmux persistence); core to his Claude Code / AI-tools thread and reusable as a topic page. -->
