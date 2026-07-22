---
type: youtube-video
source_date: 2025-02-28
url: https://www.youtube.com/watch?v=CxTMHw-M0Yg
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity]
tags: [security-awareness, 2025-threats, mfa, password-manager, phishing, defense]
---

# You're going to get Hacked in 2025

## Summary

A PSA-style security-awareness video (sponsored by Bitdefender) in which Chuck Keith
walks through the "top five" cybersecurity threats of the 2025 threat landscape and the
concrete defenses an individual, family, or company can adopt. His organizing thesis is
that everyone — even the tech-savvy — should become a **"zero trust human"**: trust
nothing by default, always verify through an independent channel. He opens by demoing
deepfakes (turning his daughter into a "trailer-park dude," a fake Taylor Swift singing),
then covers baseline IT-security hygiene before the ranked threat list.

Baseline hygiene (things you should *already* be doing): use a password manager with a
unique password per account; enable multi-factor authentication everywhere; follow the
3-2-1 backup strategy; update software immediately; run antivirus and leave it on; and
stay informed. The ranked threats, worst last, are: (1) **AI-powered hacking** —
LLM-perfected phishing, obfuscation, dating-app/chatbot scams; (2) **AI-powered malware**
— uncensored dark-web LLMs (WormGPT, FraudGPT), polymorphic malware, LLM-based code
obfuscation to evade detection; (3) **supply-chain attacks** — you get hacked through a
vendor (Starbucks via Blue Yonder); (4) **IoT** — botnets, default credentials, unpatched
smart devices; (5) **deepfakes** — stolen face/voice, live video impersonation, voice
scams targeting loved ones. He closes with a bonus sixth threat, **quantum computing**
("harvest now, decrypt later"), and a "defense in depth" / "Swiss cheese" layering
metaphor. The persona payload is the repeated "zero trust human" framing, the
verify-then-verify-again discipline, and using **AI to fight AI**.

## Key claims (dated — 2025 threat landscape)

All claims are paraphrase unless quoted in the next section. Version-dated to the video's
publication (2025-02-28) as its snapshot of the threat landscape.

**Baseline IT-security hygiene (his non-negotiable starting point):**
- Use a password manager (he doesn't care which — "just use one") and a secure, unique
  password for every login; never reuse passwords.
- Enable multi-factor authentication (MFA) wherever possible — password plus a second
  factor (SMS, authenticator app / OTP). "Two forms always."
- Back up data with the **3-2-1 strategy**: three copies, on two different media types,
  one completely offline (an offline copy can't be reached by ransomware).
- Update your OS and applications the moment patches arrive — updates patch the bugs
  that get you hacked.
- Run antivirus and leave it on; the habit of turning it off "to test things" and
  forgetting is a common opening. (He recommends Bitdefender as sponsor.)
- Stay informed / "update your brain."
- Cites a Bitdefender consumer report (~7,000 respondents): 37% write passwords down;
  18% reuse the same password across three or more accounts; one in four consumers has
  been hit by a security incident.

**Threat 1 — AI-powered hacking / social engineering:**
- Bitdefender's 2024 assessment (1,200 surveyed, mostly IT/security people): 96% are
  concerned about AI's impact on the threat landscape.
- LLMs remove the old tell of phishing (grammar/spelling errors); AI-written phishing
  emails are now "perfect." Phishing remains the most common form of cybercrime.
- Stats cited: 3.4 billion phishing emails sent per day; email impersonation ≈ 1.2% of
  global email traffic; Darktrace reported a 135% increase in malicious email campaigns
  in Q1 2023.
- "Four pillars of AI phishing" (attrib. Mailgun): collect data on your interests/
  behaviors, use tools like WormGPT, personalize/target each attempt, and impersonate
  friends/family by copying their writing style.
- He demoed Grok 3 writing a phishing email in his own voice.
- Obfuscation: attackers use NLP-evasion techniques to slip malicious links past email
  filters; 78% of discovered malicious emails use two or more obfuscation techniques.
- Dating-app/chatbot scams: a cited 2,087% increase in scammers using chatbots; fake
  AI-generated personas with realistic invented (non-real-person) photos.
- **Defense:** be a zero trust human. Open emails but don't click links — "never click a
  link in an email," always go to the source (e.g., type chase.com yourself). Only
  interact with emails you initiated/expect. For anything unusual (info requests,
  payments), verify via a separate channel (call/text) that you initiate. Paste
  suspicious messages into a trusted LLM to assess them (AI vs. AI); Bitdefender's
  **Scamio** is a purpose-built LLM for this. The FBI is also warning people.

**Threat 2 — AI-powered malware:**
- Writing malware normally requires an expert security coder; AI lowers the barrier.
- Regular LLMs (ChatGPT, Grok) refuse to write malware, but dark-web **WormGPT** and
  **FraudGPT** are uncensored, purpose-built-for-crime LLMs sold on the dark web — now
  "a script kiddie" can produce malware.
- **Polymorphic malware** that adapts: HYAS Labs' 2023 proof-of-concept "BlackMamba"
  used an LLM to modify its code at runtime and evade antivirus.
- Palo Alto Unit 42 used LLM-based rewriting on JavaScript malware to reduce VirusTotal
  detections — enough transformation layers can fool classifiers into seeing malicious
  code as benign. Future direction: malware that adapts to its environment without human
  input (still emerging, limited evidence).
- **Defense:** patch software (most malware exploits unpatched bugs); reduce attack
  surface — don't install untrusted apps (jab at his editor Isaac installing unknown
  voice software); use advanced AV that uses ML/AI to catch emerging threats; stay
  informed (follow accounts like BleepingComputer, or ask an LLM). This is
  **defense in depth** — multiple layers.

**Threat 3 (ransomware sub-thread) — encryption-less ransomware:**
- Classic ransomware encrypts your files and demands payment for the key.
- Cited: 5,400 ransomware victim organizations in 2024; average ransom demand $2.73M,
  often paid.
- **Encryption-less ransomware** doesn't lock data — it exfiltrates ("borrows") it and
  threatens public release (devastating for e.g. a healthcare provider). Backups don't
  help here. For attackers it's "safer" because vendors like Bitdefender release free
  decryptors against popular ransomware.
- **Double extortion** = encrypt + threaten to leak; **triple extortion** = adds a third
  action (e.g., DDoS the company, or harass its customers/employees).
- **Defense:** still back up; use anti-ransomware AV features (Bitdefender ransomware
  protection); at his studio, a 45Drives centralized server runs an anti-malware service
  that continuously analyzes for ransomware and acts to stop spread.

**Threat 4 — supply-chain attacks:**
- You can be hacked through a vendor even if your own security is excellent.
- **Starbucks (Dec 2024):** its payroll/scheduling vendor **Blue Yonder** was hit by
  ransomware (group "Termite"), disrupting operations at 11,000 US stores — employees
  tracked schedules/payroll by hand. Starbucks itself wasn't breached.
- Other forms: a breached medical provider leaking your data; a trusted software update
  carrying malware (cites the 3CX incident). 2024 dubbed "the year of supply-chain
  attacks."
- Future targets: major AI providers (OpenAI, local AI), Apple Intelligence, satellites/
  internet infrastructure, and clouds (AWS, Azure, Google Cloud).
- **Defense:** as an individual you have little control. Test updates before deploying
  (business); as a user, read release notes / run them past AI. Patching is still safer
  than not patching. Above all, **diversify and decentralize** — don't rely on one cloud
  provider or one hard drive; spread your data out.

**Threat 5 — deepfakes (rated scariest):**
- 36% of security pros call it a very significant threat.
- Attackers can steal your face and voice and make "you" say/do anything — and do the
  same to family, coworkers, or a CEO. Needs as little as **one photo and three seconds
  of audio**; apps like FaceApp do it in moments; it can be done live on a phone/FaceTime
  call.
- Real cases cited: Elon Musk crypto-scam deepfakes (David Bombal's hacked channel; one
  victim lost $690,000, another sent $10,000); ByteDance "OmniHuman" Taylor Swift singing
  in Japanese; David Beckham multi-language; Jennifer Aniston "free MacBooks" scam;
  Arup's Hong Kong employee wired **$25 million** after a deepfake video call; deepfake
  Biden robocalls; deepfake audio of a Maryland school principal sparking death threats.
- Stats: 1 in 10 people have received an AI-cloned voice message and 77% of them lost
  money; a 1,740% surge in deepfake incidents in North America between 2022 and 2023.
- **Defense:** detection tools exist (Sensity, Intel FakeCatcher, Reality Defender,
  Microsoft Video Authenticator, Resemble AI) but it's AI vs. AI and detection may fall
  behind. Be a zero trust human: if "grandma" calls, hang up and call her back on her own
  number; verify via an alternate source. FBI recommends a family **safe word** (a
  non-obvious phrase). Limit your digital footprint — "they can't copy what they don't
  have access to." (Jokes that his beard protects him since AI tools handle hair/beards
  poorly.)

**Bonus Threat 6 — quantum computing:**
- Quantum computers could break today's strong encryption. "Harvest now, decrypt later":
  a hacker on public Wi-Fi (e.g., Starbucks) can capture your encrypted TLS traffic now
  and decrypt it later once quantum computing is powerful enough.
- **Defense:** always use MFA (a cracked password still isn't enough); change passwords
  regularly (captured-then-changed credentials become worthless); prefer providers
  offering quantum-resistant / post-quantum cryptography. He expects everyone to be on
  post-quantum cryptography in the future.

**Closing framework:** cybersecurity is **defense in depth** / the **"Swiss cheese"**
model — each layer has holes, but stacking layers covers them. A cup of coffee and a keen
eye isn't enough; you want real defenses (e.g., Bitdefender) as backup for your bad days.

## Notable verbatim quotes

> It's almost impossible to not get hacked in 2025 — from DeepFakes to AI-powered malware
> and phishing. Even the most tech-savvy, careful, vigilant of us are vulnerable. So let's
> do something about it.

> I want us to become zero trust humans when it comes to technology.

> For basic IT security hygiene, passwords: use a password manager. I don't care which one
> you use, just use one.

> Please, please use multifactor authentication whenever you can.

> The same technology you're using to make sure your emails don't sound stupid, the
> hackers are doing the same thing just to try and trick you.

> When you get an email you can open it, but that's all you can do. If you see a link,
> don't click that link. Never click a link in an email. I don't care if it's from your
> bank or your grandson, your sister or your mom — always go to the source.

> You've heard the old adage, trust but verify. No — don't trust, verify, and then verify
> again.

> AI versus AI. That's how we're going to beat them.

> The barrier to entry is super low, and LLMs are getting smarter and smarter.

> Diversifying, decentralizing your stuff. Don't use just one cloud provider. Don't put
> all your data on one hard drive. Spread your stuff out so you're not dependent on one
> thing.

> It could be as simple as having one picture of someone and just three seconds of audio
> of their voice, and you can become them.

> They can't copy what they don't have access to.

> While you may think a cup of coffee and a keen eye is all you need to keep yourself safe
> — no. You want to have defenses in place.

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: dense, canonical statement of the "zero trust human" personal-security philosophy plus concrete defensive playbook (password manager, MFA, 3-2-1 backup, never-click-links, verify-via-alternate-channel, AI-vs-AI, defense in depth) — strong material for a cybersecurity topic hub and persona beliefs/voice. -->
