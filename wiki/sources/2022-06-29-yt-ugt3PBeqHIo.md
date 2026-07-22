---
type: youtube-video
source_date: 2022-06-29
url: https://www.youtube.com/watch?v=ugt3PBeqHIo
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [linux-terminal]
tags: [linux, recovery, troubleshooting, boot, learn-by-breaking]
---

# i KILLED my Linux computer!! (to teach you something)

## Summary

A Linux fundamentals lesson framed around Chuck deliberately destroying a
disposable Linux machine to teach file/directory management and the danger of
destructive commands. The box belongs to Hack The Box Academy (the series
sponsor), whose free, resettable cloud lab is pitched as the safe place to
"break" Linux without consequences. Chuck's stated pedagogy is explicit and
repeated: **"Build it, learn it, break it."** The tutorial walks through
creating files (`touch`, `cat`, `cat` with here-doc/`EOF`, `echo`), creating
directories (`mkdir`, `mkdir -p` for nested parent/child directories),
inspecting them (`ls -l`, `tree`), moving and renaming (`mv`), copying
(`cp`, `cp -r`), and deleting (`rm`, `rmdir`, `rm -r`, `rm -rf`). The climax is
the infamous `sudo rm -rf --no-preserve-root /` command, which wipes the file
system and leaves the machine unusable — demonstrating live that "everything in
Linux is a file," so deleting files deletes the commands themselves. As a final
stunt he uses a bash `for` loop to create over 1.1 million nested directories
(named `another one`) to probe how many directories it takes to break Linux.

## Key claims (dated — the concepts)

All dated 2022-06-29 (paraphrase unless quoted):

- Chuck's teaching method is "build it, learn it, break it" — you learn Linux by
  creating things, then intentionally breaking them in a safe/ephemeral environment.
- `touch <file>` creates an empty file; multiple filenames after `touch` create
  several files at once.
- `cat <file>` displays a file's contents; `cat > file.txt` (then Ctrl+D) writes
  typed input into a file; `cat << EOF > file.txt` starts a here-document that
  accepts multiline input until the delimiter (`EOF`, which can be any word) is
  entered — useful in bash scripts.
- `echo "text" > file.txt` is a quick one-liner to create a file with content.
- `mkdir <name>` makes a directory; passing multiple names makes several. A
  directory is the Linux term for what Windows calls a folder.
- In `ls -l`, the first character of the permission string tells you the type —
  `d` for directory, `-` for a file — a more reliable signal than color (Chuck
  notes he is colorblind and distrusts relying on color in tech).
- `mkdir -p parent/child/child` creates a directory tree, making parent and child
  directories in one command (`-p` = parent).
- `tree` displays the current directory as a visual tree of nested directories.
- `mv <file> ./dir` moves a file; `./` means "right here / current working
  directory," and omitting it makes Linux look at the root (`/`), causing a
  permission-denied / not-found error. `mv file ./dir/newname.txt` moves and
  renames in one step; multiple files can be moved at once.
- `cp <file> <dest>` copies (leaving the original in place); handy for backing up
  a file before changing it. `cp file file.bk` backs up within the same directory
  (destination must have a different name).
- Copying a non-empty directory requires `cp -r` (recursive) — it errors without
  it.
- `rm <file>` deletes a file (multiple at once supported); deletion is not
  reversible.
- `rmdir <dir>` removes a directory but refuses if it is not empty — Linux
  "protecting you from yourself."
- `rm -r <dir>` recursively removes a directory and everything inside it.
- `rm -rf --no-preserve-root /` with `sudo` forcibly, recursively deletes the
  entire file system from root: `-f` = force (ignore all warnings), `--no-preserve-root`
  removes root's special protection. This breaks the machine 100%.
- Because "everything in Linux is a file," deleting the file system also deletes
  the binaries/commands themselves, so afterward even basic commands (`pwd`,
  `echo`) no longer work.
- There is a per-command limit on nested child directories (Chuck could create
  only ~600 in one `mkdir -p`), so he wrote a bash `for` loop repeating it ~1500
  times to reach 1,116,017 directories.
- Warnings: only run destructive commands on a temporary/ephemeral machine; on
  Hack The Box's free tier you get ~one instance per day, so a wipe can't be reset
  until the next day (paid users can reset freely).

## Notable verbatim quotes

> I created over 1 million directories in Linux with one command. Why? I don't
> know. I just wanted to see if I could do it, but seriously, how many
> directories will it take to break Linux?

> This is gonna teach you something you're gonna learn. I'm gonna force you to
> learn. So get your coffee, ready time to learn some Linux and watch me do
> something stupid.

> Okay. Build it, learn it, break it. Pitch wisdom for the kids.

> The first thing we always do is launch our home, our terminal, our happy place.

> Colors can trick you trust me. But over here, this won't trick you it'll tell
> you exactly what's going on.

> When I'm dealing with tech, I don't rely on colors because I am colorblind. I
> hate colors.

> Now we've had so much fun creating things. What do you say? We destroy? I say we
> should do that.

> We're gonna go, Nope, gas, the pedal going right through it all. That's what
> force means.

> Remember everything in Lenux is a file. And we just deleted a lot of files. So
> those files were our commands. Those files were things, how we did things. So
> that's how you can break Linux.

> Also don't ever do this on any other computer, unless it's temporary or
> ephemeral.

> Have you hacked the YouTube algorithm today? [...] We gotta hack YouTube today.
> Ethically. Of course.

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: 'learn by breaking then fixing' teaching style -->
