---
type: youtube-video
source_date: 2022-10-31
url: https://www.youtube.com/watch?v=X2YH-XyqyXE
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [homelab-selfhosting]
tags: [raspberry-pi, home-automation, maker, gpio, halloween, fun]
---

# I Built a HAUNTED HOUSE with Raspberry Pi

## Summary

A Halloween-themed maker/homelab project video in which Chuck Keith builds an
automated haunted house using a Raspberry Pi, Python, and cheap hardware. He walks
through escalating "spookiness levels": (1) playing a scary sound through speakers via
Python (triggered manually by an iPhone Shortcut over SSH), (2) hijacking a store-bought
animatronic Halloween prop by cutting its "try me" button wires and driving them with a
relay board wired to the Pi's GPIO pins, (3) automating the whole thing with a PIR
motion sensor and recording victims with the Pi Camera. He then shows an "extreme"
tier: pneumatic haunted-house props (a prop launcher, an ankle blaster, an air
compressor) from FrightProps, controlled via a "Pico Boo" relay device that he in turn
drives from the Raspberry Pi so the pro props can be scripted in Python. Throughout, the
video is interleaved with footage of Chuck scaring his family, friends, and trick-or-
treaters, and pitches ITProTV as sponsor (IT certifications framed as escaping a "scary
story" dead-end job). The whole build is presented as proof that learning tech is fun
and that a Raspberry Pi opens "a whole new world."

## Key claims (dated — the build + ethos)

- 2022-10-31: A Raspberry Pi Halloween haunted house can be built from a simple
  store-bought Halloween prop, a bit of "Raspberry Pi magic," and a little Python code.
- 2022-10-31: The project is layered into escalating spookiness levels — level one
  (sound only), level two (relay + prop), level three (motion sensor + camera), plus an
  "extreme" pneumatic-props tier shown later.
- 2022-10-31: Level one needs only a Raspberry Pi and computer speakers wired to the
  audio jack; a Python script (using `pygame`) plays a scary sound file. Chuck did a
  headless install with Raspberry Pi OS Lite 32-bit and SSHes in.
- 2022-10-31: `pygame.mixer` is initialized, a sound loaded via `pygame.mixer.Sound()`,
  volume set with `set_volume(1)` (~100%, loudest), and played with `.play()`. Chuck
  uses a zombie-scream sound in OGG format because it played nicely with the Pi; WAV
  should work too, and files can be converted with Audacity or Adobe Audition.
- 2022-10-31: With no motion sensor, the script can be triggered manually from an iPhone
  using the Shortcuts app — an "Run script over SSH" action that runs the Python script
  on the Pi at one button press.
- 2022-10-31: Animatronic props are activated by shorting two wires together. You rip
  off the "try me" button and cut/strip its two wires; larger animatronics instead use a
  1/8-inch jack step-pad whose wires do the same thing.
- 2022-10-31: A relay board makes the Pi short those two prop wires on command. It is
  wired to the Pi GPIO with female-to-female DuPont wires: ground to pin 39, VCC to pin 2
  (5V power), and IN1 to pin 37 (the trigger). Each relay terminal has its own IN pin.
- 2022-10-31: The relay is controlled in Python via `RPi.GPIO`: set board numbering
  mode, set the relay pin as output, then drive it `GPIO.HIGH` (open) and `GPIO.LOW`
  (close/connect the wires) — you can hear the relay click when it fires.
- 2022-10-31: A PIR motion sensor is wired to the Pi (ground to pin 6, power to pin 4
  at 5V, data to pin 35) and read in Python as an input; it prints `0` for no motion and
  `1` when motion is detected, inside a `while True` loop.
- 2022-10-31: Combining the sensor with the relay and sound: a `while True` loop with an
  `if something == 1` block fires the prop (HIGH then LOW), plays the sound, and sleeps
  between triggers so people can react.
- 2022-10-31: The Pi Camera captures the scares. Chuck enables legacy camera support via
  `raspi-config` (interface options) because it plays nicest with Python; tests with
  `raspistill -o test.png` and `raspivid`, converts H.264 to MP4 with GPAC's `MP4Box`,
  and installs `python3-picamera` to record on motion.
- 2022-10-31: To avoid overwriting recordings, each clip is saved with a timestamped
  filename built from Python's `datetime.now()` cast to a string.
- 2022-10-31: Other triggers are possible too — Chuck mentions a vibration sensor placed
  inside a candy bowl so a scare fires when kids reach for candy.
- 2022-10-31: The "extreme" tier uses legit pneumatic haunted-house props from a website
  called FrightProps (a prop launcher and an ankle air blaster), powered by a heavy-duty
  air compressor and switched by a "Pico Boo" — described as a simpler/"dumber" Pi-like
  device with a built-in relay. Chuck connects the Pico Boo to his Raspberry Pi so the
  pro props can be controlled with Python.
- 2022-10-31: Chuck claims real haunted houses trigger props the same basic way (relay-
  switched) but are generally less sophisticated than his Python setup — he says he
  toured haunted houses and talked to the operators to confirm.
- 2022-10-31: Ethos: discovering the Pi could do this "blew my mind" and "opened up a
  whole new world"; the GPIO pins are "those little pokey spiny things you always
  ignore" that are actually "amazing." The whole video frames tech as play — building
  something fun teaches Raspberry Pi, Python, GPIO, sensors, and relays hands-on.
- 2022-10-31: Sponsor pitch: ITProTV; framed via a "scary story" of a beardless man
  stuck selling toilets who never studied — versus getting A+, CCNA, AWS, and hacking
  certifications to land a better IT job. Code `networkchuck` for 30% off "forever."
- 2022-10-31: Chuck credits his wife (for tolerating the craziness and buying/decorating
  props), his team ("Wave team"), and a handyman named Luke who built him a coffin;
  he admits he "spent way too much time on this."

## Notable verbatim quotes

> "In this video I'm gonna show you how to build a raspberry pie haunted house. And all
> you'll need is a simple Halloween prop, some raspberry pie magic and a little bit of
> python code."

> "when I found out raspberry pies could do this, this blew my mind, opened up a whole
> new world."

> "well wire this motion sensor up to the G P I O pins on our raspberry pie, which are
> all those little pokey spiny things on your raspberry pie that you always ignore. But
> now we're gonna use, cause they're amazing by the way"

> "How cool is that? ... Isn't that cool? Oh that's magic."

> "that's how most haunted houses, if you're a fan of haunted houses like I am, will
> trigger their props. But I guarantee you they're not as sophisticated as us using
> Python."

> "what you're about to see here ... is a lot of python fun, powering a bunch of
> different props, recording videos. It's, I got a little crazy this year. I spent way
> too much time on this."

> "You can start studying right now and get it certifications that will change your
> life. ... they are here to make sure that your life isn't a scary story."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: tech-is-fun maker ethos (Pi home automation) -->
