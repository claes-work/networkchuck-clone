---
type: youtube-video
source_date: 2021-05-21
url: https://www.youtube.com/watch?v=jwnvKOjmtEA
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [linux-terminal, cybersecurity]
tags: [linux-for-hackers, sudo, users, permissions, ep-4]
---

# sudo = POWER!! (managing users in Linux) // Linux for Hackers // EP4

## Summary

Episode 4 of the free "Linux for Hackers" course, taught by Chuck Keith using a
browser-based Linux lab from sponsor Hack The Box Academy (Linux Fundamentals course,
User Management module). The whole lesson is framed as an Avengers-vs-Thanos story:
the viewer creates user accounts (the Avengers) to stop Thanos from wiping out the
system, and `sudo` is repeatedly compared to the Infinity Gauntlet — temporary,
super-powerful access you slip on for a single command.

Chuck walks through the core of Linux user, group, and permission management: who a
user is (`whoami`), creating users two different ways (`adduser` vs `useradd`),
inspecting the account files (`/etc/passwd`, `/etc/shadow`, `/etc/group`), setting and
changing passwords (`passwd`), modifying accounts (`usermod`), switching/impersonating
users (`su`), and deleting users (`userdel`). He then dives into `sudo` proper — what
the root/super user is, why you should never log in as root, and how the sudoers file
(`/etc/sudoers`, edited safely with `visudo`) controls who may use `sudo`. He shows
groups end-to-end: creating a group (`groupadd`), granting a group sudo rights in the
sudoers file, adding a user to a group with append (`usermod -aG`), removing a user
from a group (`gpasswd -d`), checking your own groups (`groups`), and deleting a group
(`groupdel`). The episode closes on the principle of least privilege — Iron Man
destroys the Infinity Gauntlet group, removing even his own special access.

## Key claims (paraphrase; dated 2021-05-21)

- To do anything on a Linux system you must be a user on it; `whoami` prints which user
  account you currently are.
- Not all users are equal; `/etc/passwd` lists every user account on the system, many
  of which are service accounts that can't be logged into but still serve a purpose.
- There are two commands to create a user and, confusingly, they both work but differ:
  `adduser` is the "full" interactive one (prompts for password, name, etc.) and
  `useradd` is "lazy" — it just creates the bare account and does nothing else.
- Adding a user requires root; running the command without elevation fails with "only
  root may add a user." Prefixing with `sudo` borrows root's power for that one command.
- Chuck describes `sudo` as "kind of like saying please in Linux" — asking for super
  powers to run a command; it stands for "super user do."
- In `/etc/passwd`, each line's fields are: username, an `x` (password is stored
  elsewhere), UID, GID, comment/name info, home directory, and default login shell.
- The `x` after the username means the password is stored separately in the shadow file
  at `/etc/shadow`, which needs sudo to read; the value stored there is a hash, not the
  plaintext password.
- Creating a user also creates a matching group of the same name with that user as its
  only member; that's why new users get both a UID and a GID (e.g. 1001/1001).
- `adduser` gives a user a bash shell and a home directory by default; `useradd` does
  not set a password, defaults the shell to `sh`, and does not create a home directory
  (you can add one with the `-m` switch).
- `passwd <user>` sets or changes a password for a user (note: `passwd` with no "o-r").
- `usermod` modifies an existing account: `--shell /bin/bash` changes the login shell,
  and `-l <newname> <oldname>` renames the user's login name.
- The root user (super user) is the boss — can change or delete anything, including
  `rm -rf` everything — so sudo access is dangerous and, by default, restricted; you
  don't want to hand it to just anyone.
- `su` switches/impersonates another user (`su - <user>`); with no username it switches
  to root. Using `su` normally requires the target user's password, but `sudo su -`
  becomes root without needing the root password — which is why you keep sudo and never
  log in as root directly.
- Exit an impersonated user shell with Ctrl-D, `exit`, or `logout`.
- A user not listed in the sudoers file can't use sudo; attempting it fails with "you're
  not in the sudoers file, this incident will be reported."
- The sudoers file (`/etc/sudoers`) defines who may use sudo. Best practice is to edit
  it only with `sudo visudo`, never a plain text editor, because visudo runs a syntax
  check and refuses to save a broken file (protecting you from bricking the system).
- A sudoers entry has the form `username host = command` — e.g. `thanos ALL = ALL`
  grants all commands on all systems; you can restrict to a single command by naming its
  path (e.g. `/sbin/useradd`).
- A `%` prefix in the sudoers file denotes a group; members of the `sudo` group get
  full sudo access, and a `NOPASSWD: ALL` entry lets them run any command without a
  password (convenient but risky).
- `groupadd <name>` creates a group; `/etc/group` lists all groups and their members and
  is more self-explanatory than `/etc/passwd`.
- `groups` prints which groups the current user belongs to; being in the `sudo` group is
  what grants gauntlet/sudo access.
- `usermod -aG <group> <user>` appends a user to a group; `-a` means append so existing
  group memberships are preserved. Using `-g` alone would replace all other groups.
- `gpasswd -d <user> <group>` removes a user from a group.
- `userdel <user>` deletes a user account.
- `groupdel <group>` deletes a group; deleting a group does not delete the users in it,
  it just removes the group (and any special privileges it granted).
- Principle of least privilege: strip powerful/unneeded access once it's no longer
  needed — Chuck demonstrates by deleting the privileged group, which also removes his
  own elevated rights.

## Notable verbatim quotes

> "putting on the infinity gauntlet and giving yourself super godlike permissions which
> is also known as sudo or the sudoer's file"

> "we're going to temporarily borrow some power from the root which he's also known as
> the super user"

> "this is kind of like saying please in linux please do this i'm getting super powers
> to do this"

> "in linux we store our passwords in the shadows where they're hidden you can't see
> them"

> "when we create a user in linux we both create a user and a group for that user"

> "that command is lazy because he doesn't do anything but just say okay yeah here's a
> user account i'm not gonna do anything else"

> "in linux that's definitely the pseudo command ... it stands for super user do
> essentially every time we use that command it's like we're slipping on the infinity
> gauntlet"

> "you never want to become the infinity gauntlet never log in as root that's why we
> have sudo"

> "you're not in the sudoers file this incident will be reported"

> "this is the only best practice recommended way to edit the sudoers file"

> "if you mess up your suitors file you can break the entire system there is some checks
> in there that'll keep you safe"

> "the a stands for append so this command here we're appending the groups that ironman
> is part of"

> "using the principle of least privilege we're going to remove the the infinity
> gauntlet group"

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: Linux for Hackers EP4 — sudo & user management -->
