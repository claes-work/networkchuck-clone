---
type: youtube-short
title: "HTTPS Doesn't Hide This From Your ISP!!"
channel: "@NetworkChuck"
source_date: 2026-06-18
url: https://www.youtube.com/watch?v=9fA2wAWvhJM
ingested: 2026-07-22
tier: L2
domains: [networking, cybersecurity]
---

# "HTTPS Doesn't Hide This From Your ISP!!"

## Summary

A quick networking/privacy explainer: the padlock (HTTPS) encrypts your traffic but does not hide which sites you visit — your ISP and potentially attackers still see every destination. Chuck preempts the "secure DNS solves it" objection with a Wireshark demo showing that even with encrypted DNS, the TLS SNI field still reveals the site being visited. His recommended fix is a VPN, which encrypts all PC traffic, not just browser traffic.

## Key points (paraphrase)

- 2026-06-18: HTTPS/the padlock encrypts traffic contents but does not conceal which websites you visit; ISPs and possibly hackers see every site.
- 2026-06-18: Secure DNS hides DNS queries (shown in Wireshark) but doesn't help — the SNI field still exposes exactly which site you're visiting.
- 2026-06-18: A VPN is the recommended fix because it encrypts all traffic on the PC, not just browser traffic; HTTPS alone "doesn't do everything."

## Notable verbatim quotes

- "That padlock in your browser does not hide which websites you visit. Your ISP and potentially hackers see every single one."
- "With secure DNS, I suddenly cannot see DNS traffic. That doesn't matter. I can still see SNI, which shows me exactly what site you're visiting."
- "Many people think that because HTTPS exists, you don't need a VPN, but it doesn't do everything. And there's more on your PC happening than just browser traffic. A VPN will encrypt it all."

## Guest attribution

Solo Chuck.
