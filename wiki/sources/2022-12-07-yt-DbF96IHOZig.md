---
type: youtube-video
source_date: 2022-12-07
url: https://www.youtube.com/watch?v=DbF96IHOZig
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [homelab-selfhosting, cloud-devops]
tags: [monitoring, uptime-kuma, grafana, self-hosting, learn-x-now]
---

# you need to monitor your stuff RIGHT NOW!! (free)

## Summary

A "learn X RIGHT NOW" tutorial in which Chuck Keith walks through self-hosting
**Uptime Kuma**, a free, open-source monitoring tool created by Louis Lam. The pitch
rests on three selling points: it is free, "beautiful," and easy to set up (about five
minutes). Chuck frames it as enterprise-grade monitoring you can run in a home lab: it
watches websites, DNS servers, game servers, Raspberry Pis, and any home-lab or cloud
service, and it alerts you (Slack, Discord, Telegram, email, etc.) when something goes
down so you don't have to stare at a dashboard.

Chuck presents two deployment paths and says he runs both for redundancy:
1. **On-prem / home lab** — host on a Linux box (Raspberry Pi, spare laptop, enterprise
   server) via Docker + Docker Compose. Best for monitoring internal home-lab services
   without poking holes in the firewall.
2. **Cloud** — spin it up on a VPS (sponsor: Linode / "LE Node") using their marketplace
   one-click Uptime Kuma image. Best for monitoring anything on the public internet.

He then demonstrates creating several monitor types (HTTP, HTTP-with-keyword, DNS, TCP
port, ping), explains HTTP status-code ranges (200/400/500), sets up a Slack webhook
notification, and builds a public **status page**.

## Key claims (dated — the monitoring setup)

All claims dated 2022-12-07 (paraphrase unless quoted):

- Uptime Kuma is a free, open-source, self-hosted monitoring tool that tracks whether
  services are up or down and shows response-time graphs, certificate expiration info,
  and dashboards.
- Two hosting choices: inside the home lab (on a Linux-based server — Raspberry Pi, spare
  laptop, or enterprise server) or in the cloud on a VPS. On-prem avoids opening firewall
  holes for internal monitoring; cloud is better for monitoring public internet services.
  Chuck runs one instance in each for redundancy.
- **Cloud setup (Linode):** create a node, use the marketplace's pre-built Uptime Kuma
  image, fill in email / limited sudo user / password, optionally skip DNS, pick a region,
  choose a size (he picks a Shared CPU Nano, 1 GB, ~$5/month). Reverse DNS in the node's
  network settings gives a free DNS name to reach the instance.
- **On-prem setup (Docker):** SSH into the Linux server; install Docker and Docker Compose
  (`sudo apt install docker.io -y`, `sudo apt install docker-compose -y`); `mkdir` a
  directory and `cd` in; create `docker-compose.yml` with the official Uptime Kuma image
  (from Louis Lam), a mapped volume for persistent data, and exposed ports; run
  `docker compose up -d`; verify with `docker ps`. Access the web UI at the container's
  IP on **port 3001**.
- Monitor types demonstrated: **HTTP** (with a check interval — he prefers 30s over the
  default 60s — retries, cert-expiry notification, ignore-SSL for self-signed certs,
  accepted status codes, and HTTP method options); **HTTP with keyword** (loads the page
  and searches for a case-sensitive word/phrase — e.g. "start brewing" on
  networkchuck.coffee — up only if the keyword is found, even on a 200 OK); **DNS** (resolve
  a hostname against a specified resolver — he points it at his AdGuard server); **TCP port**
  (monitor a specific port — e.g. Plex on port 32400); **ping** (ICMP echo).
- HTTP status-code teaching nugget: 200 range = OK/up; 400 range = client-side problem;
  500 range = server-side problem.
- **Notifications:** configured under Settings → Notifications; supports Slack, Discord,
  Telegram, email, and many more. Slack is set up via an incoming webhook URL (create a
  Slack app → add incoming webhook → copy the webhook URL into Uptime Kuma). Notifications
  can be applied to all existing monitors and set default-enabled.
- **Status pages:** create a public page (with a URL slug) listing chosen monitors, usable
  as a dashboard on a TV/iPad; supports posting incidents and a dark mode.
- Uptime Kuma also offers two-factor authentication and reverse-proxy setup under settings.

## Notable verbatim quotes

> "It'll just tell me Slack, discord, whatever this is uptime kua. A monitoring tool you
> cannot believe is free."

> "Two reasons. You're going to love this. One, it's free. Two, it's beautiful... And I
> lied. Three reasons. Three, it's really easy to set up."

> "Now inside is cool because you can easily monitor all your home lab stuff without even
> thinking about it. You don't have to poke holes in that firewall."

> "First we're pulling the official container image from Louis Lam for uptime Kuma. Then
> we're naming it Uptime Kuma. And then right here, this is very important. We're mapping a
> volume to make sure that our uptime kuma data is persistent even if we tear down that
> container and build it back up. And then finally we expose some ports."

> "Anything in the 400 range as far as response codes go indicates there's an issue with
> the client, which is you... Anything in the 500 range, it's a problem with the site, it's
> a server issue, which if you're hosting your own website, the problem's still you."

> "Actually that's a nugget you wanna store in your pocket for pretty much anything in it,
> not just uptime kuma."

> "I can't tell you how lucky we are right now in this day and age to have this. Setting up
> monitoring has never been easier and it was so hard back in the day."

> "Again, a tool I cannot believe is free and a tool I can't believe you're not already
> using... Do it right now."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
