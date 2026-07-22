---
type: youtube-video
source_date: 2022-07-19
url: https://www.youtube.com/watch?v=oZGZRtaGyG8
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [networking, certifications-career]
tags: [subnet-mask, subnetting, ccna, networking-basics]
---

# What is a Subnet Mask??? (you NEED to know it!!)

## Summary

An episode in NetworkChuck's beginner subnetting series (part of / adjacent to
"You SUCK at Subnetting"). It builds on a prior episode where he taught converting
an IP address to and from binary, and now explains what a subnet mask actually *does*
under the hood — why a `255` in an octet "freezes" the corresponding octet of the IP
address.

Chuck's teaching method: a running toilet-with-an-IP-address gag frames the lesson,
and he leans on a "handy dandy chart" of the eight bit values (128, 64, 32, 16, 8, 4,
2, 1) plus a subtraction technique to convert decimal octets to binary. He converts the
mask `255.255.255.0` to binary, showing the first three octets are all ones and the last
is all zeros. The core insight: **ones in the mask are network bits** (the frozen part
that tells you which network you're on) and **zeros are host bits** (used to create/
assign IP addresses to hosts). He then derives the host-count formula, demonstrates that
"subnetting" is simply changing the mask to steal a network bit and turn it into a host
bit (or vice versa), converts the changed mask back to decimal (`255.255.254.0`), and
notes that mask bits are always contiguous. Range/subnet-ID topics are deferred to the
next episode. Sponsored by HCL BigFix (endpoint discovery/management/remediation).

## Key claims (concepts)

- [2022-07-19] Every IP address has a subnet mask; the mask's job is to tell you how big
  the network is and how many IP addresses it holds.
- [2022-07-19] Hack from the prior episode: a `255` in a subnet-mask octet means the
  corresponding octet of the IP address is "frozen" — it won't change. This episode
  explains *why*.
- [2022-07-19] Converting a decimal octet to binary works by subtraction against the bit
  chart (128, 64, 32, 16, 8, 4, 2, 1): if a bit value can be subtracted from the
  remaining amount, that bit is on. Worked example: 255 − 128 = 127, − 64 = 63, − 32 =
  31, and so on until every bit is on and the remainder reaches 0.
- [2022-07-19] An octet of `255` is all eight bits on (128+64+32+16+8+4+2+1 = 255); an
  octet of `0` is all bits off (zero in binary is still zero).
- [2022-07-19] In the subnet mask, the **ones are the network bits** — the part of the
  IP address that won't change and tells you which network you're on.
- [2022-07-19] In the subnet mask, the **zeros are the host bits** — each can be used to
  build an IP address in that network and be assigned to a host.
- [2022-07-19] Host-count formula: number of possible hosts = 2 raised to the power of
  the number of zero (host) bits. For `255.255.255.0` that's 2^8 = 256 possible addresses.
- [2022-07-19] You must subtract 2 (for the subnet/network address and the broadcast
  address — the first and last IPs) to get usable addresses. Official formula: 2^(number
  of zeros) − 2. So `255.255.255.0` yields 256 − 2 = 254 usable IPs.
- [2022-07-19] To get more hosts you need more zeros (host bits), which you get by
  stealing/borrowing a bit from the network side. Turning one network bit into a host
  bit gives 2^9 = 512 addresses, 510 usable.
- [2022-07-19] That act — changing the subnet mask to suit your needs — *is* subnetting.
  "All subnetting is, is changing the subnet mask to suit our needs."
- [2022-07-19] Borrowing that bit changes the mask's decimal value: the third octet
  becomes seven bits on = 254, so the mask becomes `255.255.254.0`.
- [2022-07-19] Subnet-mask bits are **contiguous**: a solid row of ones followed by a
  solid row of zeros — you never get an interleaved pattern like `1110`.

## Notable verbatim quotes

> The subnet mask. This is how we create the networks of the world. This is where the
> magic of subnetting actually happens.

> If we see a 255 in the subnet mask, we know that the corresponding octet or the
> corresponding number in our IP address is frozen. Just it's done. It can't move. It
> won't change.

> These ones and zeros in our subnet mask, they're speaking to us, they're telling us
> something. They're whispering things about our network. Dark mysteries.

> The ones tell us... which part of the IP address are the network bits.

> The zeros they tell us which parts of the IP address are host bits.

> It's gonna be two to the power of zeros. How many zeros there are?

> We stole a bit from the network side, giving us more host. That's subnetting. You just
> subnetting, because all really subnetting is, is changing the subnet mask to suit our
> needs.

> The numbers are contiguous... It'll always be a row of ones. It'll always be a row of
> zeros.

> Have you hacked the YouTube algorithm today?

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
