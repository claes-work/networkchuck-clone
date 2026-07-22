---
type: hub
domain: cybersecurity
created: 2026-07-14
updated: 2026-07-22
---

# Cybersecurity — hub

Ethical hacking, pentesting, hands-on hacking demos, and security tooling — the "you just hacked X" hook that draws newcomers into security. Chuck's signature security format is a live, physical attack demo (Raspberry Pi + Kali Linux) wrapped in an explicit white-hat ethics frame: learn to hack so you can learn to defend.

## Key ideas & topics

### The hands-on hacking-demo format (Raspberry Pi + Kali Linux)
Chuck's recurring security-teaching pattern is to run a real attack on cheap, tangible hardware — a credit-card-sized Raspberry Pi running Kali Linux (a Linux distro packed with networking-attack tools), remotely accessed over SSH — so the attack feels concrete rather than abstract. He personifies the rig (the Pi is "Malcolm," "a bad dude") and ties each demo directly to certification study, framing "what one setting would have stopped this?" as a CCNA/CCNP Security study question. Wireless attacks additionally require a USB wireless adapter that supports monitor mode. See [[../../sources/2018-04-17-yt-lTlTjeCjXYM]] and [[../../sources/2019-08-27-yt-q7HkIwbj3CM]]. Related: [[../linux-terminal/linux-terminal]].

### Hack-a-Cisco-switch demo — VLAN hopping via DTP (2018-04-17)
Chuck plugs the Pi into an access port on VLAN 1, then attacks his own network remotely. Using the **Yersinia** tool he launches a **DTP (Dynamic Trunking Protocol)** attack — "switch spoofing" — that tricks the switch into converting the harmless access port into a **trunk port**, giving access to all VLANs. From there he can read broadcast traffic on every VLAN, discover IPs/VLANs, and assign himself any VLAN. He verifies port state before and after with `show interface fa1/0/14 status` / `show interface trunk`, notes the whole attack can also be run in GNS3 (where he first did it), and poses the defense as a study question: a single default practice — disabling DTP / hardcoding ports as access (`switchport mode access` / `nonegotiate`) — prevents it. [[../../sources/2018-04-17-yt-lTlTjeCjXYM]]

### Hacking public WiFi — with the ETHICS/education/legality frame (2019-08-27)
Chuck's key reframe: on free public WiFi you are not hacking the network, you are hacking the **people** on it — stealing their traffic. He runs three attacks against **consenting family members** (wife Abby, daughters):
- **Evil twin** — the Pi joins the real network for upstream internet (so victims notice nothing), stands up a rogue AP with a lookalike SSID via **hostapd**, surveys clients with **airodump-ng** (Aircrack-ng), serves a fake site, and DNS-spoofs victims with **DNSChef**.
- **Deauthorization attack** — copies the real SSID + channel with **airbase-ng**, grabs the target's MAC from airodump-ng, sends deauth frames so the device auto-roams to his stronger signal.
- **ARP spoofing / man-in-the-middle** — joins the same WiFi, scans with **nmap**, then uses **Ettercap** to forge ARP replies (tell the router "I am the victim," tell the victim "I am the router") plus simultaneous DNS spoofing.

The **ethical framing is explicit and repeated**, and should be treated as core to his security voice: "do not do this to someone without their permission," practice only on your own network/family/friends who consent, and the whole point is to become a **white-hat**: *"Learn how to hack things so you can learn how to protect things."* He also notes enterprise networks (Starbucks, McDonald's) isolate clients and are harder targets than home-style single-owner networks, and closes on defense — a **VPN encrypts the traffic and defeats all three attacks** (NordVPN is the paid sponsor). [[../../sources/2019-08-27-yt-q7HkIwbj3CM]]

### Security certifications — CCNA Cyber Ops vs CCNA Security (2019-03-12)
Comparing the two 2019-era Cisco security tracks: **CCNA Security** needed a prerequisite (CCENT / CCNA R&S / any CCIE), was **one exam** (210-260 IINS), targeted an entry-level network **security admin**, and fed into CCNP Security → CCIE Security. **CCNA Cyber Ops** had **no prerequisite**, was **two exams** (210-250 SECFND + 210-255 SECOPS), and targeted a **SOC analyst** role (correlating data, forensics, incident response, compliance frameworks). Chuck's verdict: get **CCNA Security first** — Cyber Ops is a dead-end track (no CCNP Cyber Ops exists) and Security is more marketable to recruiters; get a cert for (1) knowledge and (2) marketability. He also restates his standing rule that everyone should get CCNA Routing & Switching before any specialty track.

> ⚠️ Version note: **Both certs were later retired** in Cisco's February 2020 overhaul. CCNA Security, CCNA Cyber Ops, CCENT, and the separate CCNA tracks were consolidated into a single CCNA plus the new CyberOps Associate/Professional certs. This reflects Chuck's advice **as of 2019-03-12** and is not current cert guidance.

[[../../sources/2019-03-12-yt-PusUAu9gGiI]]. See also the certifications/career workstream and [[../homelab-selfhosting/homelab-selfhosting]] for the home-lab practice environment behind this study.

## Source pages

- 2018-04-17 — [[../../sources/2018-04-17-yt-lTlTjeCjXYM]] — Hack a Cisco Switch with a Raspberry Pi (VLAN hopping / DTP / Yersinia)
- 2019-03-12 — [[../../sources/2019-03-12-yt-PusUAu9gGiI]] — CCNA Cyber Ops vs CCNA Security (both since retired)
- 2019-08-27 — [[../../sources/2019-08-27-yt-q7HkIwbj3CM]] — Hacking Public WiFi with a Raspberry Pi and Kali Linux (evil twin / deauth / ARP MITM; ethics + VPN defense)
