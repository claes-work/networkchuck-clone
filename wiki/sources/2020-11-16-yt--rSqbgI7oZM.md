---
type: youtube-video
source_date: 2020-11-16
url: https://www.youtube.com/watch?v=-rSqbgI7oZM
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, networking]
tags: [sniffing, mitm, arp-spoofing, wireshark, ethical-hacking, defense]
---

# how Hackers SNiFF (capture) network traffic // MiTM attack

## Summary

An ethical-hacking tutorial in which Chuck demonstrates how an attacker
captures ("sniffs") network traffic and performs a man-in-the-middle (MiTM)
attack against machines on his own lab network. The premise: on a switched
network a device normally only sees traffic addressed to it, so an attacker
uses **ARP spoofing** to trick the victim and the gateway into sending their
traffic through the attacker's machine, which then captures it with tools like
**Wireshark** and **Ettercap**. The video pairs the offensive demonstration
with the defensive takeaway — encryption (HTTPS/TLS) is what keeps sniffed
traffic unreadable — and frames the whole exercise as something to be done only
on your own equipment / with permission, for learning and defense.

> ⚠️ SOURCE QUALITY: The auto-generated caption file for this video is
> corrupted — it contains non-English fragments and unrelated token noise rather
> than a usable English transcript. The summary and key claims below are grounded
> in the video's title/premise and the standard concept it teaches, NOT in a
> readable transcript. No verbatim quotes are recoverable from the caption file.
> A clean transcript re-fetch is needed before any of Chuck's specific wording,
> examples, or exact defensive advice can be quoted or attributed.

## Key claims (dated — concept + defense)

_All paraphrase; derived from the video title/premise, not a verified transcript
(see source-quality note above). Dated 2020-11-16._

**Concept (how the attack works):**
- On a switched network a host normally only receives frames destined for it, so
  simply "listening" is not enough to see other devices' traffic. (2020-11-16)
- ARP spoofing lets an attacker position their machine between a victim and the
  gateway (man-in-the-middle), so both sides send traffic through the attacker.
  (2020-11-16)
- Once in the middle, the attacker captures and inspects the passing packets with
  packet-analysis tools such as Wireshark and Ettercap. (2020-11-16)

**Defense:**
- Encryption is the core defense: traffic protected by HTTPS/TLS remains
  unreadable to an attacker even when the packets are captured. (2020-11-16)

**Lab / ethics framing:**
- The demonstration is performed on Chuck's own lab network, and the technique is
  presented for learning and defensive understanding — to be used only on systems
  you own or are authorized to test. (2020-11-16)

## Notable verbatim quotes

None recoverable — the caption file for this video is corrupted (see the
source-quality note above). No verbatim wording is attributed to avoid
fabrication; this section should be filled in from a clean transcript re-fetch.

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: core cybersecurity topic (packet sniffing / ARP-spoofing MiTM + HTTPS defense) worth promoting into wiki/topics, but caption file is corrupted — re-fetch a clean transcript before full ingest to recover Chuck's exact wording and defensive framing. -->
