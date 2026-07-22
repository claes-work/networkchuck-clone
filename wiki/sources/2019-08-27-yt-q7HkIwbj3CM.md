---
type: youtube-video
source_date: 2019-08-27
url: https://www.youtube.com/watch?v=q7HkIwbj3CM
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, linux-terminal]
tags: [kali-linux, raspberry-pi, wifi, ethical-hacking, pentest, demo]
---

# Hacking (redacted) PUBLIC WiFi with a Raspberry Pi and Kali Linux

> Educational security content. Chuck demonstrates real WiFi attacks against
> targets who consented (his wife and daughters), and frames the entire video
> around defense, education, and white-hat ethics. All attacks are performed with
> permission on his own family; he repeatedly warns against doing any of it without
> consent.

## Summary

A hands-on ethical-hacking demonstration in which Chuck uses a credit-card-sized
Raspberry Pi running Kali Linux to attack public-WiFi users at coffee shops. He
frames it up front: he is not hacking the WiFi (which is free) — he is hacking the
*people* on it, stealing their internet traffic. The video has two stated goals: (1)
get viewers excited to start hacking (with permission) so they learn about security,
and (2) scare viewers into never connecting to public WiFi without a VPN. The sponsor
is NordVPN, which he later demonstrates defeating his own attacks.

He runs three attacks against consenting family members:

1. **Evil twin** (at a chain coffee shop and a local one) — the Pi is turned into a
   rogue wireless router broadcasting a WiFi name resembling the real one, luring the
   target to connect; the Pi first joins the real network for upstream internet so the
   victim notices nothing, then DNS-spoofs the victim to a fake website.
2. **Deauthorization attack** (added at the less-secure local shop) — the fake AP
   copies the real SSID exactly (and its channel); deauth frames forcibly disconnect
   the already-connected target, who then auto-roams to the attacker's stronger signal.
3. **ARP spoofing / man-in-the-middle** (on the same network, no rogue AP) — the Pi
   poisons ARP so the victim thinks the Pi is the router and the router thinks the Pi
   is the victim, placing the attacker in the middle of all traffic, with DNS spoofing
   layered on top.

He notes the chain shops (Starbucks, McDonald's) were "pretty secure" — he couldn't
ping/reach other hosts, so only the evil twin worked there — while a single-owner
coffee shop with a basic home-style network allowed all three attacks. Each attack
ends with the target enabling NordVPN, after which the attacker can no longer see or
spoof the encrypted traffic. He closes by pushing viewers toward white-hat hacking,
security certifications, and his Discord community.

## Key claims (dated — technique + tools + ethical framing)

- **[2019-08-27] The real target of "public WiFi hacking" is the people, not the
  network.** Since the WiFi is free, the value is in stealing other users' internet
  traffic and data, not breaking into the access point. (paraphrase)
- **[2019-08-27] Ethics/legality framing is explicit and repeated.** Chuck states a
  disclaimer that you must never do this to anyone without their permission; his
  targets (wife Abby, daughters incl. Chloe) consented. He urges viewers to practice
  only on their own home network / family / friends with permission, and frames the
  whole exercise as learning to become a *white-hat* hacker — "learn how to hack
  things so you can learn how to protect things." (paraphrase)
- **[2019-08-27] Hardware.** A single Raspberry Pi (his has a small LCD screen, driven
  by a wireless keyboard) runs Kali Linux and serves as the full "hacking station." A
  USB wireless adapter that **supports monitor mode** is required for the wireless
  attacks. (paraphrase)
- **[2019-08-27] Evil twin technique.** First connect the Pi to the real network for
  upstream internet (so victims still reach the web and suspect nothing); run a web
  server on the Pi to host the fake destination site; use **airodump-ng** (Aircrack-ng
  suite) in monitor mode to survey nearby networks and clients; use **hostapd** to
  stand up the rogue AP with a chosen SSID; hand out addresses with **DHCP**; and use
  **DNSChef** for DNS spoofing so victims requesting e.g. starbucks.com land on the
  Pi's web server. He deliberately named the SSID "Starbucks" (not the real "Google
  Starbucks") to lure connections. (paraphrase; tools per transcript)
- **[2019-08-27] Deauthorization attack.** At the less-secure local shop he copies the
  real SSID and WiFi channel exactly, uses **airbase-ng** ("a quick and dirty way to
  set up a wireless network") for the fake AP, grabs the target iPad's **MAC address**
  from airodump-ng client output, then sends deauth frames to both the router and the
  target to force a disconnect; because his AP has a stronger signal, the device
  auto-roams to him without the user noticing. He confirms success by the victim's IP
  changing from a 172.x address to a 192.x address on his network. (paraphrase)
- **[2019-08-27] ARP spoofing / man-in-the-middle.** No rogue AP — the attacker joins
  the same legitimate WiFi, scans it with **nmap** to find targets/device types, then
  uses **Ettercap** to send forged ARP replies: telling the router "I am the victim"
  and the victim "I am the router," inserting himself in the middle. Ettercap also
  performs DNS spoofing simultaneously. He explains ARP (Address Resolution Protocol)
  maps IP addresses to MAC addresses and that abusing that mapping is the "secret
  sauce." (paraphrase)
- **[2019-08-27] Defense: a VPN defeats all of these attacks.** With NordVPN enabled,
  the victim's traffic is encrypted/hidden: the attacker's DNS window goes from a
  "matrix"-like stream of visited sites to a "ghost town," and DNS spoofing no longer
  works — the victim reaches the real sites. He recommends always using a VPN on any
  public WiFi and highlights auto-connect (incl. a "Hey Siri, protect me" shortcut).
  (paraphrase; NordVPN is the paid sponsor)
- **[2019-08-27] Enterprise networks are harder targets than home-style ones.**
  Starbucks and McDonald's networks isolated clients (he couldn't ping other hosts),
  limiting him to the evil twin; a single-owner shop's basic home-style network allowed
  deauth, ARP poisoning, and denial-of-service too. He adds that vulnerabilities are
  found daily, so no network is permanently safe. (paraphrase)
- **[2019-08-27] Career/learning pitch.** Security is a big, well-paid field; he points
  viewers to networking/security fundamentals, Security+, CCNA, and CEH ("C"), his
  courses, and his Discord community, and promises a follow-up detailed walkthrough
  (blog post or video). (paraphrase)

## Notable verbatim quotes

> "Now, when I say hack, what do I mean? Because Starbucks Wi-Fi, as we all know, is
> free. Well, you see, I'm not really hacking the Wi-Fi. I'm hacking you. I'm hacking
> the people. I'm going to steal your data, steal your internet traffic. I will own
> you."

> "Now, disclaimer, do not do this to someone without their permission."

> "I want you to be absolutely terrified of going to any public place and connecting to
> Wi-Fi and not having a VPN."

> "I'm using a tool called DNS Chef to do what's called DNS spoofing. I'm hacking their
> DNS so that when they go to maybe netflix.com or starbucks.com, they won't go to the
> real website."

> "And suddenly I'm in the middle of their conversation. I'm easedropping. This is
> often referred to as a man-in-the-middle attack because I am the man in the middle."

> "Just don't do it illegally."

> "Hackers are real. They're out there. And you could become one right now. And what
> I've shown you is kind of a method to become a white hat hacker, which is what you
> should be. Learn how to hack things so you can learn how to protect things, so you can
> help other companies protect themselves."

> "Man, hacking is fun. Exhausting. You need coffee for it, but really not much else."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: Kali+Pi ethical-hacking demo format + ethics framing -->
