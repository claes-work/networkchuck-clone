---
type: youtube-video
source_date: 2023-05-19
url: https://www.youtube.com/watch?v=B1vqKQIPxr0
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [networking, certifications-career]
tags: [subnetting, vlan, coffee-shop, network-design, real-world]
---

# subnetting my coffee shop

## Summary

A subnetting tutorial (episode 7 of NetworkChuck's subnetting series) that teaches
**subnetting based on host requirements** (variable-length / VLSM-style design) rather
than the more common "how many networks do I need" approach. Chuck frames the whole
lesson around a real-world scenario: designing the networks for **his coffee shops**.
He walks through the four-step process using his recurring teaching props — the "Nora"
powers-of-two chart and its "double" sibling "Nora two" — converting the subnet mask to
binary, counting host bits, and (the one key difference from network-based subnetting)
**reserving host bits from the right instead of hacking them from the left** ("the
upside down / uno reverse card").

The primary worked example: a `10.1.1.0/24` network broken into three coffee-shop
subnets, each sized for ~40 hosts, yielding three `/26` networks. A second practice
example flips to an ISP scenario (`142.x.x.x/16`, five customers needing 20 public IPs
each → `/27` subnets). He closes by promoting the Network Chuck Academy for subnetting
practice and previews the next episode (reverse-engineering a broadcast address from a
host IP `/21`).

Notable bio detail: Chuck opens by saying he is **launching new coffee shops** and
needs help designing their networks — indicating NetworkChuck Coffee involves (or he is
planning) physical coffee shop location(s), not only an online coffee brand. He also
repeatedly jokes that each coffee shop has its own on-site network admin.

## Key claims

- [2023-05-19] Subnetting based on **host requirements** is nearly identical to
  subnetting based on network requirements, with one key difference: you reserve host
  bits starting from the **right** (rather than hacking network bits from the left).
- [2023-05-19] The four-step process taught: (1) convert the subnet mask to binary,
  (2) use the powers-of-two chart to find how many host bits are needed to contain the
  required host count, (3) reserve those host bits from the right and let the rest
  become network bits, (4) find the increment (the value of the last network bit) and
  use it to lay out the subnets.
- [2023-05-19] Worked example: `10.1.1.0/24` subnetted for three coffee shops, each
  needing ~40 hosts. 40 hosts requires 6 host bits (nearest power of two that contains
  40 is 64), giving a `/26` mask (`255.255.255.192`) with an increment of 64 and 62
  usable addresses per subnet.
- [2023-05-19] Per-coffee-shop host count is estimated at ~30 hosts, rounded up to ~40
  for headroom: five employees, one server, two Raspberry Pis, two wireless access
  points, and up to 20 guests.
- [2023-05-19] The three resulting coffee-shop networks are `10.1.1.0/26`,
  `10.1.1.64/26`, and `10.1.1.128/26`.
- [2023-05-19] Second (practice) example: an ISP with a `142.x.x.x/16` block and five
  customers each needing at least 20 static public IPs. 20 hosts requires 5 host bits
  (nearest power of two is 32), giving a `/27` mask (`255.255.255.224`), increment 32,
  30 usable addresses per customer — conserving addresses while leaving room for growth.
- [2023-05-19] **Bio:** Chuck states he is "launching some new coffee shops" and needs
  help designing their networks, implying NetworkChuck Coffee has / is planning
  physical coffee shop location(s) beyond the online brand. See
  [[../entities/networkchuck-coffee]].
- [2023-05-19] Recurring gag that every coffee shop has its own network admin ("yes,
  it's network shop coffee. Every single coffee shop has their own network admin").
- [2023-05-19] Promotes Boson NetSim as (in his words) the best network simulator for
  CCNA/CCNP study and the official sponsor of the CCNA series; paid sponsor of the
  episode is IPRoyal (residential proxies, code "Chuck" for 30% off).
- [2023-05-19] Promotes the Network Chuck Academy for additional subnetting practice.

## Notable verbatim quotes

> I'm launching some new coffee shops and I need help designing the networks. I need a
> Subnetting expert. That's you, right?

> If you watched episodes one through six of our series, you no longer suck at
> subnetting, right?

> I'm not just saying give me three networks out of the subnet. Now I need you to subnet
> based on how many hosts we have in each network. This is different. A bit real world.

> Each coffee shop has five employees, one server, two raspberry pies because it's a
> network. Chuck coffee shop, what do you expect? Two wireless access points... and up
> to 20 guests.

> We're gonna flip, reverse it... We're gonna start from the right... Now because we're
> in the upside down, we're not actually going to hack the bits. Scratch that. We're
> going to save the bits.

> Yes, it's network shop coffee. Every single coffee shop has their own network admin.
> Do we need it? Yes.

> Now what you just did there was real world, you helped me subnet and address my coffee
> shop networks. And this is what you'll probably see more commonly when you're given a
> problem to solve when it comes to subnetting.

> Subnetting is a skill that you need to practice over and over and over to get pretty
> good at it. And if you're like me, you forget every year or so and you have to come
> back and relearn it.

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: NetworkChuck Coffee physical shop (bio) + real-world subnetting design -->
