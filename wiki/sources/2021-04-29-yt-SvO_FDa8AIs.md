---
type: youtube-video
source_date: 2021-04-29
url: https://www.youtube.com/watch?v=SvO_FDa8AIs
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, linux-terminal]
tags: [twitter, osint, recon, privacy, ethical-hacking]
---

# Twitter OSINT (Ethical Hacking)

## Summary

A hands-on tutorial in which Chuck demonstrates **Twint** (Twitter Intelligence), a
Python-based OSINT tool that scrapes Twitter to gather information about accounts,
keywords, and locations. He frames the video up front as reconnaissance/information
gathering — explicitly NOT breaking into accounts — and opens with an ethics/consent
disclaimer. He installs the tool via `git clone` and `pip3 install -r requirements.txt`,
recommending the free Google Cloud Console (Cloud Shell) as a zero-setup Linux
environment that runs entirely in the browser.

He walks through Twint's CLI capabilities: pulling a user's tweets (`-u`), limiting
results (`--limit`), keyword search (`-s`), filtering by minimum likes (`--min-likes`),
date filtering (`--since`), image-only tweets (`--images`), outputting to JSON
(`-o ... --json`), and location-based search via `--near` (city) or `-g` (geo
coordinates + radius). He then shows the "real power" — importing Twint as a Python
module to build interactive scripts (a "hot topic" search prompt, and a "my people"
script that pulls everyone who tweeted at him and fetches their recent tweets), tying
it back to how reconnaissance feeds an actual OSINT investigation. Sponsored by
Skillshare; David Bombal appears as an example search target.

## Key claims (dated — technique + ethics)

- **[2021-04-29]** The tool demonstrated is **Twint** ("Twitter Intelligence") — a
  Python tool that gathers information from Twitter by scraping. (paraphrase)
- **[2021-04-29]** Technique: Twint requires **no API, no Twitter login, and has no rate
  limit**; it simply scrapes Twitter, which Chuck calls crazy powerful. (paraphrase)
- **[2021-04-29]** Setup is fast (~5 minutes): `git clone --depth=1 <url>`, `cd twint`,
  then `pip3 install -r requirements.txt`. On a non-Cloud-Shell box you also need
  `git`, `python3`, and `python3-pip` installed. (paraphrase)
- **[2021-04-29]** Chuck's preferred free environment is **Google Cloud Console's Cloud
  Shell**, launched from the browser — praised because it needs nothing but a web
  browser and is completely free. (paraphrase)
- **[2021-04-29]** CLI usage: `-u` targets a username, `-h` shows help/switches,
  `--limit` caps results, `-s "<keyword>"` searches a user's tweets by term. (paraphrase)
- **[2021-04-29]** Filtering: `--min-likes 100` returns only tweets with at least that
  many likes; `--since <date>` limits by date; `--images` returns only tweets with
  images. (paraphrase)
- **[2021-04-29]** Output: `-o <file>.json --json` writes results to a JSON file for
  later analysis (while still printing to the terminal). (paraphrase)
- **[2021-04-29]** Location recon: `--near <city>` finds people tweeting near a place;
  `-g <lat>,<lon>,<radius>km` searches by precise geo coordinates within a radius.
  (paraphrase)
- **[2021-04-29]** Python module usage is the more powerful path: `import twint`, build
  a `twint.Config()` object, set attributes (`c.Search`, `c.Near`, `c.Limit`,
  `c.Popular_tweets = True`), then run `twint.run.Search(c)`. Chuck stresses that
  attribute casing/case matters. (paraphrase)
- **[2021-04-29]** Ethics: the tool and the way it searches Twitter are **not illegal,
  but intent matters** — do not hack anyone without their permission, do not use it with
  ill intent, and use it for educational purposes only. (paraphrase)
- **[2021-04-29]** Framing: looking at old tweets and pictures may seem silly, but
  **gathering information is a vital part of hacking** — this is reconnaissance for a
  real OSINT investigation. (paraphrase)

## Notable verbatim quotes

> "if you think we're going to be hacking into twitter or hacking into someone's account
> we're not doing that... but we will be using this amazing python hacking tool to gather
> information from twitter"

> "while the tool we're using is not illegal and the way it searches twitter is not
> illegal your intent does matter please do not hack anyone without their permission or
> use this tool with any kind of ill intent so be careful use it for educational purposes
> only"

> "the hacking tool we're using is called twint which stands for twitter intelligence"

> "no api required it's not using the twitter apis no twitter login required it's simply
> scraping twitter and it's crazy powerful"

> "what we're doing here might seem silly i'm just looking at pictures and old tweets but
> that's that's hacking gathering information is a vital part of hacking"

> "have you hacked the youtube algorithm today... let's hack youtube today ethically of
> course"

> "you need some hacking fuel two cups minimum networkchuck.coffee if you don't already
> have some"

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT). (David Bombal is named
only as an example search target, not as a speaker.)
