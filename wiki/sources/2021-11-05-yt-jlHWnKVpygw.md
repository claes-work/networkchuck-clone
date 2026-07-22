---
type: youtube-video
source_date: 2021-11-05
url: https://www.youtube.com/watch?v=jlHWnKVpygw
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [homelab-selfhosting, cybersecurity, networking]
tags: [raspberry-pi, travel-router, vpn, wireguard, wifi, security]
---

# my SUPER secure Raspberry Pi Router (wifi VPN travel router)

## Summary

A step-by-step tutorial building a portable travel router out of a Raspberry Pi
running OpenWRT, then routing all of its traffic over a NordVPN connection. Chuck's
stated use case is a family road trip: the Pi connects to any public wifi (Starbucks,
hotels, Airbnbs) as a client, rebroadcasts its own SSID for his family to join, and
tunnels everything through VPN so traffic on untrusted public networks stays
encrypted. He walks through imaging OpenWRT to an SD card, headless SSH access,
securing the default (passwordless) root login, editing OpenWRT config files in `vi`
and `nano`, adding a USB wifi adapter (a second wireless interface) as the broadcast
access point, and finally uploading a NordVPN OpenVPN profile and configuring the
firewall so all client traffic exits through the tunnel. The video mixes CLI editing
with the OpenWRT LuCI web GUI, showing both paths for most steps. Sponsor: Hostinger
(web hosting).

## Key claims (dated — the build + concept)

All dated 2021-11-05 (paraphrase unless quoted):

- Core concept: a travel router connects to public wifi as a *client* on one wireless
  interface, broadcasts its own protected SSID on a *second* interface for your
  devices, and forwards all that traffic over a VPN — so on any untrusted public
  network your traffic is encrypted and your real IP hidden.
- Hardware needed: a Raspberry Pi (OpenWRT supports nearly all models, Zero through
  Pi 4); Chuck recommends the Pi 4 for built-in wifi, Ethernet, and speed. Plus power
  supply, micro SD card + reader, Ethernet cable, and a USB wifi adapter (~$12) known
  to work with the Pi and OpenWRT.
- Two wireless interfaces are required. The Pi 4's onboard wifi connects out to public
  wifi; the USB adapter broadcasts the SSID your devices join. If your Pi lacks
  built-in wifi, you need two USB wireless adapters. The Ethernet port joins the same
  local network (Chuck plugs in his Raspberry Pi NAS to stream Plex movies in the car).
- OS: OpenWRT is a Linux-based open-source router firmware. Chuck writes it to the SD
  card with Raspberry Pi Imager using the "use custom" image option.
- Headless setup: connect the Pi's Ethernet port to a computer; the Pi defaults to IP
  192.168.1.1, so set the computer's Ethernet adapter to a static 192.168.1.10, then
  SSH in as `root@192.168.1.1`.
- Security note: OpenWRT's default root login has NO password — Chuck immediately sets
  one with `passwd` and calls the passwordless default "super insecure."
- Config lives in `/etc/config/` (network, wireless, firewall, dhcp). Chuck backs up
  network, wireless, and firewall with `cp` to `.bk` files before editing.
- Network hardening tip: change the LAN subnet away from the common `192.168.1.1`
  (hackers know that default) — he uses `10.71.71.1`.
- Adds a `wwan` interface with `proto 'dhcp'` (pulls an IP from whatever public wifi it
  joins), sets `peerdns '0'` and manual DNS (Cloudflare `1.1.1.1`, Google `8.8.8.8`),
  and a `vpnclient` interface on `tun0` with `proto 'none'`.
- Firewall change: in the wan zone, change `input` from `reject` to `accept`.
- USB wifi adapter driver install: `opkg update` then install a batch of wifi driver
  packages; verify the adapter appears via `lsusb` and bring it up with
  `ifconfig wlan1 up`.
- Radio-0 (onboard) fix he found on a forum: channel 36→7, `hwmode` 11a→11g,
  `htmode` VHT80→HT20, and add `option short_gi_40 '0'`; enable with `option disabled 0`,
  then `uci commit wireless` and `wifi`.
- The USB adapter (wlan1) becomes the access point: set its SSID (he uses
  `NetworkChuck_travel`), encryption `psk2`, and a wifi key.
- VPN step: download a NordVPN OpenVPN UDP config, upload it to the Pi via `scp` to
  `/etc/openvpn/client.conf`, install OpenVPN packages, set NordVPN username/password
  variables, generate the VPN config with a bash script, and apply a firewall config so
  the tunnel works. He notes the steps are "pretty much the same for most VPN providers"
  and that you must be a paying NordVPN subscriber.
- Verification: before VPN, "what's my IP" showed an IP starting with 107; after
  enabling the tunnel it changed to a NordVPN IP — confirming all traffic now exits
  through NordVPN.
- Reliability tweak: add a `hotplug` config so the VPN service restarts automatically
  if the interface drops — important for an always-on travel router.
- Caveat: a Pi router "won't be as fast as" a beefier router like a pfSense box, but it
  does the job; people do use Raspberry Pis as their main home router.

## Notable verbatim quotes

> "This will be my official travel router. When I take my family on a road trip here
> soon, and it will securely connect me and my family, wherever we go to the internet
> over VPN."

> "The onboard wifi... that sucker will connect to any public wifi available... The USB
> wireless adapter will be giving me and my family wifi. It will be the one
> broadcasting my SSID."

> "Just real quick, notice they did not prompt us for a password. Super insecure. Let's
> go ahead and change that."

> "This one.one is the most common home network IP address or subnet, and you know
> what? Hackers know that too. So we're going to change it, so they don't know."

> "We're not secure. We're not protected. We're not going over VPN. Our network traffic
> is not encrypted. That's not good."

> "If you know anything about me, I hate wireless networking. So don't ask me what that
> meant. I just know it fixed it and it works. And that's really all I care about."

> "A reboot fixes everything, guys."

> "We know hackers hack Starbucks wifi all the time."

> "That is a Nord VPN IP, which means all my traffic is going over Nord VPN through this
> Raspberry Pi router. Are you freaking kidding me? That's amazing."

> "People often do use the Raspberry Pi as their main router in their house. You can
> replace your main router with this sucker. Now it won't be as fast as other fun
> routers like getting a pfSense router with a beefy set of hardware, but it still does
> the job."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
