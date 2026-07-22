---
type: youtube-video
source_date: 2020-09-18
url: https://www.youtube.com/watch?v=wwwAXlE4OtU
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [networking, certifications-career]
tags: [free-ccna, network-design, hierarchical-design, ep-6]
---

# DO NOT design your network like this!! // FREE CCNA // EP 6

## Summary

Episode 6 of NetworkChuck's FREE CCNA series (sponsored by Boson Software) teaches
network design using Cisco's hierarchical model. Chuck frames the lesson around a
running example — his fictional "NetworkChuck Coffee" company — and starts by building
a **bad** network so students learn to recognize and fix it in the field: a single
router doing everything (router + switch + modem + wireless access point), then switches
daisy-chained switch-to-switch as the company grows. He shows that daisy-chaining
creates **single points of failure** — when his pug Moses chews through one cable, every
device downstream goes down. Home networks tolerate this (you miss a Netflix episode);
businesses cannot (it costs money).

He then builds up the fixes. First insight: connecting every access switch back to the
router works for internet traffic (Layer 3) but is not ideal for devices talking to each
other on the same network. The better intermediary is a **multi-layer switch (Layer 3
switch)** — a switch that handles both MAC addresses (Layer 2) and IP addresses (Layer
3), and is blazing fast. This produces the **two-tier architecture**: an **access
layer** (tier 1, the access switches devices plug into) and a **distribution layer**
(tier 2, the multi-layer/distribution switch everything routes through). Because all
traffic funnels through the distribution switch, it must be a big, high-horsepower box
(e.g. Cisco Catalyst 3850, ~480 Gbps backplane; larger Catalyst options into the
terabit range) — never a tiny 8-port switch.

The distribution layer does more than distribute: it's also called the **aggregation
layer** and handles inter-VLAN routing, route filtering, management, ACLs, security
policies, routing, summarization, and next-hop redundancy (terms covered in later
episodes). To remove remaining single points of failure, you add redundancy —
duplicate distribution switches, dual links to each access switch, and dual routers —
which is ideal but expensive, so it's always a budget trade-off with the business.

Chuck then introduces the **three-tier architecture** for large multi-building campuses.
Meshing multiple buildings' distribution switches directly together gets messy and
doesn't scale, so you add a **core layer** (tier 3): a "big dadd" Layer 3 core switch
(ideally two, cross-connected) that is the network backbone — associated with low
latency and high reliability, expensive and beefy (e.g. modular Cisco Catalyst 9600,
~25.6 Tbps backplane). Distribution layers connect up only to the core, not to each
other, which lets a campus scale cleanly. Importantly, a two-tier design is the
**collapsed core** model — the core's role isn't gone, it's collapsed into the
distribution layer, which then serves as both distribution and backbone. Chuck notes
the collapsed-core / two-tier model is what he's seen and worked with most in real
companies (one corporate office); true three-tier shines for large campuses like
Cisco's own headquarters. He closes by previewing future topics (data centers, cloud,
WAN, SOHO) and assigns homework: find out whether your own company runs two-tier,
three-tier, or "some weird tier."

## Key claims (dated — the design principles)

- **[2020-09-18]** If your network can't afford to lose a single link, switch, or
  router, it's designed wrong — you must design out single points of failure.
- **[2020-09-18]** Home networks and early small businesses often collapse many roles
  (router, switch, modem, wireless access point) into one device; having one device do
  everything is bad design.
- **[2020-09-18]** Daisy-chaining switches (connecting switch-to-switch in a chain)
  creates single points of failure: if one link or switch fails, everything downstream
  goes down.
- **[2020-09-18]** A single point of failure means that if one thing fails, most of the
  network goes down; the goal of good design is **redundancy** — a cable or switch can
  fail and things stay up.
- **[2020-09-18]** Connecting access switches directly to a router handles internet
  (Layer 3) traffic well but is not ideal for devices communicating with each other on
  the same local network.
- **[2020-09-18]** A **multi-layer switch (Layer 3 switch)** handles both Layer 2 MAC
  addresses and Layer 3 IP addresses and is very fast, making it the right device to
  aggregate access switches.
- **[2020-09-18]** The **two-tier architecture** = access layer (tier 1, access
  switches for end devices) + distribution layer (tier 2, the distribution/multi-layer
  switch all traffic passes through).
- **[2020-09-18]** Because all traffic funnels through it, the distribution switch must
  be large and high-horsepower; an undersized (e.g. 8-port) switch there will be
  overwhelmed.
- **[2020-09-18]** The distribution layer (also called the **aggregation layer**)
  handles route filtering, inter-VLAN routing, management, ACLs, IPS/security policies,
  routing (it is Layer 3), summarization, and next-hop redundancy.
- **[2020-09-18]** Redundancy (dual distribution switches, dual links per access switch,
  dual routers) removes single points of failure but is expensive — always a budget
  trade-off with the business.
- **[2020-09-18]** The **three-tier architecture** adds a **core layer** (tier 3) for
  large multi-building campuses; the core is a powerful Layer 3 backbone switch (ideally
  two, cross-connected).
- **[2020-09-18]** The core layer is characterized by low latency and high reliability;
  it is the network backbone, so it must be expensive, reliable, and beefy.
- **[2020-09-18]** In three-tier, distribution layers connect up to the core only (not
  meshed to each other), and typically only one building holds the campus core — this
  scales far better than directly meshing buildings.
- **[2020-09-18]** A two-tier design is the **collapsed core** model: the core's role
  isn't removed, it's collapsed into the distribution layer, which acts as both
  distribution and backbone.
- **[2020-09-18]** The collapsed-core / two-tier model is the one Chuck has seen and
  worked with most; three-tier is best reserved for large campuses (many buildings
  needing high-speed interconnection).
- **[2020-09-18]** Networking hardware is not cheap (Layer 3 switches and routers can
  run into the hundreds of thousands of dollars), "which is why we make the big bucks."

## Notable verbatim quotes

> "if you can't afford to lose one link or one switch or one router you're doing it
> wrong"

> "to find a bad network you don't have to look very far look in your house i'm not
> kidding your home network sucks"

> "this right here is what we call now say it with me a single point of failure don't
> ever have those in your network ever"

> "in your home you can afford it to fail because the worst thing that can happen is you
> miss an episode of netflix or worse you can't watch my next video"

> "this my friends is a multi-layer switch often referred to as a layer 3 switch ... it's
> literally a switch that can deal with ip addresses and mac addresses it can do it all
> and it's blazing fast"

> "so don't put a tiny little eight port switch and your distribution layer he'll die"

> "the core layer what is he doing ... he's like that massive guy at the gym just over
> there oh there's grunting that's all he does is grunt and lift ... he's just fast and
> he's associated with low latency and high reliability"

> "the core switch is expensive reliable and beefy because he is the network backbone
> and a ton of traffic goes through him"

> "notice what they call it the collapsed core layer ... the functions of the core were
> collapsed into the distribution layer"

> "no one said networking is cheap which is why we make the big bucks"

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: FREE CCNA EP 6 — network design -->
