---
type: youtube-video
source_date: 2024-11-04
url: https://www.youtube.com/watch?v=XvbVePuP7NY
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [ai-tools, homelab-selfhosting]
tags: [local-ai, voice-assistant, home-assistant, privacy, self-hosted]
---

# my local, AI Voice Assistant (I replaced Alexa!!)

## Summary

Chuck builds a fully local, AI-powered voice assistant to replace Amazon Alexa,
driven by a privacy motivation: he is "done with cloud-based stuff" and wants
nothing running in the cloud where "people [are] all up in [his] business." The
build is structured as escalating difficulty "levels."

The stack is centered on **Home Assistant** (running on a Raspberry Pi 4), which
he set up in a prior video as fully local, free, open-source home-automation
software. On top of it he assembles a local **voice pipeline** using
**Rhasspy**-provided, Wyoming-protocol services offered as Home Assistant
add-ons:

- **openWakeWord** for wake-word detection (default wake word "Nabu" / "Okay Nabu").
- **Whisper** (OpenAI's locally hosted model, via **faster-whisper** / Wyoming
  Whisper) for speech-to-text — explicitly NOT the cloud version.
- **Piper** for text-to-speech.
- Home Assistant **Assist** for intent recognition (turning speech into commands
  like turning lights on/off).
- **Ollama** running **Llama 3.2** as the conversational "brain" (a local
  ChatGPT-like LLM that never touches the internet), swapped in as the Home
  Assistant conversation agent to add smarts and conversational context/memory.

Level 2 adds a **Wyoming satellite** — a remote Raspberry Pi (Pi 4, Pi OS Lite
64-bit) turned into a networked voice endpoint using a **ReSpeaker 2-Mic Pi HAT**
(mics + speaker + status LEDs), the `wyoming-satellite` repo, a Python venv, and a
`systemd` service (plus a second service for the LED pixel-ring). Multiple
satellites can be deployed around the house, all talking to Home Assistant over
the Wyoming protocol on port 10700.

Level 3 offloads the AI-heavy pieces (Whisper STT, Piper TTS, and the Ollama LLM)
off the weak Raspberry Pi onto beefier hardware — first a laptop (RTX 3080
mobile), then ultimately his dedicated AI server **"Terry"** (built in an earlier
video). Whisper and Piper run as **Docker containers** (Wyoming Whisper on port
10300, Wyoming Piper on port 10200; on Windows via WSL2). Getting the GPU to work
inside the Docker containers was very hard — he got it working on Terry but not
the laptop, and says CPU works well enough.

Finally he trains a **custom wake word "Terry"** using Home Assistant's
openWakeWord training environment in **Google Colab** (producing `.tflite` and
`.onnx` files, uploaded to Home Assistant via the **Samba** add-on into an
`openWakeWord` folder). He also shows the **ESP32-S3-BOX** (Espressif) as a
screen-equipped satellite option. Two things he could NOT finish this video and
defers to a follow-up: getting a fully custom AI-cloned voice for Terry, and full
polish. Sponsor: Bitdefender (Scam Copilot), demoed via a Home Assistant
voice-sentence automation.

## Key claims (dated — stack + privacy)

- (2024-11-04) The entire voice assistant can run **fully local / offline**, with
  no cloud dependency, as a privacy-motivated replacement for Alexa. [paraphrase]
- (2024-11-04) **Home Assistant** (on a Raspberry Pi 4) is the base platform —
  fully local, free, open-source home-automation software. [paraphrase]
- (2024-11-04) The voice pipeline uses **Rhasspy**-provided, Wyoming-protocol
  services: **openWakeWord** (wake word), **Whisper**/faster-whisper (STT),
  **Piper** (TTS), and Home Assistant **Assist** (intent recognition).
  [paraphrase]
- (2024-11-04) **Ollama running Llama 3.2** is used as the local LLM
  conversation agent ("brain"), replacing Home Assistant's default agent to add
  intelligence plus conversational context/memory. [paraphrase]
- (2024-11-04) Home Assistant makes wiring a local LLM (Ollama) into the voice
  pipeline "stupid easy" via an official, supported Ollama integration.
  [paraphrase]
- (2024-11-04) The **Wyoming protocol** / **Wyoming satellite** lets any device
  (e.g. a Raspberry Pi with a **ReSpeaker 2-Mic Pi HAT**) act as a remote voice
  endpoint that connects back to Home Assistant; multiple satellites can be
  deployed around the house. [paraphrase]
- (2024-11-04) AI-intensive components (Whisper, Piper, Ollama) can be **offloaded**
  from the Raspberry Pi to more powerful hardware — a laptop, and ultimately his AI
  server "Terry" — with Whisper and Piper run as **Docker containers** (Wyoming
  Whisper / Wyoming Piper). [paraphrase]
- (2024-11-04) Getting the GPU working inside the Whisper/Piper Docker containers
  is very difficult; he succeeded on Terry but not the laptop, and says **CPU
  works well enough**. [paraphrase]
- (2024-11-04) A **custom wake word** ("Terry") is trained with Home Assistant's
  openWakeWord environment on **Google Colab**, yielding `.tflite` + `.onnx` files
  uploaded via the **Samba** add-on. [paraphrase]
- (2024-11-04) The **ESP32-S3-BOX** (Espressif) is a screen-equipped
  satellite/voice-assistant device option, unlike the DIY Pi builds. [paraphrase]
- (2024-11-04) Self-hosted voice assistance is "okay" and good enough for him to
  switch off Alexa, though Alexa still does some things better (e.g. timers,
  screens); the compelling differentiator is running **AI locally**. [paraphrase]
- (2024-11-04) Custom AI voice cloning for Terry was attempted but NOT finished in
  this video (spent a full day troubleshooting) — deferred to a follow-up video.
  [paraphrase]

## Notable verbatim quotes

> I'm done I'm throwing Alexa in the trash I want to create my very own fully local
> AI powered voice assistant

> I wanted to use AI because Alexa's kind of dumb but I don't want to use AI in the
> cloud I'm tired of people being all up in my business get out of here Jeff so I
> want to do everything local

> but seriously I'm done with cloud-based stuff I want to go fully local for
> everything

> I went with using open ai's whisper and not the cloud stuff the locally hosted
> model they provide

> I wanted to have raspy talk to an llm similar to Chad BT so [Oll]ama with llama 3
> ... home assistant makes that stupid easy they actually have [an integration] to
> where an llm like [Oll]ama can be the brain

> the Wyoming protocol ... is a small peer-[to-]peer protocol for voice assistant
> ... we can make the Raspberry Pi a Wyoming satellite essentially a remote Voice
> Assistant that can communicate with and use the voice pipeline from home assistant

> I'm going to offload everything that's AI intensive to another server

> it is possible to get the GPU to work with this Docker container but I'll tell you
> one thing it's not stinking easy I tried for hours and hours and hours I finally
> got it to work on Terry could not get it to work on him

> here's the state of voice assist[ants] hosting it yourself it's okay like I think
> it's enough for me to make the move ... it can't do AI yet which is pretty
> compelling for me to host my AI locally

> I love that it's all local I don't even care I'll live with it and so all my
> family they'll have to cuz I'm going to replace Alexa

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: local private voice assistant (self-hosted AI + own-your-data) -->
