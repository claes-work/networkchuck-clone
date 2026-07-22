---
type: youtube-video
source_date: 2020-02-16
url: https://www.youtube.com/watch?v=BezoNUflqXo
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [networking, homelab-selfhosting]
tags: [unifi, ubiquiti, dream-machine, wifi, router, homelab, review]
---

# UniFi Dream Machine - the BEST WiFi router (Review and Advanced Setup)

## Summary

Chuck reviews the Ubiquiti UniFi Dream Machine (UDM), an all-in-one home
router/gateway/access point/controller, and walks through both the quick initial
setup and the advanced settings he tweaks. His core thesis: the UDM does nothing
functionally new for Ubiquiti, but it collapses what previously required four
separate devices — a USG (Unified Security Gateway = router + firewall), a wireless
access point, and a Cloud Key (controller) — into one "beautiful," Apple-esque
capsule. He frames the whole review through his own homelab obsession: he owns all
the separate Ubiquiti gear, travels with his own router/Wi-Fi, and runs a VPN back to
his Dallas data center from Airbnbs. He took the UDM on a three-week road trip to the
US west coast as a compact replacement for his usual "suitcase" of networking gear.

The setup half: phone-based (UniFi Network app) initial config took ~5 minutes, with
auto-discovery, auto-optimize, and an internet speed test. The advanced half (from the
desktop UI at 192.168.1.1 / UI.com login): enabling Threat Management (IDS vs IPS),
Wi-Fi AI, scheduled speed tests/QoS, guest hotspot portals with captive-portal
branding, guest VLANs, DHCP guarding, GeoIP filtering, DNS/content filters, DPI-based
traffic restriction, network/endpoint scanners, honeypots, VPN, alerts, and controller
backups.

Verdict: strong recommend for home enthusiasts and small business at $300; not for
medium/large business. Standout stat: 850 Mbps throughput with threat management (IPS/
IDS) enabled — far above the USG Pro's ~250 Mbps of inspected traffic. Cons: single
WAN/LAN port (no internet failover / dual-ISP), limited advanced options (no CLI, so no
custom OpenVPN-to-a-provider config), and it is Wave 2 Wi-Fi, not Wi-Fi 6. This is a
sponsored review with a Ubiquiti-provided three-unit giveaway.

## Key claims (dated — review + setup)

Review verdict (2020-02-16):
- The UDM is "one of the best Wi-Fi routers" Chuck has ever had; best value in its class. (paraphrase)
- It does nothing functionally new for Ubiquiti — it combines a USG (router + firewall), a wireless access point, and a Cloud Key controller into one device. (paraphrase)
- Price is $300, called a steal for everything it does; the most compelling part is the multifunction all-in-one nature (no need to buy USG + switch + APs + Cloud Key separately). (paraphrase)
- Biggest performance win: 850 Mbps throughput with threat management (IPS/IDS) enabled, versus only ~250 Mbps of inspected traffic on the USG Pro (a supposedly "pro" product). (paraphrase) [note: intro states 815 Mbps; the pros recap states 850 Mbps]
- It is Wi-Fi Wave 2, not Wi-Fi 6, so it is less future-proof — but few devices use Wi-Fi 6 yet, so most users won't notice. (paraphrase)
- Includes a managed 4-port switch (supports VLANs) and a built-in controller (no separate Cloud Key/server needed); additional access points can be added for more coverage. (paraphrase)
- Cons: only one LAN/WAN port, so no internet failover / no second ISP (a downside for business). (paraphrase)
- Cons: limited advanced options — no command-line access like the USG Pro, so you cannot create a custom OpenVPN connection routing all traffic through a VPN provider (NordVPN, PIA). Chuck tried for a couple hours while traveling and it wasn't possible. (paraphrase)
- Target audience: home users who like tinkering with their network, and small businesses (its firewall + IPS/IDS throughput rivals expensive enterprise gear). NOT for medium/large business needing failover, multi-site, or UniFi Protect surveillance — those should get a more professional product. (paraphrase)
- Standalone Wi-Fi coverage was "pretty stinkin well" across his two-story house from a corner office; good, fast processor. (paraphrase)
- Notes the UniFi Dream Machine Pro was recently released and he plans to review it soon. (paraphrase)

Setup / features (2020-02-16):
- Initial setup via the UniFi Network phone app takes ~5 minutes (auto-discovery of the device, 3D rotation view, auto-optimize, internet speed test). (paraphrase)
- Three things needed: the Dream Machine + power, an internet uplink (Ethernet from cable modem into the WAN/LAN port), and a phone or computer. (paraphrase)
- The controller is "software-defined networking" — a smart controller that keeps the Wi-Fi optimized automatically and reports a "99% Wi-Fi experience." (paraphrase)
- Advises against splitting 2.4 GHz and 5 GHz into separate SSIDs; let it auto-select. (paraphrase)
- Threat Management (in beta): IDS = intrusion detection (alerts only); IPS = intrusion prevention (proactively blocks attacks). Chuck enables IPS for maximum protection. (paraphrase)
- Wi-Fi AI (beta): scans the Wi-Fi environment and picks best channels/power for the APs, scheduled (e.g. 3 a.m.) since it's CPU-intensive. (paraphrase)
- Recommends changing the default LAN subnet from 192.168.x to something uncommon (e.g. 10.77.x) for security. (paraphrase)
- Guest hotspot: captive portal with terms-of-service, custom welcome text/logo/landing page, session expiry, and per-client access restrictions; guest Wi-Fi can be put on a separate VLAN for isolation. (paraphrase)
- DHCP guarding protects against rogue-DHCP / man-in-the-middle attacks (e.g. from Kali Linux); trust only your UniFi DHCP servers. (paraphrase)
- GeoIP filtering (beta) blocks IPs from countries known for attackers. (paraphrase)
- DNS/content filters (alpha): family filter blocks VPNs, explicit/pornographic and malicious domains, and forces search engines + YouTube into Safe Mode — he hit this while traveling (couldn't watch live video or comment). (paraphrase)
- Deep packet inspection (DPI) lets you see and restrict traffic by category (e.g. block online games on a Wi-Fi network) and assign restrictions per SSID. (paraphrase)
- Network/endpoint scanners (alpha) scan endpoints for vulnerabilities/open ports; you can also run an internal honeypot. (paraphrase)
- Can create your own VPN server on the UDM to connect back home securely, or site-to-site VPN between UniFi devices. (paraphrase)
- Configurable alerts (AP/client events, rogue AP detection) to phone/email; regular controller config backups are strongly advised (cloud backup "coming soon"). (paraphrase)

Personal/context (2020-02-16):
- Chuck travels with his own router and Wi-Fi to control his environment, including a VPN from an Airbnb in Paris back to his Dallas, Texas data center. (paraphrase, self-reported)
- Career note: he used to work at Starbucks as the guy people asked to fix the printer and Wi-Fi; he turned IT/networking into a career by studying (via CBT Nuggets, where he now works). (paraphrase, self-reported)
- Sponsored: Ubiquiti provided the units for a three-tier giveaway (up to a ~$1,250 prize package). (paraphrase)

## Notable verbatim quotes

> "the dream machine this might be one of the best Wi-Fi routers I've ever had"

> "the good folks at ubiquity somehow figured out how to take a in access point at USG the security gate which is which is our router and our firewall and a cloud key and they shoved it all into one beautiful package it is kind of beautiful if I'm being honest I do like the look and feel of it it's very dare I say Apple esque"

> "I'm a bit of a geek when I travel I like to take my router with me I like to take my Wi-Fi with me I like to control that environment and just geek out wherever I go I have a from my Airbnb in Paris I have a VPN connection back to my data center in Dallas Texas that's nuts"

> "the killer thing about this little guy which is mind-boggling is this little guy can do 815 megabits per second of throughput with this setting enabled ... because on the USG Pro the product I have ... can only do 250 megabits per second of inspected traffic"

> "the biggest thing about it is that it's only 300 bucks that's crazy for all that we went through all you can do with this 300 bucks is a steal"

> "the dream machine does have a few nightmares one thing is it only has one land port which means you can't have Internet failover you can't support more than one internet provider"

> "if you're a home user and you love messing with your networks and your Wi-Fi this thing is for you it gives you everything you need in one beautiful capsule ... this thing is beautiful simple elegant I love it"

> "if you're like the resident IT guy for your family you should go deeper and make a career out of this stuff that's what I did I used to work at Starbucks and I was only always a guy that they would talk to to fix the printer and the Wi-Fi ... I decided to make a career out of it"

> "what are you drinking today let me know below what your favorite type of coffee is and your favorite brewing method mine is French press it's my daily grind"

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
