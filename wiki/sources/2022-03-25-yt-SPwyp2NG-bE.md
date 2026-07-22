---
type: youtube-video
source_date: 2022-03-25
url: https://www.youtube.com/watch?v=SPwyp2NG-bE
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [linux-terminal, cloud-devops]
tags: [bash, scripting, linux, free-course, learn-x-now, ep-1, course-kickoff]
---

# you need to learn BASH Scripting RIGHT NOW!! // EP 1

## Summary

Episode 1 of Chuck's **Bash scripting series**, delivered in his signature "learn X RIGHT
NOW" free-course format. He opens with the hard sell — learning Bash makes you awesome,
powerful, and valuable to employers, giving you the power to automate hacking, cloud VM
creation, and "pretty much anything in IT" faster. He then defines Bash: it stands for the
"Bourne Again Shell," a better version of the 1970 shell, made in 1989 (a "fun fact,"
the same year Chuck was born). Bash is both the command line for interacting with Linux
(the shell that "wraps itself around the Linux kernel") AND a powerful
programming/scripting language.

The hands-on lab spins up a Linux box in the cloud via sponsor **Linode**
(linode.com/networkchuck, $100/60-day credit for new users, ~1 cent/hour otherwise),
connects over SSH, and confirms the shell with `which $SHELL`. Chuck teaches the core
loop of a first script through a running gag — automating "saying hi to your mom":
`echo` at the command line, then writing the same into a `.sh` file with the **nano**
text editor, opening with the **shebang** (`#!/bin/bash`) to tell the interpreter which
scripting language to use, adding `sleep` delays to fake a conversation, and running it
with `bash hi-mom.sh`. He then covers execution the other way — `./hi-mom.sh` fails with
"permission denied," introduces file permissions via `ls -l` (read/write/execute), and
fixes it with `chmod +x`. He closes by deleting the Linode to stop billing (a whole
penny) and previews that future episodes will keep building until viewers are "bash
masters." Ends on the recurring "hack the YouTube algorithm... ethically of course" CTA.

## Key claims (dated — teaching + course kickoff)

- **[2022-03-25]** Course kickoff: this is **episode 1** of a multi-part Bash scripting
  series that will take viewers from "what the junk is a bash script" to reading/writing
  hacking scripts; each future episode keeps building on the last. (paraphrase)
- **[2022-03-25]** Value pitch: learning Bash makes you "a better nerd," lets you automate
  things (hacking networks, creating cloud VMs) faster, and makes you powerful and
  valuable to employers. (paraphrase)
- **[2022-03-25]** Definition: Bash stands for the **"Bourne Again Shell"** — a better
  version of the shell created in 1970; Bash was made in 1989. (paraphrase)
- **[2022-03-25]** Bash is two things: (1) the command line / shell that interacts with
  the Linux OS by wrapping around the Linux kernel, and (2) a powerful scripting/
  programming language for writing automation scripts. (paraphrase)
- **[2022-03-25]** Lab setup: you need Linux (and coffee). Chuck uses **Linode** to deploy
  a cloud Linux box in seconds — Ubuntu 21, Dallas, shared CPU, ~1 cent/hour; new users
  get a $100 credit for 60 days. WSL2 on Windows or any existing Linux also works.
  (paraphrase)
- **[2022-03-25]** You connect to the cloud box via **SSH** from Windows CMD (or terminal
  on Mac/Linux), accepting the fingerprint and entering the password. (paraphrase)
- **[2022-03-25]** `which $SHELL` confirms which shell you're in (returns the bash shell).
  (paraphrase)
- **[2022-03-25]** Core concept: a bash script is just command-line commands — instead of
  typing them one by one, you put them in a script and it runs automatically. That's it.
  (paraphrase)
- **[2022-03-25]** `echo "text"` makes Linux print/say text; it's the simple command used
  for the first script. (paraphrase)
- **[2022-03-25]** **nano** is a simple terminal text editor (like Notepad on Windows or
  TextEdit on Mac); `nano hi-mom.sh` creates/edits a `.sh` shell script file. (paraphrase)
- **[2022-03-25]** The first two characters of a script, `#!`, are called a **shebang**;
  followed by `/bin/bash` it tells the interpreter which scripting language to use (Bash,
  vs. Python, Go, etc.). Always include it in your scripts. (paraphrase)
- **[2022-03-25]** `sleep <n>` pauses the script for n seconds — used to space out the
  fake conversation. (paraphrase)
- **[2022-03-25]** `ls` lists files; `bash hi-mom.sh` runs the script via the interpreter.
  (paraphrase)
- **[2022-03-25]** Running with `./hi-mom.sh` (period-slash = "the script is right here")
  fails with **"permission denied"** because the file lacks the executable permission.
  (paraphrase)
- **[2022-03-25]** `ls -l` shows a file's permissions (read `r`, write `w`, execute `x`);
  a dash where the `x` would be means no execute permission. (paraphrase)
- **[2022-03-25]** `chmod +x hi-mom.sh` changes permissions to add the executable
  permission, after which `./hi-mom.sh` runs. (paraphrase)
- **[2022-03-25]** Reassurance/pedagogy: if it feels overwhelming, take it slow, pause and
  rewind; beginners who are lost should watch his **Linux for Hackers** series first.
  (paraphrase)
- **[2022-03-25]** Cost note: delete the Linode when done so you stop being charged — an
  hour of use cost about one penny. (paraphrase)

## Notable verbatim quotes

> "If you wanna become a hacker or a cloud engineer, or pretty much anything in IT,
> learning bash, learning this skill will make you awesome... this will make you a better
> nerd."

> "So just learn it. Okay. Just learn it. So are you ready to learn bash? Let's get
> started."

> "bash stands for the born again shell born again, because first I like to believe that
> Linux loves Jesus, but also because it's a better version than the one created in 1970,
> this was made in 1989 fun fact, the same year I was made"

> "all I wanted to hit home with here is that a bash script is just command line commands.
> That's it. But instead of you entering them one by one, we put it into a script and it
> runs auto magically."

> "these two characters combined are called a shebang. And then just after that, put in
> slash bin slash bash"

> "You just created a bash script. This might be your first one. So congrats. And it's a
> big deal. Don't downplay that."

> "in the coming episodes, we're gonna dive deeper into bash scripting. And in each
> episode we're gonna keep building and building and building... until we are bash masters
> or experts or dudes or something."

> "Have you hacked the YouTube algorithm today? ... We gotta hack YouTube today. Ethically
> of course."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: Bash scripting course kickoff (EP 1) — learn-X format free course -->
