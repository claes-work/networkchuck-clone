---
type: youtube-short
channel: "@NetworkChuck"
title: "I DDoS'd myself (don't do this)"
source_date: 2026-02-04
url: https://www.youtube.com/watch?v=acSlR6UD6yM
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, networking]
---

# I DDoS'd myself (don't do this)

## Summary

Chuck demonstrates a denial-of-service attack against his own lab web server, framing DoS as having two goals: to overwhelm and/or confuse a target. He starts with a harmless ICMP ping (the same tool IT uses to check if servers are up), then floods the server using the hacking tool `hping3` with an ICMP flood (`-1 --flood`) against target `10.7.150`. A single attacker doesn't generate enough traffic to affect the server's sub-millisecond ping times. When he adds multiple attacking computers, latency jumps from sub-millisecond to as much as 19 ms on a local LAN — this is a distributed denial-of-service (DDoS), specifically a ping/ICMP flood. He notes the attack is easy to defeat: turn off ICMP (ping) on the server and the attack no longer works.

## Key points

- 2026-02-04 — DoS has two goals: overwhelm and/or confuse the target.
- 2026-02-04 — Tool used: `hping3` with switches `-1` (ICMP) and `--flood`; target `10.7.150`.
- 2026-02-04 — A single attacker's ping flood didn't meaningfully raise latency; the server had enough bandwidth to absorb it.
- 2026-02-04 — Adding multiple attacking machines raised LAN latency from sub-millisecond to ~19 ms — a distributed denial-of-service (DDoS), aka a ping flood / ICMP flood.
- 2026-02-04 — Mitigation: disabling ICMP (ping) on the server defeats this specific attack.
- 2026-02-04 — Strong ethical/legal warning: never attack anyone without permission; "You can go to jail for this."

## Notable verbatim quotes

- "When we're DOSing something or denial of servicing something, we basically have two goals. We want to overwhelm or confuse or both."
- "This is what we call a distributed denial of service attack or a DDoS attack because we're using multiple computers to attack our target."
- "All you got to do is turn off ICMP on your server, turn off ping, can't attack him anymore. It's done. How lame."

## Guest attribution

Solo Chuck.
