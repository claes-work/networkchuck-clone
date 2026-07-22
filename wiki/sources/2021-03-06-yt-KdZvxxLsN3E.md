---
type: youtube-video
source_date: 2021-03-06
url: https://www.youtube.com/watch?v=KdZvxxLsN3E
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, linux-terminal]
tags: [sherlock, osint, username-search, recon, ethical-hacking]
---

# find social media accounts with Sherlock (in 5 MIN)

## Summary

A ~5-minute tutorial in which Chuck demonstrates **Sherlock**, a Python
command-line tool that hunts a given username across well-known social media
sites. He frames it as part of the reconnaissance / OSINT phase of hacking —
gathering publicly available information about a target. He shows two ways to run
it: install on a Linux distro (Kali, Parrot, Ubuntu), or, requiring no local
setup, open the GitHub repo's **"Open in Google Cloud Shell"** button to get a
free Linux machine in the browser (works even from a phone). After installing the
requirements with pip, he runs Sherlock against several well-known hackers'
usernames (NahamSec, The Cyber Mentor, John Hammond), speeds it up with
`--timeout 1`, and notes results are saved to a `<username>.txt` file. He
repeatedly stresses ethics: only gather info with explicit, contractual
permission if you intend to actually attack a target, and never use it with ill
intent. He also flags that the tool is not perfect (false positives — e.g. it
claimed all three targets had chess.com accounts, which he doubts).

## Key claims (dated — tool/technique + ethics)

Paraphrased unless quoted; all dated 2021-03-06.

- Sherlock is a Python "hacking tool" used to find social media accounts tied to
  a username. [2021-03-06]
- This falls under **OSINT** — gathering publicly available information about
  hacking targets — which is part of the hacking process. [2021-03-06]
- Doing this is **not technically illegal** because you are only collecting
  publicly available information, but the lines blur based on your intentions, so
  be careful. [2021-03-06]
- Requirements: **Python 3 on a Linux distribution** (Kali, Parrot, Ubuntu, etc.)
  — or nothing local at all. [2021-03-06]
- The GitHub repo offers an **"Open in Google Cloud Shell"** button that spins up
  a free Linux machine in the browser (Google account required); you pay nothing.
  You can run the whole thing from a phone with just a web browser. [2021-03-06]
- Install step is one command: `python3 -m pip install -r requirements.txt`.
  [2021-03-06]
- Usage: `python3 sherlock <username>`; `python3 sherlock --help` shows options.
  [2021-03-06]
- Add `--timeout 1` to spend only one second per site and speed up the scan;
  interrupt a slow run with Ctrl-C. [2021-03-06]
- Sherlock writes results to a file (`<username>.txt`) in the working directory,
  visible via `ls`. [2021-03-06]
- The tool is **not perfect** — it produced false positives (claimed chess.com
  accounts for people who likely don't have them). [2021-03-06]
- Ethics: gathering this kind of info can reveal vulnerabilities / footholds, but
  if you are actually hacking a person or company you need **explicit permission
  — hired, under contract** — otherwise you can get into legal trouble.
  [2021-03-06]

## Notable verbatim quotes

> "this is a legit hacking tool part of the hacking process called osens [OSINT]
> where we gather information about our hacking targets"

> "what we're doing is not technically illegal we're just gathering publicly
> available information on the internet but the lines can blur based on your
> intentions so just be careful"

> "it's a tool called sherlock and all you need is python 3 installed on a linux
> distribution can be cali [Kali] can be parrot can be ubuntu whatever or it can
> be nothing"

> "gathering information like this could lead to possible vulnerabilities
> possible footholds"

> "if you're seriously trying to hack someone or a company make sure you have
> explicit permission i'm talking like they hired you there's a contract the
> whole nine yards otherwise you could get into trouble"

> "now i'm saying they all have chess accounts i doubt they actually do let me go
> see yeah that's that's bogus so it's not perfect"

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
