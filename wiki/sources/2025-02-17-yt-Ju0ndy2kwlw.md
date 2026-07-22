---
type: youtube-video
source_date: 2025-02-17
url: https://www.youtube.com/watch?v=Ju0ndy2kwlw
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [ai-tools, homelab-selfhosting]
tags: [local-llm, mac-studio, cluster, distributed-inference, exo, self-hosted-ai]
---

# I built an AI supercomputer with 5 Mac Studios

## Summary

Chuck clusters five Mac Studios (M2 Ultra, 64 GB unified RAM each) into a single
distributed-inference rig with the goal of running "the biggest and baddest" local LLM
he can find — ultimately Meta's Llama 3.1 405B, a model normally reserved for cloud data
centers. The build uses **EXO Labs** (beta clustering software) to auto-discover the
nodes and split model layers across them, so no single machine has to hold the whole
model. The hardware was actually bought to replace NetworkChuck Studios' PC video-editing
pipeline with Macs; Chuck commandeered them to "play with them first."

The video doubles as a teaching piece on running local AI: what parameters mean, why more
parameters ≈ "smarter," the VRAM required per model size, and how **quantization** (FP32 →
FP16 → INT8 → INT4) shrinks big models to fit on smaller GPUs at the cost of precision. The
central hardware argument is Apple's **unified memory architecture**: because M-series Macs
pool one memory bank for CPU and GPU, five 64 GB Macs give ~320 GB of GPU-usable RAM at a
fraction of a 4090's cost and power draw — while acknowledging Nvidia's CUDA/tensor-core
ecosystem still wins on raw AI speed.

The recurring theme is that **networking is the bottleneck**. Nodes talk constantly, and
Chuck's 10 GbE switch (and even a 40 Gbps Thunderbolt bridge) can't match the 400–800 Gbps
interconnects real AI clusters use, so token throughput collapses as nodes are added. He
does succeed in running Llama 3.1 405B locally — at ~0.5 tokens/second — proving the concept
even if it's impractically slow. He closes noting that for a single Mac Studio, Llama 3.3
70B via Ollama "runs like a dream," and that EXO's MLX path on Mac still needs work versus a
future Nvidia-based cluster. Sponsored by NordVPN.

## Key claims (dated 2025-02-17)

- Chuck connects **five Mac Studios (M2 Ultra, 64 GB unified RAM each)** into one AI cluster,
  aiming to run the largest models he can, up to **Llama 3.1 405B** (405 billion parameters).
- The Macs were bought to switch NetworkChuck Studios' **video-editing pipeline from PC to
  Mac**; the AI cluster is Chuck playing with them before handing them over.
- He uses **EXO Labs** (new/beta software) to cluster heterogeneous hardware — a Raspberry Pi,
  a spare laptop, a gaming PC with a 4090 — so they pool resources and run models together.
- Chuck already runs local AI on a dedicated server named **Terry** (2× RTX 4090), so his data
  stays local and never goes to cloud companies like OpenAI.
- **Parameters ≈ learned knowledge**: each parameter is a numerical weight in a neural network;
  more parameters generally means a smarter, more capable model. A model predicts its response.
- VRAM guidance he gives (with quantization baked in): Llama 3.2 1B ≈ 4 GB; 3.2 3B ≈ 6 GB
  (a 2060); Llama 3.1 8B ≈ 10 GB; a 14B ≈ 16 GB (a 3090); **Llama 3.3 70B ≈ 48 GB** (needs
  two 4090s — no single consumer GPU does it); **Llama 3.1 405B ≈ 1 TB of VRAM** (data-center
  H100/A100 territory; ~42 RTX 4090s).
- Newer generation number ≠ smarter: Llama 3.2 1B is newer than Llama 3.1 8B but not more
  capable — model size/reasoning matters more than version.
- **Quantization** shrinks models to fit smaller GPUs by reducing precision: FP32 = full,
  FP16 = ~0–2% loss, INT8 = 4× smaller (~1–3% loss), INT4 = 8× smaller (~10–30% loss, the
  practical floor). Chuck runs a pre-quantized 4-bit version of the 405B model.
- **Unified memory architecture** is the enabler: M-series Macs share one memory pool for CPU
  and GPU, so 5 × 64 GB = **~320 GB of GPU-usable RAM**, with no CPU↔GPU transfer overhead.
- Cost/power framing: a Mac Studio ≈ **$2,600 for the whole computer**; a single RTX 4090 ≈
  **$1,600** for one part; the Macs draw far less power (all five idled at ~46 watts).
- **Nvidia still wins on raw AI performance** — dedicated tensor cores and CUDA optimization;
  models are built for Nvidia first. Apple's **MLX** (Machine Learning Acceleration) helps and
  is what EXO uses on Mac, but CUDA wins on ecosystem support.
- **Networking is the bottleneck.** Nodes exchange huge amounts of data; Chuck's 10 GbE
  Ubiquiti switch and even a 40 Gbps Thunderbolt bridge are far below the 400–800 Gbps
  interconnects enterprise AI networking (referencing his prior Juniper video) uses.
- Measured token throughput (small model, tokens/sec): ~117 on one Mac → ~29 across five over
  10 GbE; Thunderbolt was only modestly faster. Bandwidth, not compute, capped it.
- **Llama 3.1 405B ran locally at ~0.5 tokens/second** across the cluster — proof of concept,
  impractically slow. On a single host it fell into swap (borrowing SSD space) and stalled.
- EXO exposes an **OpenAI-compatible API**; Chuck got Daniel Miessler to add EXO support to the
  **Fabric** project so he could pipe local cluster inference through Fabric.
- Practical takeaway: a **single Mac Studio (64 GB) runs Llama 3.3 70B (and DeepSeek R1 70B)
  beautifully via Ollama** — full GPU, no swap — which he calls the real sweet spot.

## Notable verbatim quotes

> "I'm connecting them together and forming a super powerful AI cluster. Why? I want to run
> the biggest and baddest AI models I can find."

> "Everything's local. They don't get my data."

> "You can actually think of a parameter as learned knowledge... the more parameters it has,
> the smarter it is."

> "The new Macs don't do that. They have one pool of memory for everything."

> "So in my mind I'm thinking 64 times five. What does that give me? 320 gigabytes of RAM
> that can be used for the GPU."

> "This however, will be our biggest bottleneck, not ideal."

> "We're running the biggest, baddest model of them all on local hardware. What would normally
> take an entire data center of stuff? We're doing it right here. Slow, but we did it. Take
> that Zuckerberg, take that Musk. We don't need you, although we're using your model."

> "We're rocking a blazing speed of 0.8 tokens a second. But you know what? We did it."

> "This model with my 64 gigs of RAM on my Max Studio runs like a dream, which is pretty
> amazing. The 70 B model is awesome."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: 5-Mac-Studio local-LLM supercomputer — self-hosted-AI at scale -->
