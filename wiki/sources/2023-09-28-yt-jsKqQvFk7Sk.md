---
type: youtube-video
source_date: 2023-09-28
url: https://www.youtube.com/watch?v=jsKqQvFk7Sk
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [homelab-selfhosting]
tags: [raspberry-pi, raspberry-pi-5, hardware, review, maker]
---

# the Raspberry Pi 5

## Summary

Chuck reviews the newly announced Raspberry Pi 5 — the first new Pi flagship in four
years (the Pi 4 launched in 2019). He walks through the spec sheet (CPU, GPU, the new
in-house RP1 south-bridge chip, USB/PCIe/camera/RAM upgrades, the long-awaited power
button), installs the new active cooler, sets it up as a dual-4K desktop, then stress-tests
it: browsing, playing multiple YouTube videos, 4K file playback over his NAS, and a head-to-head
benchmark battle against the Pi 4 (sysbench CPU, Geekbench, Speedometer browser test, and the
Open Arena game for GPU). His verdict: the Pi 5 crushes the Pi 4 on every metric and is a usable
(if not flawless) desktop replacement, especially exciting for the projects the new PCIe interface
unlocks. The video reflects his long-running Raspberry Pi enthusiasm and ties back to how a Pi first
got him into Linux and IT.

## Key claims (dated — 2023-09-28)

- The Raspberry Pi 5 is the first new flagship Pi in four years; the Pi 4 came out in 2019. (paraphrase)
- Availability: expected to ship sometime in October 2023, in two models — 4GB at $60 US and 8GB at $80 US. No more 2GB model. (paraphrase)
- CPU: 2.4 GHz quad-core 64-bit Arm Cortex-A76; Raspberry Pi claims 2–3x the performance of the Pi 4. It also has cryptographic extensions to speed up security tasks like VPN/encryption. (paraphrase)
- GPU: 800 MHz VideoCore VII, supporting OpenGL ES 3.1 and Vulkan 1.2, driving dual 4K 60p HDMI output with HDR. (paraphrase)
- The RP1 is Raspberry Pi's own in-house-designed south-bridge chip controlling I/O (USB, ethernet, storage) between the CPU and external peripherals — Chuck frames it as the biggest thing about the Pi 5. (paraphrase)
- USB: two USB 2.0 and two USB 3.0 interfaces (like the Pi 4), but the USB 3.0 ports now run simultaneous 5 Gbit/s — a big deal for projects like a Pi NAS. (paraphrase)
- Camera/display interfaces: the old single 2-lane MIPI interface is replaced by a pair of 4-lane 1.5 Gbit/s MIPI transceivers, tripling total bandwidth and supporting up to two cameras or displays. (paraphrase)
- No onboard storage (which Chuck had hoped for), but peak SD card performance is doubled via SDR104 high-speed mode. (paraphrase)
- A PCIe 2.0 interface is added, opening the door to high-bandwidth peripherals (network cards, SSDs) — Chuck is especially excited about this for projects. (paraphrase)
- RAM upgraded to LPDDR4X-4267. (paraphrase)
- The power button — long on people's wishlist — is finally included; pressing it while running prompts shutdown/restart, and it powers the board on. Chuck is a huge fan and hates having to unplug/replug. (paraphrase)
- Connectivity: same dual-band 802.11ac WiFi and Bluetooth 5, now adding BLE (Bluetooth Low Energy). It also has a real-time clock (RTC) powered by an external battery to keep time when powered off. (paraphrase)
- The Pi 5 draws so much power and runs hot enough that Raspberry Pi made an active cooler (fan + heatsink) for it — Chuck believes this is the first time they've done so. During testing, the active cooling kept temps around 51°C under load. (paraphrase)
- Desktop feel: usable but not the snappiest; noticeable lag/stutter when pushing four YouTube videos or multitasking on dual 4K monitors. 720p and 1080p video play reasonably; full 4K playback (local and over the NAS) is laggy and "isn't working great." (paraphrase)
- Benchmark results (Pi 4 → Pi 5): sysbench single-thread ~700 → ~1000 events/sec; multi-thread (4 threads) ~28,000 → ~41,000. Geekbench single-core 258 → 597, multi-core 695 → 1530; crypto score 158 → 654; machine learning 189 → 284. Speedometer 2.0 browser test 19.2 → 54.6. Open Arena game (720p) was unplayable (~15 fps) on the Pi 4 but smooth on the Pi 5. (paraphrase)
- Overall verdict: the Pi 5 wins on every metric and is "ridiculous" in a good way; a solid choice for the average person or a kid learning to code. (paraphrase)
- Personal note: Chuck bought his first Raspberry Pi to learn Linux, which is how he got started in IT. (paraphrase)

## Notable verbatim quotes

> "This is the new Raspberry PI five and it's kind of amazing."

> "This thing is so powerful, they had to make an active cooler for it. Have they ever done that before? I don't know. It's got everything. We have a power button, frankly. That's all I needed to know. I'll take 20."

> "Now I think the biggest thing is the RP one. This is silicon design in-house by Raspberry Pi."

> "This also enables a big change in camera interfaces... This triples the total bandwidth supporting a combination of up to two cameras or displays."

> "They now have a P C I E 2.0 interface. This opens up a whole new world for high bandwidth peripherals... oh my gosh, the projects this opens up for us. Are you kidding me?"

> "The power button, it's here, it's finally here and it's a button. Press it and it does stuff."

> "I'm a huge fan of the power button. I hate having to unplug it and plug it back in. I feel like I'm breaking it every time."

> "In fact, that's what I did when I bought my first raspberry pie. It's why I bought it. I wanted to learn Linux and I did."

> "We tested the pies and clearly the PI five is just, it's ridiculous. It's the winner. It only took four years, but at least it came out in 2023 and not in 2024."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
