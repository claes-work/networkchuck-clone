---
type: youtube-video
source_date: 2021-11-02
url: https://www.youtube.com/watch?v=XIoHFklOcVQ
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [networking, cybersecurity, cloud-devops]
tags: [nvidia, dpu, smartnic, bluefield, ai-security, networking]
---

# Nvidia does cybersecurity?!?.....and networking?

## Summary

Chuck Keith interviews Kevin Deierling, SVP of Networking at Nvidia, about why a
company famous for gaming GPUs is now a major force in networking and cybersecurity.
Nvidia entered networking via its acquisition of Mellanox (Deierling joined through it),
and is now positioned as a leading provider of high-performance networking at 25 Gig and
above, including InfiniBand for HPC/AI. The core thesis: the data center is the new unit
of computing, and it takes three processors working together — the CPU (general
compute), the GPU (AI/machine-learning workloads), and the new DPU (data processing
unit) for data-intensive infrastructure tasks like packet switching, encryption,
compression, and software-defined networking/storage/security.

The conversation frames the DPU as the answer to a wall that software-defined networking
(SDN) hit: SDN gave flexibility and scalability, but running network/security/storage in
software on the general-purpose CPU is inefficient — Deierling cites a figure that ~a
third of compute can be consumed just running SDN infrastructure. Nvidia's BlueField DPU
("a computer in front of the computer") does three things: **offload, accelerate, and
isolate**. Hardware accelerators handle RDMA file transfer at line rate, deep packet
inspection, IPsec/TLS encryption, and DDoS mitigation with near-zero CPU load. Chuck
relates this to his Cisco background (ASICs built for packet switching) and to a David
Bumble 40 Gig file-transfer test where the CPU, not the network, was the bottleneck.

The interview also covers **DOCA** (Nvidia's DPU SDK/framework, positioned as "CUDA for
the DPU") for partner development; **Morpheus**, an AI-driven cybersecurity app that uses
DPU telemetry plus GPU AI to detect anomalies (leaked credentials, misconfigurations,
suddenly-unencrypted flows) rather than fixed rules; partnerships with Palo Alto Networks
(9x firewall performance via offload), VMware/Dell (Project Monterey, running vSphere on
BlueField), and media/entertainment (SMPTE 2110 uncompressed video over Ethernet with
precise timing). It closes on Nvidia's Omniverse "digital twin" work — including an AI-
generated Jensen Huang and kitchen in the GTC keynote — and the thesis that every
business will become an AI business.

**Likely sponsored / Nvidia-promotional interview.** The technical concepts below are
captured; pure product-promotion and vision talk is summarized, not treated as
independent claims.

## Key claims (paraphrase, dated 2021-11-02)

- Nvidia entered networking through its acquisition of Mellanox and is now (per
  Deierling) the largest provider of networking at 25 Gig and above speeds, and produces
  InfiniBand as a leading HPC/AI networking technology.
- The "data center is the new unit of computing": problems no longer fit in one server,
  so compute is split across CPU (general), GPU (AI/ML), and DPU (data/infrastructure).
- A **DPU (data processing unit)** offloads data-intensive infrastructure tasks — packet
  switching/processing, encryption, compression, software-defined networking/storage/
  security — that CPUs run inefficiently. Nvidia's product is the **BlueField DPU**.
- The DPU is "software-defined and hardware-accelerated": it contains embedded Arm cores,
  but the real advantage is dedicated hardware accelerators, not the Arm cores themselves.
- A DPU's three functions: **offload** (move tasks off the x86 CPU), **accelerate**
  (run them on hardware accelerators for real speedup), and **isolate** (separate the
  infrastructure domain from the application domain for security + operational benefit).
- SDN consumes large amounts of CPU — Chuck cites a metric that roughly a third of
  available compute can be dedicated to running SDN; hyperscalers adopt DPUs first
  because CPU cores spent on infrastructure are cores they can't sell to customers.
- **RDMA** (and RoCE, RDMA over Converged Ethernet) lets the DPU move files VM-to-VM at
  line rate (100–200 Gbps) with zero CPU involvement, doing TCP/IP-style sequence and
  CRC checking in hardware.
- Deep packet inspection / firewalling on a CPU bottlenecks a 100 Gbps link at ~10 Gbps;
  offloading to the DPU (via Palo Alto's offload feature on DOCA) yielded ~9x better
  performance (near 100 Gbps) at zero CPU load — Deierling calls it "infinite efficiency."
- DDoS mitigation on a CPU that must inspect every packet brings the CPU to its knees
  (accomplishing what the attack intends); the DPU can do it with zero CPU.
- **DOCA** is Nvidia's open DPU SDK/framework — "what CUDA is for the GPU, DOCA is for the
  DPU" — with libraries and reference apps letting partners (storage, networking,
  security vendors) build on BlueField; forward compatibility across BlueField 2/3/4 is a
  stated goal.
- BlueField includes hardware engines for regular-expression search and malware-signature
  matching, letting things like Python regex be hardware-accelerated.
- **Morpheus** is an AI cybersecurity application: BlueField generates telemetry on all
  packet activity (a software "span port"/probe) and feeds a GPU-run neural network that
  flags anomalous behavior ("humans behaving like machines," leaked credentials, a
  normally-encrypted flow suddenly appearing unencrypted) rather than fixed rule sets;
  Splunk is named as a Morpheus collaborator. "It takes an AI to fight cybercrime."
- **Kronos** (time-synchronized data center) and **packet pacing** provide precision
  timing in the NIC — used to deliver streaming video to many homes at each home's exact
  receive rate; part of DOCA.
- **Rivermax** (part of DOCA) supports SMPTE 2110 uncompressed pro video (4K/8K) over
  Ethernet with tight multi-camera synchronization — a single 4K/8K stream can saturate a
  10 Gig link, driving 100+ Gig links for Hollywood/live production.
- VMware partnership: **NVIDIA AI Enterprise** brings Nvidia AI (Clara, Isaac, Riva,
  Metropolis) to virtualized VMware; **Project Monterey** puts the VMware/vSphere
  environment (ESXi, vMotion, vSAN, Tanzu) onto BlueField DPUs — transparent to admins
  while gaining hardware acceleration. Dell provides the hardware.
- Isolation decouples applications from infrastructure so each can be patched/upgraded on
  its own cadence (e.g. a new Linux kernel or security patch without app dependency
  breakage) — framed as a hardware-level analog to microservices/containers.
- GeForce NOW cloud gaming: DPUs isolate the internet-facing infrastructure domain from
  the game/application domain for security while preserving a native "seat on the server."
- **Omniverse** is Nvidia's real-time "digital twin" simulation platform; the GTC keynote
  featured an AI-generated Jensen Huang and kitchen (via Omniverse) that viewers,
  including Chuck, did not notice was synthetic; the BMW virtual factory was another demo.
- Overarching thesis: every business will become an AI business; those that don't embrace
  AI "aren't going to be around anymore" because "AI is the most powerful technology
  force of our time."

## Notable verbatim quotes

> "They're kind of changing the game completely. And they're creating new tech... things
> like DPS or data processing units, which will help us do more with networking and cyber
> security and even AI than we ever thought possible."
> — Chuck (intro)

> "The data center is the new unit or computing."
> — Kevin Deierling

> "You're still running on the wrong horse. Different horses for different courses. And in
> this case, the CPU is actually not very good at running software defined network."
> — Kevin Deierling

> "The real magic we like to say offload accelerates and isolate. Those are the three
> things that the DPU does."
> — Kevin Deierling

> "You get 10 times the performance or 50 times the performance with zero CPU... 50 times
> the performance divided by zero is an infinite efficiency game."
> — Kevin Deierling

> "So Doka is for the DPU what CUDA is for the GPU."
> — Kevin Deierling (caption garbles "Doka"/"Kuda"; product names are DOCA and CUDA)

> "We're looking for humans that are behaving like machines or machines that are behaving
> like humans... We're not defining it precisely. That's the beauty of a neural network
> and AI."
> — Kevin Deierling (on Morpheus)

> "It takes an AI to fight cybercrime."
> — Kevin Deierling

> "Can we just call it the matrix? I mean, that's what we're talking about right now.
> Aren't we let's be honest here."
> — Chuck (on Omniverse digital twins)

> "The businesses that don't become AI and embrace it, aren't going to be around anymore
> because AI is the most powerful technology force of our time."
> — Kevin Deierling

## Guest attribution

Guest interview — NOT solo. Two speakers:

- **Chuck Keith (the SUBJECT / @NetworkChuck)** — host. His questions, analogies (Cisco
  ASIC background, David Bumble 40 Gig test, microservices comparison, home/video-editing
  use case, sci-fi/Matrix framing) and enthusiasm ARE attributable to him and may train
  voice/persona.
- **Kevin Deierling** — SVP of Networking at Nvidia (joined via the Mellanox
  acquisition). All technical/product claims about DPUs, BlueField, DOCA, Morpheus,
  RDMA, VMware/Palo Alto partnerships, and Omniverse are HIS statements (Nvidia's
  position), NOT Chuck's. Do NOT attribute Nvidia product/vision claims to the SUBJECT.

Note: the closing caption reads "I enjoyed talking to Josh" — a caption garble; the
host is Chuck, not "Josh."
