---
type: youtube-video
source_date: 2025-04-23
url: https://www.youtube.com/watch?v=6WYBvbn-mgQ
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [homelab-selfhosting]
tags: [zima-board, single-board-computer, x86, homelab, hardware, review]
---

# Can This Tiny Board Replace Your Entire HomeLab? – Zima Board 2

## Summary

Chuck reviews the ZimaBoard 2 (sent to him by Ice Whale / "Zima"), an x86 single-board
computer positioned as a compact, premium homelab server. He unboxes it, compares it to
the original ZimaBoard, walks through the upgraded specs, then builds a full homelab on
it live: Proxmox as the type-1 hypervisor, a pfSense firewall VM (with Snort IDS/IPS), an
Ubuntu desktop VM, and LXC containers (including Pi-hole). He dedicates both 2.5 GbE NICs
to pfSense via PCI passthrough, runs iperf throughput tests, and lands on an enthusiastic
verdict: the board can genuinely run a whole (or travel) homelab, with RAM as its single
real limitation. The video is not sponsored by Ice Whale ("they are not paying me for
this"); it carries a paid Incogni ad read on data brokers.

## Key claims (paraphrase unless quoted)

- (2025-04-23) The ZimaBoard 2 runs an Intel N150: 4 cores, boost up to 3.6 GHz — a solid
  processor upgrade over the original.
- (2025-04-23) The N150 uses Intel's Gracemont cores, which offer ~35–45% better IPC than
  the Goldmont architecture of the original's N3450; overall Chuck estimates the board is
  ~40–70% faster than its predecessor (new architecture plus more cache and speed).
- (2025-04-23) RAM: 8 GB LPDDR5X at 4800 MHz — same quantity as the original but roughly
  double the speed. A 16 GB model also exists (Ice Whale did not send Chuck that one).
- (2025-04-23) Networking: two 2.5 Gigabit Ethernet ports (vs one 1 Gbit port on the
  original), and an Intel NIC instead of the original's Realtek chip — the Intel chip
  enables hardware offloading, which Chuck highlights as ideal for a pfSense firewall.
  This is the main reason he was excited about the board.
- (2025-04-23) Expansion/IO: PCIe 3.0 slot (vs 2.0 on the original), USB upgraded from 3.0
  to 3.1, two SATA ports, two USB ports, DisplayPort, and same overall form factor as the
  original — but heavier because the case is now metal. Graphics frequency up to ~1 GHz
  (vs ~0.7 on the original). Supports both fanless and active cooling.
- (2025-04-23) It is x86 (not ARM like a Raspberry Pi), which is a big advantage: far more
  compatibility, and full virtualization support (VT-x / VT-d). This is why Proxmox
  installs on it where it wouldn't on ARM SBCs. Virtualization settings were enabled by
  default in the BIOS.
- (2025-04-23) The original ZimaBoard started at $89; the ZimaBoard 2 launched via
  Kickstarter with early-bird pricing for the first 200 orders (a base 8 GB model, a 16 GB
  model, plus bundles — e.g. a PCIe NVMe adapter + 2-bay HDD rack, a ~$400 smart-home kit
  with a low-power GPU docking station and Wi-Fi 6 adapter, and a ~$769 master kit). Exact
  figures came from a launch-day screenshot and are not clearly legible.
- (2025-04-23) Build/use: Chuck installs Proxmox to onboard storage + attached SATA SSDs,
  then runs a pfSense VM (2 cores, ~3 GB RAM, ~50 GB) with both 2.5 GbE NICs passed
  through via PCI passthrough; an Ubuntu desktop VM (2 cores, 3 GB RAM); and LXC containers
  (Rocky Linux, then Ubuntu running Pi-hole for DNS/ad-blocking). Snort provides IDS/IPS on
  pfSense with all rules enabled. He uses a Linux bridge ("VBR7") so Proxmox routes through
  pfSense as its own gateway after the NICs are dedicated to the firewall.
- (2025-04-23) Throughput testing (iperf): through a 1 Gbit unmanaged switch he saw ~100
  Mbit (switch was the bottleneck); connecting his laptop directly to the 2.5 GbE LAN port
  gave ~1.09 Gbit/s, and even with Snort IDS/IPS enabled he stayed around ~1.10 Gbit/s —
  though the CPU was pegged (spiking to ~107%) under heavy multi-stream load.
- (2025-04-23) Verdict: Chuck loves it. It can run a full network stack (Proxmox, pfSense,
  VMs, containers, IDS/IPS) on a tiny device and would make a great homelab, travel lab, or
  air-gapped network (e.g. running a UniFi controller + AP). The single biggest limitation
  is RAM — 8 GB with no easy upgrade path — so he'd recommend the 16 GB model for anyone
  doing what he did in the video.

## Notable verbatim quotes

> "So here's my verdict. I love this thing. It's not the most powerful SBC. This could be
> a portable app... This thing can run Proxmox, pfSense, containers, VMs. I've got a full
> network running right now with IDS and IPS enabled."

> "But the one limitation we have is RAM. I wish there was an easy way to upgrade the RAM
> here. I don't know if there is. I don't think there is. That's the biggest limitation
> here. If I just had 16 gigs of RAM, this thing would be amazing."

> "This right here is why I'm excited to use it as a firewall... this also is an Intel chip
> versus the Realtek chip on the first one."

> "Normally on SBCs you can't install Proxmox, like the Raspberry Pi... it's rocking an
> ARM-based CPU. But not the ZimaBoard 2, it's x86, which is one of its big advantages.
> Way more compatibility with pretty much everything."

> "It's amazing we're able to do all this on this little device. I know I'll keep saying
> that, but it kind of feels like magic, right?"

> "I think I actually might use this as my travel lab. Or if anything, use it as an air gap
> network... I could run a UniFi controller on this as a container. Plug in an AP and have
> a little air gapped WiFi network."

> "By the way, they are not paying me for this. They just sent it and said, hey, play with
> it. And I said, okay, let me get my coffee."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
