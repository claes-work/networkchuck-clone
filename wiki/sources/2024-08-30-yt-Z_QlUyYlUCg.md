---
type: youtube-video
source_date: 2024-08-30
url: https://www.youtube.com/watch?v=Z_QlUyYlUCg
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, networking]
tags: [ipv6, mitm6, windows, network-attack, defense, slaac]
---

# IPv6 keeps getting hacked on Windows

## Summary

Chuck explains a critical Windows IPv6 vulnerability (a TCP/IP stack flaw allowing
unauthenticated, low-complexity, zero-click remote code execution) and uses it as the
hook to teach how IPv6 works and why it keeps producing security flaws. He frames the
core danger: IPv4 home networks sit behind NAT, which acts like a "bouncer" preventing
outside devices from reaching your internal devices directly, but IPv6 uses globally
routable addresses (GUA — Global Unicast Address) that can potentially be reached by
anyone on the internet, with no NAT barrier by default.

He walks through the attack mechanically: a hacker crafts a malicious IPv6 packet and
floods the target; the Windows TCP/IP stack de-encapsulates it layer by layer; at the
network layer the payload is used to trigger an **integer underflow** (subtracting
past zero wraps around to a huge or wrong value), which causes the OS to allocate a
buffer/box far too small for the payload. The payload then spills past the buffer — a
**buffer overflow** — into adjacent memory, letting the attacker overwrite memory and
redirect execution to their own code, taking over the system. He stresses it is
zero-click (no phishing, no download needed), remote, low-complexity, and possibly
**wormable** (self-replicating like WannaCry, which spread via an SMB flaw).

Detection: run `ipconfig` in Windows Terminal and look at your adapter — link-local
addresses start with `FE80` and are not routable; addresses starting with 2 or 3
(e.g. 2001, 3001) are globally routable GUAs. The site test-ipv6.com checks external
IPv6 connectivity, but he cautions to take it with a grain of salt. Defense: (1)
install the Microsoft patch — this was fixed in a Patch Tuesday security update; (2)
optionally disable IPv6 per-interface (Control Panel → Network and Sharing Center →
adapter properties → uncheck IPv6), noting Microsoft warns disabling it may break
things on Vista/Server 2008 and newer, so ask IT at work. He closes by noting IPv6 is
a repeat offender (ping of death via ICMPv6 router advertisement handling, IPv6 DoS,
a DHCPv6 RCE) because it is relatively new (only a standard since 2017), feature-rich
(neighbor discovery, SLAAC stateless address autoconfiguration, extension headers),
and less familiar to engineers, and because networks run dual-stack (IPv4 + IPv6
simultaneously), which adds attack surface. Mid-video sponsor segment for Dashlane
(password manager, dark-web breach scanning, built-in 2FA, passkeys).

## Key claims (dated — concept + defense)

- [2024-08-30] A critical Windows IPv6 flaw allows unauthenticated, zero-click remote
  code execution — the attacker only has to send specially crafted IPv6 packets;
  the user does nothing. (paraphrase)
- [2024-08-30] The flaw chains an **integer underflow** (arithmetic wrapping below zero)
  into a **buffer overflow**: the underflow tricks the OS into allocating a buffer far
  too small, so the payload overflows into adjacent memory and can overwrite it to
  redirect execution to attacker code. (paraphrase)
- [2024-08-30] IPv4 home networks are protected by NAT, which acts as a default
  security boundary/"bouncer" — outside devices cannot easily reach internal private
  addresses directly. IPv6 GUAs (Global Unicast Addresses) are publicly routable and
  may not sit behind that NAT barrier, so devices can potentially be reached directly.
  (paraphrase)
- [2024-08-30] IPv6 exists to solve IPv4 address exhaustion — IPv4 had only ~4.3
  billion addresses; IPv6 has ~340 undecillion, "handed out like candy." (paraphrase)
- [2024-08-30] Detection: `ipconfig` shows your adapter's IPv6 address. `FE80` prefix =
  link-local, not publicly routable; a leading 2 or 3 (e.g. 2001, 3001) = globally
  routable GUA reachable from the internet (with nuance). test-ipv6.com checks
  connectivity but take it with a grain of salt. (paraphrase)
- [2024-08-30] Defense #1: apply Microsoft's fix — the flaw was patched in a Patch
  Tuesday security update; update your system. (paraphrase)
- [2024-08-30] Defense #2: disable IPv6 per-interface via Control Panel → Network and
  Sharing Center → adapter properties → uncheck IPv6, then reboot. Microsoft warns
  disabling it on Vista/Server 2008+ may break things; ask IT at work. For a private
  home network you are probably fine to disable it. (paraphrase)
- [2024-08-30] The attack is possibly **wormable** (self-replicating): a compromised
  machine could scan and attack other machines on its network — the same spread
  mechanism as WannaCry (which exploited an SMB flaw). (paraphrase)
- [2024-08-30] IPv6 is a repeat source of vulnerabilities — ping of death (via how the
  Windows TCP/IP stack handled ICMPv6 router advertisement packets, enabling RCE), an
  IPv6 DoS, and a DHCPv6 RCE — because it is relatively new (only standardized ~2017),
  feature-rich (neighbor discovery, SLAAC, extension headers = more attack surface),
  and less familiar to engineers than IPv4. (paraphrase)
- [2024-08-30] Networks currently run dual-stack (both IPv4 and IPv6 in most cases),
  and the way the two interact introduces additional attack vectors. Common best
  practice has been to disable IPv6 when it is not being used on a private network.
  (paraphrase)

## Notable verbatim quotes

> "All hackers have to do is send a specially crafted IPv6 packet to your system and
> they'll use an integer underflow to trigger a buffer overflow. And before you know
> it, you're drowning."

> "Now get your coffee ready. We're going to talk about IPv6, not because it's boring,
> but you just need coffee to learn. It is required."

> "IPv6, it was supposed to save the internet and it did."

> "It's like having security or a bouncer at the door. But with IPv6, your toilet might
> have this IPv6 global unicast address and I could connect directly to it and hack
> your toilet."

> "This packet is specifically designed and tailored to attack your system and exploit
> this flaw, and they'll just start sending them, a lot of them. Why not?"

> "They don't have to click on a phishing email. They don't have to download free RAM
> from the internet. They're just sitting there receiving IPv6 packets as they should."

> "So we used an integer underflow to cause a buffer overflow."

> "The more features we can use, the more features hackers can hack."

> "Rebooting always helps everything."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
