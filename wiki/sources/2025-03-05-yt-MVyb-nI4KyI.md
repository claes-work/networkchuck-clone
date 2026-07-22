---
type: youtube-video
source_date: 2025-03-05
url: https://www.youtube.com/watch?v=MVyb-nI4KyI
channel: "@networkchuck_v2"
ingested: 2026-07-22
tier: L2
domains: [linux-terminal, cloud-devops]
tags: [python, pyenv, version-management, dev, tooling]
---

# How I handle multiple Python Versions (pyenv)

## Summary

Chuck walks through installing and using **pyenv**, his favorite tool for managing
multiple Python versions on one machine. He motivates the problem (some projects only
support older Python versions; new syntax/features break code written for an earlier
release), then demonstrates the full workflow on a fresh Linux (Ubuntu-style) install:
installing pyenv via curl, wiring the pyenv command into the shell load path through the
`.bashrc`/profile, installing the recommended Python build dependencies via `apt`, then
installing and switching between Python versions globally, per-shell, and per-directory.

He explains pyenv's **shim** mechanism: pyenv inserts small shim scripts at the very
front of the `PATH` so that commands like `python3` are intercepted and routed to pyenv,
which then applies whichever version setting (global/local/shell) is in effect. Notes
that pyenv officially supports Linux and macOS (via Homebrew) but not Windows natively —
on Windows you use it through WSL. Closes by mentioning pyenv can also manage virtual
environments (which he doesn't normally use), and teases that a "new thing" may change
his mind on virtual environments and eventually replace pyenv for him.

## Key claims (dated — the workflow)

All dated 2025-03-05 (source publication date):

- **Why multiple versions:** the latest Python isn't always right — some projects only
  support earlier versions, and Python updates add features and change syntax, so a tool
  written for e.g. Python 3.10 can break under 3.12. The old workaround (uninstall 3.12,
  reinstall 3.10) is painful; pyenv solves it.
- **Platform support:** pyenv provides install instructions for Linux and macOS but not
  Windows — it explicitly does not support Windows, though it works on Windows via **WSL**
  (essentially Linux). On macOS, install with **Homebrew (brew)**.
- **Install (Linux):** install pyenv with the official **curl** command from the pyenv
  GitHub repo.
- **Shell setup:** the pyenv command must be added to the shell load path. Copy pyenv's
  provided shell-config commands into `~/.bashrc`, and also into your profile /
  `.bash_profile` (check which you have with `ls -a`). Instructions also exist for zsh and
  fish. After this, `pyenv` becomes usable.
- **Build dependencies:** pyenv recommends installing the **Python build dependencies**
  before installing versions. On Ubuntu/Debian/Mint, install the prerequisites via `apt`
  (copy the listed package command); this lets pyenv build almost any Python version.
- **List available versions:** `pyenv install -l` lists all installable versions; the
  main CPython versions appear at the top (ranging from 2.x up to 3.14 at time of
  recording).
- **Install a version:** `pyenv install 3.10` installs the latest 3.10.x (here 3.10.16)
  — omitting the patch number gets the latest patch of that minor line.
- **Shims (how it works):** `echo $PATH` shows `pyenv/shims` at the very front of PATH.
  A shim is a small script; because it sits first in PATH, `python3` resolves to the shim
  instead of the system Python. The shim passes the command to pyenv, which applies the
  configured version. Before installing a version, the shims directory is empty; after,
  it contains shims like `python3`, `python3.10`, etc.
- **Global switch:** `pyenv global 3.10` sets the global Python version; `python3 --version`
  then reports 3.10 (vs. the system default 3.12).
- **Per-directory (local) switch:** create/enter a project directory and run
  `pyenv local 3.12` to pin that directory to a version (installing it first with
  `pyenv install 3.12` if needed). Inside the directory `python3 --version` reports the
  local version; leaving the directory reverts to the global version.
- **Per-shell:** pyenv can also set a version just for the current shell session.
- **Virtual environments:** pyenv can also set up virtual environments; Chuck says he
  doesn't normally use them, but hints a "new thing" may change his mind and eventually
  make him stop using pyenv.

## Notable verbatim quotes

> managing multiple python versions on your system can be a massive pain that's why in
> many of my tutorials you'll see me using a tool called pyenv this sucker is amazing you
> can install multiple python versions switch between them with ease it's my favorite

> some projects only support earlier versions of python and as you might imagine as they
> update python they're adding new things they might be changing some syntax in the way
> they want you to write these programs

> I found this tool like last year and before then I don't know what I was doing I think I
> was just dying

> what I love about it is you can switch globally saying you know what right now we're all
> using python 3.10 or you can do it per project and the way it does this is actually very
> clever it does it with what's called a shim

> they put these little code snippets these shims at the very beginning of your path
> that's where it's going to look first

> this coffee break in the entire video is sponsored by Network Chuck coffee yes I do have
> my own coffee brand really it's just for me because I want to make sure I'm drinking the
> best coffee possible

> that's just magic pyenv itself is magic I love it if you've never used it before try it
> out

> I actually may stop using pyenv eventually because of this new thing you'll see but for
> now I'm still using this I love it

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: canonical practical dev-tooling workflow (pyenv) Chuck reuses across many tutorials; strong voice + concrete command sequence worth promoting to a topics page. -->
