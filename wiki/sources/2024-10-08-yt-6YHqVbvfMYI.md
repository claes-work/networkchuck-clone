---
type: youtube-video
source_date: 2024-10-08
url: https://www.youtube.com/watch?v=6YHqVbvfMYI
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [homelab-selfhosting, networking]
tags: [ntp, time-server, gps, stratum-1, homelab]
---

# so...I put a Time Server in my HomeLab

## Summary

Chuck builds a self-hosted stratum-1 time server in his studio homelab so his network
can get accurate time from his own hardware instead of reaching out to external servers
on the internet. The device is the **Open Time Card Mini** from Time Beat (which had
sat unused in his closet for 18 months): a GPS/GNSS module (u-blox) that receives time
signals from GPS satellites carrying atomic clocks, with a **Raspberry Pi CM4** (compute
module) on top acting as the server, mounted on a CM4 PCIe I/O board so it can slot into
any server via a PCIe slot (for power). It ships plug-and-play with Time Beat software
pre-installed; all it needs is a GPS antenna and power.

The video doubles as a concept explainer. Chuck walks through the history of timekeeping
(sundials → water clocks → mechanical → pendulum → quartz → atomic → GPS), how computers
keep time (quartz RTC + CMOS battery) and why they **drift** (1-2 seconds/day, up to ~10),
why accurate synced time matters, and the two protocols: **NTP** (millisecond accuracy,
what most systems use) and **PTP / Precision Time Protocol** (microsecond-to-nanosecond
accuracy). He explains stratum levels (stratum-1 talks directly to an atomic clock;
each hop away adds latency), PTP mechanics (grand master, boundary clocks, transparent
clocks, multicast "who has the best time" election, hardware timestamping on the NIC,
frequent sync messages), and PPS (pulse-per-second from the GPS module).

The build hits real troubleshooting: the GPS antenna gets no satellite lock inside the
server room or on the couch (raw NMEA data shows all nines), so Chuck ends up putting the
antenna **outside** to get a fix. He configures Time Beat via its YAML file, deploys the
monitoring stack (Elasticsearch + Grafana via a Kubernetes Helm chart), installs Time Beat
as a client on his 45Drives Proxmox servers, verifies NIC hardware timestamping support
with `ethtool -t`, fixes a firewall issue (allow PTP on UDP 319/320), and reaches
nanosecond-level sync once client-side hardware timestamping is enabled. He also sets up
NTP for non-PTP systems using **chrony**, and repoints Windows' internet-time source to
his own self-hosted stratum-1 server (`time.HogwartsStudio...`). He notes Time Beat also
sent a **PTP Mini grandmaster** (same CM4 internals, in a box, not PCIe) which he plans to
run as a second source.

## Key claims (paraphrase; dated 2024-10-08)

**Concept — how time works and NTP/PTP:**
- Computers keep time while powered on via the CPU/OS, and while powered off via a quartz
  crystal RTC (real-time clock) kept charged by the CMOS "watch" battery.
- A quartz crystal vibrates at a constant 32,768 times per second when an electrical signal
  is applied; this same oscillation is used in computer RTCs.
- RTC clocks **drift** ~1-2 seconds per day (up to ~10) due to temperature, crystal
  imperfections, aging, power supply, and electromagnetic interference — so devices need
  external synchronization.
- **NTP** (Network Time Protocol, invented by David Mills) syncs time across the internet
  over **UDP port 123**, achieving ~1-10 millisecond accuracy; clients poll every 64-1024
  seconds (configurable).
- **Stratum** levels describe distance from the atomic-clock source: a **stratum-1** server
  talks directly to an atomic clock (e.g. `time.nist.gov` fed by NIST's cesium atomic clock
  in Boulder, Colorado); a **stratum-2** server syncs from a stratum-1 (e.g.
  `time.windows.com` is stratum-2). Stratum can go to 15; more hops = more latency.
- **PTP** (Precision Time Protocol) achieves microsecond-to-nanosecond accuracy. It uses
  multicast messages for a "best clock" election, designates a **grand master** (the most
  accurate source), and can use **boundary clocks** (a switch relaying/offloading time to
  clients) and **transparent clocks** (a switch that measures its own packet-processing
  delay and corrects the timestamp before forwarding).
- PTP's speed comes from **hardware timestamping** on the NIC — capturing the exact send/
  receive time at the hardware level to bypass software delays. NICs must support it; the
  Raspberry Pi CM4 and Pi 5 support hardware timestamping, but the Pi 4 does not.
- PTP grand masters send sync messages far more often than NTP — as frequent as every 2s,
  1s, or subsecond (down to every 125 ms).
- Accurate time matters practically: `apt update` failed because the clock was out of sync;
  security/TLS, software, and website access all break with bad time (you can also be
  "time hacked").
- Industries needing this precision: financial trading (buy/sell in nanoseconds), NASA,
  and broadcast (syncing multiple audio/video sources). Meta spearheaded the open-source
  **Time Appliance Project (TAP)**, with Time Beat contributing.
- Scale intuition (from Ian at Time Beat): a million seconds ≈ 12 days; a billion seconds
  ≈ 32 years — illustrating the millisecond-vs-nanosecond gap.

**The build:**
- Hardware: Open Time Card Mini (Time Beat) = u-blox GPS/GNSS module + Raspberry Pi CM4
  server + CM4 PCIe I/O board; a standard magnetic GPS antenna bought on Amazon plus an
  SMA-to-TNC adapter.
- Setup requires only the antenna and a power source (PCIe slot provides power); tested
  first in a ZimaBoard PCIe slot, then moved into a 45Drives Proxmox server.
- GPS antenna got no satellite lock indoors (server room, couch) — raw serial NMEA output
  read via `minicom` on `/dev/ttyS0` showed all nines; a lock was only achieved with the
  antenna **outside**.
- The **PPS (pulse-per-second)** signal from the GPS module — precisely aligned to the
  satellites' UTC atomic-clock time — is the Pi's primary reference, acting like the
  oscillation source (analogous to the quartz crystal/pendulum).
- Time Beat software (pre-installed, configured via a YAML file) runs the device as a
  PTP server-only grand master; it can also run as a client on Windows and Linux.
- Monitoring: Time Beat provides an Elasticsearch database + Grafana front end, deployed
  via a Kubernetes Helm chart, showing the offset shrinking from millisecond to nanosecond.
- Client setup on a 45Drives server: verify NIC PTP support with `ethtool -t <iface>`,
  install Time Beat, enable clock adjustment + hardware timestamping, point to the
  interface (`eno1`); nanosecond sync only appeared after enabling client hardware
  timestamping.
- Firewall must allow PTP traffic on **UDP 319 and 320** (a firewall block prevented
  clients from syncing).
- For non-PTP systems, Chuck uses **chrony** for NTP and repoints Windows' internet-time
  server (Control Panel → Date and Time → Internet Time) to his self-hosted stratum-1
  (`time.HogwartsStudio`, set up via internal DNS). He chose not to expose it publicly.
- Alternatives mentioned: **PTP4L (PTP for Linux)**, but Chuck considers Time Beat better
  for reaching nanosecond accuracy. Time Beat also sent a **PTP Mini grandmaster** (same
  CM4 internals, boxed, full-size HDMI, external power, not PCIe) he plans to run as a
  second source. Chuck repeatedly admits he doesn't actually need this precision — "I
  don't really need it at all, but I want it."

## Notable verbatim quotes

> "I'm installing a time server in my studio... typically to receive time we talk to
> another server somewhere else outside our network. I don't want to do that anymore. I
> want to host it myself and talk to my own server."

> "This is the Open Time Card and it's kind of crazy. It has a GPS module that receives
> signals from satellites with atomic clocks."

> "There's a problem that plagues time. It's called drift, not Tokyo Drift. This is the
> bad kind."

> "He's a stratum one NTP server because he's talking directly to this atomic clock...
> He's not relying on his RTC chip. No, no, he's talking to the big guy."

> "PTP does a thing called hardware timestamping... it'll capture the exact time a packet
> is sent or received and stamp it with the time on the NIC hardware level. This bypasses
> any delays that you might experience through software."

> "A million seconds is 12 days, a billion seconds is 32 years. And that makes it easier
> to understand that gap."

> "Do you see this 0.18 nanosecond accuracy. What even is that?"

> "Oh my gosh, we're in nanosecond level now. Yes. Oh, this is cool. Nanosecond level
> synchronization. I don't know why I'm so excited about this. I don't really need it at
> all, but I want it."

> "I always say this, if you don't track your time, then you don't know what you're doing."

> "I'm now using my own stratum one NTP server self-hosted in my studio."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT). (Ian and other Time Beat
staff are quoted/paraphrased by Chuck as sources; the video is narrated solely by Chuck.)
