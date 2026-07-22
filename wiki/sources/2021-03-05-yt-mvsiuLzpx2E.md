---
type: youtube-video
source_date: 2021-03-05
url: https://www.youtube.com/watch?v=mvsiuLzpx2E
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, homelab-selfhosting]
tags: [hacking-lab, kali-linux, vms, metasploitable, pentest, learn-by-doing]
---

# how to build a HACKING lab (to become a hacker)

## Summary

Chuck walks a beginner through building a free, self-contained hacking/pentest lab on a
single laptop or PC — a "safe secure hacking environment" where you can attack real,
deliberately vulnerable web servers without breaking the law or exposing your home
network. The blueprint: run VirtualBox on your host, spin up two virtual machines — Kali
Linux as the attacker and an intentionally vulnerable target VM downloaded from VulnHub
(he uses the Mr. Robot box) — and then isolate both machines behind a VirtualBox
**internal network** with a manually created DHCP server so they can talk to each other
but not to the host or the internet. He proves the isolation by pinging across the
boundary (fails both ways), runs an Nmap scan from Kali to discover and fingerprint the
target, opens the target's web page in a browser, and then deliberately stops — leaving
the actual capture-the-flag exploitation to the viewer as the learn-by-doing exercise.
Sponsored by ITProTV, whose instructor Daniel Lowry attacking the same box inspired the
video.

## Key claims (dated — the lab blueprint + ethics)

All dated 2021-03-05 (source publication). Paraphrase unless quoted.

**Ethics / why isolate (the safety framing):**
- You can start hacking real servers right now "in a safe and secure environment where you won't get in trouble."
- VulnHub machines are *legitimately* vulnerable — putting them on your real home network could open you and your house to attack, because if they're vulnerable for you to attack, a more experienced hacker could use them to break into your network.
- The whole point of the lab is a boundary/wall between your laptop and the hacking environment: the VMs are isolated so the host cannot talk to them and they cannot talk to it or anything else.
- Targets are legal, downloadable, deliberately vulnerable VMs — not real third-party systems. Nothing outside the lab is touched.

**Hardware / prerequisites:**
- All you need is one computer (laptop or PC), at least 16 GB of RAM, and a decent internet connection to download the images. (Chuck runs it on a Razer Blade.)
- The entire environment is free.

**The blueprint (ordered steps):**
1. **Install VirtualBox** (free; Linux/macOS/Windows) plus the VirtualBox Extension Pack. VirtualBox creates both the attacker and target VMs.
2. **Download the images** early because they're large: the Kali Linux pre-built VirtualBox image (Chuck picks 64-bit), and a vulnerable machine from VulnHub (he chooses the Mr. Robot OVA).
3. **Import the OVA files** into VirtualBox (double-click each; rename if desired) — but do not power them on yet.
4. **Isolate the network.** In each VM's Settings → Network, change the adapter from NAT/Bridged to **Internal Network** and give both the same network name (his example: "malfoy"), so the two VMs share a private network cut off from the host and internet.
5. **Create a DHCP server for that internal network** (the isolated network has none, so VMs wouldn't get IPs). From a terminal in the VirtualBox install directory (`cd /program files/oracle/virtualbox` on Windows), run `VBoxManage dhcpserver add` specifying `--network`, `--server-ip`, `--lower-ip`, `--upper-ip`, `--netmask 255.255.255.0`, and `--enable`. His example uses server-ip 10.38.1.1 and a pool of 10.38.1.110–10.38.1.120.
6. **Boot the VMs.** Kali logs in with default user `kali` / password `kali`. Verify Kali pulled an IP with `ip address` (it gets 10.38.1.110). Confirm isolation: Kali cannot ping Google or the host, and the host cannot ping Kali.

**First hacking steps (enumeration, shown; exploitation left to viewer):**
- The vulnerable box's login is unknown by design — you must find it on the network rather than log in.
- Run `sudo nmap -sS -T4 10.38.1.110-120` from Kali to scan the range; it discovers the target at 10.38.1.111 with ports 22 (SSH), 80 and 443 (web) open, indicating a web server.
- Browse to the target's IP (10.38.1.111) to see the Mr. Robot-themed vulnerable web app.
- Chuck deliberately stops there so the viewer does the hacking themselves.

**Learning philosophy:**
- The target is a capture-the-flag (CTF): find three hidden flags (strings of text/data) in the file system using your hacking skills.
- Following a walkthrough is fine — as long as you actively learn *why* each attack works ("how did they know to do that, why did that work") rather than just copying.
- After finishing one box, download another from VulnHub and repeat — endless free practice in your isolated lab.

## Notable verbatim quotes

> do you want to start hacking right now like hack real servers in a safe and secure environment where you won't get in trouble

> these machines are legit vulnerable so if you were to put these on your real home network they could open you and your house up to an attack because if they're vulnerable for you to attack it you better believe that another hacker maybe a more experienced one could use it to get into your network we don't want that

> this entire environment will be running off this guy but our hacking environment will be separate and secure inside of it there's basically a wall a boundary between our laptop and the hacking environment

> truly all you need for this is just one computer a laptop a pc whatever you'll want to have at least 16 gigs of memory but bam that's all you need

> for our example here we're using kali linux my favorite hacking linux distro

> they are isolated this laptop i'm on cannot talk to them over the network and they can't talk to it and they can't talk to anything else

> we need a dhcp server dhcp server this server has one job on the network to hand out ip addresses to assign them

> i'm not gonna show you how to hack this box because i want you to hack it so go forth and prosper get your hacking secure hacking environment set up and tackle this thing

> don't feel bad that you're following a walk through as long as you attempt to learn everything you're looking at when they try and attack learn about that attack go whoa how do they do that how do they know to do that why did that work this is how you learn hacking

> once you're done with this one attack another one go download another box from vuln hub in your own safe secure hacking environment and it's all free

> oh hacking and coffee go hand in hand you have to

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: build-a-hacking-lab blueprint (learn-by-doing + safe/legal targets) -->
