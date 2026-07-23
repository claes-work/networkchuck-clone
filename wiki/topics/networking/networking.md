---
type: hub
domain: networking
created: 2026-07-14
updated: 2026-07-23
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

- **DNS — how name resolution works (canonical explainer).** Chuck's from-scratch walkthrough of DNS as "the phonebook of the internet" (2024-08-28, [[../../sources/2024-08-28-yt-NiQTs9DbtW4]]): what happens when you type a domain — the resolver/recursion chain (stub resolver → recursive resolver → root → TLD → authoritative), caching at each hop, and the common record types (A, AAAA, CNAME, MX, NS, TXT). A core-fundamentals reference page for the beginner-networking track.

- **WiFi 6 (802.11ax) — "is it a switch?" (Clear to Send collab).** Chuck brings on Rowell Dionicio and François Vergès of the **Clear to Send** WiFi podcast to settle whether WiFi 6 "is a switch" — a provocation from an earlier Chuck video that drew backlash from the WiFi community (2019-09-28, [[../../sources/2019-09-28-yt-rcb27jWOwD0]]). **The 802.11ax mechanics — OFDMA, MU-MIMO, Target Wake Time, BSS Coloring, 1024-QAM, 8 spatial streams — are the guests' expert content, not persona material.** Chuck's role is the half-joking provocateur ("it *is* a switch") and the beginner questions; the guests explain why it is not.

- **AI networking — InfiniBand / RoCE fabrics for GPU clusters.** Chuck steps into the AI-datacenter era: how the network that stitches together thousands of GPUs differs from a normal enterprise LAN (2024-02-09, [[../../sources/2024-02-09-yt-fb69FyW2KLk]]). Covers **InfiniBand** vs **RoCE** (RDMA over Converged Ethernet), why GPU training traffic demands lossless, ultra-low-latency, high-bandwidth back-end fabrics, and how this reshapes network-engineering skills. Bridges networking into AI infrastructure — cross-links [[../ai-tools/ai-tools]].

- **ZTNA vs the traditional VPN (Twingate — "not a VPN").** Chuck demos **Twingate** as Zero Trust Network Access for remote access, explicitly positioning it as *not* a VPN — identity-based, least-privilege access to specific resources instead of a full network tunnel (2024-12-20, [[../../sources/2024-12-20-yt-1lZ3FQSv-wI]]). This advances his recurring "the traditional VPN is ending" take toward a ZTNA replacement model. See also DMVPN branch/remote-access framing above; this is the modern zero-trust counterpoint. Cross-links [[../homelab-selfhosting/homelab-selfhosting]].

- **The future of network engineering (career reflection).** Chuck reflects on where the network-engineer role is heading and how to stay relevant: adapt to AI and automation rather than fear them (2025-06-13, [[../../sources/2025-06-13-yt-4hkJX7LBdXc]]). A 2025 update to his long-running automation-is-changing-networking thread (below) — the fundamentals still matter, but the differentiator is layering AI/automation on top. Career framing also relevant to [[../certifications-career/certifications-career]].

- **Cisco Live 2025 — pivot back toward networking.** Chuck at Cisco Live 2025, signalling a return of focus toward networking content after years of broader IT/AI coverage (2025-06-21, [[../../sources/2025-06-21-yt-tTQ4vfCdMYw]]) — reconnecting with the Cisco networking community and its latest announcements.

- **Automation is changing networking (dated position, evolving).** As of 2017 Chuck already noted the network engineer's day-to-day is "starting to change a little bit" toward Python/automation (2017-11-06, [[../../sources/2017-11-06-yt-9Vs56S95Mrs]]). By late 2018 he made network automation and programmability his stated main focus and "the thing I'm most stoked about," partnering with Cisco for tooling content (2018-10-25, [[../../sources/2018-10-25-yt-O8HDIRtMvwI]]). He frames automation positively — as erasing the "sucky parts" of the job (3 a.m. outage calls, lone-engineer overload) and freeing time to experiment — while insisting networking fundamentals (CCNA/CCNP/CCIE) stay essential (2018-10-30, [[../../sources/2018-10-30-yt-eAdrnTOcPOg]]). ⚠️ This is a 2017–2018 view captured early in his automation journey; treat it as period-dated and check for later evolution before presenting it as his current position. Hands-on automation experiments (monitoring a Cisco router with Arduino/Raspberry Pi/Python via DevNet, 2018-12-16, [[../../sources/2018-12-16-yt-7UkkrNoZUwU]]) sit at the [[../cloud-devops/cloud-devops]] boundary.

### Enterprise / real-world networking field trips

Chuck's on-location tours of production infrastructure — where textbook networking meets the physical/broadcast/carrier-grade world.

- **Equinix Dallas data center tour — the physical internet.** Chuck walks a real Equinix Dallas data center to show where "the internet" physically lives: cages, cross-connects, and the Meet-Me Room where carriers and networks interconnect (2025-09-08, [[../../sources/2025-09-08-yt-v477fvbj3rk]]). Grounds abstract peering/interconnection concepts in racks and fiber. Cross-links [[../homelab-selfhosting/homelab-selfhosting]] (his own colo history) and [[../certifications-career/certifications-career]].

- **FIFA World Cup broadcast network — SMPTE ST 2110 at scale.** Chuck goes behind the scenes of the FIFA World Cup broadcast network to see how live global sports video rides IP: **SMPTE ST 2110** (uncompressed video/audio/data as separate flows over IP), and the roles of **HBS** (Host Broadcast Services) and the **IBC** (International Broadcast Centre) (2026-07-19, [[../../sources/2026-07-19-yt-LhnH0juUaGw]]). Shows enterprise/broadcast networking as a demanding, latency- and precision-critical discipline beyond the standard enterprise LAN.

### AIOps / networking-meets-AI

The thread where AI stops being a workload the network carries and starts running the network itself — a 2025 extension of the "automation is changing networking" line above.

- **AIOps: letting AI run a real network (Marvis).** Chuck hands network operations to AI, using **Juniper Mist Marvis** as an AI-driven network assistant/operations layer to run a live network — troubleshooting and driving actions via natural language rather than manual CLI (2025-07-29, [[../../sources/2025-07-29-yt-ySLe49h81yg]]). A concrete step past "automation frees the engineer" toward AI as an active operator.

- **AI running the data center (Juniper/Apstra).** Chuck explores AI operating the data-center fabric with **Juniper Apstra** (intent-based data-center automation), extending intent-based networking (see DNA Center above) into an AI-run data center (2025-09-19, [[../../sources/2025-09-19-yt-Zx4SL2h1uDg]]). Pairs with the AI-datacenter fabric page above and cross-links [[../ai-tools/ai-tools]].

- **Thunderbolt-5 RDMA Mac Studio AI cluster ("Ethernet is dead").** Chuck builds an AI inference cluster of Mac Studios stitched together over **Thunderbolt 5 with RDMA**, using the provocative "Ethernet is dead" framing as deliberate hyperbole — the real point is that TB5 can carry inference traffic between nodes as a low-latency interconnect (2025-12-20, [[../../sources/2025-12-20-yt-bFgTxr5yst0]]). Companion to the InfiniBand/RoCE GPU-fabric page above; both are about the specialized fabrics AI compute demands. Cross-links [[../ai-tools/ai-tools]].

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
- [[../../sources/2019-09-28-yt-rcb27jWOwD0]] — How WiFi 6 (REALLY) works — "is it a switch?" feat. Clear to Send (2019-09-28)
- [[../../sources/2024-02-09-yt-fb69FyW2KLk]] — AI networking: InfiniBand / RoCE fabrics for GPU clusters (2024-02-09)
- [[../../sources/2024-08-28-yt-NiQTs9DbtW4]] — DNS explainer: name resolution, record types, recursion (2024-08-28)
- [[../../sources/2024-12-20-yt-1lZ3FQSv-wI]] — Twingate ZTNA remote access ("not a VPN") (2024-12-20)
- [[../../sources/2025-06-13-yt-4hkJX7LBdXc]] — The future of network engineering (adapt to AI/automation) (2025-06-13)
- [[../../sources/2025-06-21-yt-tTQ4vfCdMYw]] — Cisco Live 2025 (pivot back toward networking) (2025-06-21)
- [[../../sources/2025-07-29-yt-ySLe49h81yg]] — AIOps: letting AI run a real network (Marvis) (2025-07-29)
- [[../../sources/2025-09-08-yt-v477fvbj3rk]] — Equinix Dallas data center tour (physical internet, cross-connects) (2025-09-08)
- [[../../sources/2025-09-19-yt-Zx4SL2h1uDg]] — AI running the data center (Juniper/Apstra) (2025-09-19)
- [[../../sources/2025-12-20-yt-bFgTxr5yst0]] — Thunderbolt-5 RDMA Mac Studio AI cluster ("Ethernet is dead") (2025-12-20)
- [[../../sources/2026-07-19-yt-LhnH0juUaGw]] — FIFA World Cup broadcast network (SMPTE ST 2110, HBS/IBC) (2026-07-19)
