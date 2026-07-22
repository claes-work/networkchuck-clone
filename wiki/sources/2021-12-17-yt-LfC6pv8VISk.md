---
type: youtube-video
source_date: 2021-12-17
url: https://www.youtube.com/watch?v=LfC6pv8VISk
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [linux-terminal]
tags: [linux-for-hackers, processes, ps, kill, htop, ep-7]
---

# KILL Linux processes!! (also manage them) // Linux for Hackers // EP 7

## Summary

Episode 7 of Chuck Keith's free "Linux for Hackers" series covers Linux process
management from the command line: how to view running processes, monitor system
resource usage, kill misbehaving processes, and move jobs between the foreground and
background. Chuck frames it as a must-have skill for anyone working with Linux, drawing
the analogy to a Windows user opening Task Manager (Ctrl+Alt+Delete) to end a stuck
task — except on Linux it's all done through the terminal.

As with the rest of the series, the sponsor is Hack The Box Academy, whose free
browser-based Linux lab (the "Linux Fundamentals" course → "Service and Process
Management" → the "My Workstation" instance) is used as the follow-along environment.

Chuck walks through: `ps` and its common switches (`ps -u <user>`, `ps aux`),
filtering output with `grep`, the combined `pgrep` shortcut for finding a process by
name, the `top` and `htop` live process monitors, foreground vs. background processes
(demonstrated with `ping` and `sleep`), the job-control shortcuts Ctrl+C and Ctrl+Z,
the `jobs` table, `bg`/`fg` to move jobs, `&` to launch straight to the background,
kill signals (`kill -l`), and finally `kill`, `kill -9`, and `pkill` to terminate
processes — including killing many at once by name.

## Key claims (dated — the concepts/commands)

All dated 2021-12-17.

- Nearly everything you do on Linux starts a process — launching any application (e.g.
  Firefox) creates a process (references the concept covered in EP 6).
- `ps` is the main command for viewing running processes; run bare, it only lists what
  is running in the current terminal (the bash shell and the `ps` command itself), so
  you must be specific about what you want to see.
- `ps -u <username>` lists the processes belonging to a given user account.
- Output can be filtered by piping into `grep` — e.g. `ps -u <user> | grep firefox`.
  Chuck notes `grep` stands for "global regular expression print" and is Linux-speak for
  finding/filtering stuff.
- `ps aux` is Chuck's most-used form: `a` = all users, `u` = show the owning user of each
  process, `x` = include processes not attached to a terminal. Its first large block of
  processes is typically owned by root.
- The most common everyday pattern is `ps aux | grep <program>` to locate a process.
- `pgrep <name>` combines `ps` and `grep` into one command and returns a process's PID by
  name directly — an easy way to find a process quickly. Caveat: `pgrep` is not installed
  on every system, which is why Chuck often falls back to `ps aux | grep`.
- `ps --help` shows help-for-the-help because the command is so large; use
  `ps --help simple` for a simple rundown of options.
- `top` is a live monitor of running processes sorted by CPU usage, showing PID, user,
  CPU and memory; press `q` to quit. In the lab, the top consumer is the VNC process used
  to access the box in the browser.
- `htop` does essentially the same thing as `top` but looks nicer/cooler; press `q` to
  quit.
- To kill a stuck/frozen process, use the `kill` command, which requires a process ID or
  job ID — you cannot kill by typing the program name with plain `kill`.
- There are foreground and background processes. A foreground process (e.g.
  `ping -c 100 networkchuck.com` or `sleep 30`) occupies the terminal so you cannot do
  anything else until it finishes or is stopped.
- Ctrl+C stops/interrupts a foreground process.
- Ctrl+Z stops (pauses/"puts to sleep") a foreground process rather than killing it.
- `jobs` lists current/stopped jobs in a jobs table, each with a job number/label.
- `bg` continues a stopped job in the background (specify the job ID, e.g. `bg 1`, when
  there is more than one job); a background process keeps running and cannot be stopped
  with Ctrl+C or Ctrl+Z.
- `fg` (e.g. `fg 1`) brings a background/stopped job back to the foreground, where Ctrl+C
  can then stop it.
- Appending `&` to a command (e.g. `ping -c 300 hackthebox.eu &`) launches it straight
  into the background without touching the foreground.
- Processes have statuses (running, waiting/sleeping, stopped, zombie, and more). A
  stopped process shows status `T` in `ps -ax` — `T` stands for "traced" but effectively
  means stopped.
- Killing a process actually sends a kill signal; `kill -l` lists all available signals.
- Signal 15 (SIGTERM) is the default sent when no signal is specified — it politely asks
  the process to die, and the process can refuse, so a default `kill` may not terminate a
  misbehaving process.
- The keyboard shortcuts are themselves kill signals: Ctrl+Z = signal 19 (SIGSTOP),
  a second/related Ctrl+Z path = 18 (SIGCONT / continue), and Ctrl+C = signal 2
  (SIGINT / interrupt).
- `kill -19 <PID>` is equivalent to Ctrl+Z (stop); `kill -2 <PID>` is equivalent to
  Ctrl+C (interrupt).
- Signal 9 (SIGKILL), used as `kill -9 <PID>`, forcibly terminates a process with no
  negotiation — the process has no option but to die.
- `pkill` is to `kill` what `pgrep` is to `ps`: it kills by name instead of PID —
  e.g. `pkill -9 <name>` kills all matching processes at once (Chuck kills all `ping`
  processes at once this way).

## Notable verbatim quotes

> "The easiest command to remember in Linux, if you want to get rid of something, you kill it."

> "There's about 15,000 different ways to do one thing in Linux."

> "It's more like a suggestion: please die, process, but please do it at your leisure whenever you want. And if you don't want to, then that's fine too."

> "The command that will kill no matter what. It's not asking, it's not suggesting, it's saying: you will die. It's forcibly terminating a process."

> "Just like the ps command had the pgrep command, the kill command has the pkill command."

> "Have you hacked the YouTube algorithm today? ... You gotta hack YouTube today. Ethically, of course."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: Linux for Hackers EP7 — process management -->
