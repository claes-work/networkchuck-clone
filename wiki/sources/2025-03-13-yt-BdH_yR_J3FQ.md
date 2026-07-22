---
type: youtube-video
source_date: 2025-03-13
url: https://www.youtube.com/watch?v=BdH_yR_J3FQ
channel: "@networkchuck_v2"
ingested: 2026-07-22
tier: L2
domains: [homelab-selfhosting, ai-tools, cloud-devops]
tags: [open-webui, ssl, reverse-proxy, domain, self-hosting, local-ai]
---

# Turn Open WebUI into a real website (Domain + SSL)

## Summary

Part 2 of Chuck's Open WebUI pair (the setup video is [[2025-03-13-yt-JJ_0-pAOIEk]]). The
premise: Open WebUI is one of the best ways to self-host your AI hub — it gives you control
and can connect to the big cloud models (ChatGPT, Gemini, Grok, Claude) via API keys — but it
has **no built-in SSL**, which makes it awkward to put a real domain name and an SSL
certificate in front of it. This tutorial fixes that by wrapping an already-running Open WebUI
server in a proper domain + HTTPS so it looks "nice, safe, and secure" for the friends/family
group you're sharing it with.

The video assumes you already have Open WebUI running and — the stated **hard prerequisite** —
that the server has a **public IP address** (his example is a Hostinger VPS reached at
`185.28.224.x`). A machine on a private/LAN address (`192.168.x.x`, `10.x.x.x`) will not work
with this method; Chuck flags that as a separate future video.

Three steps: (1) acquire a domain — he registers one directly through Cloudflare as a
one-stop-shop, but notes you can bring an existing domain from GoDaddy/Hostinger by pointing
its nameservers at Cloudflare's; (2) in Cloudflare DNS, add an **A record `@`** pointing to the
VPS public IP, plus a **wildcard A record `*`** so any subdomain (e.g. `ai.<domain>`) resolves
to the same server; (3) on the VPS, deploy **Nginx Proxy Manager** via a small
`docker-compose.yml` and `docker compose up -d`, then use its web admin (port 81) to create
**proxy hosts** — one pointing the bare domain at `localhost:81` (the NPM admin itself), and one
pointing `ai.<domain>` at the VPS IP on port **8080** (Open WebUI's default), with WebSocket
support enabled. The result: `ai.<domain>` loads Open WebUI over HTTPS with no port in the URL,
and the browser reports a secure connection. Hosted on a Hostinger VPS, using its browser
terminal. Fictional example domain used throughout: `ilovebernardhackwell.com`.

## Key claims (dated — setup)

- **[2025-03-13]** Prerequisites: Open WebUI must already be running on a server, and that
  server must have a **public IP address**. Private/LAN IPs (`192.168.x.x`, `10.x.x.x`) do not
  work with this method — a VPS in the cloud is the expected setup. (paraphrase)
- **[2025-03-13]** Problem being solved: Open WebUI has **no built-in SSL**, so adding your own
  domain + SSL certificate is otherwise hard. (paraphrase)
- **[2025-03-13]** Step 1 — get a domain. Chuck's preferred method is registering it directly in
  **Cloudflare** (one-stop-shop, since you'll use Cloudflare for SSL/WAF anyway). The domain
  costs a little money; Cloudflare's service is free. (paraphrase)
- **[2025-03-13]** Bring-your-own-domain path: if the domain is registered elsewhere (GoDaddy,
  Hostinger), add it to Cloudflare on the free plan and change the nameservers at your registrar
  to the ones Cloudflare provides; once Cloudflare recognizes them, you can manage it there.
  (paraphrase)
- **[2025-03-13]** Step 2 — Cloudflare DNS. Add an **A record** with name `@`, pointing the root
  domain to the VPS public IP. (paraphrase)
- **[2025-03-13]** Add a second **A record** with name `*` (wildcard) to the same VPS IP, so any
  subdomain (e.g. `ai.<domain>`) resolves to the server. That completes the Cloudflare side.
  (paraphrase)
- **[2025-03-13]** Step 3 — deploy **Nginx Proxy Manager (NPM)** on the VPS. Create a directory
  (`mkdir npm`), `cd npm`, create `docker-compose.yml` with `nano` and paste the config from the
  linked GitHub page, save with Ctrl-X / Y / Enter. (paraphrase)
- **[2025-03-13]** Spin it up with **`docker compose up -d`**; verify the container with
  `docker ps`. (paraphrase)
- **[2025-03-13]** NPM admin runs on **port 81** (`<IP>:81`). Default login is `admin@example.com`
  / password `changeme`, and it prompts you to change those on first login (which you should).
  (paraphrase)
- **[2025-03-13]** First proxy host: domain = the bare domain, scheme HTTP, forward host
  **`localhost`**, port **81** — so the domain itself reaches the NPM admin. Enable **WebSocket
  support**. (paraphrase)
- **[2025-03-13]** Second proxy host: domain = **`ai.<domain>`** (the subdomain, covered by the
  wildcard record), forward host = the **VPS public IP**, port **8080** (Open WebUI's default).
  Enable WebSocket support. (paraphrase)
- **[2025-03-13]** Result: browsing to `ai.<domain>` loads Open WebUI over HTTPS with **no port
  specified** (NPM handles it) and the browser shows the connection as secure. (paraphrase)
- **[2025-03-13]** Having NPM on the server "unlocks" many other self-hosting possibilities; you
  can dig into it or just follow along and leave it be. (paraphrase)
- **[2025-03-13]** Value framing for Open WebUI: it can run local AI models, and it can connect to
  the big cloud models (ChatGPT, Claude, Gemini, Grok) via API keys — pay-as-you-go instead of a
  monthly plan. (paraphrase)

## Notable verbatim quotes

> "open web UI it's amazing it's one of the best ways to self-host your AI and connect it to
> other AIs like ChatGPT Gemini Grok Claude it gives you control but you know what's not great
> about open web UI it doesn't have built-in SSL"

> "I'm going to be assuming right now that you have a public IP address we can use if you set up
> an open web UI server in your house on a laptop or something and it has a private IP address
> like 192.168... or 10... this scenario will not work for you"

> "we're already going to be using Cloudflare for our SSL and our WAF or our web application
> firewall but we can also buy a domain from them which is nice one-stop shop"

> "it's a wildcard saying whatever subdomain you have it's going to go to the same address that
> we put in right now which is our VPS server"

> "we'll use the best text editor in Linux period it's called Nano"

> "with just one more command we're going to spin up Nginx proxy manager it's so stinking cool
> you ready the command will be docker compose up -d"

> "notice I'm not going to specify any ports because Nginx proxy manager is taking care of that
> for us Ready Set Go and it just stinking works... connection is secure"

> "hit that subscribe button please and please make sure you hack the YouTube algorithm hit that
> like button... you got to hack YouTube today ethically of course"

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
