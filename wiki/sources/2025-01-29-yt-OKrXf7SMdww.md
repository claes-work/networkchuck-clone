---
type: youtube-short
channel: "@NetworkChuck"
title: "DeepSeek in Deep Trouble! (Internal database exposed)"
source_date: 2025-01-29
url: https://www.youtube.com/watch?v=OKrXf7SMdww
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, ai-tools]
---

# DeepSeek in Deep Trouble! (Internal database exposed)

## Summary

Chuck reacts to Wiz Research's discovery that DeepSeek left a publicly accessible
ClickHouse database completely open — no authentication required — exposing secret keys,
plain-text chat messages, backend details, and logs. He notes Wiz found it with simple
recon against DeepSeek's public infrastructure, that it could have allowed privilege
escalation and server takeover, and that Wiz (ethical hackers) reported it responsibly so
DeepSeek could lock it down. His takeaway: DeepSeek found novel ways to build top AI models
but missed security basics, and this is a core reason he prefers running AI locally.

## Key points

- [2025-01-29] Wiz Research found a publicly accessible ClickHouse database from DeepSeek exposing secret keys, plain-text chat messages, backend details, and logs.
- [2025-01-29] The database required no authentication at all; found via simple recon of DeepSeek's public infrastructure.
- [2025-01-29] Exposure could enable privilege escalation within the server, potentially leading to server takeover.
- [2025-01-29] Wiz reported it responsibly; DeepSeek locked it down.
- [2025-01-29] Chuck's framing: DeepSeek innovated on AI models but missed security basics.
- [2025-01-29] Chuck cites this as a reason he prefers running AI locally rather than sending data to DeepSeek's servers. <!-- ★ L3-candidate: recurring "run your AI locally / control your own data" belief -->

## Notable verbatim quotes

- "AI security starts with infrastructure." (Chuck endorsing Wiz Research's line)
- "now this is one of the big reasons why I prefer to run my AI locally"
- "moral the story be careful who you give your data to and don't forget your security Basics it'll come back to bite you"

## Guest attribution

Solo Chuck.
