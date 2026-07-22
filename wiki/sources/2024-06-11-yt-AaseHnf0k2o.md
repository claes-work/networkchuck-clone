---
type: youtube-video
source_date: 2024-06-11
url: https://www.youtube.com/watch?v=AaseHnf0k2o
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [homelab-selfhosting]
tags: [retropie, raspberry-pi, retro-gaming, emulation, maker, fun]
---

# RetroPie: A Raspberry Pi Gaming Machine

## Summary

A hands-on build tutorial in which Chuck (with editor/team member Alex doing much of
the legwork) turns a Raspberry Pi into a RetroPie emulation console that can play retro
games from many classic consoles on one device. The video covers the full build:
picking hardware (Raspberry Pi 4 or 5, microSD, power, keyboard, monitor/TV, gamepad),
flashing RetroPie with Raspberry Pi Imager, an alternate install path for the Pi 5
(install Raspberry Pi OS first, then clone and run the RetroPi setup script), and
first-boot configuration in EmulationStation (keyboard mapping, gamepad configuration,
hotkeys, hostname/password/WiFi/timezone/SSH via `raspi-config`).

It then moves through the "make it yours" layer: copying ROMs onto the Pi over the
network with SCP, scraping box art and metadata, tuning UI/game-list views, save states,
RetroArch settings (and the reminder that RetroArch settings must be saved manually),
downloadable cheats, RetroAchievements integration, and finally online multiplayer via
RetroArch Netplay — culminating in Chuck and Alex playing across two different Pis on
two different networks (Zombies Ate My Neighbors, Street Fighter II). The throughline is
Chuck's "tech is fun" ethos: this is a playful maker project, full of coffee-break gags
and roasting, showing that homelab skills (Linux, SSH, networking) make hobby projects
possible.

Notable legality caveat: Chuck explicitly refuses to show how to obtain ROMs — he only
shows how to transfer already-acquired ROMs onto the device.

## Key claims (dated — the build + ethos)

All dated 2024-06-11 (paraphrase unless quoted):

- A single Raspberry Pi running RetroPie can emulate games from many retro consoles on
  one device, and can add modern features on top: achievements, save states, cheats
  ("Game Shark"-style), any controller you want, and online multiplayer (no more couch
  co-op only).
- Hardware needed: a Raspberry Pi (Pi 4 minimum recommended; Pi 5 gives a better
  experience), a microSD card (larger is better for lots of ROMs), power supply,
  keyboard, and a monitor or TV (a TV — even an old CRT — is preferable if using it as a
  console). Optionally a gamepad (they use an Xbox controller) and speakers (HDMI
  carries audio automatically).
- RetroPie can also be installed on a machine running Ubuntu, but the video focuses on
  Raspberry Pi.
- Install method (Pi 4): use Raspberry Pi Imager, choose device, choose storage
  (microSD — warns this wipes the drive), then under "Emulation and Game OS" pick
  RetroPie and the version matching your Pi, then write to the card.
- At recording time there was no RetroPie image for the Raspberry Pi 5. Workaround:
  flash Raspberry Pi OS (64-bit) to the Pi 5, then install RetroPie on top.
- Pi 5 install-on-top steps: `sudo apt update` and `sudo apt upgrade -y`, ensure git is
  installed (`sudo apt install git`), `git clone` the RetroPie setup repo, `cd` into
  `RetroPie-Setup`, make the script executable with `chmod`, then run
  `sudo ./retropie_setup.sh`. Choose "Basic install" for most cases. 64-bit shows an
  "unofficially supported" message that can be accepted.
- Post-install tweaks in the RetroPie-Setup script: enable Autostart (so
  EmulationStation auto-boots) and the Bash welcome tweak (extra system info on login),
  then `sudo reboot`.
- First boot best practice: configure the keyboard BEFORE the gamepad, so you always
  have a fallback if the gamepad is misconfigured. Set a button to "Hotkey Enable"
  (Chuck uses spacebar).
- System configuration via `raspi-config` (reached through the RetroPie menu): set
  hostname, change password, set localization/timezone and WiFi country, and enable SSH
  for remote access. WiFi is set through the RetroPie WiFi option rather than
  raspi-config.
- Getting ROMs onto the Pi: Chuck's preferred method is SCP (secure copy) over the
  network — find the Pi's IP (RetroPie config → "show ip"), then
  `scp -r <local-roms-path>/* user@<pi-ip>:~/RetroPie/roms/`. The command works the same
  on Mac, Linux, or Windows.
- Scraping: EmulationStation's scraper (Chuck prefers "ScreenScraper") pulls box art,
  release year, and descriptions for every game; grid view is his preferred game-list
  style; "ignore articles" sorts e.g. "The Legend of Zelda" under L, not T.
- Hotkey combos (hotkey button + another): hotkey+Start exits a game; hotkey+right
  shoulder saves a state; hotkey+left shoulder loads it; hotkey+D-pad right/left cycles
  save-state slots; hotkey+B resets; hotkey+X opens the RetroArch menu.
- RetroArch settings do NOT save automatically — you must go to Configuration File →
  Save Current Configuration.
- Cheats: RetroPie can download a large set of pre-configured cheat files via the Online
  Updater (enable advanced settings → menu item visibility → online updater → update
  cheats), then load a cheat file per console and enable individual cheats.
- RetroAchievements: create an account at retroachievements.org, then in RetroArch
  Settings → Achievements, enter username/password. Hardcore mode disables cheating
  (no save states, no rewind). Reboot to log in and unlock achievements in-game.
- Netplay (online multiplayer): there's a host and a client; the person with the more
  stable connection should host. Critically, host and all clients MUST run the exact
  same RetroArch version (update via RetroPie-Setup → Update). Configure under RetroArch
  Netplay settings: set mode (host/client), port (default 55435), host IP, and nickname;
  save configuration. Launch a game and pick "Launch with net play enabled." The host
  shares their external IP with the client to connect.
- Ethos: the project is framed as pure fun ("tech is fun") — Chuck jokes about the
  dopamine hits of achievements, coffee breaks during long installs, and the value of
  doing it "because it's cooler" than emulating on a phone.
- Academy bonus: two exclusive Network Chuck Academy videos extend the build —
  accessing RetroPie from a web browser, and setting up a custom relay server for
  Netplay to avoid UPnP/router issues.

## Notable verbatim quotes

> "You can legit play every retro game from every retro console on this little device.
> It's kind of crazy. I feel like I'm making it up, but I'm not."

> "those dumb dopamine hits you get when you're playing your PS five and Xbox. You now
> get that when you finally beat the Special cup. Boom, achievement unlocked. And you
> can pretend like your life has meaning."

> "Now I know what you're thinking, Chuck. I can do this on my iPhone now. Sure, but
> it's not as cool. This is better. So just do this."

> "Now I'm not going to show you how to get ROMs, I'm just going to show you how to get
> ROMs on your Raspberry Pi, your RetroPi."

> "Perfect time for a coffee break and it's done. One more coffee break in Network
> Chuck coffee."

> "there is something extremely important that you must remember whenever you're
> changing any of these RetroArch settings, they don't save automatically, you have to
> save them yourself."

> "you need to make sure that the host and the clients are all using the latest version
> of RetroArch, because if you're not all on the same version, it will not work."

> "This is so cool. Two different pies. So sick. Two different networks, two different
> pies."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT). (Team member/editor
Alex appears on camera walking through some steps and playing Netplay, but is Chuck's
employee presenting Chuck's tutorial, not an independent guest with distinct positions.)
