---
type: youtube-video
source_date: 2021-03-28
url: https://www.youtube.com/watch?v=NWyqSbnsvGU
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, linux-terminal]
tags: [instagram, osint, recon, privacy, ethical-hacking]
---

# Instagram OSINT

## Summary

Chuck walks through **Osintgram**, a Python OSINT (open-source intelligence)
command-line tool for gathering publicly available information about an Instagram
account. He frames it up front as reconnaissance, not account compromise: "you're
not hacking into Instagram, you're not stealing passwords" — you're using a hacking
tool to find out information, which "in the hacking world is half the battle." He
opens and closes with an ethics disclaimer, stresses that intent matters even when
the data is public, and demonstrates against a consenting target (fellow creator
David Bombal).

The tutorial covers the full setup on a Debian-based Linux box (he uses Kali Linux,
with Google Cloud Shell offered as a free alternative): `git clone` the tool,
install Python 3 / pip3, `pip3 install -r requirements.txt`, then create a `config`
directory holding three files built with `echo` — `username.conf`, `pw.conf`, and
`settings.json` (seeded with `[]`). He stresses using a **dummy Instagram account**
(never your main) for the credentials the tool logs in with. He then runs
`python3 main.py <target>` and demos the interactive commands: `list` to see options,
`stories`, `propic`, `fwingsemail` (emails of users the target follows), and `addrs`
(registered addresses / geotags from the target's tagged photos). He hits Instagram
rate-limiting ("throttling") mid-demo from repeated runs and switches to Google Cloud
Shell with another account to complete the `addrs` pull. The video ends with an OSINT
challenge to the audience (find where he was on Sept 2, 2018 — hinting it is NOT on
his Instagram) with free coffee as the prize. Sponsored by ITProTV.

## Key claims (dated — technique + ethics)

- (2021-03-28) The video is explicitly **not** about breaking into accounts or
  stealing passwords; it teaches OSINT reconnaissance — using a tool to gather
  publicly available information about an Instagram account. (paraphrase)
- (2021-03-28) Ethics/intent framing: don't hack anyone without permission; even
  though the information is publicly available, your intent still matters, so be
  careful. (paraphrase)
- (2021-03-28) The tool is **Osintgram**, a Python OSINT/hacking tool run from the
  command line. (paraphrase)
- (2021-03-28) Recon is central to hacking — gathering information about a target is
  "half the battle" in the hacking world. (paraphrase)
- (2021-03-28) Hacking machine options: a Debian-based Linux VM (Chuck uses Kali
  Linux, his favorite hacking distro, currently tied with Parrot), or the free
  Google Cloud Shell / Console as an alternative. (paraphrase)
- (2021-03-28) Setup workflow: `git clone` the repo, `cd` into it, ensure Python 3
  (≥3.6) and pip3 are installed (`sudo apt install python3` / `python3-pip`), then
  `pip3 install -r requirements.txt`. (paraphrase)
- (2021-03-28) Config step: create a `config` directory and, with `echo` redirected
  to files, make `username.conf` (dummy IG username), `pw.conf` (dummy IG password),
  and `settings.json` containing `[]`. (paraphrase)
- (2021-03-28) Operational-security note: use a **dummy Instagram account** for the
  tool's login credentials, never your main account. (paraphrase)
- (2021-03-28) Run with `python3 main.py <target-username>`; it logs in and drops
  into an interactive prompt. Useful commands include `list`, `stories`, `propic`,
  `fwingsemail` (emails of users the target follows), and `addrs` (registered
  addresses / geotag locations from the target's tagged photos). (paraphrase)
- (2021-03-28) Downloaded output lands in the tool's `output/` directory; Chuck opens
  files with `xdg-open`. (paraphrase)
- (2021-03-28) Running the tool repeatedly triggers Instagram **rate-limiting /
  throttling** ("please wait a few minutes and try again"); Chuck attributes the
  failures to how many times he ran it while recording. (paraphrase)
- (2021-03-28) Limitation: OSINT results are only as good as what the target exposed
  — e.g. `addrs` only returns locations the target actually tagged. (paraphrase)

## Notable verbatim quotes

> "Instagram hacking. Now if you're here to hack into someone's Instagram account,
> get out of here — we're not doing that. But I am going to show you a hacking tool
> that you can use to find out information about someone's Instagram account."

> "Disclaimer, like always: don't hack anyone without permission. While this
> information is publicly available, it still matters what your intent is, so be
> careful."

> "You're not hacking into Instagram, you're not stealing passwords or anything, but
> you are using a hacking tool to find out information — and in the hacking world,
> that's half the battle."

> "You'll need one important thing: a dummy Instagram account, because in a moment
> we're going to use our username and password to set this up. You don't want to use
> your main Instagram account."

> "You can't hack without coffee."

> "I love this because — command line — you feel like a boss when you're doing it,
> and it's pretty quick when it works."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
