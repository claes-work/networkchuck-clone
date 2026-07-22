---
type: youtube-video
source_date: 2020-02-28
url: https://www.youtube.com/watch?v=vbaJcRxASo0
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [linux-terminal, homelab-selfhosting]
tags: [raspberry-pi, linux, learning, hacking, coding, desktop, tutorial]
---

# How to Setup a Raspberry Pi LEARNING Desktop (Linux, Hacking, Coding)

## Summary

A hands-on tutorial in which Chuck Keith, with help from his daughters, turns a Raspberry Pi 4 into an "ultimate learning desktop" for his homeschooled kids to learn Linux, hacking, and programming. The video walks through the full setup: formatting a microSD card, installing the BerryBoot bootloader to run multiple Linux flavors from one SD card, configuring Raspbian, disabling auto-login and creating per-user accounts from the command line, enabling remote access (SSH + VNC) with a static IP so the kids can log in from their iPads, and installing hacking tools (Yersinia, Ettercap) directly on Raspbian without needing Kali Linux. He closes with a candid assessment of the Pi 4 as a daily-use machine — great for learning, browsing, and light coding, not a power-user replacement — framed around the ethos that a $35 device is cheap enough to let kids experiment and even break.

## Key claims (dated — 2020-02-28)

- Chuck says the Raspberry Pi "might be the best thing to learn Linux hacking programming" — his core reason for using it. (paraphrase)
- He and his wife homeschool their kids, and he wants them to learn Linux and become hackers and programmers; he's building the Pi into a learning desktop for them. (paraphrase)
- Recommended hardware: a Raspberry Pi 3 or 4 (he wouldn't go below a Pi 3), a 16–32 GB microSD card (32 preferred), a USB SD adapter, power cable, monitor, keyboard, mouse, and a second computer to prep the SD card. (paraphrase)
- Setup flow for the SD card: format it fresh using the SD Memory Card Formatter tool from the SD Association (available for Windows and Linux), then extract the downloaded BerryBoot zip and copy its full contents onto the freshly formatted card. (paraphrase)
- BerryBoot is a bootloader that lets you boot and run multiple flavors of Linux from a single SD card without swapping cards; there is a separate download for the Pi 4 vs. the Pi 3, and getting the right one matters. (paraphrase)
- BerryBoot can also boot an OS from network-attached storage (a remote NAS), not just the local SD card. (paraphrase)
- He recommends buying a Pi kit (with heat sinks, fan, case) to make setup easy, but notes none of it is required — he often runs Pis "naked" and they're usually fine. (paraphrase)
- First OS choice is Raspbian (the Debian-based OS built for the Pi), full version, installed over the network — this is the kids' main driver. (paraphrase)
- Wi-Fi configured in the BerryBoot menu carries over automatically into Raspbian. (paraphrase)
- Raspbian boots straight into the "pi" user with no login screen by default; to get per-user logins he edits `/etc/lightdm/lightdm.conf` with `sudo nano` and comments out the `autologin-user=pi` line. (paraphrase)
- He creates per-child accounts on the command line with `sudo adduser <name>` (e.g. "Chloe Panda", "Addie Pig"), setting each child's own password; `adduser` without sudo fails because only root can add users. (paraphrase)
- Accounts can be verified by reading `/etc/passwd` with the `cat` command. (paraphrase)
- Non-pi users lack pi's permissions; to make system changes as another user, impersonate pi with `su pi` — the default password for pi is "raspberry" (which he recommends changing). (paraphrase)
- Remote access is enabled via `sudo raspi-config` → Interfacing Options → enabling SSH (command-line remote) and VNC (for iPad access). (paraphrase)
- To keep remote access reliable, he converts the Pi from DHCP (dynamic IP) to a static IP by editing `/etc/dhcpcd.conf` — uncommenting and setting the interface (wlan0 for Wi-Fi), static IP address (/24), static router/gateway, and DNS (he uses Google's 8.8.8.8). (paraphrase)
- He notes a static IP can also be set via the GUI (right-click Wi-Fi icon → wireless & wired network settings) but must be done as the pi user — it edits the same `dhcpcd.conf` file behind the scenes. (paraphrase)
- He changes the pi user's default password with `passwd` for security, prompted by the login warning that SSH is enabled with the default password unchanged. (paraphrase)
- Kids remote in from iPads using the free VNC app by entering the Pi's IP address. (paraphrase)
- You don't need Kali Linux to hack: the tools pre-installed on Kali can be installed on other distros, so he installs Kali-style tools directly on Raspbian. (paraphrase)
- Install workflow: run `sudo apt update` first to refresh the package list, then `sudo apt install <tool>`. He installs Yersinia (a network attack tool for Cisco switches/routers, runnable in GUI mode with `-G`) and Ettercap (for man-in-the-middle attacks, also with a `-G` graphical mode). (paraphrase)
- Verdict on the Pi 4 (4 GB RAM model): not a true desktop replacement for a power user, but perfect for daily learning tasks — Linux, hacking scripts, coding, web browsing, editing documents, even Minecraft and YouTube video playback. A web-based coding app (Tinkercad) loaded but slowly. (paraphrase)
- Learning-lab ethos: at $35 he can "stomach that price of letting them just have at it," including letting the kids break it — because kids often break things. (paraphrase)

## Notable verbatim quotes

> make that work the Raspberry Pi for this little tiny device might be the best thing to learn Linux hacking programming and that's exactly what I'm going to use mine for

> my wife and I we homeschool our kids and I want them to learn Linux I want them to become hackers and programmers and everything and I'm gonna turn this guy into a desktop for them to learn

> berry boot and boot loader which allows us to have multiple flavors of Linux such a cool thing to do

> make sure you do sudo or su do however people say it to make sure you have godlike master permission this gives you authority every time you execute a command in Linux

> you don't need Kali Linux — heck why is that well because all the tools that you have pre-installed on Kali you can install those on other Linux distributions which means we can install Kali tools on raspbian

> y'all don't come to my house I got people hacking with raspberry PI's now

> can it be a true desktop replacement for a power user no no it won't be because you'll be doing a lot more than what this little guy can handle but for daily tasks like learning Linux or trying a few hacking scripts or learning coding this thing's perfect

> so for $35 I can stomach that price of letting them just have at it

> this is the perfect device for my kids to learn and play around and tinker with things and and possibly even break it because kids often break things

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: Raspberry-Pi-as-learning-lab ethos -->
