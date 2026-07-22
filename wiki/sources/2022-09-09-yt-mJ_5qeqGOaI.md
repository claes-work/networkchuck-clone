---
type: youtube-video
source_date: 2022-09-09
url: https://www.youtube.com/watch?v=mJ_5qeqGOaI
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [networking, certifications-career]
tags: [subnetting, home-network, vlsm, you-suck-at-subnetting, ep-6]
---

# let's subnet your home network // You SUCK at subnetting // EP 6

## Summary

Episode 6 of the "You SUCK at Subnetting" series applies the subnetting method
from earlier episodes to a practical scenario: taking a single home network and
breaking it into four smaller, more secure networks — wireless, IOT, DMZ, and
user. Chuck argues that keeping every device on one flat network is insecure, and
that subnetting (rather than simply bolting on more networks) is the "right" way
to segment.

The teaching walks through a repeatable four-step method on a Class C network
(192.168.1.0). (1) Convert the subnet mask to binary; the ones are network bits,
the zeros are host bits. (2) Determine how many host bits to "steal"/"hack" and
flip into network bits — using a powers-of-two chart (introduced here as the
mnemonic character "Nora Two" / "no-four-two," the doubling companion to
"Nosferatu," the decimal-to-binary chart from earlier episodes). Four networks
requires 2 bits; the example of 17 networks requires 5 bits (since 16 is not
enough, jump to 32). (3) Convert the new mask back to decimal/CIDR — flipping two
host bits yields 255.255.255.192, a /26. (4) Find the increment (the value of the
last network bit, here 64) and use it to lay out each subnet's range, remembering
that the network/zero address counts, so the first range is .0–.63, the next
.64–.127, and so on. Chuck closes with the usable-host formula (2^host_bits − 2 =
62 usable in a /26) and homework: redo the same network as five subnets and post
the mask (decimal + CIDR) and ranges in the comments. Sponsored by ITProTV
(code "networkchuck" for 30% off), with coffee plug (networkchuck.coffee).

## Key claims (dated — concepts)

All dated 2022-09-09 (paraphrase unless quoted):

- Keeping all your devices on the same/flat network is insecure; you should
  segment it into separate networks such as wireless, IOT, DMZ, and user.
- Subnetting is the preferred way to break up a network into smaller networks,
  versus "lazily" just adding more separate networks.
- The subnet mask, converted to binary, tells you everything about a network:
  the ones are network bits (describe the network) and the zeros are host bits
  (how many hosts fit on the network).
- To create more networks, you must steal ("hack"/"flip") host bits and convert
  them into network bits.
- Use a powers-of-two chart ("Nora Two" — each value double the corresponding
  decimal-to-binary "Nosferatu" chart value) to find how many bits you need:
  find the first chart value ≥ the required number of networks, and count the
  bits to reach it.
- Four networks needs 2 borrowed bits; 17 networks needs 5 bits (16 is
  insufficient, so jump to 32).
- Flipping the first two host bits of a Class C /24 mask yields
  255.255.255.192, which in CIDR notation is /26 (counting network bits:
  8+8+8+2 = 26).
- The increment equals the value of the last (lowest-order) network bit; for a
  /26 that increment is 64, which sets the size and ranges of each resulting
  subnet.
- Subnet ranges must include the zero/network address, so the first /26 range is
  .0–.63, the second .64–.127, etc. — four subnets across the original /24.
- Usable hosts per subnet = 2^(host bits) − 2 (subtracting the network and
  broadcast addresses); a /26 has 6 host bits → 2^6 = 64 → 62 usable addresses.
- These four steps work on any network requirement; Class A and Class B addresses
  follow the same method even though they may "feel weird" compared to the Class C
  example.

## Notable verbatim quotes

> "You can't keep all your stuff on the same network."

> "We're going to use the power of subnetting to break up your current network
> into four smaller networks, wireless IOT, DMZ, and user."

> "When you need more networks, you need more bits. And the only way you can get
> more bits is by hacking them or stealing them from the host bits."

> "The increment is simply the last network bit we have."

> "This might trip you up a little bit 63, not 64, because remember we're
> including the zero, the zero is still an address."

> "If we account for the subnet address and the broadcast address, subtracting
> two, we get 62 usable addresses in our network."

> "No matter what type of network you encounter, these four steps will work."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: You SUCK at Subnetting EP6 — home network -->
