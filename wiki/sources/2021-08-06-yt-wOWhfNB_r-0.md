---
type: youtube-video
source_date: 2021-08-06
url: https://www.youtube.com/watch?v=wOWhfNB_r-0
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [linux-terminal]
tags: [linux-for-hackers, systemctl, systemd, services, daemons, ep-6]
---

# start, stop, restart Linux services (daemon HUNTING!!) // Linux for Hackers // EP 6

## Summary

Episode 6 of Chuck Keith's free "Linux for Hackers" series (sponsored by Hack The Box
Academy, which provides the free PwnBox lab used in the demo). The framing gimmick:
Linux is full of "demons" (daemons) — hidden background processes that make the system
tick — and this episode is about "demon hunting," i.e. finding and managing Linux
services/daemons.

Chuck builds the concept from the ground up. First he defines a **process** as "an
instance of a running program," demonstrating with interactive processes (launching
Sublime Text and `nano`) and finding them via `ps aux` piped to `grep`. When a program
closes, its process disappears. He then contrasts these **interactive processes** with
**daemons** — the many background processes in `ps aux` that the user never started.
Daemons are the Linux equivalent of Windows services (print spooler, NTP, etc.) and are
conventionally named with a trailing **`d`** (e.g. `sshd`, `ntpd`). He hunts for `sshd`
and `ntpd` via `ps aux | grep`.

The core of the lesson is **systemd**, the "master daemon" — the init system and service
manager. Chuck explains that at boot the kernel hands off to systemd, which is PID **1**
(shown via `pstree` and `ps aux`, scrolling to the top), and which **forks** all other
processes. Its two jobs: init system (boot/mount/start services) and service manager. He
notes systemd calls services **"units."**

He then demonstrates the day-to-day `systemctl` commands against `sshd` and `ntp`:
`stop`, `status`, `start`, `restart`, `reload`, the combined `reload-or-restart`,
`disable`, `enable`, `is-active`, `is-enabled`. He warns that stopping `sshd` while
connected over SSH will log you out, and that these commands need `sudo`. He covers
listing services with `systemctl list-units` (active only), `-t service` to filter by
type, and the gotcha that `list-units` (even with `--all`) only shows units systemd has
already parsed/loaded — to find not-yet-loaded units like `nginx` you need
`systemctl list-unit-files`. He mentions other init systems (SysV init, Upstart, OpenRC)
but notes systemd dominates modern distros, and other unit types (sockets, targets,
timers, mounts, devices) exist but are out of scope.

The episode ends with a realistic troubleshooting scenario: enabling and starting
`nginx` fails. systemd's failure message points to `systemctl status` and `journalctl`.
`journalctl -xe` initially shows no entries, so Chuck restarts the logging daemon
(`systemd-journald.service`), re-runs the failing `nginx` start, and then reads the log:
nginx can't bind because **port 80 is already in use** by another service. Fixing that
is deferred to later in the series. The extended version (masking, targets, etc.) is on
his free learning site.

## Key claims (paraphrase unless quoted)

- [2021-08-06] A **process** is an instance of a running program; launching any program
  (Sublime, `nano`) creates one, and closing it ends it — same concept on Windows/macOS.
- [2021-08-06] `ps aux` lists all processes; pipe to `grep <name>` to filter (e.g.
  `ps aux | grep sublime`, `ps aux | grep nano`).
- [2021-08-06] **Interactive processes** are ones the user explicitly starts; **daemons**
  are background processes the user never started that run by themselves.
- [2021-08-06] Daemons are Linux's equivalent of Windows **services** (print spooler,
  NTP, etc.); they run networking, printing, SSH, etc.
- [2021-08-06] Daemons conventionally end in **`d`** — e.g. `sshd` (SSH daemon), `ntpd`
  (NTP daemon, keeps time in sync).
- [2021-08-06] The term "daemon" comes from Greek mythology — a supernatural being with
  no bias toward good or evil, just working in the background — not the negative modern
  "demon."
- [2021-08-06] **systemd** is the "master daemon": it controls all other daemons and is
  itself a daemon (trailing `d`).
- [2021-08-06] systemd has two jobs: (1) the **init system** (started by the kernel at
  boot; mounts the filesystem, starts services) and (2) the **service manager**.
- [2021-08-06] systemd is the first process started; via **forking** it starts all other
  processes. Its **PID is 1** (verified with `pstree` and `ps aux`).
- [2021-08-06] systemd refers to daemons/services as **"units."**
- [2021-08-06] **`systemctl`** is the command-line tool for controlling daemons via
  systemd.
- [2021-08-06] `sudo systemctl stop sshd` stops a service; commands need `sudo`.
  Stopping `sshd` while connected over SSH logs you out.
- [2021-08-06] `sudo systemctl status sshd` shows whether a daemon is active/running
  (inactive vs. active/running).
- [2021-08-06] `sudo systemctl start sshd` starts a service; `restart` kills and
  restarts it; `reload` reloads config without restarting (only if the daemon supports
  it).
- [2021-08-06] `systemctl reload-or-restart <unit>` reloads if possible, otherwise
  restarts.
- [2021-08-06] `sudo systemctl disable ntp` stops a service from auto-starting on boot
  (does not stop it now); `sudo systemctl enable ntp` makes it auto-start on next boot
  (does not start it now).
- [2021-08-06] Quick checks: `systemctl is-active <unit>` and `systemctl is-enabled
  <unit>`.
- [2021-08-06] `sudo systemctl list-units` lists active units; append `-t service` to
  show only services. Unit full names have a type suffix (e.g. `ntp.service`); systemctl
  auto-resolves the short name.
- [2021-08-06] Unit types include service, socket, target, timer, mount, device.
- [2021-08-06] Gotcha: `list-units` (even `--all`) only lists units systemd has already
  parsed/loaded into memory; to see not-yet-loaded units (e.g. `nginx`), use
  `sudo systemctl list-unit-files`.
- [2021-08-06] systemd was not the only init system: SysV init, Upstart (long used by
  Ubuntu), OpenRC and others predate it, but modern distros have widely adopted systemd.
- [2021-08-06] When a service fails to start, systemd points you to `systemctl status`
  and `journalctl` (the systemd logs); `journalctl -xe` shows detailed log entries.
- [2021-08-06] `journalctl` relies on the **`systemd-journald.service`** daemon; if logs
  are empty, restart it with `sudo systemctl restart systemd-journald`.
- [2021-08-06] In the demo, `nginx` (a web server) fails to start because **port 80 is
  already in use** by another service, so it can't bind (fix deferred to later episodes).

## Notable verbatim quotes

> did you know that your linux system has a bunch of demons in it — yep i said demons —
> now apparently it's the good kind not the bad kind but still they're there, they're in
> the background, you can't see them, and they are the reason that your linux system can
> run.

> demons are kind of like services in linux.

> the official term of a process is an instance of a running program.

> how can we identify its daemon-ness? a daemon service will have a d at the end. so like
> ssh, it is a daemon and it will have a d, so sshd.

> the way we control our demons is by dealing with the master daemon. yes, there is a
> master demon process. his name is systemd. he basically commands all the other demons.

> when we boot our linux system we power it up, it boots, loads the system kernel, and
> then the kernel kicks it over to systemd.

> since systemd is the first processor first daemon created, his process id ... because
> he's the first one is number one.

> when he's talking to his daemons ... he doesn't call them daemons ... he calls them
> units. so when you see the term units associated with systemd, just know that equals
> daemons or services.

> if you're actually ssh into your box, doing this will break your system — like, it
> won't break your system, but you'll be logged out. so be careful.

> he's active and he's forrest gump, man — he's running, he's healthy.

> enable ... this will make sure a service or daemon will start up automatically on your
> next boot. it won't start the service right now but it will make sure next time it
> will.

> when you use systemctl list units it will only list units that it's attempted to parse
> and load into memory ... so to list units that aren't parsed and aren't part of memory
> we need a different command ... list unit files.

> journalctl is itself a daemon that we may need to restart. that's exactly our case
> here.

> nginx — i know by default it's going to use port 80 as its web server — and you know
> what, that's already being used ... by some other daemon, and it couldn't bind.

> get your coffee ready ... let's go demon hunting.

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: Linux for Hackers EP6 — services/daemons (systemctl) -->
