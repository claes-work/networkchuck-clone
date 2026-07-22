---
type: youtube-video
source_date: 2021-09-24
url: https://www.youtube.com/watch?v=2rVzRoF7vQw
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, networking]
tags: [rogue-device, network-attack, hak5, awareness, defense]
---

# this device is HACKING my network!! (I'm letting it happen)

## Summary

Chuck demonstrates the **Circle** — a consumer parental-control and internet-filtering
device — and reveals that it works by running a real, well-known network attack on his
own LAN: **ARP poisoning (ARP spoofing)**. Rather than replacing the router (the usual
way to filter a home network's traffic), the Circle simply plugs into the existing
router and inserts itself between the kids' devices and the gateway by lying about which
MAC address owns the router's IP. Once devices believe the Circle *is* the router, all
their traffic flows through it, letting it filter sites, track time-per-activity across
multiple devices, and enforce rewards/limits.

The video is framed as a security-awareness lesson: a common black-hat man-in-the-middle
technique is here repurposed for a "good" reason, and Chuck stresses that even his fairly
secure home network (Ubiquiti UniFi Dream Machine) does **not** detect or stop it. He
then teaches the defensive countermeasure — pinning a **static ARP entry** for the
router — which both bypasses the Circle and, more generally, protects any host against
ARP-poisoning man-in-the-middle attacks. He uses `arp -a` to observe the poisoned table
and Wireshark (filtered by ARP) to watch the attack happen live, noting Wireshark even
flags a duplicate use of the router's IP.

Motivation: Chuck bought the device himself (not sponsored by Circle) to better protect
his five daughters online. Sponsor read for a web host is interleaved (unrelated to the
security content).

## Key claims (dated — concept + defense)

All dated 2021-09-24 (paraphrase unless quoted):

- The Circle is a parental-control / internet-filtering device that works by **ARP
  poisoning** the local network, so no router replacement is needed — it just plugs into
  the existing router via Ethernet.
- By default all home-network traffic exits through the router (the **default gateway**);
  that is why filtering normally requires a router with built-in features.
- **ARP (Address Resolution Protocol)** is how devices map an IP address to a MAC
  address — Chuck likens it to "Google Maps of your home network." A device broadcasts
  "who has this IP?" and the real owner replies with its MAC.
- In an **ARP-poisoning attack**, the attacking device (the Circle) answers those
  requests *instead of* the router, claiming the router's IP belongs to the attacker's
  MAC. Victim devices then send all internet-bound traffic to the attacker, who is now a
  **man-in-the-middle**.
- The attack is **continuous**: the Circle keeps re-asserting itself so the real router
  never gets a chance to correct the record. Wireshark detects a **duplicate use** of
  the router's IP.
- Concept demonstration: Chuck reads the ARP table with `arp -a`; before the attack the
  router's IP maps to the real router's MAC (ending `...FF-59`), and after assigning the
  target device to the Circle, the same IP maps to the Circle's MAC (`...C3-D0`).
- Circle claims all captured traffic data stays **locally** on the device and is not sent
  to the internet.
- Feature Chuck values: it can aggregate one child's **time-per-activity across multiple
  devices** (phone + gaming PC + others), enforce filters, block/log visited sites, set
  time limits, and grant reward time (e.g., Disney+).
- The device can push a **local VPN profile** to a child's phone so filtering still
  applies off the home network (on LTE/5G or other Wi-Fi) — the filter runs locally, not
  by tunneling back home.
- Even a security-conscious network (Chuck's Ubiquiti UniFi **Dream Machine**) does not
  catch this attack — highlighting how stealthy ARP poisoning is.
- **Defense (the takeaway):** add a **static ARP entry** for the router so the host
  ignores poisoned replies. On Windows the command is
  `netsh interface ipv4 add neighbors "<interface>" <router-IP> <router-MAC>`, using the
  correct interface name (e.g., "Ethernet" / "Local Area Connection") and the **real**
  router MAC with dashes (not colons). The entry then shows `type: static` in `arp -a`,
  and dynamic entries learned via ARP no longer override it.
- Circle is transparent about the technique on its own website, acknowledging ARP
  spoofing/poisoning is used by black hats but stating it uses it "for a good reason."

## Notable verbatim quotes

> "This device right here is designed to hack my network like on purpose. And I bought it to do that."

> "It's an attack called an ARP poisoning attack, which is a very common hacking attack."

> "AARP stands for the address resolution protocol. And that's what pretty much everything in your network uses to find out where things are. And it's kind of like the Google maps of your home network."

> "The IP address is kind of like the router's name... The MAC address is where he lives."

> "All my daughter's devices think that the router is the circle device... My kids just got hacked. And it's a good thing."

> "So he's the boss now."

> "So again, we'll fix this by adding a static AARP entry."

> "And when I received that poison from the circle device telling me he's the boss, I'm like, no, no, no, no. I've got his address memorized. I know where he lives. You can't lie to me. I know the truth."

> "My home network is pretty secure... I have ubiquity... I've got a dream machine. It doesn't catch this, which is kind of crazy."

> "It's true that ARP spoofing can be used by black hats to compromise network security. The circle device uses ARP spoofing for a good reason."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: clean teaching demo of ARP poisoning / MITM concept plus a concrete static-ARP defense (netsh command) and Wireshark detection — strong topic material for cybersecurity/networking pages. -->
