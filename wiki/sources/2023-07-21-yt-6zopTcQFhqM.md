---
type: youtube-video
source_date: 2023-07-21
url: https://www.youtube.com/watch?v=6zopTcQFhqM
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [networking, certifications-career]
tags: [subnetting, reverse-subnetting, vlsm, ccna]
---

# Subnetting…..but in reverse

## Summary

Part of Chuck's CCNA subnetting series (sponsored by Boson Software, which
provided the exam-style question and the NetSim lab environment). Where earlier
episodes taught forward subnetting (given a requirement, design the mask), this
episode covers **reverse subnetting**: a host already has an IP, subnet mask, and
default gateway configured, and you must derive the network address, broadcast
address, and usable range from that existing configuration. Chuck frames it as a
real-world troubleshooting scenario: a host ("Beatrice") on IP `172.17.29.x` with
mask `255.255.240.0` can't ping anything. By reverse-subnetting her configuration,
you discover the actual cause — her default gateway/router lives in a different
network than she does, so she has no reachable gateway.

The method reuses forward-subnetting skills but skips the first two steps because
the mask is already given: convert the mask to binary, count the network bits to
get the prefix, find the increment from the last network bit, and build the network
ranges to locate which network the host belongs to. Chuck closes by inviting viewers
to reverse-subnet their own device's IP config (from `ipconfig`/`ifconfig` or phone
settings) and teases the next episode: subnetting a subnet (VLSM).

## Key claims (dated — the method)

All dated 2023-07-21 (paraphrase unless quoted):

- **Reverse subnetting = working backward from an existing config.** When a host's
  IP address, subnet mask, and default gateway are already set, you derive the
  network address, broadcast address, and network range from them — the subnetting
  has already been done, and you have to figure out who did it and why.
- **Why it matters (troubleshooting).** A common real-world ticket: a host has no
  network access and can't ping anything. Reverse-subnetting the configuration lets
  you diagnose the cause.
- **Half the work is already done.** In forward subnetting you compute the mask;
  here the mask is given, so you skip steps one and two and jump straight to step
  three (find the increment).
- **Step: convert the mask to binary.** Example mask `255.255.240.0` converts to
  binary; the computer "speaks" binary.
- **Step: count network bits for the prefix.** The prefix in CIDR notation is the
  count of contiguous ones (network bits) in the binary mask. For `255.255.240.0`
  that is 20 ones → `/20`.
- **Step: find the increment.** The increment comes from the last (rightmost)
  network bit in the mask. For `/20` the last network bit sits in the third octet
  and represents 16, so the increment is 16.
- **Step: build the ranges, incrementing in the correct octet.** With a `/20`,
  incrementing happens in the **third** octet, not the fourth — unlike the class C
  addresses beginners are used to. Networks step: `172.17.0.0`, `172.17.16.0`,
  `172.17.32.0`, `172.17.48.0`, `172.17.64.0`, … (increment of 16 in the third octet).
- **Shortcut.** You don't have to write out the entire range for each network — just
  list the network addresses and keep incrementing until you reach the host's network.
- **Locating the host.** Beatrice's IP `172.17.29.x` falls inside the `172.17.16.0`
  network (16–31 in the third octet), not the first network.
- **`.255` or `.0` can be valid host addresses.** When the network is large enough,
  an address ending in `255` (or `0`) is not automatically the broadcast/network
  address — because incrementing happens in the third octet here, the broadcast for
  Beatrice's network is the last address in the range, not simply the `.255` in the
  fourth octet. Don't discount `.255` / `.0` addresses on sight.
- **The diagnosis.** Beatrice sits in the `172.17.16.0` network; her default gateway
  `172.17.0.1` sits in the `172.17.0.0` network (where Bernard and the router are).
  Because her router isn't in her own network, she can't reach the gateway — or the
  internet — even though her IP is valid.
- **Subnetting is a skill that needs practice.** Weird cases will keep surprising you
  even once you feel competent; that's expected.

## Notable verbatim quotes

> "How to reverse subnet or backwards subnet."

> "Most of what we were doing was figuring out the subnet mask we already had. That
> half the work is already done for us. So we can remove steps one and two and jump
> right into step three."

> "We first have to convert our subnet mask from decimal to binary to the language
> that our computer loves."

> "All we have to do is count the network bits, which are the contiguous ones."

> "The increment is the last network bit in our subnet mask."

> "You're used to class C addresses, right? So you're used to incrementing in the
> fourth octet. No, we're gonna do it here in the third octet."

> "Just know if you see 2 55 or even zero as the IP address, those can be valid.
> Don't immediately discount those. If the network's big enough, it can contain that."

> "No wonder she can't get to anything, not even the internet because her default
> gateway isn't even in her network. She's lost."

> "Subnetting again, is a skill. You have to keep practicing."

> "Can you subnet a subnet? A subnet? A subnet? That's what we're doing in the next
> episode."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
