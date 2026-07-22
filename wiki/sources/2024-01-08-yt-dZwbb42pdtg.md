---
type: youtube-video
source_date: 2024-01-08
url: https://www.youtube.com/watch?v=dZwbb42pdtg
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, networking]
tags: [wifi-hacking, wpa, aircrack, evil-twin, ethical-hacking, defense]
---

# 3 Levels of WiFi Hacking

## Summary

Chuck demonstrates how three tiers of attacker — a "noob," a "hipster," and a
"pro" — attack a WiFi network and the individuals on it, simulated (with
permission) at Bear Cave Coffee in downtown Mesquite, Texas. He opens with an
explicit legal/ethical disclaimer: these are real attacks and must never be run
on anyone without explicit permission — do it only in your own house, on
consenting friends/family. The video walks through four attack families and
their defenses:

1. **Man-in-the-middle (ARP spoofing)** — the noob connects to the open coffee
   shop WiFi and uses Kali Linux + Bettercap to poison ARP, inserting himself
   between a victim ("Bob") and the router, then captures traffic in Wireshark.
   Defense: a VPN (he uses NordVPN, a sponsor) encrypts all traffic over
   WireGuard so the attacker sees nothing.
2. **Evil twin** — a clone of a legitimate WiFi network on the same channel
   (ideally same password). The hipster hides a Flipper Zero (ESP32 dev board
   running Marauder firmware) with a captive portal to phish credentials; the
   pro uses a WiFi Pineapple Enterprise that broadcasts a stronger signal and
   abuses saved-network probe requests to force devices to auto-connect. The
   noob eventually builds one manually with an Alpha adapter, dnsmasq, and
   hostapd. Once connected, attackers can DNS-spoof victims to cloned websites
   and hook browsers with BeEF.
3. **WiFi password cracking** — capture the WPA four-way handshake (EAPOL) via
   the aircrack-ng suite (airmon-ng, airodump-ng), optionally forcing it with a
   deauthentication attack, then crack the handshake against a wordlist
   (rockyou) or a targeted, site-profiled wordlist built with CeWL, Pipal, and a
   custom Python combinator.

Defensive takeaways: use a VPN for personal traffic; use a strong,
randomly-generated WiFi password unrelated to you; and for evil-twin / MITM
protection at scale, use enterprise WiFi with host isolation and rogue-SSID
detection. Chuck closes noting he uses these techniques (mainly a VPN) to
protect his family while traveling to Japan.

## Key claims

- [2024-01-08] Three attacker tiers are framed by skill: noob (laptop + Kali +
  YouTube tutorials), hipster (Flipper Zero, always carried, looks like a toy),
  pro (WiFi Pineapple Enterprise, automated scripts, ~5 minutes/few clicks).
- [2024-01-08] **Level 1 — Man-in-the-middle via ARP spoofing:** ARP is how
  devices discover each other on a network; the attacker sends malicious ARP
  packets so the router believes the attacker is Bob and Bob believes the
  attacker is the router, placing himself in the middle. Set to full-duplex,
  target the victim, enable spoofing, and capture in Wireshark (filter by source
  IP or DNS). The noob needs no understanding of ARP — just a tutorial.
- [2024-01-08] **MITM defense:** A VPN (NordVPN) encrypts all traffic; with
  spoofing on, Wireshark shows only encrypted WireGuard traffic between victim
  and the VPN — the attacker can see nothing and cannot spoof DNS. Onion-over-VPN
  / double-VPN for the paranoid.
- [2024-01-08] **Level 2 — Evil twin:** a copy of a real network on the same
  channel (and ideally same password) that users can't distinguish from the real
  one. Flipper Zero (ESP32 + Marauder firmware) adds a captive portal
  impersonating Google/Facebook to phish credentials; its limitation is it can't
  provide internet, so victims quickly disconnect. The WiFi Pineapple broadcasts
  a stronger signal (devices prioritize strongest signal) and listens for saved-
  network probe requests, cloning any remembered SSID and broadcasting it so
  auto-connect-configured phones join a hacker network without the user acting.
- [2024-01-08] **Post-connection attacks:** DNS spoofing points victims to
  attacker-controlled clones of real sites (DNS spoofing is common and hard to
  notice); the BeEF framework then hooks the victim's browser to rickroll,
  access the webcam, harvest logins, and escalate access.
- [2024-01-08] **Level 3 — WPA cracking:** capture the four-way handshake
  (EAPOL messages) with aircrack-ng (airmon-ng to enter monitor mode, airodump-ng
  targeting the AP's MAC/channel). The handshake isn't the password but contains
  the ingredients to derive it by guessing many passwords until one decrypts a
  handshake message.
- [2024-01-08] **Deauthentication attack:** the attacker forges deauth messages
  pretending to be the router (abusing a legitimate WiFi feature), forcing
  clients — one target or all — to disconnect and reconnect, capturing the fresh
  handshake without needing to wait or be connected to the network.
- [2024-01-08] **Wordlists:** the noob uses the generic rockyou list (finite, no
  guarantee, slow). Hipster/pro build targeted lists because passwords tend to be
  pertinent to the location — CeWL crawls the coffee shop's website for keywords,
  Pipal ranks the likely password words (top 10), and a custom Python script
  combines them; this cracked "mesquite coffee" in about half a second.
- [2024-01-08] **Defense:** for personal traffic, use a VPN; for your own/
  business network, use a strong randomly-generated WiFi password unrelated to
  you. Beyond that, ordinary gear can do little against evil-twin/MITM —
  enterprise WiFi can do host isolation (kills MITM) and detect/mitigate rogue
  same-SSID networks.
- [2024-01-08] **Ethics/own-network framing:** all attacks were demoed with
  permission at his simulated coffee shop; running them on others without
  explicit permission is illegal and will get you in trouble.

## Notable verbatim quotes

> You should not use any of these on anyone without explicit permission. Now, if
> you want to test them out in your house, on your friends and family with
> permission, go for it. Have fun, practice, teach. Otherwise, don't do this to
> anybody. You will get in trouble. This is illegal.

> Now what's scary is the new hacker didn't have to know what ARP spoofing is or
> how a man in the middle attack works. He just had to follow a tutorial online
> and hit a few keys on his keyboard.

> This is called an evil twin attack, and twins are already scary. You add an
> evil one, I'm done.

> The wifi pineapple listens for those probes, all the probes, every wireless
> connection your phone remembers and is looking for. The wifi pineapple grabs
> it, makes an evil twin of it and broadcasts it.

> Having the four-way handshake doesn't mean you have the wifi password, but it
> [means] you have the ingredients to figure it out.

> It's like you got a lock and you're trying a bunch of different keys to see
> which one will unlock it.

> The first thing you can do is just have a strong wifi password, randomly
> generated characters that have nothing to do with you.

> Security does come at a price, but it's a lot cheaper than the consequences of
> not having it.

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: strong hands-on cybersecurity tutorial with clear tool/technique taxonomy (Bettercap, aircrack-ng, Flipper Zero, WiFi Pineapple, CeWL/Pipal, BeEF), explicit ethics framing, and concrete defensive guidance — good source for topics/cybersecurity and persona voice/beliefs -->
