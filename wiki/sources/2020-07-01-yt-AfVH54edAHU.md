---
type: youtube-video
source_date: 2020-07-01
url: https://www.youtube.com/watch?v=AfVH54edAHU
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [linux-terminal, cybersecurity]
tags: [kali-linux, wsl2, windows, linux, tutorial]
---

# Kali Linux on Windows in 5min (WSL 2 GUI)

## Summary

A fast, hands-on tutorial in which Chuck Keith walks through running Kali Linux
on Windows 10 using WSL 2 (Windows Subsystem for Linux, version 2) — including a
graphical desktop reachable over RDP. The pitch: WSL 2 is better than WSL 1
because it runs an actual Linux kernel on Windows, and Kali installs "like an
app" from the Microsoft Store. Chuck covers the full setup from checking Windows
version, enabling the required Windows features, installing the WSL 2 kernel
update, setting WSL 2 as the default, installing Kali, adding the XFCE desktop
environment, and connecting with XRDP + Windows Remote Desktop. He closes by
demonstrating theHarvester (an OSINT recon tool) against `davidbomble.com` to
prove the GUI Kali install is fully usable.

## Key claims (dated — setup steps)

All dated 2020-07-01 (video publish date).

- WSL 2 is preferred over WSL 1 because it uses a real Linux kernel on Windows,
  rather than a translation layer.
- Requirements: Windows 10 (Home edition is fine), version 2004, with a
  sufficiently high build. Check your version by hitting the Windows key, typing
  `winver`, and pressing Enter.
- If the required version isn't present, run Windows Update (Start → type
  "update" → "Check for updates"); expect it to take a while and possibly a few
  restarts.
- Install WSL: open Windows PowerShell as administrator (Start → "powershell" →
  right-click → Run as administrator), then run the first provided command and
  reboot when prompted (Y + Enter).
- After reboot, reopen PowerShell as administrator and run a command to enable
  the Virtual Machine Platform feature, then run the next command; restart the
  machine again.
- Update the WSL 2 Linux kernel package: open the provided link in a browser,
  download the latest kernel package installer, and run it through the wizard.
- In an administrator PowerShell, run the command that sets WSL 2 as the default
  version.
- Install Kali from the Microsoft Store: open Store (Start → "store"), search
  "Kali Linux," and install it like an app.
- Launch Kali from the Start menu; on first run it installs and prompts for a
  username and password. `cat` of the OS release confirms it's Kali Linux.
- Update/upgrade the install: `sudo apt update && sudo apt upgrade -y`.
- Install a desktop environment: `sudo apt install kali-desktop-xfce -y`
  (during setup you'll pick a keyboard/locale — English).
- Verify WSL version in PowerShell with `wsl --list --verbose`; Kali should show
  as running version 2.
- Install the RDP server: `sudo apt install xrdp`.
- Start the RDP service: `sudo service xrdp start`.
- Get the Kali IP address with `ip address` (in the demo it was
  172.27.183.200).
- Connect with Windows Remote Desktop Connection (Start → "remote desktop"),
  entering the Kali IP and the login you set during install — this opens the
  Kali XFCE GUI on Windows.
- The base GUI install is bare-bones; add tools as needed. Chuck installs and
  runs theHarvester (the OSINT tool from his Google hacking video) against
  `davidbomble.com` using Google as the source, finding an email and some
  subdomains.

## Notable verbatim quotes

> "Kali Linux on Windows 10 it runs like an app not even kidding it's amazing."

> "we're actually using a Linux kernel on Windows crazy."

> "we can just install Kali Linux like a app and I love that."

> "whoa look at that yes Kali Linux running on windows so weird can it be real
> let's try it."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
