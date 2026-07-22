---
type: youtube-video
source_date: 2021-03-13
url: https://www.youtube.com/watch?v=6CnDdXVTxhU
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, linux-terminal]
tags: [phoneinfoga, osint, recon, ethical-hacking]
---

# find info on phone numbers with PhoneInfoga

## Summary

Chuck demonstrates **PhoneInfoga**, an OSINT (open-source intelligence)
reconnaissance tool for gathering information about a phone number — validating it,
locating its origin, identifying carrier/line type, and generating searches to find
where the number appears online. He frames it as part of the OSINT process a hacker
uses during a penetration test, and opens with an explicit ethics disclaimer: this is a
hacking tool, the data is publicly available, but intent matters — don't use it to hack
anyone without explicit permission.

Rather than install locally, he runs it for free in **Google Cloud Shell** (a free
Linux server in the browser), which already ships with Docker. He pulls the PhoneInfoga
Docker image and runs a CLI scan (`scan -n`) against a US number, then launches the
tool's **web UI** by mapping port 8080 and using the `serve` command plus Cloud Shell's
web preview. The scan runs a numverify check (validating the number, giving a rough
location and line type — landline vs. toll-free) and then generates **Google dork**
requests (advanced Google searches) across general footprints, documents, social media
(Facebook, Twitter, LinkedIn, Instagram), reputation sites, and telecom sources. He
tracks a US number back to IT Pro TV and looks up a nagging toll-free number that
others flag as a PayPal/loan scam. Sponsored by IT Pro TV.

## Key claims (dated — tool/technique + ethics)

- **[2021-03-13]** PhoneInfoga is a reconnaissance / OSINT tool for finding information
  about phone numbers — who a number belongs to, where it exists online — not a tool
  that "hacks" the number itself. (paraphrase)
- **[2021-03-13]** Ethics: this is a hacking tool shown as part of the OSINT process;
  the information accessed is publicly available on the internet, but intent matters —
  never use it to hack anyone without explicit permission. Practice and have fun, but
  don't weaponize the results. (paraphrase)
- **[2021-03-13]** PhoneInfoga runs on pretty much any Linux distro; alternatively you
  can run it free and instantly in Google Cloud Shell, which provides a free Linux
  server in the browser with Docker preinstalled. (paraphrase)
- **[2021-03-13]** Two install paths per the PhoneInfoga docs: install it as an
  application, or the easier route — run it via Docker. Chuck pulls the image and runs
  it with `docker run -it sundowndev/phoneinfoga`. (paraphrase)
- **[2021-03-13]** CLI usage: `scan -n <number>` scans a number; start with the country
  code (e.g. `1` for a US number). (paraphrase)
- **[2021-03-13]** The scan first runs a numverify check that validates the number is
  real, returns an approximate location, and identifies the line type (landline,
  toll-free, etc.); it may not always find carrier info. (paraphrase)
- **[2021-03-13]** Beyond validation, PhoneInfoga generates Google dork requests —
  advanced Google searches — across categories: general footprints, documents, social
  networks (Facebook, Twitter, LinkedIn, Instagram), individual footprints, reputation
  footprints, temporary-number footprints, and OVH Telecom (more common in Europe).
  (paraphrase)
- **[2021-03-13]** The web UI is launched by publishing port 8080 and running the
  `serve` command: `docker run -it -p 8080:8080 sundowndev/phoneinfoga serve -p 8080`;
  in Google Cloud Shell you view it via the web preview icon on port 8080. The UI is
  easier to parse than raw CLI output. (paraphrase)
- **[2021-03-13]** Practical uses shown: identifying an unknown caller, and checking a
  bothersome toll-free number — where linked search results flagged it as a scam
  (loan / PayPal scam call). (paraphrase)
- **[2021-03-13]** A noted flaw: the Facebook Google-dork it generates omits the
  parenthesized area-code format, so a number stored as `(352) 600-...` on Facebook is
  missed until you manually add the parentheses to the search. (paraphrase)
- **[2021-03-13]** Running lots of unusual searches can trigger Google's "I'm not a
  robot" CAPTCHA, which thinks you're up to no good. (paraphrase)
- **[2021-03-13]** Learning to search — to find things out about people, places, and
  phone numbers — is a vital step in becoming a hacker; PhoneInfoga is a tool worth
  having in your tool chest. (paraphrase)

## Notable verbatim quotes

> "In this video, we are not going to be hacking any phone numbers. But we are going to
> be using hacking tools to find out more information about these phone numbers."

> "Do not hack anyone unless you have explicit permission. And while the information
> we're accessing is publicly available on the internet, your intent does matter. So
> yes, practice, yes, have fun, but don't use this information to hack anyone."

> "Google Cloud Console. Basically, a free Linux server we get right now in just a few
> seconds."

> "These are actually Google dork requests, which might sound ridiculous, but Google
> dorking is a real thing. It's basically advanced Google searching."

> "Google doesn't like you doing all this kind of weird stuff. The searches, they think
> you're up to no good, but you're not. You're doing it ethically, right? Of course."

> "A vital step in learning how to become a hacker is just learning how to search for
> things, how to find things out about people, places, things, nouns, phone numbers."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
