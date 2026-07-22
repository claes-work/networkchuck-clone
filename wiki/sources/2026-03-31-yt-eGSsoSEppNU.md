---
type: youtube-video
source_date: 2026-03-31
url: https://www.youtube.com/watch?v=eGSsoSEppNU
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity]
tags: [security-news, breach, 2026, defense, analysis]
---

# the WORST hack of 2026

## Summary

A breaking-news / analysis video (2026-03-31, filmed within hours of discovery) in
which Chuck walks through what he calls potentially "the most sophisticated and
dangerous supply chain attack in history": the hijack of **Axios**, the most popular
JavaScript HTTP library (100M+ downloads/week, depended on by ~174,000 projects). An
attacker stole a lead maintainer's long-lived NPM classic access token, never touched
Axios's actual source code, and instead added a single dependency line to
`package.json` that pulled a malicious `plain_crypto.js` package. Its post-install
script silently deploys a remote access Trojan (RAT) ~1.1 seconds after `npm install`,
then erases all trace of itself. Chuck explains the anatomy of the attack (token theft,
staged clean file, CI/CD bypass via NPM CLI, dropper + obfuscation + C2 callout,
self-cleanup), gives viewers terminal commands to check whether they're affected, and
frames the broader lesson about the fragility of the open-source dependency chain. He
closes with his signature end-of-video prayer and a guest cameo from his daughter
Maddie ("Pikachu") re-explaining supply chain attacks via the coffee analogy.

## Key claims (dated — the incident + lessons)

- (2026-03-31) Axios, the most popular HTTP library with over 100 million downloads a
  week and ~174,000 dependent projects, was hijacked. [paraphrase]
- (2026-03-31) The attack vector was a stolen **long-lived NPM classic access token**
  belonging to a lead maintainer (screen name "Jason Saiman"); the attacker then changed
  the account email to `i.have.stop@proton.me`. [paraphrase]
- (2026-03-31) The attacker never injected malicious code into Axios's source — they
  added **one line to `package.json`** pulling a dependency, `plain_crypto.js`, that
  looks like a harmless crypto helper and was never imported by any of Axios's 86 source
  files; it exists only to run its post-install script. [paraphrase]
- (2026-03-31) The attacker staged a **clean version of the file ~18 hours before** the
  malicious one, and bypassed normal CI/CD guardrails by publishing via the **NPM CLI**
  directly. [paraphrase]
- (2026-03-31) Two release branches were poisoned within 39 minutes of each other:
  **1.14.1** (1.x) and **0.30.4** (0.x). Any project using a caret (`^`) range on those
  releases would pull the compromised version on the next `npm install` — often
  automatic in CI/CD. [paraphrase]
- (2026-03-31) On `npm install`, the post-install script runs automatically and triggers
  a **dropper** that writes `setup.js`, which uses two layers of obfuscation (XOR +
  base64, plus a "7077" marker) to hide from static scanners. [paraphrase]
- (2026-03-31) `setup.js` detects the OS (Mac/Windows/Linux), contacts the attacker's
  **C2 (command-and-control) server**, and downloads the OS-specific RAT — all ~1.1
  seconds after install. [paraphrase]
- (2026-03-31) After execution, the malware **self-cleans**: it deletes `setup.js` and
  the malicious `package.json`, then renames a pre-staged `package.md` back to
  `package.json`, leaving a clean version and no trace. [paraphrase]
- (2026-03-31) **socket.dev** was the first company to detect the attack; **John Hammond**
  live-streamed a walkthrough of the code. [paraphrase]
- Lesson — trust chain: an average npm project trusts 200 to 2,100 strangers with code
  execution; you trust the app you install, but that app trusts its dependencies (e.g.
  you trust openclaw, openclaw trusts Axios). This is where supply chain risk lives.
  [paraphrase]
- Lesson — detection: check with `npm list -g axios`; the bad versions are **1.14.1** and
  **0.30.4**; run a deeper filesystem search, check for the RAT, and check whether the
  machine reached out to the (now-down) C2 IP. [paraphrase]
- Lesson — remediation if compromised: don't just delete files; treat the machine as
  **fully compromised**, rotate every API key, credential, and token. [paraphrase]
- Lesson — trend: this kind of attack is happening more and more often, and AI is
  helping attackers move faster, not just defenders. Stay alert and secure. [paraphrase]

## Notable verbatim quotes

> This just became the most dangerous command that anyone can run. npm install anything.

> A hacker took over the lead maintainer's account, injected malicious code without
> actually injecting malicious code, and it deploys a remote access Trojan in under 1.1
> seconds. And the malware erases itself. No trace left behind.

> This just might be the most sophisticated and dangerous supply chain attack in history.

> the average npm project trusts 200 to 2,100 strangers with code execution.

> At this point, the attacker has access to your system. They can access your stuff in
> 1.1 seconds, and you didn't even know. And you weren't doing anything weird or wrong.
> You were just installing or using software from people that you trust. It's not your
> fault. It's a supply chain attack.

> If someone wanted to poison me, they could just put poison in this cup of coffee, but
> that'd be hard cuz I'm always watching my coffee. But, they could instead go to the
> coffee roaster and poison the beans I buy.

> But if you found anything, stop right now. Don't just delete files. Treat your machine
> as a compromised machine. Rotate your API keys. Every credential, every token.

> AI is amazing and it's been helping us build stuff, but it's also helping the hackers
> do things. This is happening way more often than it should. So, pay attention. Be
> secure.

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

(Note: near the end, Chuck's daughter Maddie Keith / "Pikachu" appears in a brief cameo
re-explaining supply chain attacks via the coffee analogy; her lines are not
subject-attributable and are not persona training data.)

<!-- ★ L3-candidate: most-recent corpus item; canonical worked example of Chuck's supply-chain-attack teaching (Axios/npm token theft → post-install RAT → self-cleanup), coffee-poisoning analogy, and his practical detect/remediate checklist — strong voice + beliefs material for cybersecurity persona. -->
