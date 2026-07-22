---
type: youtube-video
source_date: 2020-10-03
url: https://www.youtube.com/watch?v=eZYtnzODpW4
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity]
tags: [ddos, dark-web, tor, ethical-hacking, education, security-awareness]
---

# i bought a DDoS attack on the DARK WEB (don't do this)

## Summary

An experiential security-education video in which Chuck Keith explains DDoS/DoS
attacks by demonstrating them **against his own lab infrastructure only**. He recounts
buying a DDoS-for-hire script from a dark-web marketplace (accessed via a VPN client
plus the Tor browser, paid in bitcoin) — then notes the same scripts are freely
available on GitHub, so viewers should not go to the dark web. The video's spine is a
progression through increasingly sophisticated attack techniques, each shown hitting
his own web server (10.7.1.50) while he watches ping latency and site availability
change: a single-machine flood (Low Orbit Ion Cannon, hping3 ICMP/ping flood) that
barely moves the needle, the same attacks distributed across multiple servers (a true
DDoS) that visibly degrade the target, a TCP SYN flood exploiting the three-way
handshake, and finally an HTTP GET flood ("Sapphira" script) that forges up to a
million unique requests to evade firewall detection. He also stands up a botnet using
the open-source "Build Your Own Botnet" (BYOB) framework to illustrate how zombie
machines are recruited and commanded.

The concept payload is entirely conceptual/defensive: WHY each attack works (turning
legitimate protocols — ping, TCP handshake, HTTP GET — into weapons), why single-source
attacks fail against a well-provisioned server, how firewalls detect and block crude
attacks, and how attackers escalate to evade them. The video closes on **defense**:
firewalls, patching, redundancy, and cloud/Cloudflare DDoS protection. Throughout,
Chuck repeats a strong ethics/legality frame — attacking anyone without permission is
illegal and can lead to jail; only attack systems you own or have explicit permission
for. He offers his own URL (ddos.networkchuck.com) as a sanctioned practice target.
Sponsored by ITProTV.

## Key claims (2020-10-03)

- A DDoS (distributed denial-of-service) attack's goal is not to break in or steal
  data — it is to make a target's website/service disappear and be inaccessible to
  everyone by overwhelming or confusing the server (or both). (paraphrase)
- **Ethics/legality (stated repeatedly):** never do this to anyone without their
  permission; people have gone to jail for it; only use these tools against yourself,
  friends who consent, or your own systems. The disclaimer opens and closes the video.
  (paraphrase)
- He demonstrates every attack against his OWN web server (10.7.1.50) in a lab,
  monitoring health via ping latency from a second server (sub-millisecond when
  healthy). (paraphrase)
- A single-machine attack (Low Orbit Ion Cannon on Windows/Mac/Linux; hping3 ICMP/ping
  flood) is easy to run but usually can't overwhelm a server with adequate bandwidth —
  latency barely rises. (paraphrase)
- Distributing the same flood across multiple servers turns a DoS into a DDoS and
  visibly degrades the target (latency climbing to ~19ms on a local LAN; the website
  struggling to load). (paraphrase)
- A ping/ICMP flood is easy to defeat — just disable ICMP so the server stops
  responding to pings. Older attacks like the "ping of death" (oversized packet /
  buffer overflow) no longer work on modern systems. (paraphrase)
- A SYN flood abuses the TCP three-way handshake: send floods of SYN requests and never
  complete the handshake, exhausting the server's connection capacity; distributed, it
  can make the web server stop serving pages. (paraphrase)
- Firewalls catch on to crude, repetitive floods and quickly block the offending IPs,
  which is why simple attacks often "don't even matter." (paraphrase)
- More sophisticated dark-web scripts (e.g. "Sapphira") run an HTTP GET flood, forging
  unique requests — varying user agents and headers to compile up to ~1 million unique
  GET requests — so a firewall can't easily fingerprint and block them. (paraphrase,
  concept only)
- The same scripts he paid bitcoin for on the dark web can be downloaded free on GitHub;
  viewers should not visit the dark web. (paraphrase)
- Most large DDoS attacks use botnets: victims unknowingly run malware (via phishing or
  fake sites) that turns their machines into "zombies" answering a command-and-control
  server. He builds one with the open-source, education-oriented BYOB framework, noting
  how simple (and therefore scary) setup is, and that it ships post-exploitation
  modules (crypto miner, keylogger, packet sniffer, etc.). (paraphrase, concept only)
- Defense recommendations: secure the network with an up-to-date firewall and best
  practice, patch servers and applications with the latest OS releases, and build
  redundancy (multiple servers/firewalls). No network is truly immune. (paraphrase)
- Moving to the cloud helps: AWS/Azure and services like Cloudflare (sitting in front of
  a site) provide DDoS protection — safer, though not immune. (paraphrase)
- Career framing: learn this as an **ethical** hacker so you can help companies prepare
  for and recover from these attacks; you'll rarely run one on a client but must
  understand how they work. (paraphrase)
- He grants explicit permission to attack only one specific target — his own URL
  ddos.networkchuck.com — as a sanctioned practice site. (paraphrase)

## Notable verbatim quotes

> "disclaimer this is for educational purposes only never do this to anyone without
> their permission ever"

> "no i want to bring you down i don't want to hack into your website i want your
> website to disappear and be inaccessible to everyone"

> "please again don't attack anyone without permission you can go to jail for this
> people have gone to jail for this so be careful"

> "hackers want to take a good thing and make it a bad thing"

> "the scariest part about a dos attack is it's crazy easy to do an attack like this
> like anyone can do it and you can cause some serious damage"

> "i told you i got this off the dark web and i did i paid bitcoin with that sucker but
> then i later found out you can just download these for free on github"

> "really no network is safe from a ddos attack ... the best way to mitigate that is
> just make sure you're as redundant as possible"

> "maybe learn to become a hacker an ethical hacker obviously your job is to help
> companies be prepared for these situations"

> "i'm only giving you permission to attack my website this specific url and that's it
> so don't don't go attacking anyone else"

> "again disclaimer don't attack anyone without permission you can get in trouble you
> can go to jail so just be careful out there"

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: dark-web DDoS demo against own infra — stunt-education + ethics framing -->
