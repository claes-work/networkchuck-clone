---
type: youtube-video
source_date: 2025-03-28
url: https://www.youtube.com/watch?v=vrELBV-r4Aw
channel: "@networkchuck_v2"
ingested: 2026-07-22
tier: L2
domains: [homelab-selfhosting, linux-terminal]
tags: [raspberry-pi, samba, smb, file-server, self-hosting, nas]
---

# Create Your Own Raspberry Pi File Server in Minutes (SMB Share)

## Summary

A short, on-location homelab tutorial in which Chuck sets up an SMB (Samba) file
share on a Raspberry Pi to use as an "emergency travel NAS." While traveling, he
needed a quick way to offload the video he was recording and vacation files, and
to sync them back to his house/studio — so he bought a Raspberry Pi from Best Buy
and shared an attached external hard drive over the network. He walks through
installing Samba, editing the `smb.conf` config, setting wide-open permissions,
restarting the service, live-troubleshooting a broken config, adding an SMB
password, and finally connecting from his Mac. He is explicit that the "quick and
dirty" 777 / wide-open approach is fine for messing around in a home lab but is not
the most secure method. Signature framing: coffee break at the start (Aeropress /
"arrow press"), casual live troubleshooting, and the value of learning to
troubleshoot as part of the lesson.

## Key claims (dated — setup, 2025-03-28)

- SMB stands for Server Message Block; the protocol was originally built for
  Windows, and Samba is an open-source implementation of SMB that lets non-Windows
  users (e.g. Linux/Raspberry Pi) access it.
- The share source can be any location on the Pi — Chuck uses an external hard
  drive mounted at `/mnt/usb`, but it does not have to be an external drive.
- Prerequisite: some form of network access to the Pi; Chuck connects over SSH
  (`ssh NetworkChuck@<pi-ip>`).
- Install Samba with `sudo apt install samba samba-common-bin -y` (the `-y` avoids
  the confirmation prompt).
- Edit the config file at `/etc/samba/smb.conf` using `sudo nano`, scrolling to the
  very bottom (shortcut: Ctrl+W then Ctrl+V in nano) and appending the share block.
- In the config block: the name in `[brackets]` is the share name shown on the
  network (Chuck named his "emerg trav nas"); `path` points to the shared location
  (`/mnt/usb`); options set it browsable, writable, read only = no, guest ok / no
  guest as chosen; and `force user` sets the owning user (his is `NetworkChuck`;
  the default Raspberry Pi user would be `pi`).
- Using `777` permissions makes the share wide open (everyone can do everything);
  Chuck flags this as not the most secure option but fine for a home lab.
- Set folder permissions recursively with `sudo chmod -R 777 /mnt/usb`.
- Restart the Samba service with `sudo systemctl restart smbd`; check it with
  `sudo systemctl status smbd`.
- Validate the Samba config with `testparm` (or `sudo testparm -v` for more verbose
  output) — Chuck used this to diagnose a broken config, then simplified the file by
  deleting the garbage and keeping just the share block plus simple global settings.
- Set an SMB password for the user with `sudo smbpasswd -a <username>` (his is
  `NetworkChuck`).
- Connect from a Mac via Finder → Go → Connect to Server → `smb://<pi-ip>/<share-name>`,
  then authenticate with the SMB password.

## Notable verbatim quotes

> "one of the best ways to do that is with an SMB share, SMB standing for the server message block"

> "Samba is an open-source version of the SMB protocol. Normally SMB protocol was built for Windows, but thanks to open source folks all of us get access to it."

> "this is my emergency travel NAS because I left my trip without any kind of tech but I needed a quick way to sync my stuff back to my house or my studio. I stopped at a Best Buy, bought a Raspberry Pi — not meaning to rhyme right now"

> "keeping in mind this is not the most secure way to share an SMB directory, this is quick and dirty. Most of the time if you're just messing around in your home lab in your house this is fine, especially since we're using 777 as permissions which makes it wide open"

> "777 which is everyone can do everything for all time"

> "okay I've got an issue. This is fun, live troubleshooting."

> "the way I can test that really quickly by typing in testparm, which made me crave a meatball parmesan sandwich"

> "after a bit of troubleshooting here's what I found: most of that file was garbage, so what I did is make it very simple, deleted everything and had just this"

> "in this video not only do we set up an SMB share on our Raspberry Pi, we also learn how to troubleshoot it a bit, which I think is very valuable for us"

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
