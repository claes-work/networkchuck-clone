---
type: youtube-video
source_date: 2020-06-28
url: https://www.youtube.com/watch?v=hrVa_dhD-iA
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity]
tags: [google-dorking, osint, ethical-hacking, recon, search-operators]
---

# Google HACKING (use google search to HACK!)

## Summary

Chuck demonstrates "Google hacking" (a.k.a. "Google Dorking") — using advanced
Google search operators to perform **passive reconnaissance** on a target. He opens
with a shock hook (open webcams and exposed database passwords found via search),
then frames the technique as the first step any ethical hacker takes: gathering
public intel ("recon," "footprinting," "fingerprinting") before an attack. He walks
through the core search operators (`site:`, `inurl:`, `intext:`, `intitle:`,
`filetype:`, `allinurl:`, and the `-` negation), demonstrating each against
`starbucks.com`. He introduces the **Google Hacking Database (GHDB)** — a public
catalog of pre-built "dorks" that surface webcams, passwords (env files), failed-login
logs, registry files, and Nessus vulnerability-scan reports. He closes by extending
recon to LinkedIn/job-board profiling (fingerprinting an employee's skill set to
infer a company's tech stack) and mentions two follow-on tools, **theHarvester** and
**Netcraft**, for pulling emails and subdomains.

The persona-relevant thread is the repeated **ethics framing**: everything shown is
passive recon of publicly-available data, which is legal "up to a point"; the line is
crossed when you *use* that information against a target without permission, or switch
to *active* recon (directly contacting the company, social engineering). Sponsored by
IT Pro TV (his stated primary hacking-learning source at the time); part of his
"becoming a hacker" series.

## Key claims (dated 2020-06-28)

Technique / operators (all paraphrase):
- "Google hacking" / "Google Dorking" is a real technique that real hackers use; it
  is a form of reconnaissance — gathering as much information about a target as
  possible before hacking. Also called recon/reconnaissance, footprinting, or
  fingerprinting.
- `site:starbucks.com` — restricts results to one domain (no space after the colon).
- `inurl:admin` — finds pages with a keyword (e.g. `admin`) in the URL; useful for
  finding pages/areas not meant to be publicly reachable, hinting at vulnerabilities.
- `intext:admin` — searches for the keyword inside the body of the page.
- `intitle:login` — searches the page title; good for finding login pages, which
  typically carry "login" in the title.
- `filetype:pdf` (also `filetype:log`, `filetype:reg`, env files) — finds publicly
  available files of a type across a domain and its subdomains; can surface NDAs,
  court cases, database credentials, failed-login logs, Windows registry files.
- The `-` (minus/negative) sign before an operator excludes matches (e.g.
  `-inurl:admin.html` drops results containing that string).
- `allinurl:` behaves like `inurl:` but treats everything after it as required —
  "kind of like doing quotes on a search."
- The **Google Hacking Database (GHDB)** is a public, categorized catalog of ready-made
  search strings ("dorks") that can expose vulnerabilities, passwords, usernames, and
  emails. Example finds shown: open webcams (`intitle:"webcam 7"` type strings),
  env-file database passwords, failed-login log files, exposed registry files, and
  Nessus vulnerability-scan reports (which reveal a target's known weaknesses in a
  convenient format).
- Recon extends beyond Google: `site:linkedin.com intitle:starbucks "network engineer"`
  surfaces employees; reading their listed skills (BGP, OSPF, Ansible, Azure, AWS,
  Cisco, Arista) lets you infer the company's tech stack and likely vulnerabilities.
  Twitter/photo OSINT can leak badges or on-screen info in backgrounds.
- **theHarvester** (learned via IT Pro TV) pulls emails, subdomains, and IPs for a
  domain from sources like Google; **Netcraft** returns even more subdomains/hosts.

Ethics framing (all paraphrase):
- In most cases this is legal because it is **passive recon** — only accessing
  information that is already publicly available (often exposed by accident, e.g. an
  open webcam or leaked passwords).
- It is legal to *find* exposed information; it becomes **illegal to use it** —
  turning that info against the target, using it to extract more, or feeding it into
  another attack — unless you have explicit permission. "It's not illegal to find it,
  but it's illegal to use it."
- Switching to **active recon/footprinting** (directly reaching out to the company —
  social engineering, walking into a store, connecting on LinkedIn to solicit info)
  is illegal without explicit permission from the company.
- The context throughout is the **ethical hacker / pentester**: a hacker who does
  things "for good, not for bad." If a dork exposes a target's vulnerabilities, the
  ethical move is to report it to them, not exploit it.
- Practical rule of thumb: "keep it passive, people, unless you have permission."
- Observation on why these hacks work: "the majority of these hacks can happen because
  of the mistakes of just people doing people things" — information exposed
  accidentally.

## Notable verbatim quotes

> "you can do some crazy hacking stuff just by searching on Google"

> "webcams are perfectly safe right wrong"

> "in this video we're talking about Google hacking or Google Dorking what some people
> call it this is a legit thing that hackers actually use"

> "of course I'm talking in the context of being an ethical hacker a hacker who does
> things for good not for bad"

> "the more you know about your target the better you can hack"

> "a big reason why what we're doing is not illegal is because we're doing passive
> recon which in most cases means that we're just trying to get information that's been
> made public that's publicly available"

> "what we're hoping as hackers is that this information was made public by accident"

> "now again don't go take these and then try to use them that's that's the line you
> don't want to cross it's not illegal to find it but it's illegal to use it"

> "so keep it passive people unless you have permission"

> "the more you know the more you can hack"

> "the majority of these hacks can happen because of the mistakes of just people people
> doing people things no one's perfect and you can expose that"

> "you're an ethical hacker you might want to let them know report this to them but you
> can see how this is crazy bad for them but very viable for us"

> "keep studying keep learning and keep hacking"

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: Google-dorking OSINT technique + ethics framing -->
