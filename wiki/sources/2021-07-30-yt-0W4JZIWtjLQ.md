---
type: youtube-video
source_date: 2021-07-30
url: https://www.youtube.com/watch?v=0W4JZIWtjLQ
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [networking, cybersecurity, certifications-career]
tags: [free-ccna, port-security, switchport, mac, ep-14]
---

# you NEED to learn Port Security……RIGHT NOW!! // FREE CCNA // EP 14

## Summary

Episode 14 of Chuck Keith's FREE CCNA course (a series sponsored by Boson Software),
teaching how to secure switch ports on a Cisco switch. Chuck frames the lesson around a
physical attack device — the Hak5 Shark Jack — which plugs into an exposed Ethernet
jack, pulls an IP via DHCP, and runs an Nmap scan of the network. He uses that threat
model to motivate three layers of defense: (1) shut down unused ports, (2) put
leave-open ports into a "black hole" VLAN with no DHCP / gateway, and (3) configure
**switchport port-security** on used ports so only approved MAC addresses can connect.

The bulk of the episode walks through Cisco IOS configuration (in Boson NetSim and on
Chuck's own physical switch), then shows equivalent controls in UniFi. He closes by
demonstrating a live violation with the Shark Jack, showing the `err-disabled` state,
and how to recover the port. He notes he "jumped the shark" ahead of the exam
objectives to cover port security because he wanted to play with the device, and will
resume the objectives in order next episode. He also briefly names more advanced,
enterprise-grade port security approaches (802.1X, certificates, Cisco ISE) as "better
ways" beyond CCNA baseline. Sponsors: Privacy (virtual debit cards) and Boson (summer
sale, code "summer21", ~25% off).

## Key claims (dated — port-security concepts/config, 2021-07-30)

- A Hak5 Shark Jack attack works only if three conditions hold: the port is active/up
  (not shut down), a DHCP server is reachable so it can get an IP, and it can reach
  (scan) other hosts on the network. (paraphrase)
- The Shark Jack runs a small Linux server, gets an IP via DHCP, and that IP alone
  reveals subnet mask (network size), default gateway/router IP, and likely the DNS
  server. (paraphrase)
- Defense layer 1 — shut down unused ports. On Cisco, `show ip interface brief |
  include down` lists down interfaces; entering the interface and issuing `shut` sets
  it to **administratively down**, which is stronger than plain "down" because it
  cannot come up until an admin allows it (`no shut`). (paraphrase)
- Defense layer 2 — for ports that must stay open, put them in a "black hole" VLAN: a
  VLAN with no DHCP server and no default gateway, isolated from other ports.
  (paraphrase)
- Creating a black hole VLAN on Cisco: `vlan 666` to create it, then per interface
  `switchport access vlan 666`; `show vlan brief` verifies membership. Ports in that
  VLAN cannot talk to other ports on the switch. (paraphrase)
- On a fresh Cisco switch there is one VLAN (VLAN 1) and all ports belong to it; a VLAN
  is described as "a way to create a switch inside of a switch." (paraphrase)
- If two switches are joined by a trunk, ensure the black hole VLAN does not traverse
  the trunk; combine black-holing with shutdown for "double protection." (paraphrase)
- Defense layer 3 — port security ties a switch port to allowed MAC address(es).
  When a device plugs in, the switch learns its MAC into the MAC address table; port
  security tells the port to allow only specified MAC(s) and reject others.
  (paraphrase)
- Cisco port-security config sequence on an interface: `switchport mode access` (hard-
  code as access port, not trunk) → `switchport port-security` (enable) → `switchport
  port-security maximum <n>` (default 1) → `switchport port-security mac-address
  <sticky | address | forbidden>` → `switchport port-security violation <shutdown |
  restrict | protect>`. (paraphrase)
- The `maximum` default is 1; a value of 2 is common when an IP phone and a computer
  daisy-chain on one port (two MACs on the port). (paraphrase)
- `mac-address` options: hardcode a specific MAC; `forbidden` to explicitly deny a
  learned MAC; or `sticky`, which auto-learns the first MAC that plugs in and locks the
  port to it — Chuck's preferred/default method because he is "too lazy" to look up and
  hardcode MACs. (paraphrase)
- Violation modes: **shutdown** (default) — shuts the port down and sends an SNMP
  message; **restrict** — keeps port up, drops violating traffic, sends SNMP message;
  **protect** — same as restrict but no SNMP message. Chuck prefers shutdown.
  (paraphrase)
- Verification commands: `show port-security` (config + violation count),
  `show port-security address` (learned secure/sticky MACs),
  `show port-security interface <int>`, `show interfaces <int> status`. (paraphrase)
- A port security violation puts the port into an **err-disabled** state — different
  from an admin shutdown (the switch, not the admin, disabled it). Recovery: enter the
  interface, `shut` then `no shut` to bring it back up. (paraphrase)
- UniFi equivalents: disable a port profile to shut a port; create a VLAN network with
  no DHCP + device isolation for a black hole; use a MAC ID filter allow-list for
  per-port MAC restriction — but UniFi has no "sticky" option (per Chuck's knowledge).
  (paraphrase)
- Beyond CCNA baseline, enterprises use more advanced port security: 802.1X (login
  with credentials to gain port access), certificate-based device auth, and Cisco ISE
  (profiles devices intelligently to judge good/bad). (paraphrase)
- Educational/ethics disclaimer: the attack demonstration is for educational purposes;
  do not hack anyone without permission unless a legitimate authorized pentester.
  (paraphrase)

## Notable verbatim quotes

> "Every time I see one, I see a hacking opportunity. Each jack is a port to a network
> that I can take advantage of."

> "So knowing that this is what the Shark Jack needs to perform an attack, what do you
> say we mess that up?"

> "It's administratively down. ... Not just down. I don't have anything plugged into me
> down like I can't come up at all unless the admin says I can."

> "A network that goes absolutely nowhere. You're just stuck in a hole. This is a
> network that has nothing. There's no DHCP. There's no default gateway."

> "We're gonna tell that switch port that only a device with the MAC address of this one
> right here ending in E3D9. Only that MAC address can actually be alive and up on that
> switch port. If any other device with a different MAC address comes onto that
> switchport, shut that sucker down."

> "He's a bit like our bouncer. He's going to bounce him out. This guy is the only guy
> on the list."

> "What it will do is you plug in your device, your switch will learn that MAC address
> and then stick it like a post-it and say, 'Okay, that's the only MAC address allowed.'"

> "I'll just say, you know what, whatever gets plugged in first is the only one allowed.
> So, sticky. Boom."

> "It puts it in an error disabled state. Error disabled. Different from an admin
> shutdown. Similar result, but different. We didn't shut this down as an admin. The
> switch shut it down because of a port security violation."

> "The best thing to do for ports that are just not being used is to put them in a black
> hole and shut them down."

> "I know I kind of jumped the shark, jumped the shark a bit by going forward in the
> exam objectives and going to port security. I did that because I just couldn't help
> it. I wanted to jump to it because I thought it was cool."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: FREE CCNA EP 14 — port security -->
