---
type: youtube-video
source_date: 2025-11-17
url: https://www.youtube.com/watch?v=KxfAW8wPDX4
channel: "@networkchuck_v2"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity]
tags: [dark-web, threat-intel, osint, cybercrime, interview]
---

# Dark Web Expert Explains How He Infiltrates Cybercrime Forums

## Summary

An interview on the secondary NetworkChuck channel (@networkchuck_v2) with a cyber
crime threat-intelligence analyst about how he monitors and infiltrates dark-web
cybercrime forums, and about an open-source "dark web OSINT with AI" tool he built.
Chuck (with a second off-camera host, "Alex") plays the curious interviewer, drawing
out the guest's methods rather than teaching himself.

The bulk of the technical content is the GUEST's expertise (context only). The guest
walks through: why scraping `.onion` (Tor) sites is slow rather than truly hard;
how researchers locate hidden sites via ~13–15 dark-web search engines, onion "wiki"
directories, and forums that also advertise onion domains; the difference between
passive OSINT and going "active" (HUMINT) with sock-puppet accounts, burner numbers,
and maintained fake personas; operational-security (OPSEC) discipline; and how threat
actors get caught through OPSEC slip-ups (reused old emails, logging into real Gmail
over Tor, location leaks in Instagram stories). He demos his tool — a Python/LangChain
pipeline that fans a refined query across 15 search engines, semantically filters
~100–480 results down to ~20, scrapes them through Tor, and has an LLM produce an
investigative summary with artifacts (crypto addresses, group names, monikers) and
next-step queries. He stresses a human-in-the-loop check against LLM hallucination.

Chuck's framing contribution: his own dark-web curiosity, his stated preference for the
CLI over the UI, his use of Obsidian and markdown, his shout-out to Daniel Miessler's
Fabric, and his defense of using a VPN together with Tor (referencing pushback he got
for recommending it previously).

## Key claims (dated)

All claims dated 2025-11-17 (source publication).

**Guest (context — threat-intel expertise, not persona training):**
- Scraping the dark web is slow, not impossible; the hard part is routing through the
  Tor network (min. 3 relays), unstable circuits, and sites that are only up a few days
  a week — but experienced scrapers do it routinely. (paraphrase)
- Hidden onion sites are found via dark-web search engines (~13–15), onion "wiki"
  directory pages segmented by category (marketplaces, forums, research), and forums
  that also market their onion domain alongside their clear-web domain (example given:
  a Russian cybercrime forum). (paraphrase)
- The "easy" onion drug/market sites surfaced by a plain Google search are largely fake
  or heavily monitored/controlled by law enforcement; real access comes from months of
  monitoring forums and finding private Telegram channels/groups. (paraphrase)
- Going "active" (HUMINT) requires sock-puppet accounts not tied to you, burner phone
  numbers, never using a recovery email tied to your real identity, and maintaining a
  consistent written persona (age, background, speech patterns) with careful
  note-taking so personas don't blur. A small slip "burns" the persona. (paraphrase)
- OPSEC is critical because high-level threat actors retaliate (e.g., swatting) once
  they identify a real researcher; the guest deliberately stays at "level 2" and has
  not engaged high-level actors. (paraphrase)
- Top skill for this work is critical thinking; the technical parts (scraping, sock
  puppets) can be learned. (paraphrase)
- Whether to use a VPN with Tor is "yes and no" / depends: for scraping, VPN→Tor hides
  Tor use from an ISP that might otherwise block or flag it; there is ongoing debate
  over VPN→Tor vs Tor→VPN ordering. (paraphrase)
- Tool stack: Python `requests` + BeautifulSoup; Tor as a SOCKS proxy on default port
  9050 ("torify"); Docker; a Streamlit-style UI on localhost:8501; LangChain (chosen
  over LangGraph for better docs); supports GPT-4.1/4o, Claude, Gemini, Llama, and local
  models. Three LLM prompts: refine-query, filter-results (output as indices/numbers to
  avoid hallucination), and generate investigative summary. Prompt style borrowed from
  Daniel Miessler's Fabric. (paraphrase)
- Cryptocurrency attribution: firms like Chainalysis (and his employer's own historical
  database) tie crypto addresses to threat actors via link analysis; attribution
  remains difficult. (paraphrase)
- Ransomware is now the dominant threat; "affiliates" run a revenue-share (e.g., 70/30)
  model with ransomware operators; "stealers" (bundled with pirated software ~70% of the
  time) are a common initial-access vector, exfiltrating credentials/cookies/tokens.
  (paraphrase)
- A larger/agentic version of the tool would not "defeat" the dark web — the juiciest
  intel lives in paid/private forums and Telegram groups that resist scraping (scraping
  is detectable and gets accounts banned), so automated and manual work stay
  hand-in-hand. (paraphrase)
- Tool is free/open-source on GitHub; he plans to present it at DEF CON and invites
  pull requests. (paraphrase)

**Chuck (persona-relevant framing/positions):**
- Chuck has been to the dark web himself and frames it as fascinating but easy to "get
  yourself in trouble." (paraphrase)
- Chuck defends recommending a VPN alongside Tor, noting he got "so much crap" for
  saying so previously, and asks the expert to adjudicate. (paraphrase)
- Chuck prefers the command line over the GUI ("I so prefer command line… I like this")
  and uses Obsidian and markdown for notes/reports. (paraphrase)
- Chuck repeatedly stresses keeping a human in the loop against LLM hallucination.
  (paraphrase)
- Chuck flags the safety/legal risk to viewers who might imitate the "active" work, and
  commits to adding disclaimers. (paraphrase)

## Notable verbatim quotes

- Chuck: "That's an insane job." (line 36)
- Chuck: "Why has it been almost impossible to scrape the dark web up until now?" (framing question, ~lines 46–49)
- Chuck: "The dark web, it's like inherently built to not be indexed. How are you locating all the things you're trying to scrape?" (paraphrased framing, ~lines 112–116)
- Chuck: "Even then I think with agentic you still want to have yourself like the human in the loop mentality because you never know if it's going to give you just a complete hallucination answer." (lines 874–878)
- Chuck: "Oh so you do say use VPN with tour. … I said yeah do that. I think it's the safe thing people are like oh no that's stupid. Don't do that. They gave me so much crap for saying that." (lines 1062–1069)
- Chuck: "I so prefer command line like I'm like oh yeah this is I like this." (lines 1705–1707)
- Chuck: "You use Obsidian Man after my own heart." (line 709)
- Guest (context): "my name is Apur Singh Goautam. I'm from India. I came here I think in 2019 … currently I'm working as a senior threat research analyst … it's cyber crime threat intelligence." (lines 5–11)
- Guest (context): "a little miss just cost you your persona like your persona is burnt." (lines 1180–1182)

## Guest attribution

- **Guest:** Apurv Singh Gautam (transcript auto-caption spells it "Apur Singh Goautam" /
  "Apur Singam"; Twitter/X handle given as "ASG Scorpion"). Self-described senior threat
  research analyst at a cyber-crime threat-intelligence vendor rendered by the captions
  as "Cyberel" — likely **Cyble** (spelling uncertain; `attribution: uncertain`). Came
  to the US in 2019 for a master's; started dark-web/scraping work in 2018.
- **NOT Bitdefender-related.** Despite the Nov 2025 window containing other Bitdefender
  interviews, this guest is with a different (threat-intel) vendor.
- **Persona boundary:** ALL threat-intel methods, tool internals, OPSEC tradecraft, and
  ransomware/stealer explanations above are the GUEST's expertise and are recorded as
  **context only** — they do NOT train the NetworkChuck persona. Only Chuck's own
  questions, framing, stated preferences (CLI, Obsidian, Fabric), and his VPN-with-Tor
  position train the persona.
- Second off-camera host addressed as "Alex" asks two closing questions (danger of the
  tool; whether scaling it defeats the dark web) — production/team context, not persona.

<!-- ★ L3-candidate: Chuck's on-record defense of "use a VPN with Tor" (and the prior backlash he references) is a datable persona belief worth promoting to beliefs.md; also reinforces his CLI-over-GUI and Obsidian/Fabric preferences. -->
