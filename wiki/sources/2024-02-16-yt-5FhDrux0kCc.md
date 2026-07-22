---
type: youtube-video
source_date: 2024-02-16
url: https://www.youtube.com/watch?v=5FhDrux0kCc
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [homelab-selfhosting]
tags: [single-board-computer, mini-pc, raspberry-pi-alternative, homelab, hardware]
---

# I ditched my Raspberry Pi for this

## Summary

Chuck speed-runs building a combined travel NAS and travel router the night before flying his wife and six kids to Japan for a 14-hour flight. His previous travel setups were built on Raspberry Pi — a Pi router running OpenWRT and a Pi NAS running OpenMediaVault. This time he wants more (Plex streaming to the whole family, backing up vlog footage to the studio, extra Docker containers and VMs) and decides the Pi can't handle it. He reaches for a **ZimaBoard** (an x86 single-board computer he'd been sent for free, no strings attached) as the Raspberry Pi alternative, and documents a chaotic trial-and-error journey through multiple operating systems and router approaches before landing on a working solution. The video is framed as a real deadline-driven build with a "Chuck from the future" narration recorded after returning from Japan.

The core takeaway: the ZimaBoard being **x86 instead of ARM** unlocks options the Pi can't run (Proxmox, TrueNAS, PfSense, virtualized routers), but under time pressure the fancy virtualized approaches all failed, and Chuck ended up with the OS the board shipped with (CasaOS) plus a dedicated GL.iNet travel router — the "boring" default combo that actually worked.

## Key claims (paraphrase, dated 2024-02-16 unless noted)

- **The alternative is the ZimaBoard**, an x86 single-board computer Chuck received free from the company (disclosed as a no-strings gift). The unit is the "8/32" model: Intel Celeron quad-core, 8 GB RAM, 32 GB onboard eMMC storage. It's roughly the same size as a Raspberry Pi 5 and ships already in a case.
- **Why switch from the Pi: x86 vs ARM.** Because the ZimaBoard is x86 (not ARM like the Pi), it isn't limited to ARM-friendly OSes like OpenMediaVault and OpenWRT — it can run desktop/server x86 software including Proxmox, TrueNAS and PfSense. Chuck says he was "kind of full of Raspberry Pi" and wanted something more powerful and more fun.
- **Hardware that excited him:** two SATA connections (ideal for a NAS), two Ethernet ports, USB, and a PCIe slot (which sticks out the side of the case). The PCIe slot means expandability — more USB ports, a 10-gig NIC, or a WiFi 6 card for router use. It also supports nested virtualization.
- **Router attempt 1 — PfSense: rejected.** Chuck considered PfSense but skipped it because the common advice is to not run PfSense with wireless capabilities (wireless was an afterthought in PfSense, not what it's built for).
- **Router attempt 2 — virtualized OpenWRT on Proxmox: failed.** OpenWRT installs directly on the ZimaBoard, but Chuck wanted a virtualized image (harder). He got it running but couldn't get drivers working (USB adapter, PCIe, WiFi 6 antenna) in the ~1 hour he had.
- **Router attempt 3 — RaspAP in a Proxmox VM: partially worked, then abandoned.** RaspAP does much of what OpenWRT does but installs on any OS. He got a USB WiFi antenna working (PCIe pass-through struggled), running a wireless router in a VM on the ZimaBoard on Proxmox — but kept losing connection and devices wouldn't reconnect. No time to troubleshoot.
- **Router solution that shipped: a GL.iNet gigabit travel router.** Purpose-built for travel, runs OpenWRT with an easy "pretty wrapper" GUI. Setup is "stupid easy" — pick the WiFi/Ethernet uplink, choose the WiFi network to broadcast, done. Tradeoff vs the all-in-one dream: it's a second physical device rather than everything virtualized on the ZimaBoard, but reliability and simplicity won under deadline.
- **Proxmox on the ZimaBoard works**, installed to an external SSD (image to USB, boot, install — same as anywhere). Lesson learned: to get PCI pass-through, you must enable IOMMU / VT-d in the BIOS *before* installing Proxmox; Chuck's first install didn't work until he enabled those BIOS settings and reinstalled.
- **NAS attempt — TrueNAS: failed at the finish line.** Following YouTuber Nova Spirit Tech, Chuck installed TrueNAS (his first time) on the ZimaBoard with two 2 TB SATA SSDs via a Y-connector. Storage setup worked; Plex was the problem. TrueNAS installs Plex via Kubernetes, which pulls the newest image from GitHub on every deploy — and when it can't reach GitHub, it won't boot. It failed during his midnight test with his daughters because it couldn't reach GitHub offline.
- **NAS solution that shipped: CasaOS** — the OS the ZimaBoard ships with, a "pretty wrapper" on top of Debian 11 with a web GUI and an app store (mostly Docker apps). He'd initially dismissed it wanting something more custom, but it just worked. The two SSDs were plug-and-play (one for Plex, one for NAS); the only downside is he couldn't combine them into one pool without a beta feature he didn't want to risk on the trip.
- **Syncthing for offsite backup.** Instead of Synology/Google Drive syncing, he installed Syncthing (Docker) on both the travel NAS and his studio NAS; adding the remote device ID connected them directly over the internet with no VPN, and they synced (send-only for his use case). He calls it possibly his new go-to for all syncing.
- **Final travel network diagram:** ZimaBoard (two SSDs via SATA Y-connector) hardwired via Ethernet into the GL.iNet travel router. The GL.iNet handled DHCP (with a reservation for the ZimaBoard at 10.19.7.19) and broadcast a WiFi network ("fam"). The ZimaBoard also ran Pi-hole (Docker) for DNS, plus Uptime Kuma and Smokeping to monitor connection health. Uplink priority: hardwire into the Airbnb/hotel router when possible, otherwise use the GL.iNet's client mode to join the venue WiFi.
- **It worked in the field:** used on the 14-hour flight (device under the seat), on trains, in hotels and Airbnbs throughout Japan; kids streamed Plex (notably Bluey) to their iPads, and footage synced back to the studio overnight.

## Notable verbatim quotes

> "This thing is not ARM-based. It's X 86, which means we can do so much more than we can do with the pie. We're not limited to open media vault and open WRT."

> "It's the zema board or the Zema board. I'm not really sure how you say it. This thing is kind of a beast."

> "This is dumb and by dumb I mean amazing. It has two sayta connections. Are you kidding me? I want to build a NAS and it's got sayta connections. I'm already drooling."

> "Honestly, I'm kind of full of raspberry pie. I've had too much. I want to try something new and something I think is more powerful and maybe more fun."

> "You look anywhere, people say, do not run PF sense with wireless capabilities. Just don't do it. It wasn't meant for that. It was an afterthought."

> "I'm running a wireless router inside a virtual machine on a zema board on Prox Mox. That's just cool, right?"

> "It's stupid easy. You turn it on, you select what wifi network you want to connect to, and you choose what wifi network you want to broadcast, click, click, click, it's done. That's what I need on a trip where I'm taking my family to Japan, something easy and stupid."

> "When you're in a rush and you're just trying to get things to work, that's how most hacks happen in those moments. Always plan and slow down, except when you're about to get on the plane to Japan, then just go crazy."

> "Just by adding that remote device with that device id, they magically over the internet found each other. No VPN. And they started syncing."

> "Bluey kind of saved our lives a little bit while in Japan, but this worked like a charm."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
