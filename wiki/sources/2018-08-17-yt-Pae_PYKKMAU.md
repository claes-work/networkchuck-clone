---
type: youtube-video
source_date: 2018-08-17
url: https://www.youtube.com/watch?v=Pae_PYKKMAU
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [networking, cybersecurity, cloud-devops]
tags: [dna-center, security-automation, sdn, infosec-future, cisco, 2018]
---

# The FUTURE of Information Security Engineers - Cisco Security Automation (DNA CENTER)

## Summary

A Cisco-sponsored video (Chuck attended Cisco Live in June 2018) framing network
programmability and automation as an arriving reality for all IT tracks — not just
routing and switching, but security, collaboration, and wireless too. Chuck's core
message: security engineers should embrace automation rather than fear it, because
"you are the programmer" — the change depends on them.

He walks through Cisco DNA Center (Digital Network Architecture) as an "SDN controller
on steroids": a single portal to design, deploy, manage, monitor, and automate the
whole network. The 2018 Cisco Live headline he highlights is that DNA Center is now
"open" with APIs, so programmers can integrate their own apps and third-party products
into it.

He then illustrates security automation with a demo scenario: StealthWatch detects a
"WannaCry"-style ransomware threat hiding in encrypted traffic (using Encrypted Traffic
Analytics / ETA on Cisco routers and switches, without decrypting), reports to DNA
Center, which — via APIs — opens a ticket in ServiceNow (a third-party ITSM), notifies
the security engineer, and on a single "quarantine" tap automates the mitigation. Chuck
stresses how little manual work the engineer had to do, and closes urging engineers to
embrace the coming change and start learning programming.

## Key claims (paraphrase; dated 2018-08-17)

**The concept (as presented in 2018):**
- Cisco DNA Center (Digital Network Architecture) is a centralized SDN-style controller
  to design, deploy, provision, configure, monitor, and automate an entire network
  (APs, routers, switches) from one portal instead of logging into many devices.
- As of Cisco Live 2018, DNA Center is "open" with APIs, letting programmers/third
  parties integrate their own apps and products into it.
- StealthWatch is an analytics engine that detects malware (e.g., ransomware like
  WannaCry) in encrypted traffic *without decrypting it*, using Encrypted Traffic
  Analytics (ETA) telemetry from Cisco routers/switches — described as "NetFlow on
  steroids" that baselines normal traffic and profiles bad traffic via metadata and
  flow patterns.
- Decrypting traffic to inspect it is expensive (hardware), slows the network, and can
  be a privacy/legal violation in many countries — which is why ETA/StealthWatch's
  decryption-free approach matters.
- DNA Center's open APIs allow chaining tools: StealthWatch → DNA Center → ServiceNow
  (third-party ITSM), so a threat can be auto-ticketed, the engineer notified, and a
  one-tap "quarantine" fully automated. Cisco's demo of this took ~3 weeks to program.

**His 2018 prediction / forward-looking view (may have evolved):**
- Network programmability is no longer a far-off buzzword — it is "here" and going
  mainstream across all tracks (routing/switching, security, collaboration, wireless),
  driven by Cisco shipping products like DNA Center.
- Cisco told network engineers at the keynote "you are a developer" — Chuck treats this
  as a real, near-term identity shift for the profession.
- Automation will absorb the mundane day-to-day tasks; the answer is NOT that engineers
  lose their jobs but that they must upskill into programming and design higher-level
  solutions. "The only way you come out on top is by embracing it."
- Statistic he cites: it was estimated that by 2019, ~70% of all malware attacks would
  be encrypted (motivating decryption-free detection).

## Notable verbatim quotes

> "if you're currently a security engineer or maybe you're thinking about becoming a
> security engineer automation and programmability is at your doorstep"

> "now before you start screaming oh the network security field is dead ... no no no
> hold on slow down guys you're the programmer remember this change involves you it
> requires you it actually depends on you"

> "they said you are a developer so you are a developer what like we're developers now
> just like that"

> "it's estimated that by 2019 70% ... of all attacks on all malware will be encrypted"

> "stealthWatch can just eyeball that traffic and know if it's bad or good without
> decrypting it which is kind of crazy"

> "it's sending net flow on steroids just super net flow as telemetry about malware"

> "I think the age of just like hearing network programmability and all these buzzwords
> and going oh yeah that'll be the day ... that's over like it's it's here"

> "embrace that change man it's coming the only way you come out on top is by embracing
> it"

> "keep studying"

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: 2018 prediction on infosec/automation future (DNA Center) — track evolution -->
