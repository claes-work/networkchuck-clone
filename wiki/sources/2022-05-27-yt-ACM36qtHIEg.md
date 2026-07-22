---
type: youtube-video
source_date: 2022-05-27
url: https://www.youtube.com/watch?v=ACM36qtHIEg
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [linux-terminal, cybersecurity]
tags: [linux, terminal, tmux, productivity, shortcuts, cli]
---

# you need to HACK faster!! (Linux Terminal hacks YOU NEED!!)

## Summary

A Linux terminal productivity tutorial framed as "becoming a hacker/ninja" by working
faster at the command line. Chuck walks through a graduated list of shell tricks — from
basic `cd`/`ls` navigation up to command-line editing shortcuts, aliases, history search,
and log-watching — demonstrated live in a Hack The Box Academy browser-based Linux
instance (the video's sponsor and part of Chuck's broader "become a hacker" series). The
recurring thesis: none of these tips saves much time individually, but integrated into
daily Linux work they compound into large time savings. Note: despite the "tmux" tag,
this video does not actually cover tmux; the content is core Bash navigation, readline
editing shortcuts, and aliases.

## Key claims (dated — the tips/tools)

All dated 2022-05-27 (video publication).

- `cd` with no arguments returns you to your home directory (shown by the `~` tilde
  prompt); confirm location with `pwd`.
- `cd <path>` changes to any directory by path (e.g. `cd /usr/var/...`).
- `cd ..` moves up one directory; `cd ../..` moves up two, and you can chain more
  `../` segments to jump back multiple levels at once.
- `Ctrl+L` clears the terminal screen (faster alternative to typing `clear`).
- The up/down arrow keys scroll through command history to re-run previous commands.
- `cd -` (dash) jumps back to the previous directory you were in; it works by reading the
  built-in `OLDPWD` variable, which you can inspect with `echo $OLDPWD` (and current
  location with `echo $PWD`).
- `ls -l` lists directory contents as a detailed top-down list instead of a jumbled row.
- `ls -a` reveals hidden files (those with a leading dot, e.g. `.bashrc`); Chuck commonly
  uses `ls -al` together.
- Pre-defined aliases `ll` and `la` are faster shortcuts for common `ls` variants (they
  live in `.bashrc`).
- Aliases let you create your own commands: `alias lumos='ls -al'` makes `lumos` run
  `ls -al`. Aliases defined at the prompt are temporary and vanish on logout; to make one
  permanent, add the same `alias` line to your `~/.bashrc` file (edited with `nano .bashrc`).
- Tab completion: pressing `Tab` auto-completes a command or path when there is enough to
  uniquely match; pressing `Tab` twice (tab-tab) lists all available options/matches.
- `Ctrl+Shift++` (or `Ctrl++`) zooms the terminal in; `Ctrl+-` (or `Ctrl+Tick` /
  `Ctrl+Shift+Tick`) zooms out — bindings may vary by terminal.
- Copy/paste in the terminal: `Ctrl+Shift+C` copies selected text, `Ctrl+Shift+V` pastes
  (may vary by terminal emulator).
- Readline line editing: `Ctrl+A` jumps the cursor to the start of the line; `Ctrl+E`
  jumps to the end.
- `Ctrl+U` deletes everything before the cursor (cut); `Ctrl+Y` pastes back what was cut
  at the cursor position.
- `Ctrl+K` deletes everything after the cursor (opposite of `Ctrl+U`); combined with
  `Ctrl+A`/`Ctrl+E`/`Ctrl+Y` you can cut and re-paste text without leaving the keyboard.
- `Alt+Backspace` deletes just the last/current word.
- `Ctrl+X` then `E` opens the current command line in your default editor (nano on the
  Hack The Box VM); on save+exit the edited command runs.
- `less <file>` is better than `cat` for large files (e.g. logs) because it loads only
  part of the file rather than the whole thing at once; press `q` to quit.
- `sudo !!` re-runs your previous command with `sudo` prepended — a fast fix for
  "permission denied" errors. `!!` expands to the most recent command.
- `tail <file>` shows the last 10 lines of a file (useful for logs, e.g.
  `/var/log/auth.log`).
- `tail -f <file>` follows a file in real time, printing new lines as they are added
  (e.g. watch `auth.log` while `sudo useradd bernard` in another terminal adds a user);
  `Ctrl+C` stops the follow.
- `Ctrl+R` reverse-searches command history as you type; press `Ctrl+R` again to cycle
  through older matches, and the right arrow to bring the found command into the prompt.

## Notable verbatim quotes

> "To be a good hacker. You've gotta be fast at Linux. You gotta be a command line ninja
> navigating the Linux shell, like a wizard."

> "that dot dot is our DeLorean. That takes us back in time or just back one directory."

> "we can either type in clear like a loser. If you do that, let me make fun of you.
> I've done it. They've made fun of me. Or just hit control L and it clears the terminal."

> "This will probably be the biggest thing that'll impact your Linux speed right here.
> Instead of finishing typing, this hit tab. Whoa, Linux just read our mind."

> "each of these things aren't really saving me a lot of time individually. Individually,
> if you add all this stuff up and integrate all these things into the things you do all
> the time on Linux — years, years off your life. This is a fountain of youth right here."

> "the command less because it can do more with less. I think, I don't know. I'm just
> making crap up."

> "That's some wax on wax off situation right here."

> "have you hacked the YouTube algorithm today? ... You gotta hack YouTube today.
> Ethically. Of course."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
