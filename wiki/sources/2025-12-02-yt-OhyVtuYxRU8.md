---
type: youtube-video
source_date: 2025-12-02
url: https://www.youtube.com/watch?v=OhyVtuYxRU8
channel: "@networkchuck_v2"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, ai-tools]
tags: [scambaiting, ai, scams, interview, social-engineering]
---

# Scam Researcher shows how he tricks scammers with AI

## Summary

An interview/demo in which Chuck (NetworkChuck) talks with **Razvan Costache** (transcribed "Razan Costake"), Director of Innovation at **Bitdefender**, about how the company uses AI to detect scams and to bait scammers. The bulk of the technical content is the **guest's context** — Chuck's contribution is framing questions, reactions, and his recurring worry about protecting non-technical family members.

The guest walks through the modern scam landscape (over $1 trillion lost to scams last year, only ~7% reported; 60% of people think they can spot scams even as losses grow), then several Bitdefender techniques: fingerprinting scam ad/SMS templates via indicators of compromise (IOCs), clustering SMS campaigns with machine learning to warn customers proactively by region, and — the centerpiece — an AI **scam honeypot** with "digital victims." These AI agents answer scam calls with unscripted, personality-driven responses and realistic voice models; scammers reportedly stay on the line ~15 minutes without realizing they're talking to an AI. A live demo shows the AI victim stringing along a fake-loan scammer ("John Doe from myperfectcredit.com" offering a preapproved $5,000 loan with an advance-fee catch). The guest also covers deepfake detection with **intent analysis** (demoed on a satirical Elon Musk "edible" video), streamjacking, malvertising (1M+ ads detected by Bitdefender last year), voice cloning, and multi-touch-point attack correlation. Bitdefender uses its own trained models for analysis and public models only for the conversational layer. Closing advice (guest): don't act on first instinct, build family "patterns"/validation habits, share scam examples, and expect scammers to exploit big events (Taylor Swift Singapore concert reversing that country's scam-loss gains).

## Key claims (dated; guest = Razvan Costache/Bitdefender, Chuck = NetworkChuck)

- **[2025-12-02] [guest]** Over $1 trillion was lost to scams last year, and that figure is only ~7% because the rest goes unreported. *(self-reported/cited-by-guest figure, not independently verified here)*
- **[2025-12-02] [guest]** ~60% of people think they can spot scams, yet losses keep growing — confidence rises while education lags and AI-enabled scams improve.
- **[2025-12-02] [guest]** No one is immune to scams; there are just different tiers of scam for everyone.
- **[2025-12-02] [guest]** A common WhatsApp scam (spreading from Europe to the US) aims not at money first but at taking over accounts and propagating to victims' contacts until a critical mass of thousands is reached — "they operate like startups."
- **[2025-12-02] [guest]** Streamjacking scams use dormant hijacked accounts activated around big events (e.g. a SpaceX launch), spawning many identical deepfake "Elon Musk" accounts offering free Bitcoin/crypto.
- **[2025-12-02] [guest]** Malvertising: Bitdefender detected over 1 million scam ads/sponsored posts last year; these are a main vector for fake loan and investment scams targeting vulnerable people.
- **[2025-12-02] [guest]** Bitdefender fingerprints scam templates via IOCs — spoofed lookalike domains, grammar mistakes, reused phone numbers/contact info — so morphed variants are still detected without full re-analysis.
- **[2025-12-02] [guest]** SMS scam campaigns are clustered with machine learning; once labeled a campaign, Bitdefender can warn customers by region proactively (e.g. a "parking ticket" text active in Texas) before a detection even fires on their device.
- **[2025-12-02] [guest]** Bitdefender runs a scam honeypot of AI "digital victims" with identities, phone numbers, email, and WhatsApp; average scam call now lasts ~15 minutes and scammers still don't realize it's an AI. Responses are unscripted and personality-driven, not templated.
- **[2025-12-02] [guest]** Some scammers don't know they work for a scam operation — they believe they have legitimate jobs (common with medication-cream and loan scams).
- **[2025-12-02] [guest]** Analysis is done with Bitdefender-trained models; publicly available models (e.g. GPT-type) are used only for the conversational layer with the caller, never for the scam analysis. Multiple models/agents with different roles, human-in-the-loop for novel cases.
- **[2025-12-02] [guest]** Deepfake detection first analyzes audio (synthetic vs. modified vs. mismatched) and adds **intent analysis** — explaining *why* a video is fake/manipulative — planned to run server-side so users need no special CPU/NPU.
- **[2025-12-02] [guest]** The next frontier is multi-touch-point attack detection: correlating events across WhatsApp → browser → phone to detect a scam "without actually seeing the scam" (e.g. screen-sharing bank scams that moved desktop → mobile → browser).
- **[2025-12-02] [guest]** AI-driven mass scam calling is not yet widespread, but Bitdefender has seen AI for spam calls and voice cloning for scams impersonating family/friends.
- **[2025-12-02] [guest]** If a victim already paid: stop all communication with the scammer, contact authorities (e.g. IC3/FBI in the US), and file a complaint.
- **[2025-12-02] [guest]** Best defenses: don't act on your first instinct under panic pretexts; build family conversation "patterns"/validation habits; critical thinking is the number-one defense alongside cybersecurity tools.
- **[2025-12-02] [guest]** Scams adapt to current/geopolitical/entertainment events; when Taylor Swift announced a Singapore concert (~June), scammers pivoted en masse to ticket scams and reversed Singapore's declining scam-loss trend despite its dedicated anti-scam government unit.
- **[2025-12-02] [guest]** Has been with Bitdefender 14 years; favorite part of the job is seeing a proof of concept go live.
- **[2025-12-02] [Chuck]** Chuck frames his central concern as protecting non-technical family: he and other IT people distrust calls/texts by default, but training family (e.g. his grandmother, who he says "would fall for 99.9% of the scams" mentioned) to have that mindset is very difficult.
- **[2025-12-02] [Chuck]** Chuck receives text-message scams constantly ("oh gosh, oh three more"), underscoring how routine the problem has become.

## Notable verbatim quotes

- **[guest, Razvan Costache]** "My name is Razan Costake. I'm the director of innovation here at B Defender." *(auto-transcription of the name; likely Razvan Costache / Bitdefender)*
- **[guest]** "over $1 trillion last year lost to scams and that's just uh 7%. Because rest of it goes unreported."
- **[guest]** "the more confident they get uh the more money they they they lose because the education and the information on spotting scams is lacking."
- **[guest]** "no one is immune. ... It's just different tiers of scam."
- **[guest]** "they have strategies they operate like uh startups."
- **[guest]** "we have uh digital victims ready to be scammed. ... They have no secrets. So we're using this these honeypots to learn scammer tactics."
- **[guest]** "an average call is now like like 15 minutes. It it they talk with with an AI for 15 minutes and they still don't don't know it's an AI."
- **[guest]** "we usually don't rely on models like GPT for the work. ... the analysis is always done with B defender train models."
- **[guest]** "if it's fake, we're also going to tell you why it's fake." *(on deepfake intent analysis)*
- **[guest]** "the next big thing is actually having all these events and correlating them to detect the scam without actually seeing the scam."
- **[guest]** "don't act on your first instinct when it's something so serious ... critical thinking I think is the number one uh uh thing we can do besides using cyber security on your devices."
- **[guest, demo — AI victim baiting the scammer]** "I think you meant to say savings or maybe checking account, not taking account, right?" — scammer: "It's We're We're not taking anything, sir. We Yeah, we're giving you the money."
- **[Chuck]** "I try to tell my family how to be safe, but how do you prepare for those types of things? ... all their filters and alerts that would normally go up don't flag."
- **[Chuck]** "I get text message scams constantly. Like it's to the point where I'm like oh gosh oh three more. This is ridiculous."
- **[Chuck]** "I think about my grandmother like she would fall for 99.9% of the scams you mentioned today. And I don't know how to train her."
- **[Chuck]** "in this case sharing really is caring but just just don't share the links."
- **[Chuck]** "you became the hacker." *(joking, after the guest warns against forwarding live scam links)*

## Guest attribution

- **Guest = Razvan Costache** (auto-transcribed as "Razan Costake"), **Director of Innovation at Bitdefender**. The spelling in the transcript is unreliable (speech-to-text); treat the corrected name as **attribution: uncertain** pending confirmation from the video description. He also gives his demo email as "miminescu.me," which may hint at a fuller name but is not conclusive.
- **All techniques, statistics, product claims, and demos in this source belong to the guest / Bitdefender and are CONTEXT only. They must NOT flow into the subject persona** (`persona/voice.md`, `persona/beliefs.md`, etc.).
- **Only Chuck's contributions train the persona**: his interviewer framing, his consistent focus on protecting non-technical family (grandmother, parents), his default distrust of unsolicited calls/texts as an IT person, his easy rapport and humor (pineapple-pizza banter, "you became the hacker"), and his role of translating expert research into audience-actionable takeaways.
- Bitdefender warrants an `wiki/entities/` context page (company); Razvan Costache warrants a context person page if the name is confirmed.

<!-- ★ L3-candidate: rich, quotable interview on AI scambaiting + deepfake-intent detection; strong entity material (Bitdefender, Razvan Costache) and a vivid live demo worth promoting into cybersecurity/ai-tools topic pages. -->
