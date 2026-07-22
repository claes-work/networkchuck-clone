---
type: hub
domain: linux-terminal
created: 2026-07-14
updated: 2026-07-22
---

# Linux & Terminal — hub

Linux, bash, the command line, and sysadmin skills — making the terminal approachable for IT beginners.

## Key ideas & topics

- **Linux belongs on every network engineer's skill list.** (2017-12-19) Chuck answers "should I learn Linux with the CCNA/CCNP?" with an unqualified yes, grouping Linux alongside Python and networking as the skill set of the "next generation network engineer." His reasoning is practical: most of Cisco's newer products (security appliances, Firepower, Collaboration/Call Manager) are Linux-based, Nexus data-center switches run a Linux file system, and the majority of the world's web servers run on Linux — so back-end work eventually requires it. [[../../sources/2017-12-19-yt-TCQdJwLMqfY]]

- **Linux as the "gateway drug" — discovered via Cisco backends.** (2017-12-19) Chuck describes himself as no Linux expert, but says knowing "a little bit" has repeatedly helped his career — especially with Collaboration, where every app runs on Red Hat Linux. His own Linux use grew organically out of networking work: running OpenVPN on a Debian box, scripting Python inside Linux, and administering Cisco gear whose backends are Linux. The certification track pulled him into Linux, not the other way around. [[../../sources/2017-12-19-yt-TCQdJwLMqfY]]

- **"Just get started" — the barrier is low.** (2017-12-19) Chuck stresses that Linux is "really easy to get started": download VirtualBox, grab an Ubuntu ISO, install it, and just play. He advises CCNA beginners not to stress about Linux early (it's "a whole new world," like learning Windows for the first time) and to fold it in post-CCNA / pre-CCNP — maybe a day a week. (2018-11-23) He reinforces this in the Shawn Powers interview: free YouTube videos, courses, and VMs let you sandbox installs risk-free, making learning Linux today far easier than it used to be, and he notes Linux admin roles are lucrative precisely because Linux is a rarer skill than Windows. [[../../sources/2017-12-19-yt-TCQdJwLMqfY]] · [[../../sources/2018-11-23-yt-rPjtZUBBPEU]]

- **Raspberry-Pi-as-learning-lab ethos.** (2020-02-28) Chuck's signature framing: a $35 Raspberry Pi "might be the best thing to learn Linux, hacking, programming." The cheap price is the whole point — at $35 he "can stomach that price of letting them just have at it," including letting his kids break it, because kids often break things. Learning happens by doing, on hardware disposable enough to experiment fearlessly. [[../../sources/2020-02-28-yt-vbaJcRxASo0]]

- **The Pi learning-desktop setup (hands-on command line).** (2020-02-28) Chuck turns a Raspberry Pi 4 into an "ultimate learning desktop" for his homeschooled kids, teaching real terminal skills along the way: BerryBoot to run multiple Linux flavors from one SD card, Raspbian as the daily driver, per-user accounts created with `sudo adduser` (and verified via `cat /etc/passwd`), `sudo` as "godlike master permission," disabling autologin by editing `/etc/lightdm/lightdm.conf`, converting to a static IP in `/etc/dhcpcd.conf`, and enabling SSH + VNC via `sudo raspi-config` for remote access from iPads. The `sudo apt update` → `sudo apt install` workflow is used throughout. He also notes you don't need Kali Linux to hack — Kali's tools install fine on Raspbian. [[../../sources/2020-02-28-yt-vbaJcRxASo0]]

- **Kali Linux on a Pi as a portable hacking station.** (2019-08-27) Chuck runs Kali Linux on a credit-card-sized Raspberry Pi as a full "hacking station" to demonstrate public-WiFi attacks (evil twin, deauth, ARP/man-in-the-middle) — reinforcing the Linux command line as the environment where security work actually happens, and doubling as motivation to learn Linux by doing something exciting (with permission). [[../../sources/2019-08-27-yt-q7HkIwbj3CM]]

Related domains: the Pi/homelab hardware and self-hosting angle lives in [[../homelab-selfhosting/homelab-selfhosting]]; the Kali/ethical-hacking material is covered under [[../cybersecurity/cybersecurity]]; automation, Docker, and Ansible tooling built on top of Linux sit in [[../cloud-devops/cloud-devops]].

## Source pages

- (2017-12-19) [[../../sources/2017-12-19-yt-TCQdJwLMqfY]] — Should I Learn LINUX with the CCNA | CCNP?
- (2018-11-23) [[../../sources/2018-11-23-yt-rPjtZUBBPEU]] — Re-Learning IT after MEMORY LOSS (interview w/ Shawn Powers)
- (2019-08-27) [[../../sources/2019-08-27-yt-q7HkIwbj3CM]] — Hacking PUBLIC WiFi with a Raspberry Pi and Kali Linux
- (2020-02-28) [[../../sources/2020-02-28-yt-vbaJcRxASo0]] — How to Setup a Raspberry Pi LEARNING Desktop (Linux, Hacking, Coding)
