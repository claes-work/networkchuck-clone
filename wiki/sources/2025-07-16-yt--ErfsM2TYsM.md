---
type: youtube-video
source_date: 2025-07-16
url: https://www.youtube.com/watch?v=-ErfsM2TYsM
channel: "@networkchuck_v2"
ingested: 2026-07-22
tier: L2
domains: [homelab-selfhosting, cloud-devops, ai-tools]
tags: [n8n, self-hosting, on-premise, docker, automation]
---

# How to Run n8n Locally (Full On-Premise Setup Tutorial)

## Summary

A focused hands-on install tutorial from Chuck Keith's secondary channel
(@networkchuck_v2) walking through self-hosting n8n on-premise (in a homelab) or
on a cloud VPS, side by side. It is positioned as the "on-prem install" companion
to the main-channel n8n videos ([[2025-07-16-yt-ONgECvZNI3o]],
[[2025-10-03-yt-budTmdQfXYU]]) — Chuck explicitly tells viewers who don't know what
n8n is to go watch the main video first.

The tutorial covers three deployment flavors: exposed-to-the-internet (best
experience), fully local, and cloud VPS (Hostinger). The core setup path is:
(1) prerequisites — a cheap domain name and a free Cloudflare account, using a
Cloudflare Tunnel to reach the firewalled instance from the public internet;
(2) install Docker on Ubuntu via the apt repository; (3) install n8n via Docker
Compose following n8n's official documentation, using a `.env` file plus a
`docker-compose.yml` that spins up two containers (Traefik + n8n). Chuck also shows
the fully-local variant using a made-up `.local` domain backed by a local DNS
server entry. Throughout he stresses deferring to n8n's official docs because
specifics change over time.

## Key claims (dated — setup)

- 2025-07-16: n8n can be self-hosted on-premise (homelab) or on a cloud VPS;
  exposing the instance to the internet gives "the best time," but a fully-local
  install is also supported (paraphrase).
- 2025-07-16: The complexity in on-prem hosting comes from n8n wanting to connect
  to, and be connected to by, the public internet — while a self-hosted instance
  normally sits behind a firewall (paraphrase).
- 2025-07-16: Two prerequisites unblock internet exposure: (1) a domain name —
  potentially a subdomain — costing roughly $3–5/year, and (2) a free Cloudflare
  account. Both can be obtained from Cloudflare in one place (paraphrase).
- 2025-07-16: A Cloudflare Tunnel is free and creates a secure tunnel from your
  public domain to the n8n instance inside your network, bypassing the firewall
  (paraphrase).
- 2025-07-16 (Cloudflare Tunnel setup): In Cloudflare, manage the domain → Zero
  Trust → Networks → Tunnels → Create a tunnel → select Cloudflared → name it →
  install the connector. Chuck installs via the Debian package option (paraphrase).
- 2025-07-16: The `cloudflared` connector can be installed on the same machine as
  n8n or on any other Linux machine in the network that has access to the n8n host;
  for beginners, install it on the same machine (paraphrase).
- 2025-07-16: After pasting Cloudflare's install command (sudo password required),
  run the second command to install it as a service so the tunnel persists across
  reboots; the dashboard then shows the connector as "connected" (paraphrase).
- 2025-07-16 (tunnel public hostname): Set subdomain `n8n`, choose your domain,
  service type HTTPS, and point it at the n8n server's IP. Under Additional
  application settings, enable "No TLS Verify" (paraphrase).
- 2025-07-16: Whether on-prem or cloud, Docker is required. Chuck installs Docker
  on Ubuntu using the apt repository per the official Docker docs (two steps: set
  up the repo, then install Docker) (paraphrase).
- 2025-07-16 (n8n install): Follow n8n's official self-hosting docs. Create a
  directory `n8n-compose`, `cd` into it, and create a `.env` file with `nano .env`
  from the n8n config template (paraphrase).
- 2025-07-16: In `.env`, set the root domain (not the subdomain). Cloud/Hostinger
  users use the provided `*.hostinger.cloud` VPS hostname; homelab users use their
  Cloudflare domain; fully-local users can invent a `.local` domain (paraphrase).
- 2025-07-16: For a fully-local `.local` domain to resolve, you must add a DNS
  entry on a local DNS server pointing the `n8n` subdomain to the Docker host's IP
  (paraphrase).
- 2025-07-16 (.env values): Leave the subdomain as `N8N`; set your time zone (e.g.
  `America/Chicago`); set an SSL email for certificate generation (mainly relevant
  to cloud users) (paraphrase).
- 2025-07-16: Create a local files directory, then create `docker-compose.yml`
  (`nano docker-compose.yml`) from the n8n config, which defines two containers:
  Traefik and n8n. Traefik is not strictly required for this setup but is kept to
  stay close to the official docs; advanced users may remove it (paraphrase).
- 2025-07-16: Spin everything up with `docker compose up -d`; verify with
  `docker ps` to see the n8n and Traefik containers running (paraphrase).
- 2025-07-16: Access the instance at `https://n8n.<yourdomain>` (subdomain `n8n`).
  Once loaded, you are self-hosting your own n8n instance and ready to build your
  first automation (paraphrase).

## Notable verbatim quotes

> In this video, I'm going to show you how to self-host N8[N] on prim in your lab
> or on a VPS in the cloud.

> Now again exposing your N[8N] instance to the internet is going to give you the
> best time but you don't have to do that. This can be fully local.

> N[8N] it loves to connect to things. It also loves to have things connect to it.
> It's all about connections. Mr. social.

> Cloudflare has this amazing product called Cloudflare tunnels. It is completely
> free and what it enables us to do is create a super secret tunnel from our domain
> name from the public internet to our [n8n] instance in our network.

> We'll create our[.env] file. And we'll use nano for this because it is the best
> text editor in the world. Fight me.

> Now, for this, we're going to refer to the official documentation from N8N. Why?
> Well, because a lot of what I say here might change. So, always refer to their
> documentation.

> Now notice one thing to people who are very familiar with Docker. We're actually
> setting up two containers. We have a container called Trafic [Traefik] and a
> container called N8N.

> So now we are one step away from having this sucker spun up. one command that
> will be docker space compose up and then we'll do a space dash d just like this.
> Ready, set, go. Coffee break while it's performing magic.

> Now, at this point, you are self-hosting your very own N8N instance, and you're
> ready to start your first automation project.

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
