---
type: youtube-video
source_date: 2022-04-07
url: https://www.youtube.com/watch?v=tcae4TSSMo8
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [networking, certifications-career]
tags: [ipv4-exhaustion, ipv6, nat, cidr, subnetting]
---

# we ran OUT of IP Addresses!!

## Summary

An episode of Chuck's "you suck at subnetting" series (also part of his CCNA
series) explaining why the world ran out of IPv4 addresses and how the original
architects of the internet mismanaged the address space. Chuck frames the problem
around the fixed IPv4 pool of roughly 4.3 billion addresses (2^32) and the two
things the internet's inventors failed to anticipate: (1) how huge the internet
would become, and (2) how many devices — watches, ovens, microwaves, "toilets" —
would each need an address.

The core of the video is the **classful addressing** system (classes A, B, C, D,
E) and how it wasted addresses. He walks through each class via its default subnet
mask: class A (255.0.0.0) gives ~16 million hosts per network but only 126
networks; class B (255.255.0.0) gives 65,534 hosts and 16,382 networks; class C
(255.255.255.0) gives 254 hosts and ~2 million networks. He argues class A handed
giant 16-million-address blocks to companies like GE, IBM, AT&T, Xerox, and HP,
and that class C's plan (many small networks) should have been the model for
everything. He introduces the idea of cutting a large classful block into smaller
subnets with a longer mask — the first glimpse of **subnetting / classless (CIDR)
addressing** — noting his own home network (10.7.1.0 with a 255.255.255.0 mask) is
technically a "classless" class A network.

He also covers two categories of unusable addresses: **class D** (multicast,
reserved) and **class E** (experimental, "untouchable"), which lack subnet masks
because it doesn't matter; and the **missing 127 range** — 127.0.0.0/8 loopback
addresses (~16 million) reserved for local network testing, demonstrated by
pinging 127.0.0.1 (and 127.15.15.8) to confirm a machine can "hear itself." IANA
(the "Santa Claus of IP addresses" / "head Oprah") is named as the allocating
authority. The video is a setup piece: it promises the "bandaid" fixes — NAT and
then IPv6 — in coming episodes without detailing them. Sponsors: 3CX (business
phone system) and Boson software (CCNA/certification prep).

## Key claims (dated — the concepts)

All paraphrased unless quoted. Dated 2022-04-07.

- IPv4 has a fixed pool of roughly 4.3 billion addresses — precisely 2^32 =
  4,294,967,296 — and that supply has been exhausted.
- The internet's "official birthday" is January 1st, 1983; at that time 4.3 billion
  addresses seemed inexhaustible.
- Two things the inventors failed to anticipate: the internet's explosive growth,
  and that huge numbers of everyday devices (not just computers) would each need an
  IP address.
- An IPv4 address is four numbers separated by three dots; each octet ranges 0–255.
- Addresses were organized into classes A, B, C, D, E — Chuck argues this both
  locked away large unusable ranges and gave away far too many addresses.
- A subnet mask determines how big a network is: a 255 locks the matching octet
  (stays the same), a 0 leaves that octet free (any value 0–255).
- Class A: default mask 255.0.0.0 → ~16,777,214 hosts per network but only 126
  total networks; host-heavy.
- Class B: default mask 255.255.0.0 → 65,534 hosts per network and 16,382 networks.
- Class C: default mask 255.255.255.0 → 254 hosts per network and 2,097,150
  networks; the most familiar (home networks) and, per Chuck, the plan they should
  have used everywhere.
- Class A blocks were handed to large companies; examples given: GE owns 3.0.0.0,
  IBM 9.x, AT&T 12.x, Xerox 13.x, HP 15.x — each over 16 million addresses.
- IANA (Internet Assigned Numbers Authority) allocates/assigns address blocks; a
  company can subdivide a large block into smaller subnets with a longer mask
  (e.g. IBM's 9.0.0.0 cut into 9.4.0.0 with 255.255.255.0).
- Using a non-default (longer) mask on a classful network makes it a "classless"
  network — an early definition of CIDR/subnetting; Chuck's home network is
  10.7.1.0 with mask 255.255.255.0.
- Class D is reserved for multicast; class E is experimental — both unusable, and
  neither has a subnet mask because it's irrelevant.
- The 127.0.0.0 range (~16 million addresses) is missing from the A/B sequence
  (ranges stop at 126 and resume at 128) because it is reserved for loopback.
- Loopback addresses (anything starting 127) are used for local network testing;
  pinging 127.0.0.1 tests whether your own NIC/networking stack works.
- ping is the most common troubleshooting tool in IT — it asks "are you awake?" and
  a live host responds.
- Every machine effectively has 16 million loopback addresses that all respond to
  itself (e.g. 127.15.15.8 also pings the local host), which Chuck calls wasteful.
- The fixes to IPv4 exhaustion — a "bandaid" (NAT) and then a bigger fix (IPv6) —
  are previewed as topics for coming episodes but not detailed here.
- This chart (classes, ranges, default masks) is worth memorizing with flashcards
  for subnetting and certification exams.

## Notable verbatim quotes

> Now, I'm not sure if you knew this, but there are roughly 4.3 billion possible IP
> addresses and we're out like we don't have anymore, which is a huge problem.

> The people who invented the internet were pretty stinking smart, but... around
> the time they invented it, which the Internet's birthday is officially January
> 1st, 1983, it seemed like the 4.3 billion supply of IP addresses was
> inexhaustible.

> They mismanaged the heck out of our IP address space.

> They're like, oh yeah, maybe a few computers here and there. No, your watch, your
> oven, your microwave, your toilet now.

> The governing body who hands out IP addresses, the Santa Claus of IP addresses,
> or the head Oprah, we call them IANA.

> If you do obey the rules and you use the default subnet mask, then you're
> classful, you're full of class. You're elegant, but you're no fun.

> Anything beginning with 127 are what's known as loopback addresses.

> Ping is what we use in IT to see if something is alive and awake.

> Our computer has 16 million virtual IP addresses ready to respond to itself. Why?

> In the coming episode, I'll show you the massive bandaid we put on our IP address
> situation... and then we put an even bigger bandaid on it to really solve the
> problem.

> Have you hacked the YouTube algorithm today?... Ethically, of course.

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
