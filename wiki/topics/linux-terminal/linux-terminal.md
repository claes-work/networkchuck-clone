---
type: hub
domain: linux-terminal
created: 2026-07-14
updated: 2026-07-23
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

- **Terminal-first philosophy — "never leave the terminal."** (2024-09-06) Chuck leans into the idea that a serious Linux user can do almost everything without leaving the command line, showcasing CLI replacements for GUI tasks (including a text-based web browser) so work stays inside the terminal. The through-line: the terminal isn't a fallback, it's the preferred environment. [[../../sources/2024-09-06-yt-6h9sjYm9vTE]]

- **Pro-desktop-Linux stance — forcing the team off Windows/Mac.** (2024-08-07) Chuck moves his whole team onto desktop Linux, standing up a ThinLinc/Ubuntu 20.04 terminal server so everyone works in a Linux environment (with terminal access central to it). He's honest about the friction — desktop Linux isn't frictionless — but treats the switch as worth it, extending the "learn by living in it" ethos from the Pi to the daily-driver desktop. [[../../sources/2024-08-07-yt-qdo5lMR1lX4]]

- **Linux on Windows / Windows on Linux — WSL2, Win-KeX, and VMs.** (2024-07-03) Chuck walks through running the two OS families inside each other: WSL2 for a real Linux command line on Windows, Kali's Win-KeX for a Kali desktop over WSL, and full VMs for the reverse — practical bridges that let you get a Linux terminal without abandoning your existing machine. [[../../sources/2024-07-03-yt-vxTW22y8zV8]]

- **Clipboard-to-pipeline plumbing — xclip + pbcopy/pbpaste aliases.** (2024-05-17) In his `fabric` AI workflow, Chuck wires the system clipboard into the command line: `xclip`-based `pbcopy`/`pbpaste` aliases (macOS-style names on Linux) so he can pipe copied text straight into CLI tools and pipe results back out — a concrete example of treating the clipboard as just another stream in a Unix pipeline. [[../../sources/2024-05-17-yt-aMzdeZ8vGXQ]]

- **Modernizing the toolbox — 37 Linux commands/tools for 2025.** (2025-05-22) Chuck rounds up modern command-line tools that update or replace the classic utilities, pitching a refreshed CLI toolkit for 2025 — reinforcing that the terminal keeps evolving and it's worth periodically upgrading your daily commands. [[../../sources/2025-05-22-yt-6P-vjgPx9ww]]

- **Hiding files from the command line.** (2024-09-16) Chuck demonstrates Linux/CLI methods for hiding files "like a hacker," using the shell and filesystem tricks as the vehicle — command-line know-how framed through a security lens (also cross-listed under cybersecurity). [[../../sources/2024-09-16-yt-VcqtWsbSbgU]]

Related domains: the Pi/homelab hardware and self-hosting angle lives in [[../homelab-selfhosting/homelab-selfhosting]]; the Kali/ethical-hacking material is covered under [[../cybersecurity/cybersecurity]]; automation, Docker, and Ansible tooling built on top of Linux sit in [[../cloud-devops/cloud-devops]].

## Source pages

- (2017-12-19) [[../../sources/2017-12-19-yt-TCQdJwLMqfY]] — Should I Learn LINUX with the CCNA | CCNP?
- (2018-11-23) [[../../sources/2018-11-23-yt-rPjtZUBBPEU]] — Re-Learning IT after MEMORY LOSS (interview w/ Shawn Powers)
- (2019-08-27) [[../../sources/2019-08-27-yt-q7HkIwbj3CM]] — Hacking PUBLIC WiFi with a Raspberry Pi and Kali Linux
- (2020-02-28) [[../../sources/2020-02-28-yt-vbaJcRxASo0]] — How to Setup a Raspberry Pi LEARNING Desktop (Linux, Hacking, Coding)
- (2024-05-17) [[../../sources/2024-05-17-yt-aMzdeZ8vGXQ]] — fabric AI workflow (xclip + pbcopy/pbpaste clipboard piping)
- (2024-07-03) [[../../sources/2024-07-03-yt-vxTW22y8zV8]] — Linux on Windows / Windows on Linux (WSL2, Win-KeX, VMs)
- (2024-08-07) [[../../sources/2024-08-07-yt-qdo5lMR1lX4]] — Forcing my team onto desktop Linux (ThinLinc/Ubuntu 20.04 terminal server)
- (2024-09-06) [[../../sources/2024-09-06-yt-6h9sjYm9vTE]] — Never leave the terminal
- (2024-09-16) [[../../sources/2024-09-16-yt-VcqtWsbSbgU]] — Hide files like a hacker (Linux/CLI methods)
- (2025-05-22) [[../../sources/2025-05-22-yt-6P-vjgPx9ww]] — 37 modern Linux commands/tools for 2025
