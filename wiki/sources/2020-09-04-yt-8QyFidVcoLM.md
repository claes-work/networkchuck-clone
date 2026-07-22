---
type: youtube-video
source_date: 2020-09-04
url: https://www.youtube.com/watch?v=8QyFidVcoLM
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [homelab-selfhosting, networking]
tags: [raspberry-pi, 3cx, pbx, voip, self-hosting, phone-system]
---

# the Raspberry Pi PHONE SYSTEM! (3CX PBX at home)

## Summary

A hands-on homelab tutorial in which Chuck turns a Raspberry Pi 4 into a full home
phone system (PBX) using [[../entities/3cx|3CX]], the video's sponsor. He walks through
prepping a fresh Pi (flashing Raspberry Pi OS 32-bit with the Raspberry Pi Imager,
setting a static IP), installing 3CX with a single `wget | sudo bash` script,
completing the browser-based setup wizard (free 3CX Standard license, subdomain, ports,
extensions, operator/voicemail numbers), and then registering endpoints: softphone apps
on a cell phone and iPad via QR code, plus physical Cisco IP desk phones. He demonstrates
internal calling, hold music, and a conference call between extensions he created for his
family and pets. He closes by teasing outbound calling via a SIP trunk and IVR menus as
topics for future videos, framing the whole thing as "the geekiest thing you can do in
your home." Ties directly to Chuck's professional VoIP/collaboration background.

## Key claims (paraphrase)

- (2020-09-04) A Raspberry Pi 4 is powerful enough to run a full corporate-style phone
  system (PBX) that supports holds, conference calls, and multiple extensions.
- (2020-09-04) The phone system used is 3CX, a PBX platform that is also used in real
  corporate environments; 3CX sponsored the video and suggested the Pi build idea.
- (2020-09-04) Pi prep: format the microSD card, flash Raspberry Pi OS 32-bit with the
  Raspberry Pi Imager, complete first-boot setup, and update software as best practice.
- (2020-09-04) A static IP should be set on the Pi's interface (e.g. `eth0` for wired,
  `wlan0` for wireless) so the phone system's address stays constant.
- (2020-09-04) Installation is a single terminal command — `wget` pulls a 3CX install
  script and `sudo bash` runs it; the installer offers a beta or final version and a
  browser- vs command-line-based configuration choice.
- (2020-09-04) 3CX can be run for free with a 3CX Standard free license for home/family
  use; you register on 3CX's site to obtain the license key and paste it into the wizard.
- (2020-09-04) The setup wizard collects the license key, admin credentials, public IP,
  static-vs-dynamic IP designation, a subdomain, region/domain suffix, ports, extension
  digit length, operator extension, voicemail number, time zone, allowed calling
  countries, and prompt language.
- (2020-09-04) The 3CX management interface is reached at the Pi's IP over HTTPS —
  `:5015` during initial setup and `:5001` for the running management console — accepting
  the self-signed certificate.
- (2020-09-04) Endpoints are added as extensions; softphone apps (Android/iPhone/iPad)
  provision instantly by scanning a per-extension QR code, so you don't need physical
  hardware to use the system.
- (2020-09-04) Physical desk phones (e.g. Cisco 7941/7821) can also be provisioned by
  adding a phone, selecting a model, and plugging it in; Cisco phones may need extra steps
  not covered in the video.
- (2020-09-04) VoIP concept — extensions are short internal numbers used to call others on
  the same system instead of dialing a full 10-digit number; Chuck uses 4-digit
  extensions, operator `5000`, voicemail `9999`.
- (2020-09-04) A SIP trunk connects the internal PBX to the outside public telephone
  network, enabling real inbound/outbound calls and an IVR (interactive voice menu); the
  free license caps the number of simultaneous calls.

## Notable verbatim quotes

> "A full-blown corporate business phone system on this little bitty guy, a Raspberry Pi 4."

> "So what this is doing is it's going out to the internet, out to 3CX, and downloading a
> script. A script that when we run will install our phone system."

> "It's just a smaller number you can use to call your fellow employees. That way, you're
> not dialing a full 10-digit or however big your number is. For me, I like to use four
> digits."

> "A phone system running off a Raspberry Pi in your house. It doesn't get better than
> that. That's the geekiest thing you can do in your home. Do it today."

> "You can also connect your phone system to the outside world via what's called a SIP
> trunk. And while that's a tutorial for another day, I do already have one set up."

> "I know I'm kind of a weirdo and I have a bunch of phones like this because I'm a phone
> guy."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: Pi PBX/VoIP self-hosting (ties to collaboration background) -->
