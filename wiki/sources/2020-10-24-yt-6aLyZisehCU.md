---
type: youtube-video
source_date: 2020-10-24
url: https://www.youtube.com/watch?v=6aLyZisehCU
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [homelab-selfhosting, cloud-devops]
tags: [vmware, esxi, raspberry-pi, virtualization, homelab]
---

# VMware on a Raspberry Pi!?!?! (ESXi Install)

## Summary

A hands-on homelab tutorial in which Chuck installs VMware's ESXi — a **type 1 hypervisor**, the same OS that runs on massive servers in data centers — onto a Raspberry Pi 4. The framing concept is **virtualization**: instead of installing a single OS like Raspbian, you "slice up the pie," dividing the Pi's CPU, memory, and storage resources among several separate operating systems (basically several computers) running at once on one physical device.

Chuck's pitch is skills-and-cost driven: VMware/vSphere is enterprise virtualization technology that big companies use and that makes you valuable in the IT workforce, and being able to practice it (vSphere, ESXi, vMotion, DRS, vSAN, vCenter, clustering) on ~$100 Raspberry Pi hardware instead of a "pretty killer lab" is the whole point. He demonstrates the payoff by running multiple VMs (Ubuntu Server, Kali, CentOS with a GUI) across two 8 GB Raspberry Pi 4s — "the twins" — and clustering them together in vCenter.

The video walks through the full build end to end: updating the Pi's EEPROM firmware, preparing the microSD card with Raspberry Pi and UEFI firmware, burning the ESXi ARM installer to a USB flash drive, installing ESXi (using a second, larger flash drive as the VM datastore), accessing the vSphere web portal, creating VMs, adding NFS storage from a Synology NAS, and adding an extra USB drive as a datastore by disabling the USB arbitrator.

## Key claims (dated — the build steps)

All 2020-10-24 (paraphrase unless quoted):

- Virtualization lets one physical Raspberry Pi be divided into ~4–5 separate operating systems / "computers" by slicing up its CPU, memory, and storage resources; all run at the same time.
- ESXi is a **type 1 hypervisor** — the same OS seen on massive data-center servers — here installed on a small device.
- Recommended hardware: a Raspberry Pi 4, ideally the 8 GB version (4 GB works but 8 GB is better); a starter kit; power adapter; micro-HDMI-to-HDMI cable; a 16–32 GB microSD card; heat sinks or a fan (running ESXi makes it hot); a microSD USB adapter; mouse, keyboard, and monitor.
- Project-specific: **two USB flash drives** — one small (~16 GB) for the installer, one larger (64 GB or 128 GB recommended) to hold the VMs/datastore.
- Step 1 — Update the Pi: flash **Raspberry Pi OS Lite** with Raspberry Pi Imager, boot, log in (user `pi` / password `raspberry`), connect via Ethernet, run `sudo rpi-eeprom-update` (and `sudo rpi-eeprom-update -a` to apply), then `sudo reboot`.
- Step 2 — Erase the microSD: use Raspberry Pi Imager's **Erase** option to reformat the card.
- Step 3 — Prep the card: download and extract two files, the Raspberry Pi firmware and the UEFI Raspberry Pi firmware. From the firmware-master `boot` folder, copy all files onto the empty USB/SD, then delete the four files that start with `kernel`.
- Step 4 — From the `RPi_UEFI_Firmware_v1.20` folder, copy all files onto the card and **replace** the existing files.
- Step 5 — Edit `config.txt` and add `gpu_mem=16` at the very end to optimize the Pi, save, and reinsert the card into the Pi (don't boot yet).
- Step 6 — Download the **ESXi ARM ISO** from VMware (requires a free VMware account). Burn it to the small USB flash drive using **Rufus** (Windows; Etcher on Mac), setting cluster size to 32 KB.
- Step 7 — Boot the Pi with microSD + installer flash drive; spam **Esc** to reach the UEFI menu. In Device Manager → Raspberry Pi Configuration → Advanced Configuration, **disable** the setting that limits RAM to 3 GB (so 8 GB is usable); F10 to save.
- Step 8 — In Boot Manager, boot the installer flash drive; as the installer launches, hold **Shift+O** to edit the boot command and append `autoPartitionOSDataSize=8192` so ESXi only uses ~8 GB of the flash drive (leaving the rest for VMs). Case matters.
- Step 9 — Accept the EULA (F11), scan for install target; plug in the **larger** flash drive (F5 to rescan) and install ESXi onto it; set a root password; F11 to install.
- Step 10 — Remove the installer flash drive, reboot, enter UEFI, and in Boot Maintenance Manager → Boot Options → Change Boot Order, move the ESXi flash drive to the top (use `+`); F10 to save; continue to boot into ESXi.
- Access: browse to the Pi's DHCP IP address, accept the self-signed cert, log in as `root` with the password set during install — this opens the **vSphere** web client.
- Creating a VM: you need **ARM-architecture** ISOs (e.g. Ubuntu Server for ARM). Create/register a VM → set guest OS family Linux, version Ubuntu Linux 64-bit → change the CD/DVD drive to "Datastore ISO file," upload the ARM ISO, connect it, power on, install.
- Demonstrated running three VMs on one Pi (Ubuntu, Kali, CentOS with GUI — GUI performance is poor but works) and two on the second Pi, for five VMs total across the twins.
- **vCenter** manages multiple ESXi hosts: add hosts by IP, then create a cluster ("the twins") and add hosts to it; enables vMotion, DRS, vSAN, etc.
- Storage options: add a Synology **NAS as NFS** (or iSCSI/LUN) storage to run VMs off the NAS.
- Adding a USB drive as a datastore: by default the **USB arbitrator** passes USB devices through to VMs, so a new USB drive won't appear as storage. Fix via SSH (Actions → SSH console): `/etc/init.d/usbarbitrator stop` then `chkconfig usbarbitrator off`. Then in vSphere → Storage → Devices, clear the partition table on the drive and create a new datastore using the full disk.

## Notable verbatim quotes

> "Instead of installing one os or one operating system on a raspberry pi like raspbian boring we can slice up our pie giving a piece of the pie to each operating system we want to install."

> "We're going to install vmware's esxi on our raspberry pi this is a type 1 hypervisor it's the same os that you would see on massive servers in a data center except for putting it on the small tiny device this technology is called virtualization."

> "What's killer about this is vmware is virtualization technology that big companies use it's a skill that if you learned man you'd be valuable in the workforce."

> "Now this does involve some steps and it might feel overwhelming but don't let it be i'll walk you through each step i'll explain what's happening and we'll make sure you get started with this."

> "There are a few steps you'll need some coffee as well network coffee link below okay here we go are you ready let's do this."

> "This jerk limits ram to three gigabytes why why do you do that so we're going to disable that."

> "I've done this a million times on other hardware massive servers but on something this small this is crazy."

> "To see something like this capable of running multiple virtual machines on this credit card sized computer that's crazy."

> "When i bought this raspberry pi i went to best buy and the lady was checking me out she was like what is this thing i'm like it's a it's a computer she goes what that's computer i'm like yeah it's a computer people don't believe this."

> "This is stuff that we used to have to buy crazy lab equipment to do this now oh my gosh it's so easy now."

> "Raspberry pi's i mean gosh they what can't they do and if they can't do something we'll then get more of them and combine them and they can do something else."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
