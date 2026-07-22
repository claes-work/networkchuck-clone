---
type: youtube-video
source_date: 2021-10-02
url: https://www.youtube.com/watch?v=gyMpI8csWis
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [homelab-selfhosting, linux-terminal]
tags: [nas, raspberry-pi, openmediavault, storage, self-hosting, homelab]
---

# how to build a Raspberry Pi NAS (it's AWESOME!!)

## Summary

A two-part homelab tutorial where Chuck turns a Raspberry Pi 4 (a "credit card size
computer") into a NAS — network attached storage — using OpenMediaVault, and then
installs a Plex media server on the same Pi. His stated motivation is a portable
"travel NAS" for a family road trip that can hold movies for Plex, offload vlog footage
from his camera, and sync back to the big NAS at his house. Part one covers imaging the
SD card, headless setup, installing OpenMediaVault, attaching USB storage, and creating
an SMB/NFS share; part two installs Plex from its APT repository. Chuck hits and
troubleshoots real errors on-camera (an NFS error that he fixes by wiping/reformatting
the drive to ext4, and a Windows SMB login failure fixed by resetting the OMV user's
password). He closes by upgrading the build into a Geekworm case with a HAT and an
internal 2 TB SSD. Sponsored by Bitdefender Total Security.

## Key claims (dated — the build + concept)

All dated 2021-10-02 (paraphrase unless quoted):

**Concept / why a NAS**
- A NAS (network attached storage) is networked storage; Chuck asserts that yes, you
  need one. A commercial NAS is normally pricey, but a Raspberry Pi build is relatively
  cheap, fun, and portable — usable either as a travel NAS or as your main home NAS.
- Use case: hold a lot of movies for Plex, offload camera/vlog footage, and sync files
  back and forth to a larger home NAS.

**Hardware**
- Recommends a Raspberry Pi 4 with the most RAM you can get (4 GB or 8 GB). Essentials:
  power adapter, SD card, SD card reader, and an optional case.
- Any USB hard drive works — a large Seagate drive or a small Samsung T5 SSD (Chuck
  recommends the SSD as "wicked fast"). A big SD card can technically store everything,
  but a USB drive is more economical.
- Optional upgrade: a Geekworm kit with a Pi HAT that holds an internal SATA SSD in a
  case; the OMV instructions are identical whether using external USB or the Geekworm
  kit.

**Part 1 — imaging and headless setup**
- Prep the SD card with Raspberry Pi Imager (Windows/Mac/Linux). Choose Raspberry Pi OS
  (other) → Raspberry Pi OS Lite ("no desktop... all we care about is having a command
  line").
- Hidden Imager settings via Ctrl+Shift+X: enable SSH and set the `pi` user password
  before writing, so the install is headless (no monitor/keyboard/mouse).
- Use wired Ethernet, not Wi-Fi — Chuck tried Wi-Fi and "something broke."
- Find the Pi's IP via the home router's DHCP lease list (he uses UniFi), then SSH in:
  `ssh pi@<ip>`. Default password (if not set) is `raspberry`.
- Update first: `sudo apt update && sudo apt upgrade`.

**Part 1 — OpenMediaVault (NAS software)**
- Best NAS solution he found for the Pi is OpenMediaVault, installed with one command:
  a `wget` of a script from OpenMediaVault's GitHub piped to `bash`. Takes a while and
  may change the Pi's IP address (his went from .108 to .111), requiring a reconnect.
- Access the OMV web GUI at the Pi's IP; default login `admin` / `openmediavault`.
  First step: change the web administrator password (General Settings).
- Plug in the USB drive → it appears under Storage → Disks alongside the OS SD card.
  Mount it under Storage → File Systems. Nothing takes effect until you click Apply.
- Create a shared folder (Access Rights Management → Shared Folders), then set
  privileges giving the `pi` user read/write.

**Sharing services (SMB vs NFS)**
- Two main access methods: SMB (Windows default file sharing) and NFS (Linux/Mac). You
  can enable both. Enable each under Services, then add the shared folder under that
  service's Shares tab, then Apply.
- Troubleshooting: an NFS error was fixed by stopping SMB, deleting the shared folder,
  unmounting and wiping the USB drive, then recreating the file system as ext4. After
  reformatting, re-enabling NFS + SMB worked with no error.
- Connecting from Windows (Add a network location → `\\<pi-ip>\<share>`) initially
  failed the `pi` login; fix was to edit the OMV user and reset its password (the OMV
  share user is separate from the system SSH login). After that the share mounts and
  files transfer fine.

**Part 2 — Plex media server**
- Install steps over SSH: `sudo apt install apt-transport-https`, add Plex's signing key
  (curl) and add the Plex APT repository, `sudo apt update`, then
  `sudo apt install plexmediaserver`.
- Access Plex at `http://<pi-ip>:32400/web`. Requires a free Plex account; walk through
  setup, name the server, add a library (e.g. Movies) pointing at a folder on the NAS
  drive (create the folder via the mounted share first).
- Plex is described as "like Netflix that you host yourself"; media can then be watched
  in a browser or on the free Plex mobile app streamed off the Pi.

**Security (sponsor context)**
- Warns that downloading movies from insecure sites risks viruses/malware/ransomware,
  used to pitch Bitdefender Total Security (sponsor): antivirus, advanced threat
  defense, online threat prevention, vulnerability scans, ransomware remediation
  (restores encrypted files), phishing-page checks, and webcam/microphone privacy
  protection, all without slowing the computer. Link offered 5 devices free for 120 days.

## Notable verbatim quotes

> "We're going to turn this a raspberry PI a credit card size computer into a Nass, a network attached storage device."

> "Do I actually need a Nass? Yes. Yes. You need a Nass."

> "The best solution I found for the raspberry PI is called open media vault. It's amazing. And we can install it with just one command."

> "Now you can also set up wifi, but I highly recommend you use Ethan net for this project. In fact, I tried to do wifi and something broke. It didn't work. So go hardwire on this one."

> "He'll know yours is done. When you see the matrix stop scrolling, then you're good."

> "if you're wondering what Plex is, it's amazing. It's like Netflix that you host yourself. You host it."

> "I love seeing this installation successful errors zero. Oh, isn't that the most? It's just the best feeling in the world."

> "This little tiny package is running a mass and Plex. It's just a raspberry PI, but it's so cool."

> "Have you hacked the YouTube algorithm today? ... hack you today. Ethically of course."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
