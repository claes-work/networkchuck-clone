---
type: youtube-video
source_date: 2022-07-25
url: https://www.youtube.com/watch?v=mYCyZgAv_zE
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity]
tags: [subdomain-enumeration, recon, bug-bounty, hakluke, osint]
---

# find HIDDEN urls!! (subdomain enumeration hacking) // ft. HakLuke

## Summary

A recon/reconnaissance tutorial in which Chuck teaches subdomain enumeration —
discovering the "hidden" URLs and subdomains behind a domain — for both defensive
("what have I exposed?") and offensive (bug-bounty/pentest) purposes. He frames the
technique with a HackerOne bug-bounty context (companies pay hackers to find
vulnerabilities within a defined scope) and stresses repeatedly that these tools
require **permission** and that scope defines whether *active* enumeration is even
allowed.

The video demos two tools, both installed via Docker on Linux:
1. **Hakrawler** — a web crawler/spider built by guest **HakLuke (Luke Stephens)**,
   who is interviewed. It actively crawls a site, following links recursively to a
   specified depth, pulling subdomains (`-subs`), JavaScript files, and external links
   (Twitter/YouTube/Instagram). It queries the Wayback Machine, parses `robots.txt`
   and `sitemap.xml`, and spiders the live application. Written in **Go (Golang)** for
   speed/concurrency. This is **active** enumeration.
2. **gau / GAU ("Get All URLs")** — a **passive** enumeration tool that does *not*
   touch the target server; instead it queries existing databases (AlienVault OTX,
   the Wayback Machine, Common Crawl hosted free on AWS) for known URLs.

The video's real theme, per Chuck, is the second half: the value of **building your
own tools**. He uses the HakLuke interview to champion the "if the tool doesn't exist,
make it yourself — and ship it even if it sucks" hacker mindset. Includes a
private-internet-access (PIA) VPN sponsor read. Notes a longer full interview is
linked, and a Nahamsec bug-bounty course at NetworkChuck Academy.

## Key claims (dated 2022-07-25; labeled by speaker)

- **(Chuck)** Every website has hidden URLs/subdomains beyond its main domain;
  discovering them is called subdomain enumeration, part of the wider practice of
  **recon** — mapping all possible targets you could find vulnerabilities on.
- **(Chuck)** A subdomain (e.g. `learn.networkchuck.com`) can point to an entirely
  different system/server than the apex domain — which is exactly why enumerating them
  matters.
- **(Chuck)** This is valuable defensively too: you may have stood up a forgotten,
  unused subdomain, which is dangerous; better to find it yourself first.
- **(Chuck)** Bug bounty: companies partner with platforms like **HackerOne**;
  programs (Snapchat, Spotify, Reddit, etc.) publish a **scope** defining what you may
  and may not hack. Find a real vuln → write a report → get paid.
- **(Chuck)** You must have **permission**; not all scopes permit active enumeration —
  be careful and cautious.
- **(HakLuke)** Hakrawler is a web crawler: you feed it one or many sites; it navigates
  to them, finds all links, and recursively follows them as many levels deep as you
  specify. Goal: coverage/discovery of a web app with the least manual work.
- **(Chuck)** Hakrawler is **active** enumeration — it actually reaches out and spiders
  the target's domains, so it's powerful and must be used carefully.
- **(Chuck)** Install path (both tools): use Linux (Ubuntu/Kali), install Docker
  (`sudo apt update`, `sudo apt install docker.io -y`), then build/run from the tool's
  GitHub. Docker is his preferred, least-frustrating install method.
- **(Chuck)** Hakrawler usage: `echo https://www.networkchuck.com | sudo docker run --rm -i hakluke/hakrawler`; add `-subs` to pull subdomains, `-d` to set crawl depth.
- **(Chuck)** Hakrawler surfaces **JavaScript files** — "super juicy" for hacking/bug
  bounty — plus store pages and outbound social links.
- **(Chuck)** How Hakrawler works under the hood: queries the **Wayback Machine**
  (web archive / time machine), parses **robots.txt** and **sitemap.xml**, and spiders
  the app.
- **(HakLuke)** He writes tools in Go/Golang mainly for **native concurrency**, and
  because compiled languages run a bit faster — important since he runs tools across
  many targets. He knew Python first and can write it well, but now writes everything
  in Go because he likes it being compiled. (Caveat: a poorly-written Go tool can be
  slower than Python.)
- **(Chuck)** HakLuke chose Go partly to teach himself Go.
- **(HakLuke)** He writes tools to "scratch his own niche" — automating repetitive/
  boring tasks — usually spending no more than a day or two. It doesn't matter if a
  tool already exists; if he'd known it existed he'd have used it, but building it is a
  convenience/laziness thing.
- **(HakLuke)** Many people are afraid to release code (or blogs/videos) fearing it'll
  be "picked to pieces" — his advice is just start; nobody cares if it sucks; the
  majority will appreciate work shared openly.
- **(Chuck)** gau ("Get All URLs") by a hacker he names as "CDL" is **passive**
  enumeration — it queries databases (AlienVault OTX, Wayback Machine, Common Crawl on
  AWS) rather than hitting the target server; no spidering.
- **(Chuck)** gau usage: `sudo docker run --rm -i sxsecurity/gau networkchuck.com`;
  it returns almost too much information — parsing/using it is left for another video
  (points to a Nahamsec bug-bounty course).
- **(Chuck)** Both tools are invaluable for bug-bounty hunters (save time, automate)
  and for defenders auditing their own exposed URLs; you can start contributing by
  **forking** a repo and adding features — just share the change back.
- **(Chuck, sponsor)** Use a VPN (PIA) while scanning — sites see your IP; PIA hides
  your IP, encrypts data, has a no-log policy, covers up to 10 devices, 30-day
  guarantee, ~$2.59/mo.

## Notable verbatim quotes (labeled by speaker)

- **HakLuke:** "Hack crawler is a web crawler. So basically you feed it a website or
  many websites and it will navigate to those websites. And then it will find all of
  the links in that page... to as many levels down as you specify."
- **HakLuke:** "I usually don't spend more than a couple of days making a tool... it's
  usually just to scratch my own niche as they say."
- **HakLuke:** "Ultimately go Lang has native concurrency and that's the main reason I
  use it... I just really like go Lang as a language. But yeah, the main thing is
  concurrency."
- **HakLuke:** "It's basically being lazy, you know. It's just automating things that
  I do repetitively or that are not particularly fun to do... if I can automate that, I
  will."
- **HakLuke:** "A lot of people that I speak to about this stuff... are afraid to
  release their code because they think it's gonna get picked to pieces... And I always
  say like, just do it, just start. Nobody cares. Nobody cares if it sucks."
- **Chuck:** "This whole process of subdomain enumeration, this isn't just for hackers.
  It's for you. If you wanna keep your stuff safe or if you're just curious."
- **Chuck:** "You need permission. And that's the key here... not all scopes include
  active enumeration. Keep that in mind, be careful, be cautious."
- **Chuck:** "It doesn't matter if someone's already made this tool, make your own, add
  a little bit of change to it, do something cool that you're trying to learn, or just
  add a feature to something."
- **Chuck:** "Have you hacked the YouTube algorithm today?... You gotta hack YouTube
  today. Ethically of course."

## Guest attribution

- **HakLuke / Luke Stephens** is a **guest** in this video (interviewed segments), and
  the creator of **Hakrawler**. This is his **2nd appearance** on the channel — a
  **RECURRING guest** and a candidate for a dedicated `wiki/entities/` context page
  (entity: Luke Stephens / HakLuke). His statements above (tool design philosophy, Go
  vs Python, "just ship it" mindset) are **context only** and do **NOT** train the
  persona.
- Only **Chuck's** demo/teaching/framing (permission ethics, defensive framing, the
  Docker install walkthrough, tool usage, active-vs-passive explanation, sponsor read,
  "build your own tools" encouragement, outro) trains the persona.
- Attribution confidence: **high** for the interview blocks (transcript explicitly
  cues "Luke, go ahead and tell us..." and Chuck narrating around them). One name is
  **uncertain**: the gau creator is transcribed as "CDL" (likely an ASR mishearing of
  the author's handle); the gau tool is real (getallurls). Flag: `attribution: uncertain`
  for the gau author's name.

<!-- ★ L3-candidate: HakLuke recurs (2nd appearance) — promote entity Luke Stephens at next synthesis -->
