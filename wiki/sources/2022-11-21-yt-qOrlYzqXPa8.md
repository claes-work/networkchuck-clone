---
type: youtube-video
source_date: 2022-11-21
url: https://www.youtube.com/watch?v=qOrlYzqXPa8
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [linux-terminal]
tags: [macos, terminal, tips, reference, cli]
---

# 50 macOS Tips and Tricks Using Terminal (the last one is CRAZY!)

## Summary

A ~10-minute, fast-paced reference video walking through 50 macOS Terminal commands
and tricks. It is the macOS companion to Chuck's Linux and Windows command-reference
videos, and it doubles as evidence that he uses and teaches macOS in addition to
Linux/Windows. Structured as escalating tiers of coolness — fun tricks, macOS-native
utilities, cross-over Unix/Linux commands (macOS is Unix-based), shell/system
maintenance, Homebrew-installed "fun" toys, and a headline "best for last" trick
(Touch ID as your `sudo` password). Sponsored by Dashlane, with a mid-roll password-
manager segment. Frames macOS as very close to Linux since both are Unix-based, so
"a lot of the commands on Linux work on Mac."

## Key claims (2022-11-21) — categories / notable tips

Paraphrase unless quoted. Command spellings corrected only where captions garbled
obvious commands.

**macOS-native fun / novelty tricks**
- `say <text>` — makes the Mac speak text aloud from the terminal (he uses it to mess
  with his kids).
- `security find-generic-password -w <wifi-name>` — recovers the stored password of
  any Wi-Fi network the Mac has ever connected to.
- `pbcopy` — pipe any command's output to the clipboard (`<command> | pbcopy`); works
  with any command.
- Plain-text paste keyboard shortcut: `Cmd + Option + Shift + V` (paste without
  formatting) — noted as not a terminal command but "still pretty cool."
- `caffeinate` — keeps the Mac awake as long as the terminal is running; `Ctrl+C` to
  stop.

**Screenshots**
- Keyboard captures: `Cmd+Shift+3` (whole screen), `Cmd+Shift+4` (select region),
  `Cmd+Control+Shift+4` (region to clipboard).
- `defaults write com.apple.screencapture name <name>` — change the default
  screenshot filename; also `type` option (e.g. JPEG) and `location` option to change
  file type and save location.

**Privacy / downloads history**
- macOS keeps a history of everything downloaded in a SQLite3 database; commands shown
  to view that history and to clear it.

**Account / password**
- `passwd` — change your user password without leaving the terminal, then update the
  keychain.

**Cross-over Unix/Linux commands (macOS is Unix-based — "a lot of the commands on
Linux work on Mac")**
- Navigation/files: `cd`, `cd` (alone → home), `ls`, `pwd`, `whoami`, `mv`, `cp`.
- macOS-specific `ditto` — a "better version" of `cp` that works similarly.
- `df -h` — disk space; `nano` — edit files in-terminal (`Ctrl+X`, Y, Enter to save);
  `man` — command manuals (`q` to quit); `open` — open files/apps from the terminal.
- Networking: `ping`, `ifconfig` (and `ifconfig en0`), filtering with `grep inet`,
  regex to pull just IPv4/IPv6 addresses, `traceroute`, `dig` for DNS.
- Processes: `ps`, `ps -ax`, `top`, `top -o rsize` (sort by memory), and `kill -9 <pid>`
  after finding the PID (one of his favorite commands).

**Shells & system**
- `echo $SHELL` — shows current shell (Zsh); switch to `bash`, switch back with `zsh`.
- `uptime` — how long the Mac has been up.
- Flush DNS cache — a series of `sudo` commands.
- `qlmanage -p <file>` — Quick Look preview from the terminal.
- `diff <file1> <file2>` — compare two files.
- `curl <url>` — download files (redirect output to a file); `curl wttr.in/<location>`
  — weather in the terminal.
- `leave <hhmm>` — set a terminal alarm reminding you to leave.
- `history` — show all previously typed commands.
- `sudo spctl --master-disable` — disable Gatekeeper (warns: don't do this for people
  who don't need it, e.g. parents).

**Homebrew + "fun" packages**
- Install Homebrew first — "the missing package manager for macOS."
- `brew install cmatrix` → `cmatrix` (Matrix rain, "take the red pill, Neo").
- `brew install asciiquarium` → `asciiquarium`.
- `brew install toilet` → ASCII text art (fun fact: he used to sell toilets).
- `brew install samtay/tui/tetris` (Tetris in the terminal) — caption garbled as
  "Sam t Tetris"; type `tetris` to play.

**Python & shutdown**
- `python3 -m http.server` — start a quick web server on port 8000 so anyone on the
  network can browse/share files at your IP:8000; `Ctrl+C` to stop. macOS ships with
  Python 3 by default.
- `shutdown -h now` (shut down) / `shutdown -r now` (restart) from the terminal.

**"Best for last" (the CRAZY one)**
- Use Touch ID as your `sudo` password: edit `/etc/pam.d/sudo` with `sudo nano`, and
  just below the first comment add the line
  `auth sufficient pam_tid.so`, then save (`Ctrl+X`, Y, Enter). After that, `sudo`
  commands authenticate with the fingerprint reader. Called "best command ever."

## Notable verbatim quotes

> "Here are the top 50 Mac OS terminal commands you need to know. So get your coffee ready. This will take about 10 minutes."

> "Did you know your Mac keeps a record of all the wifi passwords you've ever used and we can find those passwords right from the terminal."

> "Now you may have known that Mac is very similar to Linux. They're both Unix based, which means a lot of the commands on Linux work on Mac."

> "We have to install brew because everything good starts with a good brew there. Check Coffee Brew is known as the missing package manager for Mac."

> "Chuck, can I play Tetris and Terminal? The answer is yes. Duh."

> "If you're like me, you're tired of typing in your pseudo password. If only we could just use our finger instead of pseudo. And that's what this is. You can use your touch ID on your MacBook as your pseudo password."

> "That's killer. Best command ever. Video over, bye."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: 50 macOS terminal tips — command-reference genre (macOS) -->
