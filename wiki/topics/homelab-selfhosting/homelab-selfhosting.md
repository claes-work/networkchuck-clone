---
type: hub
domain: homelab-selfhosting
created: 2026-07-14
updated: 2026-07-22
---

# Homelab & Self-Hosting — hub

Homelab builds, Proxmox, Docker, Raspberry Pi, and self-hosted services — learning by running your own infrastructure.

## Key ideas & topics

- **Move your home network into a real data center (DMVPN).** (2018-07-16) Chuck describes relocating his personal home network into a Dallas colocation/data center and stitching the two ends together over a DMVPN (Dynamic Multipoint VPN) tunnel — treating his own lab as production-grade personal infrastructure and using it as hands-on practice for enterprise WAN tech. See [[../../sources/2018-07-16-yt-G5HucqXioBY]]. Cross-links [[../networking/networking]] and [[../cloud-devops/cloud-devops]].
- **Self-host Pi-hole on Docker for network-wide ad and content blocking.** (2020-05-02) Chuck runs Pi-hole in a Docker container as a self-hosted DNS sinkhole that blocks ads and trackers for every device on the LAN, layering it with an upstream resolver (OpenDNS) for content filtering and wiring in IFTTT so the blocking can be toggled/automated. Positioned as an easy, high-payoff first self-hosted service. See [[../../sources/2020-05-02-yt-dH3DdLy574M]]. Cross-links [[../cloud-devops/cloud-devops]] (Docker) and [[../linux-terminal/linux-terminal]].
- **The Raspberry Pi as a cheap, fun homelab building block.** (2020-02-28) Chuck frames the Raspberry Pi as an inexpensive, low-stakes machine for learning — setting up a Pi as a full Linux "learning desktop" so beginners can practice Linux and self-hosting without risking their main computer. See [[../../sources/2020-02-28-yt-vbaJcRxASo0]]. Cross-links [[../linux-terminal/linux-terminal]].
- **Maker/automation projects with the Pi (Halloween automation).** (2019-10-27) Chuck builds a Raspberry Pi Halloween automation rig, tying physical props to software via IFTTT, Alexa voice triggers, and a REST API — a playful demonstration that a homelab is also a place to build fun, tangible automation projects, not just serious infrastructure. See [[../../sources/2019-10-27-yt-B_krqlk_cXo]]. Cross-links [[../cloud-devops/cloud-devops]] (APIs/automation).

## Source pages

- (2018-07-16) [[../../sources/2018-07-16-yt-G5HucqXioBY]] — Moving my HOME NETWORK to a DATA CENTER w/ DMVPN
- (2019-10-27) [[../../sources/2019-10-27-yt-B_krqlk_cXo]] — Raspberry Pi Halloween Automation (IFTTT/Alexa/REST)
- (2020-02-28) [[../../sources/2020-02-28-yt-vbaJcRxASo0]] — How to Setup a Raspberry Pi LEARNING Desktop
- (2020-05-02) [[../../sources/2020-05-02-yt-dH3DdLy574M]] — BLOCK EVERYTHING w/ PiHole on Docker
