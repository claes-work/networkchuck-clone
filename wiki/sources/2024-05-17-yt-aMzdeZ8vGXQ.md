---
type: youtube-video
source_date: 2024-05-17
url: https://www.youtube.com/watch?v=aMzdeZ8vGXQ
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [linux-terminal, homelab-selfhosting]
tags: [xclip, clipboard, terminal, bash-alias, wsl, x11-forwarding, ssh, five-minute-friday]
---

# I use this everyday

## Summary

A "five minute Friday" short in which Chuck shows how to copy and paste to and from
the Linux/WSL terminal clipboard using **`xclip`** (a command-line clipboard utility).
The motivation: macOS ships `pbcopy`/`pbpaste`, but those commands don't exist on
Linux or Windows. Chuck installs `xclip` (`sudo apt install xclip`), then wires up
bash aliases named `pbcopy` and `pbpaste` (deliberately reusing the Mac names so he
doesn't get confused switching between machines). He demonstrates piping a large file
or a whole article into the clipboard, then piping the clipboard into other commands —
notably `fabric` to summarize an article. The second half extends this to remote Linux
servers over SSH: install `xclip` on the remote, ensure `X11Forwarding yes` in
`/etc/ssh/sshd_config`, replicate the aliases there, and connect with `ssh -X` to force
X11 forwarding so the clipboard works on the remote box.

## Key claims

- (2024-05-17) The everyday tool is **`xclip`**, a command-line program used to access
  and manipulate the clipboard. It's what makes terminal copy/paste possible on Linux
  and WSL, where macOS's `pbcopy`/`pbpaste` don't exist. [paraphrase]
- (2024-05-17) Install it on Debian/Ubuntu with `sudo apt install xclip`. [paraphrase]
- (2024-05-17) Copy into the clipboard by piping to `xclip -input -clipboard` (e.g.
  `cat largefile | xclip -i -clipboard`); paste out with `xclip -output -clipboard`,
  which can also be redirected to a file. [paraphrase]
- (2024-05-17) Because the raw commands are long, Chuck defines bash aliases in
  `~/.bashrc`: `alias pbcopy='xclip -i -clipboard'` and `alias pbpaste='xclip -o -clipboard'`,
  then reloads with `source ~/.bashrc`. He names them after the Mac commands on purpose
  so his workflow is identical across his Mac and Linux machines. [paraphrase]
- (2024-05-17) The workflow reason he relies on it daily: piping clipboard content
  into other tools — especially **`fabric`** to summarize an article or transcript —
  instead of messily pasting large blobs directly into the terminal. [paraphrase]
- (2024-05-17) To get clipboard access on a remote Linux server: install `xclip` there,
  ensure `X11Forwarding yes` is set (and not commented out) in `/etc/ssh/sshd_config`
  (restart with `sudo systemctl restart ssh`), replicate the aliases in the remote
  `~/.bashrc`, and connect with `ssh -X user@server` to force X11 forwarding. [paraphrase]
- (2024-05-17) This remote trick works Linux→Linux (including WSL→Linux) but does NOT
  work Windows→Linux — don't bother trying. [paraphrase]
- (2024-05-17) X11 forwarding is a feature that lets you run a program on one server but
  display its graphics on another; Chuck leverages it to route clipboard actions. [paraphrase]

## Notable verbatim quotes

> "This is one of those things you didn't know you needed, but you'll end up using it every day."

> "I did this because I have a Mac and I don't want to get confused."

> "I seriously use this every single day, especially when I'm playing with fabric."

> "X11 forwarding... is a really cool feature that allows you to run a program on one server, but display the graphics on another. We're going to use that to do some clipboard magic."

> "What doesn't work is Windows logging into a Linux server. You can try to make it work. It's not a good time, just don't even think about it."

> "Have you hacked the YouTube algorithm today? ... You got to hack YouTube today, ethically, of course."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
