---
type: youtube-video
source_date: 2021-04-16
url: https://www.youtube.com/watch?v=Y17KTiJLcyQ
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [linux-terminal, cybersecurity]
tags: [linux-for-hackers, man-pages, help, tldr, linux, ep-3]
---

# HELP!! (for when you suck at Linux) // Linux for Hackers // EP3

## Summary

Episode 3 of NetworkChuck's free "Linux for Hackers" course (sponsored by, and
following along in, the Hack The Box Academy Linux lab; EP1 covers lab setup, EP2
precedes this one). The episode has three parts: (1) how to get help with any Linux
command from inside the terminal, (2) getting to know the terminal/shell better, and
(3) a rapid-fire tour of commands for learning about the system you're on.

Chuck's framing throughout is that Linux is complex, nobody remembers every command
and switch, and feeling lost is normal — so the single most important skill in Linux
is knowing **how to get help / how to learn for yourself**. He deliberately fires
through ~15 system-info commands too fast to absorb, precisely to trigger the "I need
help" feeling, then teaches the help tools.

Terminal concepts covered: the modern "terminal" is really a **terminal emulator** (a
GUI window pretending to be an old physical terminal like the VT100 keyboard+monitor);
the **shell** is the actual user interface to the OS/kernel, and the terminal emulator
is what you use to interact with the shell. Common shells: **bash** (Bourne Again
Shell, the default here and most common), plus zsh, fish, and even **PowerShell**
(pwsh) running on Linux. He also decodes the prompt: `user@hostname`, current
directory, and the trailing `$` (regular user) vs `#` (root).

Help tools taught: `man`, `--help` / `-h`, and `apropos`. System-info commands toured:
`ps`, `id`, `hostname`, `uname`, `ifconfig`, `ip`, `netstat`, `ss`, `who`, `env`,
`lsblk`, `lsusb`, `lsof`.

> Note: The title/course branding references "tldr" as a help tool, but `tldr` is
> **not** demonstrated in this transcript; the help tools actually shown are `man`,
> `--help`/`-h`, and `apropos`.

## Key claims (dated — the help tools/commands)

All dated 2021-04-16 (paraphrase unless quoted).

**Getting help:**
- `man <command>` opens the full built-in manual page for a command (description,
  switches, usage); press `q` to quit out of it. Chuck's mnemonic: "consult the man."
- `<command> --help` or `<command> -h` prints a shorter help/usage summary (the
  switches and how to use them) instead of a full manual — most commands support one
  or the other.
- `apropos <keyword>` does a keyword search across command names and documentation to
  find the command you want when you don't remember it (e.g. `apropos usb` surfaces
  `lsusb`; `apropos compress` surfaces file-compression tools).

**Terminal / shell:**
- `ps` (process status) lists running processes; used here to reveal which shell you're
  running (e.g. `bash`, or `pwsh` for PowerShell).
- The prompt shows `username@hostname`, your current directory (same info as `pwd`),
  and `$` for a normal user vs `#` for root — a handy reminder you have "godlike power"
  as root.

**System-info command tour (fast, minimal detail — homework is to `man` each):**
- `id` — info about your user (uid, groups).
- `hostname` — the machine's host name.
- `uname` — seemingly says little ("Linux") but reveals a lot with options.
- `ifconfig` — network configuration/info.
- `ip` — more network info, with many options.
- `netstat` — network status.
- `ss` — socket/session status.
- `who` — who else is logged into the system (sibling of `whoami`).
- `env` — environment variables (covered later in the series).
- `lsblk` — list block devices (hard drive info).
- `lsusb` — list USB devices plugged in.
- `lsof` — list open files (a lot of them).

## Notable verbatim quotes

> "to get help with pretty much any command out there we're going to consult the man
> the command is literally man oh man and then the command you're curious about"

> "you can either do dash h for help most commands will have that and if they don't
> have that they'll have dash dash help you can usually use either of those"

> "there's a command for that just hopefully you don't forget this command because
> then you're you're screwed the command is apropos"

> "it'll do a keyword search through the commands and the documentation"

> "that's like really the biggest thing you learn in linux is how to learn for
> yourself"

> "he's actually not a terminal he's a terminal emulator he's just pretending"

> "that's not the terminal no no no that is the shell the shell is the user interface
> we use to interact with the operating system the linux kernel"

> "bash or born against shell it is by far the most common shell you'll see"

> "when your login is root it's going to have a pound sign there instead ... because
> you do have godlike power at that point you got to be careful"

> "i want you to think i need help and right now i'm going to show you how to get that
> help"

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: Linux for Hackers EP3 — getting help in Linux -->
