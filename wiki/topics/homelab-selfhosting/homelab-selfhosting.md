---
type: hub
domain: homelab-selfhosting
created: 2026-07-14
updated: 2026-07-23
---

# Homelab & Self-Hosting — hub

Homelab builds, Proxmox, Docker, Raspberry Pi, and self-hosted services — learning by running your own infrastructure.

## Key ideas & topics

- **Move your home network into a real data center (DMVPN).** (2018-07-16) Chuck describes relocating his personal home network into a Dallas colocation/data center and stitching the two ends together over a DMVPN (Dynamic Multipoint VPN) tunnel — treating his own lab as production-grade personal infrastructure and using it as hands-on practice for enterprise WAN tech. See [[../../sources/2018-07-16-yt-G5HucqXioBY]]. Cross-links [[../networking/networking]] and [[../cloud-devops/cloud-devops]].
- **Self-host Pi-hole on Docker for network-wide ad and content blocking.** (2020-05-02) Chuck runs Pi-hole in a Docker container as a self-hosted DNS sinkhole that blocks ads and trackers for every device on the LAN, layering it with an upstream resolver (OpenDNS) for content filtering and wiring in IFTTT so the blocking can be toggled/automated. Positioned as an easy, high-payoff first self-hosted service. See [[../../sources/2020-05-02-yt-dH3DdLy574M]]. Cross-links [[../cloud-devops/cloud-devops]] (Docker) and [[../linux-terminal/linux-terminal]].
- **The Raspberry Pi as a cheap, fun homelab building block.** (2020-02-28) Chuck frames the Raspberry Pi as an inexpensive, low-stakes machine for learning — setting up a Pi as a full Linux "learning desktop" so beginners can practice Linux and self-hosting without risking their main computer. See [[../../sources/2020-02-28-yt-vbaJcRxASo0]]. Cross-links [[../linux-terminal/linux-terminal]].
- **Maker/automation projects with the Pi (Halloween automation).** (2019-10-27) Chuck builds a Raspberry Pi Halloween automation rig, tying physical props to software via IFTTT, Alexa voice triggers, and a REST API — a playful demonstration that a homelab is also a place to build fun, tangible automation projects, not just serious infrastructure. See [[../../sources/2019-10-27-yt-B_krqlk_cXo]]. Cross-links [[../cloud-devops/cloud-devops]] (APIs/automation).
- **Host a website as a Tor hidden service (.onion).** (2023-11-01) Chuck stands up a self-hosted website served over the Tor network as a `.onion` hidden service, showing how to run a site with no public IP or DNS — anonymous, censorship-resistant hosting entirely from the homelab. See [[../../sources/2023-11-01-yt-CurcakgurRE]]. Cross-links [[../networking/networking]].
- **Canonical personal infra: the server room, dual racks, and "Terry".** (2024-06-26) Chuck tours his personal server room / cable-management build — the reference picture of his on-prem infrastructure: dual racks, an 80 Gbps MikroTik QSFP+ bonded link, a 45Drives NAS, and a named dual-GPU AI server, "Terry." This is his canonical home lab; the "Terry" AI box recurs as the machine behind many 2024–25 self-hosted-AI videos. See [[../../sources/2024-06-26-yt-spoZ2zKnK88]]. Cross-links [[../networking/networking]] (MikroTik/QSFP+) and [[../ai-tools/ai-tools]] (Terry).
- **Self-host a business phone system (3CX on Proxmox).** (2024-12-09) Chuck runs a full self-hosted 3CX VoIP phone system as a VM on Proxmox — a modern, homelab callback to his Cisco Voice roots, turning enterprise telephony into a self-hostable service. See [[../../sources/2024-12-09-yt-fdM1V98iIQI]]. Cross-links [[../networking/networking]] (VoIP) and [[../cloud-devops/cloud-devops]] (Proxmox).
- **Replace Alexa with a local, private voice assistant.** (2024-11-04) Chuck builds a fully local voice assistant on Home Assistant backed by a local AI model, replacing cloud-tied Alexa so voice commands never leave the house — privacy-first home automation run entirely on homelab hardware. See [[../../sources/2024-11-04-yt-XvbVePuP7NY]]. Cross-links [[../ai-tools/ai-tools]] (local AI) and [[../cloud-devops/cloud-devops]].
- **Homelab as a resume: infrastructure monitoring.** (2024-05-16) Chuck sets up infrastructure monitoring over his homelab, framing the monitored stack itself as portfolio/resume material — proof-of-skill you can point an employer to, not just a hobby dashboard. See [[../../sources/2024-05-16-yt--2yzXSIuC8o]]. Cross-links [[../networking/networking]] and [[../it-career/it-career]].

## Source pages

- (2018-07-16) [[../../sources/2018-07-16-yt-G5HucqXioBY]] — Moving my HOME NETWORK to a DATA CENTER w/ DMVPN
- (2019-10-27) [[../../sources/2019-10-27-yt-B_krqlk_cXo]] — Raspberry Pi Halloween Automation (IFTTT/Alexa/REST)
- (2020-02-28) [[../../sources/2020-02-28-yt-vbaJcRxASo0]] — How to Setup a Raspberry Pi LEARNING Desktop
- (2020-05-02) [[../../sources/2020-05-02-yt-dH3DdLy574M]] — BLOCK EVERYTHING w/ PiHole on Docker
- (2023-11-01) [[../../sources/2023-11-01-yt-CurcakgurRE]] — Host a website as a Tor .onion hidden service
- (2024-05-16) [[../../sources/2024-05-16-yt--2yzXSIuC8o]] — Infrastructure monitoring (homelab-as-resume)
- (2024-06-26) [[../../sources/2024-06-26-yt-spoZ2zKnK88]] — Personal server room / cable management (dual racks, MikroTik 80 Gbps, 45Drives NAS, "Terry")
- (2024-11-04) [[../../sources/2024-11-04-yt-XvbVePuP7NY]] — Local voice assistant (Home Assistant + local AI) replacing Alexa
- (2024-12-09) [[../../sources/2024-12-09-yt-fdM1V98iIQI]] — Self-hosted 3CX phone system on Proxmox (VoIP)
