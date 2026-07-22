---
type: hub
domain: networking
created: 2026-07-14
updated: 2026-07-22
---

# Networking — hub

NetworkChuck's home turf: CCNA, routing and switching, subnetting, protocols, and network-engineering fundamentals — the "free CCNA" series and beyond.

## Key ideas & topics

- **CCNA / routing-and-switching fundamentals.** Networking is Chuck's core identity — he describes network engineers as people who "live in the CLI" (2017-11-06, [[../../sources/2017-11-06-yt-9Vs56S95Mrs]]). His running-config protocols in his own lab are EIGRP and OSPF (2018-07-16, [[../../sources/2018-07-16-yt-G5HucqXioBY]]). Most CCNA study/career framing lives in [[../certifications-career/certifications-career]]; this hub collects the hands-on networking technique.

- **3 Cisco CLI hacks.** Three Cisco IOS command-line time-savers he uses daily (2017-11-06, [[../../sources/2017-11-06-yt-9Vs56S95Mrs]]): (1) the `include` / `exclude` pipe switches to filter `show` output (e.g. `show run | include SNMP`, or `show processes CPU | exclude 0.00` to hide idle processes); (2) the `section` switch to pull a whole config block (`show run | section ospf`), which he calls a "game-changer"; (3) the `do` command to run `show`/exec commands without leaving configuration mode — "every engineer I've ever talked to uses this all the time."

- **Lab tooling: Packet Tracer vs GNS3.** His selection framework (2017-12-16, [[../../sources/2017-12-16-yt-MN0KzfzlRio]]): beginners should start with **Packet Tracer** — Cisco's own *simulator* (not real IOS), free via a NetAcad account, set up in five minutes, and enough for CCENT/CCNA — because "the most important part of studying is labbing" and you want to remove barriers. **GNS3** is the open-source *emulator* running real Cisco IOS (and multi-vendor appliances, Docker, Python-friendly), which he uses for his own higher-level (CCNP/voice) study, but its setup is a barrier for newcomers. He later shows GNS3 can run in the Azure cloud for free (2019-03-02, [[../../sources/2019-03-02-yt-FfJXcoqTvrs]]).

- **DMVPN + moving a home network to a data center.** To keep a full Cisco lab while travelling the world, Chuck colocated his entire home network (two Dell servers, routers, switches) in a Dallas data center and uses **DMVPN** so a small Cisco 881 branch router builds a persistent tunnel back to the hub from anywhere — carrying his Cisco phones (registered to Call Manager in Dallas), UniFi Wi-Fi, and shared routes (2018-07-16, [[../../sources/2018-07-16-yt-G5HucqXioBY]]). He frames DMVPN as branch/site remote-access tech: lightly touched at CCNA, configured at CCNP, covered deeply at CCIE. See [[../homelab-selfhosting/homelab-selfhosting]].

- **MPLS vs SD-WAN — "Is MPLS dead?" panel.** A three-person panel Chuck *hosts* with guest CCIEs Keith Barker and Jason Gooley (2019-05-10, [[../../sources/2019-05-10-yt-cDxngzbBbhI]]). **The technical positions are the guests', not Chuck's** — Jason Gooley (context, not persona) frames MPLS as a segmentation mechanism that is *not* dead: you can run SD-WAN on top of MPLS or MPLS under SD-WAN, and mix commodity internet links to offset MPLS cost. Chuck's own contribution is limited to the host role: the provocative "MPLS is dead" hook (which he throws out "to stir the pot"), entry-level questions on behalf of CCNA students, and his view that MPLS is something "you gotta know" if you're on the CCNA/CCNP/CCIE track. He asserts no independent position on whether MPLS is dying.

- **Intent-based networking / SDN / DNA Center.** Chuck's own explanation of the automation stack (2018-10-30, [[../../sources/2018-10-30-yt-eAdrnTOcPOg]]): **SDN** lets you script a config once and push it to many devices at once (e.g. an ACL to 20 routers); **intent-based networking (IBN)** goes further — instead of configuring each box, you tell a controller (his example: **Cisco DNA Center**) your *business intent* ("let these developers talk to these developer servers") and it translates that to policy across all devices. He highlights DNA Center's **"assurance"** piece, which continuously verifies the network is behaving as intended and can fix or flag issues before they become outages. (The phased "learn to code" roadmap in that same video is guest Hank Preston's — see [[../cloud-devops/cloud-devops]].)

- **Automation is changing networking (dated position, evolving).** As of 2017 Chuck already noted the network engineer's day-to-day is "starting to change a little bit" toward Python/automation (2017-11-06, [[../../sources/2017-11-06-yt-9Vs56S95Mrs]]). By late 2018 he made network automation and programmability his stated main focus and "the thing I'm most stoked about," partnering with Cisco for tooling content (2018-10-25, [[../../sources/2018-10-25-yt-O8HDIRtMvwI]]). He frames automation positively — as erasing the "sucky parts" of the job (3 a.m. outage calls, lone-engineer overload) and freeing time to experiment — while insisting networking fundamentals (CCNA/CCNP/CCIE) stay essential (2018-10-30, [[../../sources/2018-10-30-yt-eAdrnTOcPOg]]). ⚠️ This is a 2017–2018 view captured early in his automation journey; treat it as period-dated and check for later evolution before presenting it as his current position. Hands-on automation experiments (monitoring a Cisco router with Arduino/Raspberry Pi/Python via DevNet, 2018-12-16, [[../../sources/2018-12-16-yt-7UkkrNoZUwU]]) sit at the [[../cloud-devops/cloud-devops]] boundary.

## Source pages

- [[../../sources/2017-11-06-yt-9Vs56S95Mrs]] — 3 Cisco CLI (Command-line) Hacks (CCNA) (2017-11-06)
- [[../../sources/2017-12-16-yt-MN0KzfzlRio]] — CCNA Labs: Packet Tracer or GNS3? (2017-12-16)
- [[../../sources/2018-04-17-yt-lTlTjeCjXYM]] — Hack a Cisco Switch with a Raspberry Pi (2018-04-17)
- [[../../sources/2018-07-16-yt-G5HucqXioBY]] — Moving my HOME NETWORK to a DATA CENTER w/ DMVPN (2018-07-16)
- [[../../sources/2018-10-25-yt-O8HDIRtMvwI]] — What's next for NetworkChuck? (automation pivot) (2018-10-25)
- [[../../sources/2018-10-30-yt-eAdrnTOcPOg]] — How to Start Coding as a Network Engineer / Intent-Based Networking (2018-10-30)
- [[../../sources/2018-12-16-yt-7UkkrNoZUwU]] — Arduino + Raspberry Pi + Python to Monitor a Cisco Router (DevNet) (2018-12-16)
- [[../../sources/2019-03-02-yt-FfJXcoqTvrs]] — CCNA Lab in the Azure Cloud for FREE! (GNS3) (2019-03-02)
- [[../../sources/2019-05-10-yt-cDxngzbBbhI]] — Is MPLS DEAD?!? panel w/ Keith Barker + Jason Gooley (2019-05-10)
