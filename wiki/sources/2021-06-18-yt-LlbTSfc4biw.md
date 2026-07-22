---
type: youtube-video
source_date: 2021-06-18
url: https://www.youtube.com/watch?v=LlbTSfc4biw
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cloud-devops, homelab-selfhosting, networking]
tags: [load-balancing, haproxy, nginx, home-network, learn-x-now, homelab]
---

# you need to learn Load Balancing RIGHT NOW!! (and put one in your home network!)

## Summary

A landmark "you need to learn X RIGHT NOW" tutorial in which Chuck teaches load
balancing conceptually and then walks through a full home-lab build: putting a free
enterprise-grade load balancer (Kemp's **LoadMaster**, sponsor) inside his home network
so that a single public port (443) securely fronts every home service — Plex, multiple
Synology NAS boxes, Proxmox, ESXi, and websites — each reachable by its own
HTTPS subdomain instead of a bare IP address.

He opens with the classic teaching analogy: a website (`networkchuck.coffee`) whose
single server buckles under traffic, so you add a second server and place a load
balancer in front to distribute the load evenly. He then reframes the problem for the
home lab: instead of "poking holes" in your router by forwarding a separate port for
each service (443 for a site, 5000/5001 for a NAS, 32400 for Plex), you close every
port except 443, forward that one port to the load balancer, and let it route
everything internally.

The build has four pieces, all free: the Kemp LoadMaster (deployed as an OVF virtual
appliance on a type-1 hypervisor — he uses VMware ESXi, notes KVM/Proxmox work too),
a Freenom free domain (`hackwell.tk` in the demo), a Cloudflare account for DNS + SSL,
and access to the home router to forward port 443. He configures a **Virtual Service**
on a **VIP** (virtual IP, `10.7.1.30`) listening on 443, then adds sub-virtual services
pointing to **real servers** (each home service's real IP and port). He shows Kemp's
**health checks** (ICMP/HTTP/HTTPS) removing an unhealthy server from rotation, layer-3
vs. layer-4-to-7 load balancing, and **content switching / content rules** (layer-7
Host-header matching) so `plex.hackwell.tk` routes to the Plex server on 32400 while
`nasty.hackwell.tk` goes to the NAS — all behind one VIP. Cloudflare hides his public
IP (proxied A records) and issues a free Let's Encrypt **wildcard** SSL cert; he sets
encryption to Full and generates a CSR on Kemp, installing a Cloudflare origin cert so
traffic is encrypted end to end (re-encrypt to the backend). He closes by demonstrating
true load balancing across two web servers with automatic failover, and notes Kemp's
built-in web application firewall.

## Key claims (dated — LB concepts + build)

- **[2021-06-18]** A load balancer's core job: when one server can't handle the traffic
  load, you add more servers and put a load balancer in front to distribute requests
  evenly across them instead of hammering a single box. (paraphrase)
- **[2021-06-18]** The most common traditional use of a load balancer is fronting a
  website whose single server is overwhelmed; the load balancer sits between clients and
  the server pool. (paraphrase)
- **[2021-06-18]** Home-lab framing: without a load balancer, exposing multiple internal
  services means port-forwarding a separate port per service ("poking holes" —
  e.g. 443 web, 5000/5001 NAS, 32400 Plex), which Chuck considers insecure. (paraphrase)
- **[2021-06-18]** You can't forward the default HTTPS port 443 to more than one internal
  server; a single forwarded port can only point at one internal IP — a limitation the
  load balancer solves. (paraphrase)
- **[2021-06-18]** The build closes every inbound port except 443 and forwards only 443
  to the load balancer's VIP; the load balancer then routes to every internal service.
  (paraphrase)
- **[2021-06-18]** Tool used: **Kemp LoadMaster**, downloadable free (marketed at
  freeloadbalancer.com) as a virtual appliance; it should run on a type-1 hypervisor
  (ESXi or KVM preferred; Proxmox works with workarounds). (paraphrase)
- **[2021-06-18]** The free Kemp tier is "free forever," gives essentially all features
  needed for this build, and its main limit is a 20 Mbps throughput cap — which Chuck
  calls not a big deal for home use. (paraphrase)
- **[2021-06-18]** The Kemp license is tied to the VM's MAC address, so you must set the
  virtual NICs to static/manual MAC addresses so they never change. (paraphrase)
- **[2021-06-18]** A **VIP (virtual IP address)** is created on the load balancer — an IP
  that belongs to nobody until the Virtual Service claims it; it becomes the single
  portal to every service in the network. (paraphrase)
- **[2021-06-18]** Structure: a Virtual Service (VIP on port 443) contains sub-virtual
  services, each pointing at one or more **real servers** (the actual internal service
  IP + port, e.g. NAS on 5001, Plex on 32400). (paraphrase)
- **[2021-06-18]** Kemp performs **health checks** — not just a ping but protocol-level
  checks (HTTP/HTTPS/ICMP) — and stops sending traffic to a server that fails, so an
  unhealthy backend is skipped. (paraphrase)
- **[2021-06-18]** Layer-3 (network) load balancing routes on IP-level information; modern
  load balancers like Kemp operate layer 4 to layer 7 and are often called layer-7 load
  balancers. (paraphrase)
- **[2021-06-18]** **Content switching / content rules** are the layer-7 magic: a rule
  matches the Host header (e.g. `plex.hackwell.tk`) and forwards to the matching backend
  — Chuck calls this content filtering. It requires enabling content switching on the
  service and attaching the rule to the right sub-service. (paraphrase)
- **[2021-06-18]** Free domain via **Freenom** (`.tk` etc.); free DNS + SSL via
  **Cloudflare** by switching the domain's name servers from Freenom to Cloudflare.
  (paraphrase)
- **[2021-06-18]** Cloudflare's proxied A record **hides your public IP** — pinging the
  domain returns a Cloudflare IP, not the home IP, which Chuck frames as a security win.
  (paraphrase)
- **[2021-06-18]** Cloudflare issues a free **Let's Encrypt wildcard** SSL cert
  (`*.domain`), which normally costs money; it covers every subdomain automatically.
  (paraphrase)
- **[2021-06-18]** Cloudflare SSL modes: Flexible encrypts only browser-to-Cloudflare;
  setting it to **Full** encrypts Cloudflare-to-origin too, which requires generating a
  CSR on Kemp and installing a Cloudflare origin certificate. (paraphrase)
- **[2021-06-18]** On Kemp, enabling **SSL acceleration** + the **re-encrypt** option
  further encrypts traffic between the load balancer and the backend servers. (paraphrase)
- **[2021-06-18]** Alternatively, the load balancer itself can be an **SSL offloader** —
  Kemp integrates with Let's Encrypt to centrally manage certs instead of each backend
  server handling its own SSL, which is the typical enterprise pattern; here he lets
  Cloudflare handle SSL because it works for a home lab. (paraphrase)
- **[2021-06-18]** True load balancing demo: a website backed by two real servers of equal
  weight splits traffic between them; changing the weight biases traffic to one; shutting
  one down triggers automatic failover to the other. (paraphrase)
- **[2021-06-18]** Kemp includes a built-in **web application firewall (WAF)** with
  protective rules, available even on the free tier. (paraphrase)
- **[2021-06-18]** Payoff/career framing: this deploys the same enterprise-grade load
  balancer used in real IT environments, so learning it at home teaches "all the knobs"
  and translates directly to enterprise work and a resume. (paraphrase)

## Notable verbatim quotes

> "Okay, you need to put a load balancer in your house like right now. It's amazing,
> totally free, and will change the whole game for your home network."

> "we need something to balance the load. A load balancer. Huh. What a great idea."

> "I hate having holes in my network. Feels very insecure. And you know, it is. You
> shouldn't have this many holes in your network."

> "This virtual IP address will be the portal to every service you have in your network."

> "modern load balancers like Kemp can go layer 4 to layer 7. They're often called
> layer 7 load balancers... instead of relying on the layer 3 information, just looking
> at IP address stuff, we can look at things like, hey, what URL did they type in?"

> "This is called content filtering and it's amazing."

> "it's possibly the geekiest thing you can do in your home lab and it's amazing."

> "Home lab on steroids. Let's keep going."

> "I love that you can put an enterprise-grade load balancer in your house for free...
> And when you go into the enterprise environment and deploy a load balancer in a
> company, it works the same way. So, you know how a load balancer works."

> "don't forget to hack the YouTube algorithm today... Let's hack YouTube today.
> Ethically, of course."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: 'you need to learn X RIGHT NOW' format (Load Balancing) + homelab build -->
