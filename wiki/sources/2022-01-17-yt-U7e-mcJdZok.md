---
type: youtube-video
source_date: 2022-01-17
url: https://www.youtube.com/watch?v=U7e-mcJdZok
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, cloud-devops, homelab-selfhosting]
tags: [kasm, docker, kali-linux, browser-streaming, hacking-lab, cloud-browser-precursor]
---

# create the ULTIMATE hacking lab in 5min!! (Docker Containers STREAMING Kali Linux to your browser)

## Summary

A hands-on tutorial (sponsored by Kasm Workspaces) showing how to stand up a personal
"hacking lab" where full desktop apps — a Chrome/Brave browser, Kali Linux, VS Code — run
inside Docker containers on a server and are streamed to an ordinary web browser. Chuck's
brother Cameron co-hosts, explaining the underlying tech. The pitch: with one click you spin
up an isolated, disposable Kali or browser session that lives on the server (cloud or home),
not your machine, so sketchy links and malware never touch your own computer, and when you're
done you delete the session and it's gone ("ephemeral"). Chuck says he "use[s] this thing
every day" and it "change[d] the game" for him.

The build (~5 min): provision a small server (Linode cloud or on-prem via Proxmox) meeting the
minimums, create a swap partition for stability, `wget` the Kasm installer, extract it, run the
install script via `sudo bash`, then log into the Kasm web console and launch workspaces. Chuck
then demos three tweaks: (1) install the Kasm browser extension to right-click "open in Kasm"
for nefarious links; (2) enable the Kali Linux image and add a Docker run config JSON snippet
(`"user":"root"`) for root access; (3) create users (his daughters Chloe and Addie) and apply
web-filter policies (deny-by-default whitelisting, safe search).

The video captures the exact Kasm-based browser-streaming architecture that Chuck would later
commercialize as the **NetworkChuck Cloud Browser** product — this is a direct precursor.

## Key claims (dated — the build + Kasm concept)

- (2022-01-17) The lab uses **Kasm Workspaces**: you install Kasm on a server, and when you
  open a secure browser or a Kali Linux instance, Kasm automatically spins it up in a **Docker
  container and streams it to your browser** — no heavy VMs or WSL2 required. (paraphrase)
- (2022-01-17) Kasm's streaming tech is called **KasmVNC**, which Cameron corrects to note is
  **open source**. The workspace containers are regular Docker images available on Docker Hub,
  and you can build your own custom images. (paraphrase)
- (2022-01-17) Minimum server requirements: **2 vCPU, 4 GB RAM, 50 GB storage (SSD preferred)**;
  applies to both cloud and on-prem. (paraphrase)
- (2022-01-17) Cloud build uses **Linode** with **Ubuntu 20.04** (Chuck notes 21.x did not work
  for him); the 4 GB / 2 vCPU plan is ~$20/month, more than his usual $5 projects because Kasm
  needs more resources. On-prem, Chuck builds a Proxmox VM with the same specs. (paraphrase)
- (2022-01-17) Install steps: create/enable a **swap partition** for stability (and add it to
  fstab so it persists across reboot), **`wget`** the installer from S3 (a `.tar.gz`), extract it,
  run **`sudo bash`** on the release install script, accept the EULA, then save the admin
  credentials it prints and log into the Kasm web console over **HTTPS at the server IP**. (paraphrase)
- (2022-01-17) Running on a cloud server means your browsing/hacking traffic uses the **cloud's
  IP address**, hiding your home/ISP IP for a degree of anonymity; because the Kasm server sits
  on your home/business network, you also retain access to internal resources (e.g. a Synology NAS)
  remotely. (paraphrase)
- (2022-01-17) A **Chrome/Brave/Firefox extension** ("open in isolation") lets you right-click any
  link and open it in a fresh, isolated Kasm container; configure it by adding your server URL in
  the extension options and setting a default workspace image per user. (paraphrase)
- (2022-01-17) To get **root** in Kali, add JSON `{"user":"root"}` to the image's Docker run config;
  then `su` after launch. Kasm ships ~26 images (not all enabled by default, including a "Doom" one);
  Kali must be enabled and its container downloaded before first launch. (paraphrase)
- (2022-01-17) **Web filtering** is built in per user/image: deny-by-default with whitelist/blacklist,
  Google safe search, and (licensed only) URL categorization. Sessions are **transient/ephemeral** —
  deleting a session leaves "no proof" you were there. (paraphrase)
- (2022-01-17) Kasm's **Community Edition is $0 and includes all enterprise features**, limited to
  **5 simultaneous sessions** and excluding some branding and web categorization. (paraphrase)
- (2022-01-17) Business use cases (per Cameron): replacing **VDI/Citrix** (web-native, nothing to
  install on endpoints), auto-updating rolling secure images every night, and **DevOps pipelines**
  (testing custom Docker containers/code via Kasm's secure APIs). (paraphrase)

## Notable verbatim quotes

> "What I'm about to show you is the ultimate hacking workspace. No joke. This technology is nuts.
> And honestly, I use this thing every day. Change the game for me, completely."

> "It's not even on my machine. Is it a bad link? I don't care. Not my machine."

> "And no, this doesn't involve some heavy virtual machines or WSL two — it's Docker containers
> streaming to your browser."

> "So you install Kasm on your server. Now, if you wanna open up a secure web browser, or even an
> instance of Kali Linux, Kasm will automatically open this up in a Docker container and stream it
> to your browser."

> "A Docker container streaming and — shoot — even a browser, browsing in a browser on a virtual
> machine, in the cloud using Tor. And it's inside a Docker container. There's so many things
> happening tech-wise. It's like it hurts your brain to think about."

> "That instance, that browser, that VM is transient. Ephemeral — big words. It just disappears.
> 'Cause it doesn't matter."

> "That's probably the future of how we deal with weird stuff like this, how we browse the internet."

> "Community edition is $0 and includes all features of enterprise."

> "I only say yes to things I really like and enjoy and will actually use myself, especially when
> it's free and accessible to pretty much everybody."

> "Have you hacked YouTube algorithms today? ... You gotta hack YouTube today. Ethically, of course."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

(Note: Chuck's brother **Cameron** co-hosts and narrates several technical explanations. Where a
claim above was voiced by Cameron, it is factual/product exposition about Kasm rather than a
personal opinion, and Chuck endorses it on-camera; no persona-training material is drawn from
Cameron's lines. Cameron is context, not the subject.)

<!-- ★ L3-candidate: Kasm browser-streamed Kali lab — direct precursor to NetworkChuck Cloud Browser -->
