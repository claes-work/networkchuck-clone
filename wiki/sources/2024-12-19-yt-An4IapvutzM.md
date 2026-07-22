---
type: youtube-video
source_date: 2024-12-19
url: https://www.youtube.com/watch?v=An4IapvutzM
channel: "@networkchuck_v2"
ingested: 2026-07-22
tier: L2
domains: [homelab-selfhosting, ai-tools]
tags: [home-assistant, voice-assistant, local-ai, self-hosting, privacy, alexa-alternative]
---

# Home Assistant made their own Alexa!!

## Summary

Chuck unboxes and live-tests the **Home Assistant Voice Preview Edition**, a dedicated
local voice-assistant device from Nabu Casa (the company behind Home Assistant) pitched
as a private, self-hosted alternative to Amazon Alexa / Google. The device was sent to
him unpaid, as a preview unit, and he sets it up on camera without prior prep. The core
angle throughout is his own-your-own-stuff / run-everything-locally ethos: this hardware
removes the DIY barrier of building a Raspberry Pi voice satellite yourself while keeping
everything under local control instead of shipping voice data to Amazon.

The device requires an existing Home Assistant install to work. Setup goes through the
Home Assistant phone app (which discovers the device over Bluetooth), joins it to Wi-Fi,
and adds it as an ESPHome device. Chuck then walks through hardware (button, mic
mute switch, speaker, USB-C, 3.5 mm jack, a mystery "Groveport"), the LED ring, volume
via an iPod-classic-style rotating wheel, the new **micro wake word** technology, custom
wake words (he switches to "Jarvis"), TTS output with cloned voices, media/radio
playback, interrupting the assistant by saying "stop" or pressing the center button, and
timers. He hits several rough preview-edition edges: the device randomly resets a couple
times (possibly a power issue — it wants 5V/2A), and timers fail when the voice pipeline
is backed by a local LLM (Llama). He diagnoses that Llama is too "dumb" for reliable
timer/tool actions, while the built-in Home Assistant conversation agent and ChatGPT both
handle timers fine.

## Key claims (dated — 2024-12-19)

- Home Assistant / Nabu Casa built a dedicated voice-assistant device (Home Assistant
  Voice Preview Edition) as a private, local alternative to Alexa; Chuck received it free
  with no obligation to make a video (paraphrase).
- The device's value proposition is removing the barrier to entry of building your own
  Raspberry Pi voice assistant — still doable, "not for the faint of heart," but a barrier
  for many people; this device makes local voice ownership accessible (paraphrase).
- **Requires an existing Home Assistant instance** to function (paraphrase).
- Setup path: scan QR → Home Assistant **phone app** discovers the device over
  **Bluetooth**, connects it to Wi-Fi, authorizes it, and adds it as an **ESPHome device**
  / node in Home Assistant (paraphrase).
- Hardware inventory: center button, side mic on/off switch, speaker holes, USB-C port,
  3.5 mm headphone jack, a "Groveport" (unknown to him), and an LED ring; volume is set by
  rotating the top like an iPod Classic wheel (paraphrase).
- Power requirement is **5V / 2A**; using a weaker iPhone USB-C brick may have caused the
  random resets he saw, so he switched to a Raspberry Pi power supply (paraphrase).
- Uses a new wake-word technology called **micro wake word**, claimed to be much better at
  avoiding false triggers than older approaches (paraphrase).
- Custom user-defined wake words are **not yet easily supported** at preview time — Nabu
  Casa doesn't have a good pipeline to share yet, but it's planned; built-in options like
  "Jarvis" work (paraphrase).
- The center button aborts/interrupts the assistant and wakes it without the wake word,
  and supports double-, triple-, and long-press custom actions; holding the button changes
  the LED color (paraphrase).
- You can now interrupt the assistant just by saying **"stop"** (no wake word needed),
  which was not possible before — Chuck calls this "a big deal" (paraphrase).
- Supports TTS output with multiple (cloned) voices (his own, "Terry," "Mike"), and can
  act as a media player / play a radio service (paraphrase).
- **Timers are a headline feature** because Wyoming satellites don't really do timers, and
  timers are the main thing his household uses Alexa for (paraphrase).
- Timers **failed when the voice pipeline used a local LLM (Llama / Ollama)** but worked
  with the built-in Home Assistant conversation agent and with **ChatGPT** as the agent;
  he concludes Llama is too weak for reliable tool actions like setting timers (paraphrase).
- Comparison to Alexa: roughly the same size, Alexa is heavier, and "Alexa talks to Jeff
  Bezos" — i.e., the privacy/local-control advantage is the point (paraphrase).

## Notable verbatim quotes

> "this makes me so excited for the future of owning your own stuff running everything
> locally and getting rid of this thing Alexa"

> "making your own voice assistant with the Raspberry Pi not for the faint of heart it's
> not crazy hard and I show you how to do it in this video ... but it's still a barrier to
> entry"

> "what this means for us is that we no longer have to rely on ourselves to make devices
> which I don't mind doing but I know for many people that is a barrier to entry"

> "let's let's compare it to Alexa real quick ... Alexa's heavier and Alexa talks to Jeff
> Bezos so we don't like that"

> "you can say stop oh my gosh that's a big deal ... you don't even have to say like Alexa
> stop which is kind of annoying"

> "so llama's just dumb that might be what it is because chat GPT had no problem with that"

> "they did send this to me they did not pay me at all they just said hey you want this
> and I'm like please ... no video required to make for them so this is all my opinions"

> "I'm a terrible product reviewer ... I love everything and I get too excited about what
> it does and I don't care about what it doesn't do"

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
