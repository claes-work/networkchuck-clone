---
type: youtube-video
source_date: 2025-12-20
url: https://www.youtube.com/watch?v=bFgTxr5yst0
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [networking, ai-tools, homelab-selfhosting]
tags: [thunderbolt, ethernet, ai-cluster, mac-studio, networking]
---

# Ethernet is DEAD?? Mac Studio is 100x FASTER!!

## Summary

Chuck builds a second local-AI supercluster — four fully-specced Mac Studios (512 GB
unified memory each, 80 GPU cores each; 2 TB unified memory / 320 GPU cores / 32 TB
storage total; ~$50,000, loaned by Apple). This revisits his earlier-2025 five-Mac
cluster, which was a disappointment: adding machines made inference *slower* (91% slower)
because the interconnect latency, not compute, was the bottleneck.

The video's real subject is a networking fix, not a hardware upgrade. Apple quietly
enabled **RDMA (Remote Direct Memory Access) over Thunderbolt 5** in the macOS **Tahoe
26.2** beta (enabled in recovery mode). RDMA bypasses the traditional TCP/IP stack so
GPU memory talks directly to GPU memory, dropping inter-Mac latency from ~300 microseconds
to ~3 microseconds (~100x). That low latency finally makes **tensor parallelism**
viable over a consumer cluster, where before only slower **pipeline parallelism** worked.
**ExoLabs** (thought dead, revived in partnership with Apple) provides the clustering
software — now a native Mac app instead of CLI-only — running models via Apple's **MLX**
framework. Chuck runs Llama 3.3 70B FP16, Qwen3 Coder 480B, DeepSeek 671B, and the
trillion-parameter Kimi K2 thinking model, several simultaneously, and drives them from
real apps (Open WebUI, Xcode, OpenCode). Verdict: clustering local AI now genuinely makes
sense — it speeds up rather than slows down. Sponsor: Twingate (zero-trust network access).
Ends with his recurring closing prayer (recorded around Christmas).

## Key claims

All statements paraphrased from Chuck Keith, dated 2025-12-20 unless noted.

- The cluster is four Mac Studios: 512 GB unified memory each (usable as GPU/VRAM), 80 GPU
  cores each, 8 TB storage each — totaling 2 TB unified memory, 320 GPU cores, 32 TB storage.
  He calls it possibly "the most powerful local AI setup ever built." Cost ~$50,000; Apple
  loaned the hardware (he does not keep it).
- The prior early-2025 cluster used five older M2 Max Mac Studios and performed terribly —
  clustering made it ~91% slower. The bottleneck was networking **latency**, not GPU or memory.
- The new cluster is connected via **Thunderbolt 5** in a mesh (per an Apple-supplied
  diagram) plus **Ethernet**. Ethernet (a spare UniFi switch with 2.5 GbE ports, 10 GbE
  uplink) is used only so nodes can *discover* each other and to download the huge models —
  it is **not** the path over which the cluster exchanges inference data. Thunderbolt is.
  → This is the nuance behind the clickbait "Ethernet is dead": Ethernet is not eliminated;
  it is demoted to discovery/bulk transfer, while the fast GPU-to-GPU interconnect is
  Thunderbolt 5 with RDMA. The provocation is hyperbole, not a literal claim.
- **RDMA over Thunderbolt** is the actual breakthrough — a software update, enabled in macOS
  **Tahoe 26.2** (beta), toggled on in recovery mode. RDMA is the same class of tech AI data
  centers use for GPU-to-GPU communication (he ties it to a prior video on AI data-center
  networking; notes models like ChatGPT and Claude rely on RDMA-style interconnects).
- Before RDMA, the Thunderbolt links were plain TCP/IP network connections; CPU processing
  of every packet added overhead and latency (~300 microseconds/message). RDMA removes the
  TCP/IP stack for a direct GPU-memory-to-GPU-memory connection, cutting latency to
  ~3 microseconds (~100x improvement) — "a bullet train."
- **Pipeline parallelism**: splits a model's layers across machines (e.g. an ~80-layer model,
  Mac 1 = layers 1-20, Mac 2 = 21-40, …). It runs sequentially — each Mac processes then
  waits — like "a relay race … we're waiting on each other." Gives capacity (run models too
  big for one machine) but not speed.
- **Tensor parallelism**: all Macs work on every layer, splitting the *math* (~25% each), then
  combine results. In theory ~3.5x faster than pipeline parallelism — but it needs heavy
  inter-node chatter (~two comms per layer; for an 80-layer model, ~160 comms per token).
  At 300 microseconds/message that is ~50 ms of waiting per token, which made tensor
  parallelism *slower* than pipeline on the old high-latency network. RDMA's 3-microsecond
  latency is what makes tensor parallelism finally win.
- Benchmark, Llama 3.3 70B FP16 on all four nodes: pipeline (no RDMA) ~5 tok/s (~200 ms/token);
  tensor without RDMA ~3 tok/s (~370 ms/token, i.e. slower — "unusable"); tensor **with RDMA**
  ~16 tok/s (~66 ms/token). RDMA tensor parallelism ~3x faster than the old pipeline way.
- Clustering also speeds up small models that fit on one Mac: Llama 3.2 3B ran ~147 tok/s on
  one node vs ~240 tok/s across four nodes with RDMA. Power draw ~100 W/Mac (~400 W total).
- Large-model runs (single or clustered): Qwen3 Coder 480B (a mixture-of-experts model)
  ~27 tok/s single node, ~40 tok/s clustered; DeepSeek 671B ~26-27 tok/s; **Kimi K2 thinking,
  ~1 trillion parameters** (658 GB/node download, needs ≥2 nodes) ran ~28-30 tok/s at ~33% RAM
  per node, ~110 W/Mac. He ran Kimi K2 + DeepSeek 671B + multiple Llama variants concurrently.
- Cost framing: matching this ~2 TB VRAM locally with NVIDIA H100s would need ~26 H100s
  (80 GB each) at over $780,000 — and more once you build the full system. The $50k Mac
  cluster is a "proof of concept" showing local clustering is now functional and fast.
- Limitation noted: the Thunderbolt bridge shows as inactive/disabled in macOS network config,
  so the RDMA traffic is "ghost traffic" — Chuck could not visualize bandwidth/latency; Apple
  told him there is no way to monitor it yet. Beta software occasionally crashed; he used Claude
  Code / "cloud code" to build scripts to reboot and reinitialize the cluster.
- **MLX** (Apple's open-source machine-learning framework) is what actually runs the models;
  ExoLabs worked with the MLX team on the "RDMA over Thunderbolt driver [that] enables MLX
  distributed to communicate with low latency across Thunderbolt 5." MLX ops run on CPU or GPU
  without moving memory, thanks to unified memory.

## Notable verbatim quotes

> "So, I built another AI supercomput. And this one's crazy. 1 2 3 four Mac Studios, 512 gigs
> of RAM each, 2 terb of unified memory. This might be the most powerful local AI setup ever built."

> "Everyone said clustering was stupid, and they were right. So, why am I doing this again?
> Well, Apple just dropped something new. A simple software update that might change the entire game."

> "It wasn't the GPU, it wasn't the memory, it was the networking. It was that latency between
> the connections."

> "We're also using the Ethernet so the cluster can see each other, but it's not how they're
> actually connecting and exchanging information. That's where Thunderbolt comes in."

> "It's networking. It's always about networking."

> "It's like a relay race with really fast sprinters, but we're not working together. We're
> waiting on each other."

> "Apple quietly enabled in Tahoe 26.2 a technology on their Thunderbolt ports called RDMMA or
> remote direct memory access. This is huge. We're in the big leagues now."

> "With RDMA, we skip all that. RDMA is direct memory access. We remove the TCP IP stack. Say,
> 'Nah, we don't need you anymore.' … A direct connection from GPU memory to GPU memory."

> "This takes our latency from 300 microsconds down to three microsconds. Are you kidding me?
> That's 100x increase or decrease. That's a bullet train."

> "16 tokens a second on average. 66 milliseconds per token. They did it. Apple, you're awesome."

> "Like if you wanted the same specs from an Nvidia H100 cluster, you would need 26 H100s, each
> with 80 GB of VRAM. That would cost you over $780,000."

> "Clustering's awesome now. I'm running every model I can possibly run on it, and it's just
> doing it like a champ, and it's fast."

> "RDMMA over Thunderbolt driver enables MLX distributed to communicate with low latency across
> Thunderbolt 5."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: Thunderbolt AI-cluster networking / 'Ethernet is dead' nuance -->
