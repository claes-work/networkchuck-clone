---
type: youtube-video
source_date: 2021-05-08
url: https://www.youtube.com/watch?v=bllS9tkCkaM
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, homelab-selfhosting]
tags: [tor, dark-web, onion-service, raspberry-pi, self-hosting, education]
---

# i put a DARK WEB website on a Raspberry Pi!!

## Summary

A homelab/security tutorial in which Chuck Keith hosts a Tor hidden service (an
`.onion` "dark web" website) on a ~$35 Raspberry Pi, framed as an educational
exercise in understanding how Tor and onion services work rather than a how-to for
wrongdoing. The video splits into (1) a conceptual explainer of what the dark web is,
why Tor exists, and the anonymity mechanics of onion circuits, introduction points,
rendezvous points, and the distributed hash table; and (2) a hands-on walkthrough of
building the site: image a Raspberry Pi with Raspberry Pi OS, SSH in, `apt install tor`,
uncomment the hidden-service lines in `torrc`, restart Tor to obtain an onion address,
install and harden nginx, and publish a customized `index.html`. Chuck stresses the
site works from a home network with no port forwarding, and pointedly refuses to show
where illegal content lives. The dark-web-monitoring angle is used to segue into the
sponsor (Dashlane password manager / VPN).

## Key claims (dated 2021-05-08)

**Concept — what the dark web / Tor is:**
- Tor ("The Onion Router") is open-source anonymity software that runs as an overlay
  network on top of the internet; at the time of recording Chuck cites "over 7000"
  onion relays worldwide. (paraphrase)
- On the regular internet you are not anonymous: the destination site, plus every
  router and hop in between, can see your IP and what you are accessing. (paraphrase)
- On Tor, when you reach a site, neither side learns the other's identity or IP — the
  only thing you know is the domain name; anonymity comes from routing through an
  "onion circuit" of three randomly selected relays that each encrypt the traffic.
  Chuck frames it as "almost" foolproof, not absolute. (paraphrase)
- The dark web was originally created to protect identity and keep users safe, though
  it also hosts illegal marketplaces where stolen data (SSNs, passwords, emails) is
  sold; Chuck states his own passwords have been sold on such marketplaces. (paraphrase)
- Dark web addresses end in `.onion` instead of `.com`; they are typically
  randomly-generated strings (e.g. DuckDuckGo, Facebook) and the dark web is not
  indexed, so you must already know an address to reach it. (paraphrase)

**Concept — how a hidden/onion service works (the mechanics Chuck illustrates):**
- The onion service on the Pi advertises itself by forming onion circuits to three
  randomly-chosen relays, which become its **introduction points**. (paraphrase)
- The service bundles these introduction points into an **onion service descriptor**,
  adds its public key, signs it with its private key, and uploads it to a
  **distributed hash table** distributed across the onion network. (paraphrase)
- To connect, a visitor looks up the onion address in the hash table, verifies the
  descriptor with the public key, picks an introduction point, and chooses a separate
  random relay as a **rendezvous point** protected by a secret passphrase; the site is
  told the rendezvous location + passphrase via the introduction point, then both
  sides meet at the rendezvous point over encrypted onion circuits. (paraphrase)
- Chuck deliberately draws the diagram as a "jumbled mess" to illustrate how hard it
  is to trace where either party is located. (paraphrase)

**Technique — building the site on a Raspberry Pi (~5 minutes of setup):**
- Hardware: a ~$35 Raspberry Pi with SD card, USB adapter, and power cable — or any
  Linux VM/computer/server; it works behind a home firewall with no port forwarding.
  (paraphrase)
- Image the SD card with Raspberry Pi Imager (Raspberry Pi OS / Raspbian 32-bit),
  connect to the network, optionally set a static IP, and enable SSH via Raspberry Pi
  Configuration → Interfaces. (paraphrase)
- SSH in as user `pi`, then `sudo apt update`, then `sudo apt install tor`. (paraphrase)
- Edit `/etc/tor/torrc` with `sudo nano`, uncomment the `HiddenServiceDir` and
  `HiddenServicePort` lines (leaving values unchanged), save, and restart Tor with
  `sudo service tor stop` then `start`; check with `sudo service tor status`.
  (paraphrase)
- The onion address appears immediately at
  `/var/lib/tor/hidden_service/hostname` (read with `sudo cat`). (paraphrase)
- Install a web server: `sudo apt install nginx`, start it with `sudo service nginx
  start`; the default nginx page is then live as the dark web site. (paraphrase)
- Harden nginx in `/etc/nginx/nginx.conf`: uncomment `server_tokens off`, add
  `port_in_redirect off;`, and uncomment the server_name/redirect line; restart nginx.
  (paraphrase)
- Customize the site by editing `/var/www/html/index.html` (delete the default
  `index.nginx-debian.html`, create your own with `sudo nano`), then restart nginx.
  (paraphrase)

**Ethics framing:**
- The exercise is explicitly educational — to understand how Tor hidden services and
  anonymity work — not to enable crime; Chuck refuses to show where illegal content or
  marketplaces are. (paraphrase)
- Repeated "hack YouTube ethically" bit; the security takeaway for viewers is to use a
  password manager with dark-web monitoring and change passwords routinely (~every 90
  days). (paraphrase)

## Notable verbatim quotes

> "so right now on the regular internet when you go to a website you're being tracked ...
> every router and hop in between knows who i am and what website i'm accessing but the
> dark web is different"

> "we use an onion legit it's called tor or the onion router tor is an open source
> software that's designed for anonymity it lives on top of the internet as an overlay
> network"

> "the dark web was created for you to keep you safe to keep me safe it protects your
> identity"

> "i know for a fact that my stuff has been on dark web marketplaces my passwords have
> been sold"

> "i'm not going to show you where the bad stuff is because yeah there is bad stuff out
> there"

> "this is officially called tor hidden services or actually i think it's now called an
> onion service i don't know look it up"

> "next let's install tor which is crazy easy check this out sudo apt install tor that's
> it man"

> "it's up how cool is that now sure this is a default nginx page but this sucker's
> running on my raspberry pi a dark web website think about that and also i didn't
> forward any ports on my router i didn't do anything special at all with networking"

> "i'm secure like you can't find out where i am even though it's sitting on my home
> network and i can't find out who you are that's so cool"

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: Tor hidden-service on Pi — stunt-education homelab format -->
