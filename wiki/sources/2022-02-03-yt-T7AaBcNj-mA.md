---
type: youtube-video
source_date: 2022-02-03
url: https://www.youtube.com/watch?v=T7AaBcNj-mA
channel: "@networkchuck_v2"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, certifications-career]
tags: [hacking, beginners, john-hammond, interview, ctf]
---

# how to NOT be a hacking noob in 2022 // ft. John Hammond

Long-form interview / livestream ("Noobs Podcast" episode 001) in which Chuck Keith
and his brother Cameron interview cybersecurity educator **John Hammond** about how to
level up from beginner to competent hacker in 2022. Hammond is a **guest**; his advice
and expertise are **context** (see [[wiki/entities/john-hammond]]). Only Chuck's own
questions, framing, and statements train the persona.

## Summary

Chuck and his brother Cameron self-identify as hacking "noobs" who want to get serious
in 2022, and bring on John Hammond — a cybersecurity researcher at Huntress (Chuck
initially misremembers it as "Hacker One") with a "baker's dozen" (13+) certifications
— to map the beginner-to-competent path. The conversation covers: prerequisites for
getting into hacking (Linux + Python as the two core competencies), which Linux distro
to learn on, capture-the-flag (CTF) competitions and war-game platforms (TryHackMe,
Hack The Box, OverTheWire) as the primary skill-builder, the value and limits of
certifications, how Hammond built his own career, imposter syndrome/burnout, and a
technical deep-dive demo of the PwnKit Linux privilege-escalation vulnerability
(CVE-2021-4034).

Chuck's recurring framing throughout: he comes from a networking/IT background
(help desk → sysadmin → network engineer) and repeatedly maps Hammond's hacking advice
onto that world; he champions "just start / just document what you're learning" and
loves that hacking is gamified. The episode is positioned as content for career-changers
who "hate their job" and see cybersecurity as a way out. Chuck plugs his own
"Linux for Hackers" course and a virtual-machine video as companion resources.

## Key claims (dated 2022-02-03)

**Prerequisites & foundations**
- (Hammond-guest) The two absolute-necessity core competencies to start hacking are
  **Linux and Python**. — paraphrase
- (Hammond-guest) You do NOT need to be a full software engineer/architect to hack;
  you need basic scripting — variables, functions, loops, conditionals — enough to
  write a loop that brute-forces passwords or triggers a blind SQL injection.
  His answer to "do I need to learn to code to hack?" is "no, with an asterisk." — paraphrase
- (Hammond-guest) Codecademy-level Python (up through classes) is roughly enough; you
  don't need to go much further. — paraphrase
- (Hammond-guest) Best distro to learn on is debated; he personally uses **Ubuntu**
  rather than Kali/Parrot, because manually installing/configuring tools (via apt, git)
  and watching them break teaches you how Linux actually works — an essential part of
  learning that beginners should not skip. Kali is convenient once you know which tools
  you need. — paraphrase
- (Hammond-guest) You don't need to suffer through textbooks up front; if you're
  genuinely fascinated, foundational knowledge (parts of a computer, networking, IP,
  subnets) will come as you go. — paraphrase
- (Chuck) A networking background helps a lot in hacking — many network attacks
  (e.g., TCP man-in-the-middle) map directly onto what he already knows from building
  and securing networks; the new mindset is shifting from "build/secure/fix" to "how do
  we break it." — paraphrase
- (Chuck) Hacking is "almost the entire industry is gamified," which he loves. — paraphrase

**CTFs & practice platforms**
- (Hammond-guest) Capture the Flag (CTF) is a competition/sport where you solve
  cybersecurity problems and capture "flags" (tokens proving you completed a task);
  it's the single best skill-builder. Getting into CTFs is what launched his career;
  he passed the OSCP largely because he had played so many CTFs. — paraphrase
- (Hammond-guest) War-game / always-on cyber-range platforms to practice on:
  **CTFtime.org, OverTheWire, SmashTheStack, Ring Zero, TryHackMe, Hack The Box**. — paraphrase
- (Hammond-guest) There is no shame in looking at solutions/walkthroughs while learning
  (training wheels analogy) — e.g., IppSec's walkthrough videos or existing blog
  write-ups — as long as you don't bog down so much you quit. — paraphrase
- (Hammond-guest) First concrete steps for a beginner tonight: spin up a VM, install
  Ubuntu, make a TryHackMe or Hack The Box account, connect the VPN, start a room/box,
  keep Google open, and read Eric S. Raymond's essay **"How To Become A Hacker"** for
  the right mindset. — paraphrase

**Certifications**
- (Hammond-guest) Certifications get your foot in the door for a first role and pass HR
  filters, but requirements vary by employer — regulated/government roles require them
  (he needed Security+ within a 6-month grace period for one job), while his current
  startup-style employer (Huntress) doesn't care about certs, only merit. — paraphrase
- (Hammond-guest) His candid take on specific certs: doesn't hold much water for CEH or
  Security+ (though Security+ is a good IT box-to-check and HR-bypass); OSCP has started
  to "flip-flop"; eJPT is great but has fallen off; SANS GCIH is good but ungodly
  expensive; the cyber-mentor PNPT is up-and-coming. Bottom line: there is no single
  best certification — the honest answer is to experiment, expose yourself to many
  things, and absorb education like a sponge. — paraphrase
- (Hammond-guest) For pure resume/HR marketability the safe picks are Security+, OSCP,
  Pentest+, and CEH. — paraphrase
- (Hammond-guest) PNPT (his most recent cert, achieved end of 2021) focuses on Active
  Directory, password reuse/bad passwords, and Windows misconfigurations bundled with
  "human stupidity" as a real vulnerability; he thinks it has a CTF-like element. — paraphrase
- (Chuck, own plan) Chuck proposes a personal cert path for himself and Cameron:
  **eJPT first → Pentest+ → then OSCP**; Hammond validates this ordering (eJPT first,
  then OSCP) as the right way to do it. — paraphrase

**Career & getting hired**
- (Hammond-guest) Your first role could be a teacher/instructor or even a senior
  pentester if you prove effort, merit, and competency — he was hired as an instructor
  straight out of school because he had a public body of work (blog write-ups, YouTube).
  — paraphrase
- (Hammond-guest) There are no "experts" in cybersecurity — nobody is the best; it's too
  vast. Entry-level roles (e.g., analyst level 1 at Huntress) are about problem-solving
  and critical thinking, not Hollywood zero-day hacking. — paraphrase
- (Hammond-guest) On when you're "ready" to apply: same as any field — start now,
  "shotgun applications out," let the market tell you your value; keep looking/growing
  even after you land a job. CTF/war-game work goes on your blog, GitHub, portfolio,
  and YouTube — those breadcrumbs accumulate into invaluable proof for employers. — paraphrase
- (Chuck) The best way to learn anything is to teach it — reading gives passive
  understanding, but explaining a hard concept simply to someone else forces you to know
  it inside and out. — paraphrase
- (Chuck) Career advice for beginners: just start documenting what you're learning —
  make a blog post today; you don't have to be a genius or an expert, and it doesn't
  matter if 20,000 others post the same thing, because you can put it on your resume. — paraphrase
- (Chuck, self-reported) He went full-time on YouTube around 400,000 subscribers and at
  the time of this interview was closing in on 2 million. — paraphrase

**Mindset, imposter syndrome, work ethic**
- (Hammond-guest) Cure for imposter syndrome: stop looking at everyone else, get back to
  work on your own projects, and contribute — if one person is helped by what you put
  out, you're part of the community, not an imposter. — paraphrase
- (Hammond-guest) His honest productivity "secret" for juggling a day job, YouTube, and
  CTFs is to **postpone sleep** — not skip it, just do it later (2–4 a.m.); he
  acknowledges he can do this because he's young, unmarried, no kids, no house. — paraphrase
- (Chuck) Says he's "too old" (32) for the stay-up-till-3am grind he used to do; frames
  hustle as stage-of-life dependent — not everyone has to be John Hammond; find your own
  level of hustle and do something every day. — paraphrase
- (Hammond-guest, parting advice) If it's not fun, you don't like it — you can always
  gamify hacking one way or another to keep it fun. — paraphrase

**Technical deep-dive — PwnKit (CVE-2021-4034)**
- (Hammond-guest) PwnKit is a privilege-escalation vulnerability in the `pkexec` /
  polkit set-UID binary present on nearly every major Linux distribution — a low-priv
  user can become root. Disclosed by Qualys. The trick exploits how programs read
  command-line arguments: setting the first argument to null terminates the string, so
  the program reads the next value on the stack — letting an attacker sneak in a
  different program to execute as root. More reproductions reported on Ubuntu/Debian
  than Fedora/Red Hat. It has been patched — safe if you update. He demoed both a C
  proof-of-concept and a weaponized bash version served via a Python HTTP server and a
  malicious `curl … | bash` install trick. — paraphrase (context; guest expertise)
- (Chuck) Notes the demo overlaps two of his own videos ("Linux for Hackers" course
  covers `pkexec` argument handling; he made two videos on the curl-pipe-bash and
  Python-server techniques Hammond demonstrated). — paraphrase

## Notable verbatim quotes

- **Chuck:** "the best way to learn anything is teaching it 100 it is because once you
  reading something you can read it and passively understand it but to have to take that
  hard concept and explain it simply to someone else that's a whole different ball game
  you have to know that thing inside and out that's the best way to learn"
- **Chuck:** "just do one thing make a blog post about what you're learning today ...
  sure there might be 20 000 other people doing that same blog post it doesn't matter
  ... put that on your resume and that's what people are going to see"
- **John Hammond (guest):** "when people ask the question do i need to learn programming
  or coding to be a hacker i always say no but with an asterisk"
- **John Hammond (guest):** "i learned more out of the classroom than i did in the
  classroom just me personally"
- **John Hammond (guest):** "there are no experts ... there isn't a best we're all just
  in this on a team ... we're here to make security better"
- **John Hammond (guest):** "the hard answer the real raw truth you postpone sleep it's
  not that you don't sleep it's just you do it later"
- **John Hammond (guest, parting advice):** "if it's not fun it means you don't like it
  ... you can always gamify it"

## Guest attribution

- **John Hammond = GUEST / CONTEXT**, not the subject. He is a cybersecurity researcher/
  educator at Huntress and a fellow YouTuber; see [[wiki/entities/john-hammond]]. All of
  his advice, career history, cert opinions, mindset framing, and the PwnKit
  (CVE-2021-4034) technical deep-dive above are recorded as context and clearly labeled
  "Hammond-guest" — they do **not** train the persona.
- **Only Chuck Keith trains the persona.** Chuck-attributed material captured here: his
  networking/IT background and "build/secure → break" framing, "hacking is gamified,"
  the "best way to learn is to teach it" belief, the "just start documenting / make a
  blog post" beginner advice, his own eJPT → Pentest+ → OSCP cert plan, his
  stage-of-life view on hustle (32, "too old" for the all-nighter grind), and his
  self-reported YouTube milestones (full-time ~400k subs, nearing 2M).
- **Attribution confidence:** high. Speakers are clearly distinguishable in the
  transcript (Chuck host, Cameron co-host/brother, John Hammond guest). Cameron's few
  contributions (e.g., "if it's not fun you don't like it" was Cameron's phrasing that
  Hammond then echoed) are not attributed to Chuck. No ★ notable own-belief flagged —
  Chuck's statements here are solid framing/persona-voice material but not a distinctive
  standalone doctrine beyond what other sources already establish.
