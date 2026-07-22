---
type: youtube-video
source_date: 2021-06-04
url: https://www.youtube.com/watch?v=vX3krP6JmOY
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [linux-terminal]
tags: [linux-for-hackers, apt, dpkg, git, pip, package-management, ep-5]
---

# apt, dpkg, git, Python PiP (Linux Package Management) // Linux for Hackers // EP 5

## Summary

Episode 5 of Chuck's free "Linux for Hackers (and everyone)" course, covering Linux
package management — how you install, update, and remove software on Linux. Chuck teaches
hands-on inside a Hack The Box Academy "Pwn Box" running Parrot OS (a Debian-based system),
urging viewers to type every command with him because the best way to learn Linux is
hands-on.

He frames the material around two main package managers. He starts deliberately with the
"hard way," `dpkg` (d package), a low-level manager, to make viewers appreciate `apt`. He
demonstrates `dpkg`'s two flaws: you must manually download the `.deb` file first, and it
does not resolve dependencies (the Discord install fails on missing `libappindicator1` and
`libc++1`). He then shows `apt` (advanced package tool), a high-level manager that pulls
from repositories by package name and installs dependencies automatically — including
`apt --fix-broken install` to repair the broken Discord install, and installing Pidgin.

He walks through the repository concept (`apt update` refreshes the package list from
someone else's server), inspecting the sources list on Parrot (`sudo apt edit-sources`,
the Parrot `.list` file), and browsing a repo in the web browser to find nmap. He covers
listing/searching (`apt list`, `apt list --installed | grep`, `apt show`, `apt search`),
removing (`apt remove` keeps config/user data vs. `apt purge` removes everything),
upgrading (`apt update && apt upgrade`, and `apt full-upgrade`), and mentions `aptitude`
(a high-level, GUI-in-the-terminal alternative). He then covers `snap`/`snapd` as a
store-based package manager (installs VS Code with `sudo snap install --classic code`),
language-specific managers (`pip`/`pip3` for Python, `gem`/RubyGems for Ruby), and finally
`git`: cloning a GitHub hacking tool (Turbo Lister) with `git clone`, installing its Python
dependencies with `pip3 install -r requirements`, and running it against Hack The Box's
subdomains. Sponsored by Hack The Box Academy.

## Key claims (paraphrase; dated 2021-06-04)

- On Linux, apps/programs are installed as **packages**; a **package manager** installs
  them. There isn't just one — two main ones are `dpkg` and `apt`.
- **`dpkg`** (d package) is a **low-level** package manager. Chuck calls it "dumb." Two
  major flaws: (1) you must manually find and download the `.deb` package file first;
  (2) it does not install dependencies automatically.
- `.deb` is the file extension for packages on **Debian-based** Linux (the course uses
  **Parrot OS**, Debian-based). It's analogous to `.exe` on Windows / `.dmg` on Mac.
  On non-Debian systems (CentOS, openSUSE, Red Hat) packages are `.rpm` (not covered here).
- Install a `.deb` with `dpkg`: `sudo dpkg -i <package.deb>` (needs sudo privileges,
  covered in EP4). Installing Discord this way fails with dependency problems
  (`libappindicator1` and `libc++1` not installed).
- **`apt`** (advanced package tool) is a **high-level** package manager; it references a
  package by **name** (no `.deb` download needed) and installs dependencies automatically.
- Always run `sudo apt update` before installing — it refreshes the local list of available
  packages from the repository. Then `sudo apt install <package>` (e.g. `pidgin`).
- `sudo apt --fix-broken install` repairs a broken install with missing dependencies
  (used to fix the earlier Discord failure).
- A **repository** is a storage location / server holding a collection of software. `apt`
  pulls packages from repositories. Repos are owned by others and updated regularly.
- `sudo apt edit-sources` opens the sources list (choose a text editor, e.g. nano). On
  Parrot the actual repo list lives in a separate `.list` file it points to.
- Inspection commands: `sudo apt list` (all available packages), `apt list --installed`
  (installed packages), pipe to `grep` to search (`apt list --installed | grep nmap`),
  `sudo apt show <pkg>` (details about a package), `apt search <pkg>` (search descriptions).
- Removal: `sudo apt remove <pkg>` removes the app but **keeps** user data/config (safe);
  `sudo apt purge <pkg>` removes everything including config. (Pidgin's leftover `pidgin-data`
  was purged separately.)
- Upgrading: `sudo apt upgrade` updates installed packages; commonly chained as
  `sudo apt update && sudo apt upgrade`. `sudo apt full-upgrade` also removes previously
  installed packages no longer required for the upgrade (e.g. old versions).
- `dpkg` can also list installed packages: `dpkg -l` (grep-able like apt).
- **`aptitude`** is another high-level package manager — "apt on steroids," offers an
  interactive GUI-style terminal interface (`sudo aptitude`).
- **`snap`** (installed via `sudo apt install snapd`) is a store-based package manager;
  the command is `snap`. It works like `apt` on the command line but pulls from a **snap
  store** rather than a repository — developers can upload apps to the store for immediate
  availability. Install VS Code: `sudo snap install --classic code` (VS Code needs
  `--classic`), then run with `code`.
- **Language-specific package managers**: Python uses **`pip`** (`pip3` for Python 3);
  Ruby uses **RubyGems**, invoked with `gem` (e.g. `gem install rails`).
- **`git`** is a command-line tool installed via a package manager (`sudo apt install git`).
  It pulls code from places like **GitHub** (itself a repository).
- Workflow to install a GitHub tool: `git clone <repo-url>` (copies the repo into the
  current working directory), `cd` into it, `pip3 install -r requirements` to install the
  Python dependencies listed in `requirements.txt`, then run the script
  (`python3 turbolister.py`, `-h` for help; `-d <domain>` to list subdomains).
- Demo tool: **Turbo Lister** (github.com/leak-captain/turbolister) — passively lists a
  website's subdomains; run against `hackthebox.eu`.

## Notable verbatim quotes

> everyone needs to learn linux

> in linux the stuff we want to install... is contained in something called packages. we install packages. packages are the thing. packages packages packages. sorry i've already had too much coffee today. no such thing as too much.

> apt is awesome. it's super easy to do you can install things in a flash no worries but i'm not going to show you that one just yet. you got to earn that. you got to pay your dues. i'm going to show you the harder way first so you can appreciate what this is and what it does for us.

> it's referred to as a low level package manager because it's kind of — and this is my opinion — kind of dumb.

> so d package the dummy is like hey yeah sure i'll install discord for you but it needs two other things and um i'm it's just not gonna work sorry you need to go get those two other things yourself. okay lazy.

> it stands for advanced package tool and when comparing that to d package... duh it's advanced. d package is stupid.

> a repository is basically a storage location or essentially just someone's server that has a collection of all the software that we might want to use.

> remove is kind of a safe command because it will remove the application but not your user data.

> this sounds so intense we're gonna purge pigeon. this will remove everything.

> a better way is to be able to add your app to a store... and then it becomes immediately available just like in a snap right. is that why it's called that? i don't know.

> get clone we're gonna clone that repository we're basically taking their code and copying it to our linux machine here which is super cool.

> d package low level stupid. apt high level awesome.

> have you hacked the youtube algorithm today... let's hack youtube today ethically of course.

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: Linux for Hackers EP5 — package management -->
