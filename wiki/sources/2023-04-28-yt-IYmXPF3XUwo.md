---
type: youtube-video
source_date: 2023-04-28
url: https://www.youtube.com/watch?v=IYmXPF3XUwo
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [networking, cybersecurity, cloud-devops]
tags: [ztna, zero-trust, vpn, sase, network-security, 2023]
---

# the END of VPNs?!

## Summary

A networking/security explainer (2023 view) in which Chuck argues that traditional VPNs are the "old way" of remote access and pitches Zero Trust Network Access (ZTNA) as the better model. The video is framed around a sponsored walkthrough of Twingate, a zero-trust remote-access solution, but the durable content is Chuck's conceptual case for identity-based, least-privilege remote access over the classic VPN.

His core argument: a VPN typically grants a connected user access to the entire network, which is both an over-broad security posture and inefficient. He contrasts this with zero trust — "I zero trust them" — where a user gets access only to the specific resources they need, on the specific ports/protocols they need, nothing else. He frames the motivating problem around his own team: giving two "knucklehead editors" VPN access exposes servers they should never touch, and if their machine already has malware it can spread across the whole network.

Chuck then "pops the hood" on how a modern ZTNA proxy actually works, using Twingate's architecture as the concrete example: a controller (cloud-managed policy/identity plane), a connector (a Docker container deployed inside your network behind the firewall, acting as a proxy), a client (the endpoint app), and a relay (a matchmaker that facilitates NAT traversal, functioning as a STUN server). He explains NAT/network address translation, how the relay brokers a direct peer-to-peer end-to-end TLS tunnel between client and connector, and why this avoids firewall config, port forwarding, and problems with CGNAT/dynamic IPs.

He highlights several technical advantages of the ZTNA/proxy model over VPN: it is a super-secure private proxy (not a VPN); it uses the QUIC transport protocol (built on UDP, multiplexed, faster connection setup, and client-side roaming so a session survives a WiFi-to-5G switch); split tunneling by default (only resource-bound traffic crosses the tunnel, unlike VPN backhaul where everything routes through the VPN device); device security posture checks (minimum OS, screen lock, biometrics, disk encryption, firewall, MFA, and integration with endpoint protection like CrowdStrike/Intune/SentinelOne); DNS-based routing via the connector acting as a DNS proxy; alias resolution when you have no local DNS server; headless clients/services for CI/CD and Terraform automation; and identity-provider sync (Google Workspace, Okta, Azure AD).

Note: this is a 2023 snapshot and a sponsored video (Twingate). The transferable knowledge is the ZTNA-vs-VPN framing; Twingate specifics are illustrative.

## Key claims (dated — ZTNA vs VPN + his take)

All dated 2023-04-28 (paraphrase unless quoted):

- Chuck's headline take: VPNs are "the old way of doing things" and he tells viewers it is "time to ditch your VPN"; he positions ZTNA as the better replacement. (Presented as opinion/rhetoric, 2023.)
- His central security objection to VPNs: a VPN gives a user access to the entire network, including servers they should not touch; if a user's machine has malware, it can spread across the whole network.
- Zero trust means access is denied by default — you must explicitly define what each user is allowed to reach; a user gets only the specific resources, machines, and ports they need.
- Access can be scoped granularly: per-machine, per-port, per-protocol (e.g. TCP 5000 only, block UDP and ICMP), and conditioned on device attributes (OS type, antivirus/firewall present, MFA).
- ZTNA (via the Twingate example) is not a VPN — it is a "super secure private proxy"; the connector inside the network operates as a proxy that terminates, validates, manipulates, and forwards traffic.
- The architecture has four parts: controller (cloud, policy/identity), connector (Docker container inside your network, does most of the work), client (endpoint app), and relay (matchmaker/STUN server hosted by the vendor).
- Setup requires no firewall config and no port forwarding, and works even behind CGNAT or dynamic/problematic ISP setups, because the relay brokers NAT traversal to build a direct peer-to-peer end-to-end TLS tunnel.
- Security relies heavily on token-based authentication at every interaction ("more tokens than Chuck E. Cheese") plus pinned certificates in the TLS tunnel, which makes man-in-the-middle attacks near impossible.
- QUIC (a newer UDP-based transport protocol) makes connections fast via multiplexing and one-round-trip setup, and enables client-side roaming so a session survives switching networks (e.g. home WiFi to 5G) without disconnect/reconnect.
- Split tunneling is on by default: only traffic destined for the defined resources crosses the secure tunnel; everything else (Facebook, YouTube) exits via the normal internet gateway. Chuck notes VPNs can be configured for split tunnel but "it's not easy," whereas here it is built in.
- Advanced ZTNA capabilities he cites: device-security policies (minimum OS, screen lock, biometrics, disk encryption, firewall, block an entire OS), MFA enforcement, endpoint-protection integration (CrowdStrike, Intune, SentinelOne), DNS-based routing through the connector acting as a DNS proxy, aliases for networks without a local DNS server, wildcard resources (e.g. a /24 or wildcard DNS) for whole-network access, headless clients/"services" for CI/CD and Terraform automation, and identity-provider sync (Google Workspace, Okta, Azure AD) plus secure DNS over HTTPS.
- Deployment is fast and low-friction in his telling — the connector deploys in "about five minutes" via a Docker run command on any Linux box (NAS, old laptop, Raspberry Pi).
- Sponsorship disclosed: the video is sponsored by Twingate, and the free tier (up to five users) covers his business.

## Notable verbatim quotes

> "Throw your VPN in the trash, you don't need it anymore. I found something better."

> "VPN is not secure enough. Like when I give my two knucklehead editors VP[N] access, they get access to everything servers they shouldn't touch and they have a nasty habit of downloading free [stuff]. And if they already have malware ... they can blast it out to my entire network."

> "What I need is a solution that gives them access to only stuff they need. Nothing else. This is a little technique called zero trust because I zero trust them."

> "VPN is kind of the ... old way of doing things and old as [lame]."

> "By default, you can't access anything. So you have to specifically explicitly define what you are allowed to access in your network. I love that. Zero trust."

> "It's not a [VPN], it's not. Let me explain. Now the goal for Twin Gate is this right here, a secure end-to-end TLS tunnel. It's peer-to-peer between the client ... and the connector inside your network."

> "This is actually operating as a stun server. Stun does this kind of stuff and it facilitates those connections."

> "This is not a VPN. I mentioned it before. So you're probably like, well Chuck, if it's not VPN, what is it? It's a proxy actually. It's a super secure private proxy."

> "Quick [QUIC] is a new protocol ... It's a transport layer protocol ... It's built on top of UDP and it's designed to be faster and more efficient than TCP."

> "With traditional VPN when you connect, it normally means every bit of traffic you're generating ... is gonna go through that VPN device ... But with Twin Gate it does a thing called split tunnel by default."

> "It's time to ditch your VPN. Dang right."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: Clear, structured explainer of ZTNA/zero-trust vs VPN (NAT traversal, STUN, split tunnel, QUIC, device posture) — strong networking/cybersecurity topic material and a dated 2023 opinion ("VPNs are the old way / ditch your VPN"). -->
