---
type: youtube-video
source_date: 2023-10-30
url: https://www.youtube.com/watch?v=tBnJRraXDc0
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, homelab-selfhosting]
tags: [tor, dark-web, relay, privacy, internet-freedom]
---

# The Dark Web NEEDS You!

## Summary

Chuck makes a values-driven, hands-on case for volunteering to run a Tor relay
(an "onion relay") to strengthen the Tor network / dark web. He reframes the dark
web as privacy infrastructure that millions of people worldwide depend on to stay
safe and anonymous, and argues that every relay is run by ordinary volunteers —
so the viewer can and should contribute. He explains the three-relay onion circuit
(guard/entry, middle, exit), warns strongly against running an exit node (legal
exposure — police could show up; exit nodes are normally run by institutions and
universities with ISP agreements), and steers viewers toward running a guard or
middle node, noting everyone starts as a middle relay and must "earn" the guard
flag over time. He walks through hardware/bandwidth/uptime requirements for
home hosting versus cloud hosting (he prefers a cheap $3–6/month cloud VM), then
gives a full build: Ubuntu server, unattended-upgrades, installing Tor from the
Tor Project repo, editing `torrc` (nickname, contact email, ORPort, `ExitRelay 0`,
bandwidth accounting limits, control port), enabling the service, and monitoring
the relay with the `nyx` tool. The video closes on his explicit motive: supporting
the Tor Project to help people stay safe, private, and anonymous. Sponsored by
Dashlane (password manager / dark-web monitoring), delivered as a comedic "dark
web scary story."

## Key claims (paraphrase, dated 2023-10-30)

- The dark web / Tor network is kept running by "onion relays" — volunteer-run
  servers — and adding more relays makes the network faster, more robust against
  attacks, more stable, and safer from spying.
- Each Tor connection forms an "onion circuit" of three relays; each hop adds a
  layer of encryption, keeping data safe and the user's identity anonymous.
- There are three relay roles: guard (entry) node, middle node, and exit node.
- Do NOT run an exit node (for now): exit relays carry the greatest legal exposure
  and liability, because destination websites see the exit node as the origin of
  the traffic — so police pursue the exit-node operator, not the real user. Exit
  nodes are normally run by institutions and universities that have agreements with
  their ISPs.
- Guard and middle nodes rarely receive abuse complaints and are low-exposure;
  new relays always start as a middle node and must earn their way to guard status
  over time via consistent uptime and reliability (measured by "flags").
- A relay can be hosted at home on spare hardware (Raspberry Pi, old laptop, VM) or
  in the cloud; Chuck prefers cloud (~$3–6/month, easier, offloads bandwidth).
- Home hosting requirements: a public IPv4 address (static not required, port
  forwarding usually needed behind NAT), ability to handle ~7,000 concurrent
  connections, ~16 Mbps up/down recommended (10 Mbps minimum), and a required
  minimum of ~100 GB/month outbound (plus similar inbound). Limit of 8 relays per
  public IPv4 address.
- Server requirements are light: ~512 MB RAM, ~200 MB storage, any modern CPU;
  ideal uptime is 24/7, but at least ~2 hours/day to be useful.
- Home operators might receive a DMCA/copyright notice; it's manageable — the Tor
  Project provides email templates to send to the ISP/complainant.
- Choose your host carefully: some providers disallow Tor relays; the Tor Project
  publishes a good/bad ISP list and asks operators to avoid oversaturated providers
  and spread relays across the world for network effectiveness.
- Motivation / ethics framing: the dark web, like all places, can be used for bad
  things, but Chuck believes it's mostly used for good — "it's all about your
  motive" — and his motive in supporting the Tor Project and running a relay is to
  help people stay safe, private, and anonymous.

## Notable verbatim quotes

> "The dark web needs your help. So in this video I want to show you how you can become part of the dark web."

> "It can be like all places, but it's also what millions of people around the world depend on to stay safe and anonymous online. The dark web is all about privacy, and that's where you come in."

> "Did you know that every onion relay is run by people like you volunteers? Making this decision is a big deal and will have a pretty big impact."

> "You do not want to be the exit node, at least not right now. According to the experts on Reddit, the police could show up at your door."

> "According to the official tor documentation, exit relays have the greatest legal exposure and liability of all the relays, and they're normally run by institutions and universities."

> "When you start running a tor relay node, an onion relay, everyone's going to be a middle relay. Everyone. You have to earn your way to becoming a guard."

> "The goal here is to have a bunch of onion nodes throughout the world on all types of networks. If we have a bunch of onions all in one place, it kind of limits its effectiveness. We want to spread out."

> "Sure, the dark web can be used for bad things, but I think it's mostly used for good things. It's all about your motive. And I know my motive here in supporting the tor project and running a relay is to help people stay safe and private and anonymous."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: run-a-Tor-relay / internet-freedom & privacy values -->
