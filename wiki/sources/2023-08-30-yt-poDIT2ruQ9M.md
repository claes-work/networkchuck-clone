---
type: youtube-video
source_date: 2023-08-30
url: https://www.youtube.com/watch?v=poDIT2ruQ9M
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [homelab-selfhosting, linux-terminal]
tags: [tool, discovery, productivity]
---

# how did I NOT know about this?

## Summary

Chuck showcases **ntfy** (pronounced "notify"), a free, open-source, self-hostable
push-notification service that lets you send notifications from the command line (or any
script/service) to your phone, browser, or desktop. He frames it as a productivity tool:
kick off a long-running task — an Nmap scan, a large file copy, a download, a `apt`
upgrade, a server reboot — attach an ntfy command, then walk away and make coffee while
your phone tells you when it finishes.

The video is a full setup walkthrough. He deploys the ntfy server two ways, both via
**Docker**: in the cloud on a Linode ($5/month Ubuntu VM; Linode is the sponsor and now
owned by Akamai) and on-prem on a Kali Linux box (works on a Raspberry Pi too). He then
installs the ntfy mobile app (Android/iOS), points it at the self-hosted server, and
subscribes to a "topic" (e.g. `coffee`). Notifications are sent with a simple `curl -d`
command to `server/topic`. For iPhone push to work, he edits a `server.yml` config file
and sets an `upstream-base-url` of `ntfy.sh` (only a message ID is relayed, not the
notification contents). To expose an on-prem server to the internet safely he uses
**Cloudflare Tunnels** (free, no open router ports, needs a domain + Cloudflare account).

He closes with a run of "fun" use cases: piping command output into a notification,
using shell `&&` (success) and `||` (failure) to fire different alerts, cron/Windows
scheduled-task notifications, ntfy's built-in natural-language scheduling, emojis, a
reboot loop that alerts when a host comes back up, integration with Uptime Kuma, and
battery/CPU/GPU alert scripts. Shout-out to creator Philip, who reached out to Chuck
about the tool.

## Key claims (dated — the tool + use)

- 2023-08-30: **ntfy** ("notify") is a free, open-source, self-hostable push-notification
  tool; Chuck presents it as his newly discovered favorite for being notified when
  long-running command-line tasks finish.
- 2023-08-30: The ntfy server runs in Docker with essentially the same steps whether
  hosted in the cloud or on-prem; it can run on a Raspberry Pi.
- 2023-08-30: Cloud setup used a $5/month Ubuntu 20.04 Linode; new Linode users get a
  $100 / 60-day credit via the sponsor link (Linode is now owned by Akamai).
- 2023-08-30: Docker install is `sudo apt update` then `sudo apt install docker.io -y`;
  the container is verified with `sudo docker ps`.
- 2023-08-30: You send a notification with `curl -d "<message>" <server>/<topic>` from
  any terminal (Mac, Linux, Windows) — subscribers to that topic on the app/web/CLI
  receive the push.
- 2023-08-30: iPhone push notifications require editing `/etc/ntfy/server.yml`: set the
  `base-url` to your server and uncomment `upstream-base-url: https://ntfy.sh`; the
  upstream server only receives the message ID (not contents) and tells the iOS app to
  pull the message from your server.
- 2023-08-30: The config-enabled container adds a `-v` volume mapping (`/etc/ntfy` and a
  cache dir for persistence) and an option to load the config file.
- 2023-08-30: To reach an on-prem server from anywhere, use free Cloudflare Tunnels
  (via a `cloudflared` Docker container) — no router ports opened; requires a domain and
  a Cloudflare account; map a subdomain to the server's internal IP over HTTP.
- 2023-08-30: You can pipe a command's output into a notification by capturing it in a
  shell variable (e.g. `scan=$(nmap ...) && curl -d "$scan" server/topic`).
- 2023-08-30: Use `&&` to notify on command success and `||` to notify on failure; both
  can be chained to send different messages depending on the outcome.
- 2023-08-30: ntfy works from cron jobs and Windows scheduled tasks (via PowerShell), so
  scripts (backups, etc.) can report success or failure to your phone.
- 2023-08-30: ntfy has built-in scheduling — `curl -H "At: <natural language>"` (e.g.
  "10 seconds", "30 minutes", "next Tuesday") delays delivery, handled server-side.
- 2023-08-30: Emojis are added with a `-H` tags header; full list is in the ntfy docs.
- 2023-08-30: A `while` ping loop can hold until a rebooting host comes back up, then
  fire an "it's up" notification (with emoji); omitting the negation alerts when a host
  goes down instead.
- 2023-08-30: ntfy integrates natively with Uptime Kuma and many other services, and can
  act as a generic webhook (Ansible, Salt, Puppet, Chef, GitHub Actions, etc.).
- 2023-08-30: A PowerShell (or Mac/Linux) script can alert when battery drops below a
  set percentage; similar scripts can watch CPU/GPU.
- 2023-08-30: On Windows, use Command Prompt (not PowerShell) with `curl`, since
  PowerShell handles it oddly.
- 2023-08-30: ntfy is free/open-source and fully self-hostable; the creator (Philip) also
  offers a paid hosted service at ntfy.sh for those who don't want to self-host.

## Notable verbatim quotes

> "That's just a few examples of the amazing notification tool called N T F Y or notify.
> It's free open source and you can self-host it, and it's stupid how much it can do."

> "Docker is my favorite."

> "It finished before I could even say anything. That's why I love Docker."

> "It can alert off of anything you do from command line commands like this to scripts.
> Anything within a script, you can do a custom notification that'll push to your phone.
> How crazy is that? It's limitless."

> "Just know it's the absolute best way to expose your home network to the internet
> without too unsafe. It's pretty safe, actually. Kind of amazingly easy."

> "This is something that would've come in handy so many times in testing my scripts."

> "Your imagination is the only limit."

> "And shout out to Philip, the creator. He actually reached out to me and said, Hey,
> I've got this pretty cool tool. And I'm like, eh, whoa, hold on. This is actually
> pretty cool. I've got to make a video about this."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
