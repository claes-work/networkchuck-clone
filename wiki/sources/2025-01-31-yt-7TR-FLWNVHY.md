---
type: youtube-video
source_date: 2025-01-31
url: https://www.youtube.com/watch?v=7TR-FLWNVHY
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [ai-tools, homelab-selfhosting, cybersecurity]
tags: [deepseek, local-llm, ollama, self-hosted-ai, privacy]
---

# the ONLY way to run Deepseek...

## Summary

Chuck walks through running DeepSeek R1 locally instead of using the DeepSeek app or
website, framed as a privacy/data-sovereignty decision. His core argument: when you use
DeepSeek online you use their servers, they own your data, and — unlike Western services
that also harvest data — DeepSeek's servers are in China, subjecting your data to Chinese
cybersecurity laws that give authorities broad access. His fix is to run the model on your
own hardware where nothing leaves your machine.

He presents two ways to run models locally: **LM Studio** (a beautiful GUI, "for everybody"
including people not comfortable in the CLI) and **Ollama** (CLI-only, "simple and fast",
his personal favorite). Both let you download DeepSeek R1 in various parameter sizes
(1.5B → 671B); bigger models need bigger hardware, and only the full 671B model competes
with cloud models like OpenAI. Local models run "dumber" the smaller you go but are still fun.

The privacy claim is then **tested and verified**, not just asserted: Chuck runs a PowerShell
script that finds the Ollama process IDs and continuously monitors its network connections.
While chatting with the local model, no external IP addresses appear — the only connection is
local (CLI → the API listening on port 11434). Ollama only reaches out to the internet when
downloading a new model. He notes Ollama has no module/function that lets a locally-run model
access the internet.

For extra hardening he demonstrates his preferred method: running Ollama **inside a Docker
container** to isolate it from the host OS (which otherwise could touch network, files, and
system settings). The Docker command gives GPU access, sets an Ollama settings volume, exposes
port 11434, drops all privileges except GPU scheduling, caps system resources, and makes the
container filesystem read-only. On Windows this needs WSL2 + Nvidia container toolkit; Mac's
M-series GPUs aren't accessible to Docker. He concedes this may be overkill for most, since
plain Ollama already showed no internet access.

## Key claims (dated — method + privacy framing)

- (2025-01-31) DeepSeek R1 is open source, which means — unlike ChatGPT — you can run its
  models locally on your own hardware; Chuck calls local the "only recommended way" to run it.
- (2025-01-31) Using DeepSeek via its app/website runs on DeepSeek's servers, so whatever you
  tell it is stored there and they can do what they want with it. This data harvesting is not
  unique to DeepSeek — ChatGPT, Meta, and X do it too.
- (2025-01-31) DeepSeek is different because its servers are in China, whose cybersecurity laws
  give authorities broad powers to request data stored within their borders; Chuck won't hand
  any government easy access to his data.
- (2025-01-31) Two recommended tools to run models locally: **LM Studio** (GUI, beginner-friendly,
  shows whether your GPU can fully/partially offload a given quantization) and **Ollama**
  (CLI-only, simple and fast, his favorite).
- (2025-01-31) Model size dictates hardware needs: DeepSeek R1 ranges 1.5B → 671B parameters;
  the 671B is the only size that competes with cloud models and needs serious hardware (his
  dual-4090 AI server can't run it, but can handle up to 70B). A single Nvidia 4090 comfortably
  runs 14B–32B; most people can run at least 1.5B; even a Raspberry Pi can run something.
- (2025-01-31) Smaller models are "dumber" (like a lower IQ score) but still usable and fun.
- (2025-01-31) Privacy verified empirically: a PowerShell script monitoring Ollama's process
  network connections shows no external IPs while running the model locally — only a local
  connection to the API on port 11434. Ollama only reaches the internet to download a model.
- (2025-01-31) Ollama has no built-in module or function letting a locally-run model access
  the internet, so it's safe "for now."
- (2025-01-31) For extra safety, run Ollama inside Docker to isolate it from the host OS;
  Chuck's hardened container has GPU access, a settings volume, exposed port 11434, dropped
  privileges (keeping only GPU scheduling), capped resources, and a read-only filesystem.
- (2025-01-31) Windows needs WSL2 and the Nvidia container toolkit for GPU-in-Docker; Mac
  M-series GPUs are not accessible to Docker.

## Notable verbatim quotes

> "I do recommend going local and private for as many things as you can, especially local AI models."

> "It's a bit different because their servers are in China... their cybersecurity laws are a bit
> different. It gives authorities broad powers to request access to the data stored within their
> borders. Your data is subject to Chinese laws. I don't want any government to have my data and
> if a government's able to get that data easily, I'm out."

> "And right now you're running an AI model that is not touching the internet, it's not reaching
> out to servers and giving away your data. It's all right here on your computer, which is amazing.
> But hold on, how do we know that?"

> "This script will find the Ollama process IDs and then constantly check what network connections it has."

> "Whoa, hold on. Okay, this is all local. That scared me for a second."

> "Ollama, it does not have any functionality for an LLM that you run locally to access the internet.
> There's no module or function that can make that happen. So we at least know for now we're safe."

> "So what I want to do is use one of my favorite ways to segment an application to isolate it, put
> it into its own little container. And that's with my favorite technology, Docker."

> "Completely local, isolated from the rest of my OS. This is the way I prefer to run my local AI."

> "Keeping in mind the models you run locally cannot compete with the models that are in the cloud.
> Unless you have enough resources to run the DeepSeek R1 671B, you'd have to have some serious hardware."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: run DeepSeek locally for privacy (self-hosted AI + data-sovereignty) -->
