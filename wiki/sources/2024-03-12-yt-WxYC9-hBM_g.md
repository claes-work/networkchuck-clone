---
type: youtube-video
source_date: 2024-03-12
url: https://www.youtube.com/watch?v=WxYC9-hBM_g
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [ai-tools, homelab-selfhosting]
tags: [ollama, local-llm, private-ai, self-hosting, llama, open-webui]
---

# Run your own AI (but private)

## Summary

A landmark AI tutorial in which Chuck shows how to run your own **private, local LLM** on
your own machine — "kind of like ChatGPT, except it's not," with everything running on
his computer, no internet required, and no data shared with a random company. The core
setup is deliberately simple: install **Ollama** (`ollama.ai`) and run a model with one
command (`ollama run llama2`). On Windows he uses **WSL** (`wsl --install`, Ubuntu
22.04) because at the time Ollama's native Windows build was "coming soon"; macOS and
Linux install directly. He motivates the topic first with a field trip to
**Hugging Face** (`huggingface.co`, "505,000 AI models"), searching for **Llama 2 7B** —
an open LLM Meta pre-trained on over 2 trillion tokens using a ~6,000-GPU "super cluster"
(~1.7M GPU-hours, ~$20M) that anyone can now download for free. He demos model swaps
(Llama 2, **Mistral**, Code Llama, uncensored variants) and shows that a GPU makes
responses fast while CPU-only still works but slower; Macs with M1/M2/M3 work great.

He then makes the case that **private AI is the future**, especially at work: many
companies forbid ChatGPT for privacy/security/compliance reasons, but a locally-run
private model changes the equation because the data never leaves the building. He
explains two ways to teach the model your own information: **fine-tuning** (retraining on
proprietary data — heavy, needs GPUs and tooling like PyTorch/TensorFlow) and **RAG**
(retrieval-augmented generation — connect the LLM to a vector database / knowledge base
so it consults your docs before answering, without retraining). The sponsor segment
(VMware by Broadcom, with NVIDIA/Intel/IBM) frames on-prem "VMware Private AI" as a
packaged way for companies to fine-tune LLMs in their own data center. The advanced
bonus section walks through a separate project, **PrivateGPT**, run on WSL with an
NVIDIA 4090 — Chuck ingests his own markdown journals and chats with them via RAG,
asking what he did in Takayama and ate in Tokyo on his November 2023 Japan trip.

## Key claims (dated — setup + private-AI philosophy)

- **[2024-03-12]** You can run your own AI locally that is like ChatGPT but private:
  everything runs on your own computer, no internet required, and your data isn't shared
  with any company. (paraphrase)
- **[2024-03-12]** Setup is "ridiculously easy," free, and takes about five minutes.
  (paraphrase)
- **[2024-03-12]** An AI model is simply an artificial intelligence pre-trained on data;
  ChatGPT and Llama 2 are both **LLMs** (large language models). (paraphrase)
- **[2024-03-12]** **Hugging Face** (`huggingface.co`) is a community that hosts and
  shares AI models — over 505,000 of them, many open, free, and pre-trained. (paraphrase)
- **[2024-03-12]** **Llama 2** was made by Meta (Facebook), pre-trained on over
  2 trillion tokens from publicly available sources plus over a million human-annotated
  examples, with a data freshness of July 2023. Training used a ~6,000-GPU super cluster,
  ~1.7 million GPU-hours, at an estimated ~$20 million — and you can now download it for
  free. (paraphrase)
- **[2024-03-12]** The tool for running models locally is **Ollama** (`ollama.ai`);
  install it, then run a model with `ollama run <model>` (e.g. `ollama run llama2`).
  (paraphrase)
- **[2024-03-12]** Ollama at the time supported macOS and Linux natively, with Windows
  "coming soon"; Windows users install via **WSL** (`wsl --install`, which sets up Ubuntu
  22.04) and then follow the same Linux steps. (paraphrase)
- **[2024-03-12]** The demoed model is Llama 2 **7B** (7 billion parameters); a GPU
  (e.g. NVIDIA) makes inference fast, CPU-only works but is slower, and Apple M1/M2/M3
  Macs run it well. (paraphrase)
- **[2024-03-12]** Multiple models can be swapped in and out — Llama 2, Code Llama,
  Mistral, and uncensored/fine-tuned variants (e.g. a George Sung uncensored Llama 2 that
  took ~19 hours to fine-tune). Local models can **hallucinate** and may hold outdated or
  wrong info (a model called him "Chuck Davis" of "Network Chuck on Tech"). (paraphrase)
- **[2024-03-12]** Private, local AI is significant because many companies won't let
  employees use ChatGPT for privacy/security/compliance reasons — running your own model
  keeps the data in-house so it can be used at work. (paraphrase)
- **[2024-03-12]** To teach a model your own info, **fine-tuning** retrains it on
  proprietary data; it needs GPU hardware and tools/libraries (PyTorch, TensorFlow,
  pandas, scikit-learn, transformers, fast.ai). Fine-tuning a small dataset (~9,800
  examples, changing ~65M params ≈ 0.93% of a 7B model) via prompt tuning can take only
  ~3–4 minutes and does not require the 6,000 GPUs used for original training.
  (paraphrase)
- **[2024-03-12]** **RAG** (retrieval-augmented generation) connects an LLM to a vector
  database / knowledge base so that before answering it consults your documents for
  accuracy — no retraining required; it complements fine-tuning. (paraphrase)
- **[2024-03-12]** The advanced bonus uses **PrivateGPT** (a separate free project, not
  Ollama), run on WSL with an NVIDIA 4090 and accessed via web browser; Chuck ingested a
  folder of markdown journals and chatted with them via RAG, asking about his own past
  (Japan trip, November 2023). It's "not perfect" but shows the potential. (paraphrase)
- **[2024-03-12]** Philosophy: whatever data you feed a private, local AI stays with you
  or your company — "it's not leaving the door" — and this data-private approach is the
  future of how companies and individuals will approach AI. (paraphrase)
- **[2024-03-12]** Sponsor framing: VMware (by Broadcom) with NVIDIA — "VMware Private
  AI" — packages the deep-learning VMs, GPU passthrough (PCIe / vGPU), tooling, and
  vector database needed to fine-tune and deploy custom LLMs on-prem, with partner
  options across NVIDIA, Intel, and IBM. (paraphrase, sponsored)

## Notable verbatim quotes

> "I'm running something called private ai. It's kind of like chat GPT, except it's not.
> Everything about it is running right here on my computer. Am I even connected to the
> internet? This is private contained and my data isn't being shared with some random
> company."

> "It is ridiculously easy and fast to run your own AI on your laptop computer or
> whatever. It's this is free, it's amazing. It'll take you about five minutes."

> "Now made is just like, here you go kid. Download this incredibly powerful thing... this
> intelligent source of information that you can just download on your laptop and ask it
> questions, no internet required."

> "The tinfoil hat version of me stinking loves this because let's say the zombie
> apocalypse happens, right? The grid goes down, things are crazy, but as long as I have
> my laptop and a solar panel, I still have AI and it can help me survive the zombie
> apocalypse."

> "It's possible now because this AI is private, it's local and whatever data you feed to
> it, it's going to stay right there in a company. It's not leaving the door."

> "That idea just makes me so excited because I think it is the future of AI and how
> companies and individuals will approach it. It's going to be more private."

> "We're not retraining the LLM, we're just saying, Hey, before you answer, go check real
> quick in this database to make sure it's accurate."

> "I actually connected a lot of my notes and journal entries to a private GPT using RAG
> and I was able to talk with it about me asking it about my journal entries and answering
> questions about my past. That's so powerful."

> "Private AI is the future."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: private/self-hosted AI (Ollama) — AI meets his self-hosting/data-ownership ethos -->
