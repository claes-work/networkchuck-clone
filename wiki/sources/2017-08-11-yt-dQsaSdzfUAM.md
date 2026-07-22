---
type: youtube-video
source_date: 2017-08-11
url: https://www.youtube.com/watch?v=dQsaSdzfUAM
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [networking]
tags: [cucm, call-routing, route-pattern, cisco, voip, collaboration]
---

# Cisco Call Manager (CUCM) - Route Groups, Route Lists, Route Patterns!! - Part 1

## Summary

An early technical tutorial from Chuck's dial-plan series on Cisco Unified
Communications Manager (CUCM / "Call Manager"), one of his self-described favorite
topics — collaboration. Framed with a Star Wars story (the Galactic Empire's phone
system can call internally but a previous collaboration engineer forgot to configure
outside routing, so Captain Tarkin can't call Tatooine to book a team-building event),
Chuck explains the three-layer Cisco call-routing hierarchy: **route group → route
list → route pattern**. He walks through the concept of each layer and then demonstrates
configuring two route groups (one per SIP trunk, "Leia cube" and "Luke cube") in the
CUCM administration page under Call Routing → Route/Hunt → Route Group. Part 1 of a
multi-part sequence; the route pattern configuration is deferred to a later part.

## Key claims (dated — the concept)

All dated 2017-08-11 (paraphrase):

- Cisco call routing is hierarchical, top-to-bottom: **route group → route list →
  route pattern**. Chuck teaches it in that order, starting with the route group as the
  "backbone."
- A **route group** is essentially a group of gateways and trunks — a container that
  bundles the physical/logical devices that send calls out.
- A **route list** is a prioritized list of route groups. It is the "bread and butter"
  of the process because it enables **digit manipulation per route group** and provides
  a primary path plus a failover/backup (redundant) path.
- A **route pattern** matches dialed digits and points either directly to a trunk/
  gateway, OR to a route list (which points to a route group, which points to a SIP
  trunk or PSTN gateway).
- You *can* bypass the hierarchy — a route pattern can point straight to a single
  gateway or trunk — which is fine for a very simple config, but Cisco best practice is
  to use the full route group / route list structure.
- Reasons to use the full hierarchy: (1) it's Cisco documented best practice; (2)
  **scalability and redundancy/failover** — you can add multiple devices to a route
  group so a single path failure doesn't take the phone system down; (3) route lists
  give **digit manipulation** at a wider scale, and you cannot build a route list
  without a route group.
- Design principle: never design a phone system around a single path — "one path
  equals failure." Chuck cites real experience of CUBE / PRI gateways failing without
  a configured failover, which made him "look bad."
- Configuring a route group is simple — it's just adding a device (trunk/gateway) to a
  group container, with a distribution algorithm option (e.g. top-down, circular).
- Scenario design: the "Leia" SIP trunk + its PSTN is the primary path; the "Luke"
  trunk + a second PSTN is the secondary/failover path. The secondary is a more
  expensive per-minute deal and hands off digits differently, so it should be used
  sparingly and requires different digit handling.

## Notable verbatim quotes

> "I always say the best way to learn something and actually cement it into that brain
> is to tackle a problem or get your hands dirty."

> "Cisco's very hierarchical... the way you can figure this is route group to route
> list to route pattern, and we're going to focus on the route group first. Route
> groups are awesome, they're the backbone of this."

> "What is a route group? They are essentially just a group of gateways and trunks."

> "If you've been in IT for any amount of time you know one path equals failure,
> because a bad thing is going to fail."

> "Route lists... what do they do? They're basically just a prioritized list of route
> groups."

> "What better way to explain anything with Cisco or technology than with Star Wars?"

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
