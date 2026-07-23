# Log

_Append-only change record. Entry format: `## [YYYY-MM-DD] <type> | <title>` with_
_`<type>` ∈ `setup | plan | ingest | query | lint | persona-qa`._
_Ingest entries end with a synthesis-notes line (the synthesis-debt trail)._

## [2026-07-22] ingest | ledger: enumerate @NetworkChuck (main channel)
Enumerated the primary TARGET channel @NetworkChuck (`UC9x0AN7BWHpCDHSm9NiJFJQ`) into
`pipeline/ledger.csv` via `fetch_channel.ps1` (/videos + /shorts tabs) →
`merge_staging.py` → `backfill_metadata.py --top 50`.
- 522 new rows: 377 long-form + 145 shorts.
- Metadata backfill filled view counts for 375/377 long-form videos; top-by-views
  promoted 27 videos to P1 (guests excluded).
- Open work now: 373 long-form (P1:177 P2:183 P3:13) + 145 shorts. L2=0 L3=0.
- @networkchuck_v2 (second TARGET channel) still has ZERO rows → next Stage A.
Synthesis notes: none (enumeration only, no source pages written yet).

## [2026-07-22] ingest | ledger: enumerate @networkchuck_v2 (second channel)
Enumerated the second TARGET channel @networkchuck_v2 (`UCOuGATIAbd2DvzJmUgXn2IQ`) via
`fetch_channel.ps1` (/videos + /shorts) → `merge_staging.py` → `backfill_metadata.py
--top 15`.
- 46 new rows: 38 long-form + 8 shorts. Views filled for all 38; 10 promoted to P1.
- Both TARGET channels now enumerated. Open work: 411 long-form
  (@NetworkChuck 373 [P1:177 P2:183 P3:13] + @networkchuck_v2 38 [P1:17 P2:14 P3:7])
  + 153 shorts. L2=0 L3=0.
- No zero-row TARGET channels remain → next iteration starts Stage B ingest (P1 first).
Synthesis notes: none (enumeration only).

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — early era 2015–2017, P1
First ingest batch. 8 P1 long-form videos (2015-12 → 2017-06), all study/career/mindset
era. 8 ok, 0 skipped, 0 no-captions. Source pages written L2; ledger set to L2.
- 2015-12-23 6Kms924WLeg — brain-dump exam ethics ★
- 2017-01-02 dfEWw95coak — 7 study tips (New Year 2017) ★
- 2017-02-24 dmthwYTEL0M — CCNA vs college ★
- 2017-03-14 _h4ioMa7rOs — studying with kids ★
- 2017-04-01 wMyYCJBlZTQ — stop procrastinating (Pomodoro) ★
- 2017-04-24 nsi008avBfo — quit job to travel / RV milestone ★
- 2017-05-29 bQVrGvGqCQ0 — studying at social gatherings
- 2017-06-11 18m2lUoNygo — "am I smart enough?" / you-CAN-do-this ethos ★
Synthesis notes: RICH early-biography debt (7 ★ L3-candidates). Genuinely new for a
future synthesis pass: (a) Chuck's own cert/career path — enrolled at WGU but did NOT
finish the four-year degree; help desk → junior net admin → network engineer via CCNA;
personal CCNP journey (ROUTE/SWITCH/TSHOOT via INE, ~2015–2017). (b) Foundational belief
"certifications + hands-on experience > a college degree." (c) Early milestone: quit job
for a fully-remote Cisco role to RV across the USA with his family (~3k subs then;
letsjustgo.family blog; self-reported CCNP→CCIE aspiration — note NO CCIE source exists,
do not claim one). (d) Signature "you CAN do this / you're smart enough" self-belief
framing stated explicitly. (e) Family markers self-reported only (children's ages given
2017 — keep unnamed). Promote at next synthesis checkpoint into certifications-career +
persona/beliefs + persona/biography + voice.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — mid-2017 P1, 6 ingested / 2 skipped
8 P1 long-form (2017-06 → 2017-11). 6 ok, 2 skipped, 0 no-captions.
- Skipped: epgVJT9Wa-k "WHO WON?" (promo/winner-announcement, no content);
  qCx5q3BnaFc "CBT Nuggets GIVEAWAY" (garbled non-English auto-captions, unusable).
- Ingested L2:
  - 2017-06-29 woJX0eBOdnA — CCNA or Python? ★ ("unicorn" networking+programming)
  - 2017-07-23 pSB6xNpqtGI — 3 ways out of a study slump
  - 2017-08-02 UYlKgcRkiqA — how Cisco creates exams
  - 2017-08-30 EywIAz8fPnY — CompTIA or Cisco? cert sequencing ★
  - 2017-10-22 MdYhc4O3G7w — self-study certs philosophy ★
  - 2017-11-06 9Vs56S95Mrs — 3 Cisco CLI hacks ★ (first hands-on technical tutorial)
Synthesis notes: New for a future pass — (a) "unicorn" career framework: the rare
network engineer who ALSO programs (Python) is uniquely valuable. (b) Canonical
entry-cert sequencing opinion: for anyone aiming above helpdesk, skip CompTIA
A+/Network+ and go vendor-specific (Cisco CCENT/CCNA or Microsoft MCSA); A+ only to land
a first zero-experience IT job. (c) Self-study-first cert philosophy + bio: he
self-studied his own certs; earned Security+ at WGU via CBT Nuggets / Keith Barker;
CCNP in progress ~3 yrs with TSHOOT outstanding (dates his own cert timeline). (d) His
first hands-on Cisco CLI/technical tutorial (2017-11) — marks the shift from
study-advice content toward hands-on tech. Promote at next synthesis checkpoint.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — late-2017 P1, 7 ingested / 1 skipped
8 P1 long-form (2017-11 → 2017-12, the daily-upload late-2017 run). 7 ok, 1 skipped.
- Skipped: qkUTB65OfAc "You CAN Learn Python - 10 WINNERS" (winner-announcement, no content).
- Ingested L2:
  - 2017-11-23 2vJehMLbZGw — Learning Python is HARD
  - 2017-12-15 PxC5UMAiVZQ — Christmas giveaway w/ goal-setting anecdote ★
  - 2017-12-16 MN0KzfzlRio — Packet Tracer vs GNS3 ★
  - 2017-12-17 M3da0R-m_Ww — CCNP after CCNA? ★
  - 2017-12-18 f8e-be_nMa8 — is it worth it to be a net engineer? ★
  - 2017-12-19 TCQdJwLMqfY — learn Linux with the CCNA
  - 2017-12-20 SlHfqJyqsmo — am I too old? ★
Synthesis notes: New — (a) Goal-setting method + Paris-trip bio detail (late 2017; he &
wife set a 5-year goal and achieved it; self-reported). (b) Packet Tracer vs GNS3 lab-tool
selection framework for CCNA study. (c) Bio: he earned CCNA Voice before CCNP R&S;
positions collaboration/voice as a personal specialty. (d) His 2017 view on network-engineer
career longevity vs automation/SDN (DATE-SENSITIVE — likely evolves; flag for contradiction
check against later cloud/automation content). (e) "Next-gen network engineer = networking +
Python + Linux" skill-stack framing recurs (reinforces the "unicorn" framework). (f) "Never
too late / you're not too old" encouragement ethos stated explicitly. Promote at checkpoint.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — late-2017→2018 P1, 7 ingested / 1 no-captions
8 P1 long-form (2017-12 → 2018-07). 7 ok, 0 skipped, 1 no-captions (uyGVNqZ1KMU → L1).
Notable shift: the corpus starts moving from pure study-advice into hands-on tech.
- 2017-12-21 dVXHibpRmaA — net engineer salary (2017 figures) ★
- 2017-12-22 Zlc12P4F51c — how long to become a net engineer ★
- 2017-12-23 vN5a-ZjiFmI — network vs systems engineer
- 2018-02-13 BsH0SMDJdD4 — 7 study tips 2018 w/ Keith Barker CCIE ★ (GUEST collab)
- 2018-04-17 lTlTjeCjXYM — hack a Cisco switch w/ Raspberry Pi ★ (early hacking demo)
- 2018-04-25 6HsgCor5I28 — stop buying cert books ★
- 2018-07-16 G5HucqXioBY — home network → data center w/ DMVPN ★ (early homelab)
Synthesis notes: RICH. New — (a) First-person salary history + a "job-hop beats
stagnation" career/money framework (dated 2017 figures — mark time-sensitive). (b) His
personal "how I broke into networking" timeline/framework (biography material). (c)
Chuck<->Keith Barker relationship confirmed (fellow CBT Nuggets trainer, CCIE) → CREATE
wiki/entities/keith-barker.md context page at next synthesis; this collab needs
per-speaker attribution (done on the source page: 6 tips Chuck, tip 2 + CCIE anecdotes
Keith). (d) His study-resource stance: video course + lab + book, subscription training
(CBT Nuggets) > a single book — note his CBT Nuggets self-interest. (e) FORMAT EVOLUTION:
first Raspberry-Pi hacking demo (2018-04) and first personal-infrastructure/homelab video
(2018-07, reveals a Dallas colo + DMVPN traveling-branch pattern — bio). These mark the
pivot toward the hands-on hack/build content the channel is known for. Promote at
checkpoint (~2 batches away).

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2018 P1 (transition to automation), 8 ingested
8 P1 long-form (2018-08 → 2018-12). 8 ok, 0 skipped. Late-2018 = clear pivot toward
network automation / coding / DevNet.
- 2018-08-11 NBgRLL8mkUI — I PASSED THE CCNA (ICND2); interview w/ brother Cameron ★
- 2018-10-25 O8HDIRtMvwI — channel update: automation pivot ★
- 2018-10-30 eAdrnTOcPOg — start coding as a net engineer; intent-based networking ★
- 2018-11-23 rPjtZUBBPEU — memory-loss interview w/ Shawn Powers (guest) ★
- 2018-12-12 Azm4woyCNBA — canonical get-a-job-with-a-CCNA playbook ★
- 2018-12-16 iP9kuR2U8-o — fighting imposter syndrome (family interview) ★
- 2018-12-16 7UkkrNoZUwU — Arduino+Pi+Python monitor Cisco router (DevNet) ★
- 2018-12-17 KTOQHVui0fM — planning 2019 IT goals (AWS/cloud interest) ★
Synthesis notes: VERY RICH. New — (a) BIO: Cameron (the "noobs" podcast co-host) is
confirmed Chuck's BROTHER (appears in the CCNA-pass interview); their father also appears
in the imposter-syndrome video — both are context people, NOT the subject; attribution
applied. (b) BIO milestone: passed/recertified CCNA via ICND2 (Aug 2018). (c) SHIFT: an
explicit late-2018 channel pivot toward network automation / "start coding" / intent-based
networking (DNA Center, SDN) — dates the automation era; and a maker/DevNet build
(Arduino+Pi+Python). (d) Canonical "how to get a job with a CCNA" job-hunting playbook —
core certifications-career content. (e) Emerging AWS/cloud interest in his 2019 goals —
foreshadows the cloud era. (f) Shawn Powers confirmed as a recurring collaborator (Linux
educator) → CREATE wiki/entities/shawn-powers.md at synthesis (alongside keith-barker.md).
ENTITY DEBT: keith-barker, shawn-powers, cameron (brother/co-host). Promote at checkpoint
(~2 batches away).

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2018-12→2019-05 P1, 8 ingested
8 P1 long-form (2018-12 → 2019-05). 8 ok, 0 skipped.
- 2018-12-19 C4OxzOPGWnI — 5 reasons NOT to become a net engineer ★ (family on camera)
- 2018-12-19 7CP4__3t8go — CompTIA vs Cisco, 2019 REVISIT ★ (position evolved)
- 2018-12-22 FpsW-1Zuhp8 — what is a VMware engineer (interview w/ father)
- 2019-03-02 FfJXcoqTvrs — CCNA lab in Azure / GNS3 ★ (cloud era begins)
- 2019-03-05 F9j2aiqK0tw — get your CCNA in 2019 roadmap ★
- 2019-03-12 PusUAu9gGiI — CCNA Cyber Ops vs CCNA Security
- 2019-04-24 bbkBJxOo4gg — hack study habits via Atomic Habits ★ (book influence)
- 2019-05-10 LfoJEZNX4DA — do you really want it / find-your-why ★
Synthesis notes: RICH + CONTRADICTIONS to reconcile.
- POSITION EVOLVED (already flagged on-page w/ callout + wikilink): his CompTIA-vs-Cisco
  cert advice SOFTENED from 2017 ([[2017-08-30-yt-EywIAz8fPnY]]) to 2019 — 2017 = skip
  Network+; 2019 = Network+ OK for path-undecided/cloud-bound learners. Reconcile in the
  certifications-career topic page and DATE both positions.
- BIO/ENTITIES: his FATHER is also named Chuck Keith and is a VMware engineer (appears in
  FpsW-1Zuhp8) — context person, NOT the subject; add to entity debt. Wife appears on
  camera in C4OxzOPGWnI — name rendered "Abby" by captions vs SUBJECT.md "Abbey";
  RECONCILE spelling at synthesis (keep self-reported, children unnamed).
- FRAMEWORKS: study-habits framework built on James Clear's "Atomic Habits" (a BOOK
  INFLUENCE worth an entity/reference note); "find your why" motivational framework;
  honest "downsides of IT" take.
- ERA: cloud content begins (Azure/GNS3 tutorial, Mar 2019) — reinforces the automation→
  cloud trajectory. CCNA roadmap is pre-2020-overhaul (version-date it).
ENTITY DEBT now: keith-barker, shawn-powers, cameron (brother), chuck-keith-sr (father),
james-clear/atomic-habits (book). CHECKPOINT next batch (batch 9 → debt 9; then batch 10).

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2019-05→2019-10 P1, 8 ingested
8 P1 long-form (2019-05 → 2019-10). 8 ok, 0 skipped. Heavy on the 2020 Cisco cert
overhaul + more guest interviews + hands-on hacking/maker builds.
- 2019-05-10 cDxngzbBbhI — is MPLS dead? panel w/ Keith Barker + Jason Gooley ★
- 2019-05-31 sEmEUW18uNE — school-district IT interview (guest Dallas) ★
- 2019-06-10 nD7zD-cpQG0 — new CCNA 200-301 / 2020 overhaul (Susie Wee interview) ★
- 2019-06-15 l9sqsDqF0QY — CCNA/CCNP/CCIE 2020 restructure overview ★
- 2019-06-23 f4p107p3vQg — get old CCNA before 2020 (time-bound) ★
- 2019-07-09 fqtr_Yyy0a4 — CCNP in 2020 without CCNA prereq ★
- 2019-08-27 q7HkIwbj3CM — hack public WiFi w/ Pi + Kali (ethical framing) ★
- 2019-10-27 B_krqlk_cXo — Pi Halloween automation (IFTTT/Alexa/REST) ★
Synthesis notes: (a) CERT-STRUCTURE cluster: four videos document Cisco's Feb-2020
overhaul (single CCNA 200-301; CCNP two-exam core+concentration; CCNP no longer needs
CCNA; DevNet certs). ALL version-dated/historical — at synthesis, build ONE dated
certifications-career section on "the 2020 Cisco cert overhaul" and mark pre-2020 advice
(e.g. CCENT, CCNA Cyber Ops, ICND1/2) as SUPERSEDED. (b) GUESTS/ENTITIES added: Jason
Gooley (CCIE, Cisco), Susie Wee (Cisco DevNet), plus school-district interviewee — Cisco
folks are context, only Chuck's host lines train persona. (c) CAREER STANCE: generalist-
over-specialist + school-district IT as a viable niche (from the interview, Chuck-attributed
framing). (d) FORMAT: signature Kali-Linux + Raspberry-Pi ETHICAL-HACKING demo (with an
explicit ethics/education framing worth capturing in beliefs) and a fun Pi maker/automation
build — these two formats define the post-2019 channel. Promote at CHECKPOINT (next batch
= batch 8 done, debt 9; batch after = debt 10 → Stage S).

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2019-11→2020-05 P1, 7 ingested / 1 no-captions
8 P1 long-form (2019-11 → 2020-05). 7 ok, 1 no-captions (70eVeqKBgTo → L1). This batch =
the birth of the iconic "you need to learn X RIGHT NOW" era + self-hosting/Docker content.
- 2019-11-28 cxGCndru_c0 — CCNA in 84 days study plan ★
- 2019-12-21 GwHyoTVN_gA — CBT Nuggets CCNA 200-301 course (co-authored; mostly promo) ★
- 2020-02-28 vbaJcRxASo0 — Raspberry Pi learning desktop ★
- 2020-04-02 eGz9DS-aIeY — LANDMARK: you need to learn Docker RIGHT NOW ★
- 2020-05-02 dH3DdLy574M — Pi-hole on Docker + OpenDNS + IFTTT ★
- 2020-05-07 5hycyr-8EKs — LANDMARK: you need to learn Ansible RIGHT NOW ★
- 2020-05-26 KNxZIYHx29I — STRESSED OUT / learning-overwhelm prioritization ★
Synthesis notes: LANDMARK-heavy. (a) BIO: Chuck CO-AUTHORED the CBT Nuggets CCNA 200-301
course with Jeremy Cioara + Keith Barker — his portion was the Network Automation domain
(concrete, dated career fact; add Jeremy Cioara to entity debt). (b) SIGNATURE FORMAT:
"you need to learn X RIGHT NOW!!" is now established (Docker, Ansible) — a defining
voice/teaching pattern (hook → why-you-should-care → hands-on 101) that MUST shape
persona/voice.md; capture the catchphrase + energy. (c) SELF-AWARE MINDSET: the STRESSED
OUT video is Chuck addressing the overwhelm his own hype creates — a nuanced
learning-prioritization stance for persona/beliefs. (d) ETHOS: "cheap Raspberry Pi = learn
anything by doing" recurs. (e) CONTENT SHIFT: self-hosting/Docker/automation now dominate
over pure cert advice. ENTITY DEBT now: keith-barker, shawn-powers, cameron (brother),
chuck-keith-sr (father), jeremy-cioara, jason-gooley, susie-wee, atomic-habits/james-clear.
>>> SYNTHESIS CHECKPOINT DUE next iteration (debt now 10) → run Stage S.

## [2026-07-22] lint | synthesis pass 1 — @NetworkChuck P1 early era (2015-12→2020-05, batches 1–10)
First synthesis pass. Drained the 10-batch debt (59 L2 source pages) INWARD into topics +
persona; recompiled the clone. One agent per file (concurrency rule).
PROMOTED:
- persona/biography.md — added dated/cited 2015–2020 timeline entries (self-taught WGU-not-
  finished cert path; helpdesk→admin→engineer; CCNP journey via INE; CCNA Voice; 2017
  quit-job-to-travel/letsjustgo.family; late-2017 Paris goal; late-2018 automation pivot;
  Dec-2019 co-authored CBT Nuggets CCNA 200-301; 2020 learn-X era). CORRECTION captured: the
  Aug-2018 "I PASSED THE CCNA" video is BROTHER CAMERON's pass (Chuck mentoring), not Chuck
  recertifying. Confirmed Cameron = brother + podcast co-host; father = Chuck Keith, VMware
  engineer (context). Canonical wife spelling = Abbey.
- persona/voice.md — populated: signature "you need to learn X RIGHT NOW!!", "you CAN do
  this", coffee-cue, hook→why→hands-on→big-why arc, register/humor — cited verbatim banks.
- persona/beliefs.md — populated: unicorn stack, certs>degree, self-study, video+labs>books,
  study systems (Pomodoro/Atomic Habits/84-day), find-your-why, never-too-late,
  generalist>specialist, job-hop, learning-overwhelm, ethical-hacking ethos. FLAGGED the
  2017→2019 CompTIA-vs-Cisco cert-sequencing POSITION EVOLUTION (contradiction callout).
- All 7 tech-domain topic hubs (networking, cybersecurity, linux-terminal, cloud-devops,
  homelab-selfhosting, certifications-career, creator-coffee-business) built from stubs into
  real hubs: dated/cited "Key ideas" + date-ordered "Source pages" lists + cross-links.
  (ai-tools hub left as stub — no ai-tools sources ingested yet.)
- NEW entities: keith-barker, jeremy-cioara, cameron-keith, shawn-powers (context pages).
- persona/system-prompt.md — COMPILED v1 (compiled_from_sources: 59, ~640-word prompt).
  Persona mode (/networkchuck, /chuck) is now usable.
State: advanced high-water mark to "early era 2015-12→2020-05"; checkpoint 1 → Done.
Synthesis notes: none (this IS the synthesis pass; debt drained). DEFERRED to a later pass:
appearance.md still empty; father entity (chuck-keith-sr) not yet a page; atomic-habits/
james-clear reference note; reconcile children-count softness; ai-tools domain awaits sources.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2020-06→2020-07 P1, 6 ingested / 1 no-captions / 1 retry
8 P1 long-form selected (2020-06 → 2020-07). 6 ok, 0 skipped, 1 no-captions (croxobxz1bU
→ L1), 1 transient fetch error (will re-appear next batch). Post-synthesis, resumed P1.
This batch launches the FLAGSHIP FREE CCNA course.
- 2020-06-28 hrVa_dhD-iA — Google hacking / dorking (OSINT) ★
- 2020-07-01 AfVH54edAHU — Kali on Windows via WSL2 GUI
- 2020-07-04 S7MNX_UD7vY — FREE CCNA Day 0 (course kickoff) ★
- 2020-07-09 4t4kBkMsDbQ — Nmap tutorial ★
- 2020-07-14 9eH16Fxeb9o — FREE CCNA Day 1 (switches) ★
- 2020-07-26 p9ScLm9S3B4 — FREE CCNA EP2 (routers) ★
Synthesis notes: (a) LANDMARK — the "FREE CCNA" multi-episode course begins (Day 0 / Day 1
switches / EP 2 routers). This is a flagship free-education series and a canonical teaching
artifact; at the next synthesis, give it a dedicated structure under
certifications-career + networking (track episodes as they ingest) and note it in
creator-coffee-business (free-course-as-audience-engine). (b) Cybersecurity teaching
tutorials proliferate (Google dorking, Nmap, Kali-on-WSL2) — reinforce the ethical-hacking
teaching hub. No persona/belief changes needed yet (voice/beliefs already captured these
patterns in pass 1). Debt now 1.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2020-08→2020-09 P1, 7 ingested / 1 retry
8 P1 long-form selected (2020-08 → 2020-09). 7 ok, 0 skipped, 1 transient fetch error
(re-queues). More FREE CCNA + cybersecurity tutorials + AWS learn-X + Pi homelab.
- 2020-08-02 qsA8zREbt6g — hacking anonymity: Kali+ProxyChains+Tor (ethics) ★
- 2020-08-06 CRdL1PcherM — FREE CCNA EP3 (TCP/IP + OSI) ★
- 2020-08-06 3kfO61Mensg — FREE CCNA EP4 (TCP/IP+OSI real-life example) ★
- 2020-08-15 bgPuPSPZe2U — landmark: you need to learn AWS RIGHT NOW ★
- 2020-08-21 z4_oqTZJqCo — password cracking: Kali+HashCat (defensive) ★
- 2020-08-27 oIRkXulqJA4 — FREE CCNA EP5 (OSI app/transport layers) ★
- 2020-09-04 8QyFidVcoLM — Pi phone system / 3CX PBX (VoIP, ties to his collab background) ★
Synthesis notes: (a) FREE CCNA course continues — EP 3, 4, 5 (TCP/IP + OSI). Track for the
dedicated FREE-CCNA structure flagged last batch. (b) "you need to learn AWS RIGHT NOW"
extends the signature learn-X format into CLOUD (AWS) — already captured as a pattern in
pass-1 voice/beliefs; just add AWS to the cloud-devops hub next synthesis. (c) Ethical-
hacking teaching deepens (ProxyChains/Tor anonymity + HashCat password cracking, both with
explicit defensive/ethics framing) — reinforce cybersecurity hub. (d) Pi 3CX PBX ties back
to his Cisco VoIP/collaboration specialty (biography). No persona changes needed this batch.
Debt now 2.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2020-09→2020-10 P1, 7 ingested / 1 retry
8 P1 long-form selected (2020-09 → 2020-10). 7 ok, 0 skipped, 1 transient fetch error.
- 2020-09-09 7bA0gTroJjw — landmark: you need to learn Kubernetes RIGHT NOW ★
- 2020-09-18 wwwAXlE4OtU — FREE CCNA EP6 (network design) ★
- 2020-10-03 eZYtnzODpW4 — dark-web DDoS demo against own infra (ethics/education) ★
- 2020-10-11 6-66D9J5PkY — FREE CCNA EP7 (data center networks) ★
- 2020-10-19 vyqSdJLVQgg — FREE Security+ EP1 (course kickoff) ★
- 2020-10-24 6aLyZisehCU — VMware ESXi on a Raspberry Pi
- 2020-10-28 u9dBGWVwMMA — FREE Security+ EP2 (phishing awareness) ★
Synthesis notes: (a) SECOND flagship free course launches — "FREE Security+" (EP 1 kickoff,
EP 2 phishing). Alongside FREE CCNA, this establishes a "free full-course series" pattern —
at synthesis, give BOTH courses dedicated structure (certifications-career + their domains)
and note the free-course-as-audience-engine playbook in creator-coffee-business. (b) FREE
CCNA continues (EP 6 design, EP 7 data center). (c) "learn Kubernetes RIGHT NOW" extends the
learn-X format to container orchestration. (d) "i bought a DDoS on the dark web" = the
stunt-education format (dramatic real-world demo against his OWN infra + heavy ethics
framing) — a notable content archetype worth a beliefs/voice note next synthesis (how he
uses shock + ethics to teach security). No inline persona edits this batch. Debt now 3.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2020-10→2020-12 P1, 6 ingested / 1 skipped / 1 retry
8 P1 long-form selected (2020-10 → 2020-12). 6 ok, 1 skipped, 1 transient fetch error.
- Skipped: 29VLO75woK4 "6 deals you don't want to miss" (Black Friday affiliate promo, no content).
- 2020-10-31 xPi4uZu4uF0 — FREE CCNA EP8 (WANs) ★
- 2020-11-10 HfPKe98UqEI — FREE Security+ EP3 (social engineering / "hacked my grandma") ★
- 2020-11-17 UydNRZp_fmk — FREE Security+ EP4 (watering-hole/typosquatting) ★
- 2020-11-20 Q2ErfVPomFQ — FREE Security+ EP6 (attack vectors) ★
- 2020-12-06 80vIin4xGp8 — FREE CCNA EP9 (home network / IP addressing) ★
- 2020-12-18 nnAQ8SYzAnE — hack like Mr. Robot (pop-culture hacking) ★
Synthesis notes: Both free courses advance — FREE CCNA now through EP 9 (WAN, home network),
FREE Security+ through EP 6 (social engineering, web attacks, attack vectors). Note EP 5 of
Security+ not yet ingested (will surface later; the free-course structure at synthesis
should list episodes by number and flag gaps). "hack like Mr. Robot" adds a pop-culture
hacking-education archetype (reinforces the stunt/pop-culture teaching pattern). No new
persona/beliefs beyond what pass 1 captured. Debt now 4.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2020-12→2021-03 P1, 7 ingested / 1 retry
8 P1 long-form selected (2020-12 → 2021-03). 7 ok, 0 skipped, 1 transient fetch error.
- 2020-12-19 EY-Scg1z6zA — first hacking cert (PenTest+) ★
- 2021-01-18 wX75Z-4MEoM — landmark: learn Virtual Machines RIGHT NOW ★
- 2021-02-05 37tyxaQbtN4 — FREE CCNA EP10 (hybrid cloud) ★
- 2021-02-09 bsCsuoIzyTg — how big companies get hacked (attack chain) ★
- 2021-02-27 y8h5qY3zwic — FREE CCNA EP11 (ethernet cabling; kids cameo, self-reported) ★
- 2021-03-05 mvsiuLzpx2E — build a hacking lab (blueprint) ★
- 2021-03-06 KdZvxxLsN3E — Sherlock OSINT username search
Synthesis notes: (a) FREE CCNA now through EP 11 (hybrid cloud, ethernet cabling). (b)
"learn Virtual Machines RIGHT NOW" extends the learn-X format (VMs = the foundation for the
hacking-lab content). (c) CANONICAL "build a hacking lab" blueprint (VMs + Kali +
vulnerable targets, isolated/legal) — a core learn-by-doing security artifact; pairs with
the VM video + PenTest+ cert as a coherent "become a hacker" path worth a cybersecurity
sub-structure at synthesis. (d) PenTest+ positioned as the entry hacking cert (add to the
certifications-career cert map). (e) EP11 has a kids cameo — kept unnamed/self-reported.
No inline persona edits. Debt now 5 (checkpoint at 10 — ~5 batches out).

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2021-03→2021-04 P1, 7 ingested / 1 retry
8 P1 long-form selected (2021-03 → 2021-04). 7 ok, 0 skipped, 1 transient fetch error.
- 2021-03-13 6CnDdXVTxhU — PhoneInfoga phone-number OSINT
- 2021-03-14 MLxgmkRzgIQ — FREE CCNA EP12 (PoE) ★
- 2021-03-19 VbEx7B_PTOE — Linux for Hackers EP1 (course kickoff) ★
- 2021-03-28 NWyqSbnsvGU — Instagram OSINT
- 2021-04-09 A3G-3hp88mo — Linux for Hackers EP2 (file system) ★
- 2021-04-27 _u8qTN3cCnQ — VMs Pt2: Proxmox install (homelab hypervisor) ★
- 2021-04-29 SvO_FDa8AIs — Twitter OSINT
Synthesis notes: (a) THIRD flagship free course launches — "Linux for Hackers" (EP 1
kickoff, EP 2 file system). The clone now has THREE named free courses (FREE CCNA, FREE
Security+, Linux for Hackers) — at synthesis, create a dedicated "free courses" structure
(likely a certifications-career/education sub-page or entity) listing all three with their
episodes. (b) FREE CCNA now through EP 12 (PoE). (c) An OSINT tool-tutorial cluster
(PhoneInfoga, Instagram, Twitter, + earlier Sherlock) — group into a cybersecurity OSINT
sub-topic at synthesis. (d) Proxmox introduced as the recurring homelab hypervisor (pairs
with the VM + hacking-lab content) — reinforce homelab hub. No persona changes. Debt now 6.
CROSSED 99 L2 pages.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2021-05→2021-07 P1, 6 ingested / 1 no-captions / 1 retry
8 P1 long-form selected (2021-05 → 2021-07). 6 ok, 0 skipped, 1 no-captions (rI-XxnyWFnM
→ L1), 1 transient fetch error. CROSSED 100 L2 pages this batch (now 105).
- 2021-05-08 bllS9tkCkaM — dark web (Tor hidden service) on a Pi ★
- 2021-05-30 E3DEJ7odWq0 — FREE CCNA EP13 (fiber optic) ★
- 2021-06-18 LlbTSfc4biw — landmark: learn Load Balancing RIGHT NOW (homelab, Kemp) ★
- 2021-07-08 bXCeFPNWjsM — reverse shells with netcat (lab/ethics) ★
- 2021-07-27 gsvS2M5knOw — Guacamole browser remote access ★
- 2021-07-30 0W4JZIWtjLQ — FREE CCNA EP14 (port security) ★
Synthesis notes: (a) FREE CCNA now through EP 14 (fiber, port security). (b) Load Balancing
extends the learn-X format + a homelab build (Kemp LoadMaster). (c) NOTABLE PRECURSOR:
the Guacamole "access everything from your browser" video (2021-07) foreshadows his later
NetworkChuck Cloud Browser product (browser-based access) — worth a cross-link in
creator-coffee-business/Cloud Browser entity at synthesis. (d) Ethical-hacking teaching
deepens (reverse shells w/ netcat, Tor hidden service on Pi — both with lab-only/ethics
framing). Reinforces the cybersecurity hub + the ethical-hacking ethos already in beliefs.
No inline persona edits. Debt now 7 (checkpoint at 10 — ~3 batches out).

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2021-08→2021-11 P1, 7 ingested / 1 retry
8 P1 long-form selected (2021-08 → 2021-11). 7 ok, 0 skipped, 1 transient fetch error.
- 2021-08-14 mRMmlo_Uqcs — learn Python RIGHT NOW EP1 (Python course kickoff) ★
- 2021-08-20 e_f9p-_JWZw — BadUSB on $8 Pi Pico (hardware-hacking awareness) ★
- 2021-09-24 2rVzRoF7vQw — ARP poisoning/MITM demo on own network ★
- 2021-10-02 gyMpI8csWis — build a Raspberry Pi NAS (OMV)
- 2021-11-04 YJwhQowT84A — learn Google Cloud RIGHT NOW ★
- 2021-11-05 jlHWnKVpygw — Pi VPN travel router
- 2021-11-12 hHtGN_JzoP8 — crypto mining on a Pi (fun/learning)
Synthesis notes: (a) FOURTH free-course thread — a Python course begins (EP 1), again via
the learn-X format. Free-course roster now: CCNA, Security+, Linux for Hackers, Python. (b)
The "learn X RIGHT NOW" cloud series now covers AWS + hybrid-cloud + Kubernetes + Google
Cloud — a clear cloud-fluency push; group in cloud-devops hub. (c) HARDWARE-HACKING +
Raspberry-Pi maker cluster intensifies (BadUSB Pi Pico, ARP/MITM, Pi NAS, Pi VPN travel
router, Pi crypto mining) — the "cheap Pi can do anything" ethos is now a defining channel
signature; strengthen homelab hub + the Pi-as-learning-lab belief. (d) BadUSB/ARP both
carry defensive-awareness framing (consistent ethical-hacking ethos). No inline persona
edits. Debt now 8 (checkpoint at 10 — ~2 batches out).

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2022-01→2022-05 P1, 7 ingested / 1 retry
8 P1 long-form selected (2022-01 → 2022-05). 7 ok, 0 skipped, 1 transient fetch error.
- 2022-01-17 U7e-mcJdZok — Kasm Kali-in-browser hacking lab (Cloud Browser precursor) ★
- 2022-02-15 3ogyS4KOlXc — hacked wife's browser (BeEF; consent/awareness)
- 2022-03-14 GMOoXz20VZU — kids build a Pi hacking computer (kids-into-tech ethos) ★
- 2022-03-25 SPwyp2NG-bE — learn Bash Scripting EP1 (course kickoff) ★
- 2022-04-05 5WfiTHiU4x8 — You SUCK at Subnetting EP1 (course kickoff) ★
- 2022-04-07 tcae4TSSMo8 — we ran out of IP addresses (IPv4 exhaustion/IPv6)
- 2022-05-16 UtMMjXOlRQc — malware with Python (lab/ethics) ★
Synthesis notes: BIG ones. (a) DIRECT CLOUD-BROWSER PRECURSOR: the Kasm "stream Kali to your
browser" lab (2022-01) uses the SAME Kasm container-streaming tech as the later NetworkChuck
Cloud Browser (~2023) product — at synthesis, cross-link this source from the
[[networkchuck-cloud-browser]] entity + biography (documents the product's technical origin
in his own content). Brother Cameron co-hosts (context). (b) TWO MORE free-course threads —
"Bash Scripting" (EP1) and "You SUCK at Subnetting" (EP1). Free-course roster now SIX: CCNA,
Security+, Linux for Hackers, Python, Bash, Subnetting — this is clearly a deliberate
"free full course" content strategy (promote to creator-coffee-business as a defining
playbook, + a dedicated free-courses index). (c) FAMILY-AS-CONTENT pattern: wife (consent
demo) + kids (build a hacking PC) appear as recurring context — reinforces the "get anyone,
even kids, into tech" ethos (belief) while keeping family self-reported/unnamed. (d) Python
now feeds security (malware-in-Python, lab/ethics) — the coding+security convergence. No
inline persona edits. Debt now 9. >>> CHECKPOINT next batch (debt → 10) → Stage S.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2022-05→2022-08 P1, 7 ingested / 1 retry
8 P1 long-form selected (2022-05 → 2022-08). 7 ok, 0 skipped, 1 transient fetch error.
- 2022-05-27 ACM36qtHIEg — hack faster: Linux terminal tips
- 2022-06-03 4xJDDUt4Wq8 — $0.30 hacking lab (AWS; no-excuses accessibility ethos) ★
- 2022-08-06 bKFMS5C4CG0 — Docker networking (bridge/macvlan) ★
- 2022-08-08 e2h_BreIxaQ — HACK your way into an IT job (2022 playbook) ★
- 2022-08-17 xiUTqnI6xk8 — learn SQL RIGHT NOW ★
- 2022-08-30 u2M_V5LtzpQ — how YouTubers get hacked (John Hammond interview)
- 2022-08-31 DM65_JyGxCo — Docker Compose tutorial
Synthesis notes: (a) UPDATED CANONICAL "hack your way into an IT job" playbook (2022) —
promote alongside the 2018 [[2018-12-12-yt-Azm4woyCNBA]] job playbook; note evolution/
continuity in certifications-career + beliefs. (b) "$0.30 hacking lab" crystallizes the
no-excuses ACCESSIBILITY ethos (cheap cloud/hardware = anyone can learn) — a core value for
persona/beliefs; pairs with the Pi-as-learning-lab thread. (c) DevOps deepens: Docker
networking + Docker Compose + SQL learn-X — the cloud-devops hub keeps growing (Docker is
now a multi-video subtopic). (d) New guest entity: John Hammond (security educator,
interview) — add to entity debt. No inline persona edits. Debt now 10.
>>> SYNTHESIS CHECKPOINT DUE next iteration → run Stage S (synthesis pass 2).

## [2026-07-22] lint | synthesis pass 2 — @NetworkChuck P1 mid era (2020-06→2022-08, batches 9–18)
Second synthesis pass. Drained the 10-batch debt (pages 60–126, 67 new L2) INWARD; recompiled
the clone to v2. One agent per file (concurrency rule).
PROMOTED:
- NEW wiki/topics/certifications-career/free-courses.md — catalog of the SIX free full-course
  series (FREE CCNA [15 eps], Security+ [EP1-6, EP5 gap flagged], Linux for Hackers, Python,
  Bash, You SUCK at Subnetting), each with ingested-episode wikilinks. A defining content
  strategy. Linked from certifications-career hub + creator-coffee-business + index.
- persona/beliefs.md — added: no-excuses accessibility ($0.30/Pi lab), build-a-lab hands-on-
  first pedagogy, tech-for-everyone/kids, broad cloud/tooling polyglot fluency, updated 2022
  "hack your IT career" playbook (continuity w/ 2018), + dated ethical-hacking sub-note.
- persona/biography.md — added: free-course series 2020–2022; the "learn X RIGHT NOW" cloud
  era; Jan-2022 Kasm Kali-in-browser video as the documented technical precursor to the
  NetworkChuck Cloud Browser (~2023).
- wiki/topics/cloud-devops + cybersecurity hubs — extended with the full learn-X cloud series,
  Docker multi-video subtopic, OSINT cluster, ethical-hacking demo catalog, build-a-lab
  blueprint, "how X gets hacked" awareness series; refreshed source-page lists (cloud-devops
  23 sources, cybersecurity 28).
- wiki/entities/networkchuck-cloud-browser.md — added "Technical origin" note (Kasm precursor).
- NEW entity john-hammond (security educator, interview guest).
- persona/system-prompt.md — recompiled v2 (compiled_from_sources ~126, ~660-word prompt).
State: advanced high-water mark to "2015-12 → 2022-08 (batches 1–18)"; checkpoint 2 → Done.
Synthesis notes: none (this IS the pass; debt drained). DEFERRED: appearance.md still empty;
father entity (chuck-keith-sr) not yet a page; networking/linux/homelab hub source-lists not
exhaustively refreshed this pass (episodes are in youtube-index + free-courses page); ai-tools
domain still awaits sources (none ingested yet).

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2022-09→2023-01 P1, 6 ingested / 1 skipped / 1 retry
8 P1 long-form selected (2022-09 → 2023-01). 6 ok, 1 skipped, 1 transient fetch error.
- Skipped: tHBUxYGthYg "top Black Friday deals" (affiliate deals roundup, no content).
- 2022-09-23 iX0HbrfRyvc — learning Docker made easy (Portainer)
- 2022-10-05 2OPVViV-GQk — SQL injection tutorial (lab/defense)
- 2022-10-21 sLkdtjJc6mc — i hacked this photo (steganography/EXIF)
- 2022-10-31 X2YH-XyqyXE — Pi haunted house (maker/home automation) ★
- 2022-11-16 gd7BXuUQ91w — 60 Linux commands (canonical reference) ★
- 2023-01-05 uTAaFExLgwQ — hacker's roadmap / get started in IT 2023 ★
Synthesis notes: (a) CANONICAL "60 Linux Commands" reference + the 2023 "hacker's roadmap /
how to get started in IT" — both core teaching artifacts; at synthesis add the roadmap to
certifications-career (a dated companion to the job playbooks) and the Linux-commands ref to
linux-terminal. (b) Web-app security enters (SQL injection, steganography) — extend the
cybersecurity ethical-hacking catalog. (c) The Pi maker/"tech is fun" ethos continues
(haunted house). (d) Crossed into 2023 content. No inline persona edits (patterns already in
v2 persona). Debt now 1.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2023 P1, 7 ingested / 1 skipped
8 P1 long-form (one 2020 straggler + 2023-03 → 2023-07). 7 ok, 1 skipped, 0 retry.
- Skipped: yFC8pb2TPdc "learn HACKING/CEH" (2020) — garbled/junk captions, unusable.
- 2023-03-01 JJCq21Dc-Us — learn Machine Learning (FIRST AI/ML video) ★
- 2023-03-10 km81ph7pZz8 — 3 Pi hacking-gadget builds
- 2023-03-27 prVHU1fLR20 — 30 Windows commands (reference) ★
- 2023-06-19 xBIowQ0WaR8 — build your own cloud (self-hosting/data-ownership) ★
- 2023-06-28 X1CM3rZwGn8 — learn Windows / AD (learn-X) ★
- 2023-06-30 L26Xq7m0uQ0 — hack a password: Windows edition (NTLM; defense) ★
- 2023-07-10 0kk6k-VdllM — intro to cloud hacking (leaky buckets/S3) ★
Synthesis notes: MAJOR. (a) THE AI-TOOLS DOMAIN OPENS: "learn Machine Learning RIGHT NOW"
(Mar 2023) is his first AI/ML video — the ai-tools hub (empty since bootstrap) now has its
first source; at synthesis, seed the ai-tools hub + note the 2023 AI-content pivot in
biography (guests Santiago/Nacho = context). (b) The learn-X format extends to WINDOWS/AD +
Machine Learning; the command-reference genre gets a Windows companion (30 Windows cmds) to
the 60-Linux-cmds. (c) CLOUD+SECURITY CONVERGENCE deepens: "intro to cloud hacking (leaky
buckets)" + Windows password cracking (NTLM, full MITRE ATT&CK defensive mapping) — extend
cybersecurity hub. (d) "build your own cloud" crystallizes a DATA-OWNERSHIP / self-hosting
PHILOSOPHY (own your data vs Big Tech) — a value worth adding to beliefs at next synthesis.
Debt now 2.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2023-09→2024-04 P1, 8 ingested
8 P1 long-form (2023-09 → 2024-04). 8 ok, 0 skipped, 0 retry.
- 2023-09-14 qHe4mlhuNt4 — hacking a database (Oracle 23c; lab/defense)
- 2023-09-28 jsKqQvFk7Sk — the Raspberry Pi 5 (hardware overview)
- 2023-09-30 U2-JPqrALsA — access the dark web 2024 (3 levels; safety/ethics)
- 2023-12-30 nTqu6w2wc68 — learn tmux RIGHT NOW ★
- 2024-01-08 dZwbb42pdtg — 3 levels of WiFi hacking (own-network/defense) ★
- 2024-02-16 5FhDrux0kCc — ditched the Pi for an alternative SBC/mini-PC
- 2024-03-12 WxYC9-hBM_g — run your own private AI (Ollama; self-hosted LLM) ★
- 2024-04-03 gL4j-a-g9pA — 60 hacking commands (reference trilogy) ★
Synthesis notes: (a) AI-TOOLS grows: "Run your own AI (but private)" (Ollama/self-hosted
LLM, Mar 2024) merges his AI + self-hosting + data-ownership threads. Seed the ai-tools hub
with BOTH this + the ML video at next synthesis; note the private/self-hosted-AI stance as a
belief (extends "own your data"). (b) REFERENCE TRILOGY complete: 60 Linux + 30 Windows + 60
Hacking commands — a recognizable "command reference" content format. (c) tmux learn-X. (d)
WiFi (own-network) + Oracle DB + dark-web-explained extend the ethical-hacking catalog (all
defensive/safety framed). (e) Hardware thread: Pi 5 + "ditched the Pi for [alt]". No inline
persona edits. Debt now 3. P1 tier almost drained (~20 left on main).

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2024-05→2024-10 P1, 8 ingested
8 P1 long-form (2024-05 → 2024-10). 8 ok, 0 skipped, 0 retry.
- 2024-05-03 Wjrdr0NU4Sk — host ALL your AI locally (full self-hosted AI stack) ★
- 2024-06-11 AaseHnf0k2o — RetroPie gaming machine (fun/maker)
- 2024-07-26 jJrnJ9rj6fs — FrankeNAS CEPH cluster (mixed hardware) ★
- 2024-08-30 Z_QlUyYlUCg — IPv6 hacking on Windows (mitm6; defense)
- 2024-09-18 AxMWywGFSfs — he hacked my websites (guest Tyler Ramsey/HackSmarter) ★
- 2024-09-25 RUqGlWr5LBA — 18 ways I use Docker (self-host everything) ★
- 2024-10-08 6YHqVbvfMYI — stratum-1 time server in homelab (NTP/GPS)
- 2024-10-25 k02P5nghmfs — self-hosted home automation (Home Assistant; local-control) ★
Synthesis notes: (a) 2024 is HOMELAB/SELF-HOSTING HEAVY: FrankeNAS/CEPH, 18-Docker-services
showcase, stratum-1 time server, Home Assistant, RetroPie — his homelab identity is now a
dominant channel pillar; the "self-host everything / own your data / local-control" thread
runs through AI (host all AI locally), storage, and home automation → promote a unified
"self-hosting & data-ownership" framing to beliefs + homelab hub at next synthesis. (b)
AI-tools deepens again (full local AI stack, May 2024) — 3 AI videos now (ML, private AI,
host-all-AI); enough to seed the ai-tools hub properly. (c) New guest entity: Tyler Ramsey
(HackSmarter, pentester) — entity debt. (d) Security continues (IPv6/mitm6, web pentest).
No inline persona edits. Debt now 4. P1 down to ~12 on main.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2024-12→2025-09 P1 (FINAL P1), 8 ingested
8 P1 long-form (2024-12 → 2025-09). 8 ok, 0 skipped, 0 retry. THIS DRAINS THE MAIN-CHANNEL
P1 TIER (landmark/top-by-views). Corpus now reaches the current era (Sept 2025).
- 2024-12-10 -49KVplIGDo — Raspberry Pi 500 review
- 2025-02-04 EXL8mMUXs88 — self-hosted remote desktop (RustDesk)
- 2025-02-17 Ju0ndy2kwlw — AI supercomputer w/ 5 Mac Studios (local LLM at scale) ★
- 2025-02-28 CxTMHw-M0Yg — you're going to get hacked 2025 (zero-trust-human) ★
- 2025-04-23 6WYBvbn-mgQ — Zima Board 2 homelab review
- 2025-07-16 ONgECvZNI3o — use n8n RIGHT NOW (self-hosted AI automation) ★
- 2025-08-12 Qvx2sVgQ-u0 — hacking AI (prompt injection; AI+security) ★
- 2025-09-12 GuTcle5edjk — learn MCP RIGHT NOW (Model Context Protocol) ★
Synthesis notes: MAJOR — the CURRENT ERA. (a) AI is now a DOMINANT pillar: local AI at
scale (5 Mac Studios), self-hosted AI automation (n8n), AI security (prompt injection), and
the AI-agent frontier (MCP, Sept 2025). The ai-tools domain now has ~7 sources spanning
ML→private-AI→local-stack→supercomputer→automation→AI-hacking→MCP — a clear 2023→2025 AI
pivot; at synthesis, fully build the ai-tools hub + add a biography "AI era" arc + a belief
about self-hosted/private AI + AI-as-the-new-frontier. (b) AI+SECURITY CONVERGENCE (hacking
AI) and AI+SELF-HOSTING (own your AI) are his two signature 2025 angles. (c) "zero trust
human" personal-security philosophy (2025 threats) — good beliefs/voice material. (d) MILESTONE:
main-channel P1 tier is DONE. Next: continue with P2 (183 rows) or @networkchuck_v2 P1 (17).
No inline persona edits. Debt now 5.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — P1 tail + earliest era, 7 ingested / 1 retry
Mixed batch: last main P1 (recent 2025-10→2026-03) + first P2s (the EARLIEST 2014-2016
videos). 7 ok, 0 skipped, 1 transient fetch error.
- 2014-10-04 ZR7_D1V3zD0 — CHANNEL ORIGIN / first video ★
- 2014-10-19 8rVzrPzhXnA — CUCM hunt group (Cisco VoIP/collab origin) ★
- 2014-12-01 yn_qCnOh9xk — Cisco ASA license (firewall origin era) ★
- 2016-03-14 8pbu-uJlJ9E — Cisco phone hunt-group button (VoIP/collab)
- 2025-10-03 budTmdQfXYU — n8n runs my entire homelab (AI automation) ★
- 2025-10-28 MsQACpcuTkU — using AI the hard way: his terminal-AI/Claude Code workflow ★
- 2026-03-31 eGSsoSEppNU — the WORST hack of 2026 (supply-chain); MOST RECENT ★
Synthesis notes: BIG bio + persona finds. (a) CHANNEL ORIGIN (2014-10-04): confirms/ dates
the earliest bio — filming quietly in the back room at his job, a NETWORK ADMIN in DALLAS TX
surrounded by switches/routers/ASAs, channel started "to solidify everything I'm learning"
(learning-in-public origin). Promote to biography (2014 entry) — corroborates the dossier
with his own words. (b) EARLIEST CONTENT = Cisco COLLABORATION/VOICE (CUCM hunt groups, IP
phones) + ASA firewalls — confirms his origin specialty was Cisco voice/collab + security,
matching CCNA Voice. Seed a "Cisco VoIP/collaboration origin" note in networking hub +
biography. (c) PERSONA-CURRENT: he now uses a TERMINAL-AI workflow — Claude Code as daily
driver, sub-agents, synced context files, GitHub-tracked projects, "AI as critic not writer"
(2025-10). Notable current-day voice/beliefs material (how he actually works with AI now). (d)
Corpus temporal span is now COMPLETE: 2014-10 → 2026-03. No inline persona edits. Debt now 6.
Main P1 fully drained; now flowing into main P2 (long tail).

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2017 P2 (Cisco VoIP era), 5 ingested / 2 skipped / 1 retry
8 selected (2017 P2 — early Cisco collaboration/VoIP + CCNP era). 5 ok, 2 skipped, 1 retry.
- Skipped: 8HeAIXGQMA4 (INE CCNP giveaway promo); lbHASiYwGHo (42-line pointer to a
  SimpleProgrammer cross-channel collab — substance on the other channel).
- 2017-01-24 eTdHGjC0U08 — CUCM CSS/partitions via Star Wars analogy ★
- 2017-08-11 dQsaSdzfUAM — CUCM route groups/lists/patterns Pt1
- 2017-08-15 FR1Jx9z7x-w — CUCM route groups/lists/patterns Pt2
- 2017-09-20 O1aNuVYjXNM — Voice VLANs explained
- 2017-10-01 FUw_Ctrp5EM — CCENT/ICND1 pass (brother Cameron; not Chuck)
Synthesis notes: (a) PEDAGOGY: the Star Wars analogy CUCM video is early evidence of his
signature ANALOGY-BASED teaching (making hard IT approachable via pop-culture analogies) —
add to voice.md as a teaching-style trait. (b) BIO: Chuck references his OWN earlier CCENT
(~2012-13) as context in Cameron's pass video — a datapoint for the pre-2014 timeline. (c)
Confirms the deep Cisco COLLABORATION/VOICE origin specialty (CUCM call routing, voice
VLANs) — reinforces the networking-hub "Cisco VoIP origin" note flagged last batch. Long-tail
P2 draining. No inline persona edits. Debt now 7.

## [2026-07-22] ingest | yt batch (@networkchuck_v2, 8) — first v2 ingest: noobs podcast, 1 ingested / 7 dup
First @networkchuck_v2 (overflow channel) ingest. 8 P1 selected; all were the David Bombal
"become a hacker" cluster. 1 ingested, 7 skipped as dup-of.
- 2022-02-21 tWAkJw3_l2s — noobs podcast ep4 w/ David Bombal (full 3667-line episode) ★
- Skipped as dup-of tWAkJw3_l2s (short excerpt clips, guest-dominated): nQ_2dyfJYxs,
  cANWGEKNAwU, pzgw3hJ-IEM, qNTsMJD5NcA, jDMwHbNBZyc, eAJc6IVmSRg, Muyp8_dlwwY.
Synthesis notes: (a) The @networkchuck_v2 channel appears to be largely a CLIP/OVERFLOW
channel — short excerpts of main podcast/videos. Apply the shorts-dedup discipline here too
(dedupe clips against the long-form source before ingesting). (b) The "noobs" podcast (Chuck
+ brother Cameron) is confirmed with a real episode; David Bombal guest — per-speaker
attribution applied (David Bombal's hacking journey/advice = context, NOT Chuck's persona).
Reinforces [[david-bombal]] + [[cameron-keith]] entities and the podcast format. (c) LOOP
NOTE for v2: expect many more dup clips; check each v2 item against main long-form. No inline
persona edits. Debt now 8 (checkpoint at 10 — 2 batches out).

## [2026-07-22] ingest | yt batch (@networkchuck_v2, 8) — 2024-25 standalone tutorials, 8 ingested
8 @networkchuck_v2 items (2024-12 → 2025-09). 8 ok, 0 skipped, 0 retry. Unlike the earlier
v2 clip cluster, these are GENUINE standalone tutorials (v2 hosts original content too).
- 2024-12-19 An4IapvutzM — Home Assistant Voice (private local Alexa)
- 2025-02-07 ay8t4zyalK4 — is the new CompTIA A+ (220-1201/02) worth it? ★
- 2025-03-05 MVyb-nI4KyI — pyenv multiple Python versions ★
- 2025-03-13 JJ_0-pAOIEk — host Open WebUI locally (self-hosted AI hub)
- 2025-03-13 BdH_yR_J3FQ — Open WebUI as a real website (domain+SSL)
- 2025-03-28 vrELBV-r4Aw — Raspberry Pi SMB file server
- 2025-07-16 -ErfsM2TYsM — run n8n locally (on-premise)
- 2025-09-10 1tw3O2iOt1U — Cisco cert-director (Ryan Rose) on future of CCNA ★ (guest)
Synthesis notes: (a) v2 is a MIX: some clip excerpts (dedupe) + original standalone
tutorials (ingest) — triage per item. (b) CURRENT CERT STANCE: his 2025 take on the new
CompTIA A+ (220-1201/1202) — add to certifications-career as the latest dated cert-advice
datapoint (compare to his earlier A+/CompTIA positions for the evolving-position trail). (c)
Cisco's official cert-director (Ryan Rose) interviewed on the FUTURE OF CCNA — authoritative
context (attributed to guest, not Chuck); note in networking/cert hubs + add ryan-rose to
entity debt. (d) Self-hosted-AI tooling deepens (Open WebUI local + public, n8n on-prem) —
reinforces the private/self-hosted-AI thread for the ai-tools hub. No inline persona edits.
Debt now 9. >>> CHECKPOINT next batch → Stage S (synthesis pass 3).

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2018 P2 (bio-rich channel era), 6 ingested / 1 skipped / 1 no-captions
8 P2 (2018). 6 ok, 1 skipped, 1 no-captions (isMnWZqAh0k → L1).
- Skipped: DctF8QwAmfs (10 Days of Christmas giveaway announcement, no content).
- 2018-01-07 GEUSjg3Sy24 — became a CBT Nuggets trainer (Jan 2018 milestone) ★
- 2018-04-10 2BxAmdqWWJo — is NetworkChuck over? (quit eng job for CBT Nuggets FT) ★
- 2018-06-09 0I4r0QGXD7U — going to Cisco Live 2018 Orlando ★
- 2018-08-17 Pae_PYKKMAU — future of infosec (DNA Center; 2018 prediction) ★
- 2018-12-01 8qZYfLG1hSo — scheduled CCNP TSHOOT 300-135 (Dec 2018; final CCNP exam) ★
- 2018-12-14 T1-r_feNNnw — the ONE skill in IT = customer-service/people skills ★
Synthesis notes: HIGH BIO VALUE — refines the 2017-2018 timeline. (a) MILESTONE + timeline
correction: he QUIT his engineering job to join CBT Nuggets FULL-TIME on Jan 1, 2018 (became
an official CBT Nuggets trainer). This sharpens the earlier "2017 remote Cisco role + RV
travel → 2018 full-time CBT Nuggets trainer" arc — promote to biography with the precise date.
(b) CERT TIMELINE: scheduled his own CCNP TSHOOT (300-135) Dec 2018 — the final CCNP exam;
corroborates the "CCNP nearly done, TSHOOT outstanding" thread. (c) Cisco Live 2018 Orlando
attendance (Cisco-community involvement). (d) NEW BELIEF: "the ONE skill you need in IT =
customer service / people skills" — a soft-skills-over-technical value for persona/beliefs.
(e) Dated 2018 infosec-automation prediction (DNA Center) — track for evolution. No inline
persona edits. Debt now 10. >>> SYNTHESIS CHECKPOINT DUE next iteration → Stage S (pass 3).

## [2026-07-22] lint | synthesis pass 3 — recent+origin+v2 (batches 19–28, 2014-2026)
Third synthesis pass. Drained the 10-batch debt (~64 new L2, spanning the earliest 2014-2018
origin, the 2022-2026 recent/AI era, and the @networkchuck_v2 channel); recompiled clone to v3.
PROMOTED (one agent per file):
- BUILT wiki/topics/ai-tools/ai-tools.md from stub — the 2023 AI pivot → private/self-hosted
  AI (Ollama, Open WebUI, Home Assistant Voice) → local-at-scale (5 Mac Studios) → automation/
  agents (n8n, MCP, his Claude-Code terminal workflow) → AI security (prompt injection); dated
  arc + 13-source list + cross-links.
- persona/biography.md — +8 dated entries: ~2012-13 own CCENT; Oct-2014 CHANNEL ORIGIN
  (network admin in Dallas, learning-in-public); 2014-17 Cisco voice/collaboration + ASA origin
  specialty; Jan-1-2018 full-time CBT Nuggets (quit engineering job); Cisco Live 2018; Dec-2018
  CCNP TSHOOT; 2023 AI pivot; 2024-26 self-hosted-AI era.
- persona/beliefs.md — +people/soft-skills-are-THE-skill, learn-in-public, private/self-hosted
  AI (own your data), AI-as-must-learn-frontier + attack-surface, 2025 CompTIA A+ stance.
- persona/voice.md — +analogy-based teaching (Star Wars→CUCM), learning-in-public/humble-learner
  framing, 2025 terminal-AI (Claude Code) vocabulary.
- wiki/topics/certifications-career — +2023 hacker's roadmap, 2025 A+, CCNA-future (Ryan Rose
  interview, guest-attributed), command-reference trilogy, ONE-skill=people-skills.
- NEW entities ryan-rose (Cisco cert director), tyler-ramsey (HackSmarter pentester).
- persona/system-prompt.md — recompiled v3 (compiled_from_sources ~190).
State: high-water mark advanced to full span 2014-10→2026-03 (batches 1–28); checkpoint 3 → Done.
Synthesis notes: none (this IS the pass; debt drained). DEFERRED: appearance.md still empty;
networking-hub Cisco-VoIP-origin section note (captured in biography + sources for now); father
entity (chuck-keith-sr) still not a standalone page; minor collab entities (Kevin Wallace, Kris
Bryant, Jason Gooley, Susie Wee, Santiago/Nacho) not yet pages. Remaining open ingest: main P2
(~164) + P3 + v2 P2/P3 + 153 shorts.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2019 P2 (bio-critical), 7 ingested / 1 no-captions
8 P2 (2019). 7 ok, 1 no-captions (BJFxMDxG_KY → L1). (Driver crashed on a cp1252 console
print of a unicode title; re-ran with PYTHONUTF8=1 — a Windows-console quirk, not a data issue.)
- 2019-02-02 m5qsxBwXGB0 — PASSED TSHOOT → COMPLETED CCNP (Feb 2019) ★
- 2019-02-19 QpqzG931JbU — This is IT! show EP1 (co-host David Bombal) ★
- 2019-03-16 8cmmVEoftEM — WiFi 6 / 802.11ax
- 2019-05-15 _8OMN08VQ6A — Synology + CrashPlan backup (3-2-1; 2019) ★
- 2019-05-25 lzFIm3zg_nI — SCHEDULED CCIE R&S written (2019 attempt) ★
- 2019-09-06 cChGFpElMEM — most dangerous Linux commands (awareness) ★
- 2019-09-15 oPrKUSizQVQ — unlimited Google Drive (2019, obsolete)
Synthesis notes: TWO FIDELITY-CRITICAL BIO ITEMS. (a) He COMPLETED his CCNP — passed the
TSHOOT (300-135) Feb 2019, and is openly honest about FAILING it before passing (persistence/
authenticity trait for voice/beliefs). Add "completed CCNP (Feb 2019)" to biography. (b) CCIE
RESOLVED: he SCHEDULED the CCIE R&S WRITTEN exam (June 2019) as an opportunistic free-voucher
attempt — he PURSUED it, but there is NO source he PASSED or holds a CCIE. Fidelity callout
added on the source page. At synthesis, add a biography "Known uncertainties"/timeline note:
"pursued/scheduled the CCIE written (2019); no evidence of passing — do NOT claim a CCIE." This
finally sources WHY the CCIE keeps coming up. (c) "This is IT!" show with David Bombal confirmed
(EP1, co-hosted) — reinforces the [[david-bombal]] partnership. No inline persona edits (next
synthesis promotes the CCNP-complete + CCIE-pursuit facts). Debt now 1.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2020 P2, 7 ingested / 1 rate-limited
8 P2 (2020). 7 ok, 0 skipped, 1 x 429 rate-limit (YOomKJdLLEo, left open for retry).
- 2020-01-26 bTPpKxuV-CY — "going to become a HACKER" (2020 pivot into cyber content) ★
- 2020-02-06 2IY1U5ljeFE — overwhelmed with IT (learning-overwhelm coping) ★
- 2020-02-16 BezoNUflqXo — UniFi Dream Machine review
- 2020-02-27 laaGuJItNCM — goodbye Microsoft certs (MCSA/MCSE retired 2020)
- 2020-03-10 noC8t8nwji4 — UniFi Dream Machine Pro review
- 2020-05-09 OWKPxAgh9DU — Ansible network automation (Cisco lab)
- 2020-05-16 0fJz-xMrqFw — cert thing I hate (at-home proctoring shift)
Synthesis notes: (a) BIO/DIRECTION: Jan-2020 "this year I'm going to become a HACKER"
declaration — dates his deliberate pivot into the cybersecurity/ethical-hacking content that
becomes a channel pillar (pairs with the 2020 FREE Security+ + hacking-tutorial surge). Add to
biography. (b) Reinforces the learning-overwhelm coping theme (STOP/RESET). (c) UniFi/Ubiquiti
is his recurring home-network gear (homelab). (d) Mostly dated news/reviews (MS cert retirement,
UDM) — L2 is sufficient. 1 rate-limit (1 of the 3-strike safety rail; fine). No inline persona
edits. Debt now 2.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2020 P2, 6 ingested / 2 rate-limited
8 P2 (2020-07 → 2020-10). 6 ok, 0 skipped, 2 x 429 rate-limit (left open). Rate-limiting is
building (1 last batch, 2 this batch) — watch for the 3-consecutive-failure safety rail.
- 2020-07-17 -pNupSPAgJA — HUGE announcement: quit job → FULL-TIME YOUTUBE (Jul 2020) ★
- 2020-08-18 dgdOILL1184 — Kali GUI on WSL2 (Win-KeX)
- 2020-08-28 m-i2JBtG4FE — free VPN server on AWS
- 2020-09-09 Bbqdq2sR6SY — 5G & cloud gaming (2020 take)
- 2020-09-14 fQek73drZS4 — how hackers hide files (forensics/awareness)
- 2020-10-08 yLf2jRY39Rc — FREE Security+ EP0 (intro; SY0-501 vs 601) ★
Synthesis notes: LANDMARK BIO. (a) ~Jul 2020: he QUIT his full-time job (at CBT Nuggets) to
do YOUTUBE FULL-TIME — the moment he became a full-time creator. Add to biography (sharpens
the arc: 2018 CBT Nuggets FT trainer → mid-2020 full-time YouTuber; and NetworkChuck Coffee
also launched ~Jul 2020 to fund the free training — the two are linked). (b) FREE Security+
now has its EP0 intro (course-structure + SY0-501→601 exam-version note) — add to the
free-courses page's Security+ episode list. (c) Rest = dated security/networking tutorials
(Kali WSL2, AWS VPN, 5G, file-hiding) — L2 sufficient. No inline persona edits. Debt now 3.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2020 P2, 5 ingested / 1 skipped / 2 rate-limited
8 P2 (2020-06 → 2020-12). 5 ok, 1 skipped (no usable captions), 2 x 429. Rate-limiting persists.
- Skipped: YOomKJdLLEo "I PASSED the Linux+" — music-only auto-caption, no speech (unusable).
  (Note: his Linux+ pass ~2020 is already in the dossier/biography, so no data lost.)
- 2020-11-19 XYpJhhJOJSs — FREE Security+ EP5 (fills gap); beard/appearance joke ★
- 2020-11-21 YYR-96xyBSU — Cisco Catalyst 1000 SMB switch review
- 2020-11-25 H8iUYmReC9M — shut up and just DO it (action ethos) ★
- 2020-12-10 ZnhM-lp6GE8 — 5G: 3 things you don't know ★
- 2020-12-17 AdzEDoHAbw8 — i failed my exam (honesty; 14-day Twitch study streams) ★
Synthesis notes: (a) APPEARANCE (persona/appearance.md is still EMPTY): the "my beard isn't
real" joke confirms his SIGNATURE BEARD as an appearance feature + a running self-joke — seed
persona/appearance.md next synthesis (beard, coffee mug, casual style). (b) VOICE/BELIEFS: "just
DO it / stop making excuses" action ethos; and radical AUTHENTICITY — he openly posts "i failed
my exam" (studied 14 days live on Twitch and still failed) — persistence + honesty are core
voice traits; also documents his TWITCH study-stream habit (bio). (c) FREE Security+ EP5 fills
the earlier-flagged episode gap. No inline persona edits. Debt now 4.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2020-11→2021-04 P2, 7 ingested / 1 rate-limited
8 P2. 7 ok, 0 skipped, 1 x 429 (rate-limiting eased after the longer heartbeat).
- 2020-11-16 -rSqbgI7oZM — how hackers sniff / MiTM (ARP spoof) ★ [caption partly corrupted]
- 2020-12-24 3Ay2Vk4jySI — Python: when should you learn it
- 2020-12-31 W-wdGEz4f5A — thank you (2020 year-end reflection; gratitude) ★
- 2021-03-18 ZhMw53Ud2tY — 5 steps to secure Linux (defensive) ★
- 2021-03-30 9Zj3Z4KkcQA — Notion study workflow (+Anki) ★
- 2021-04-15 gwUz3E9AW0w — build a portfolio website (career tactic) ★
- 2021-04-16 Y17KTiJLcyQ — Linux for Hackers EP3 (getting help) ★
Synthesis notes: (a) VOICE/BIO: the 2020 year-end "thank you" reflection shows his warm,
COMMUNITY-GRATITUDE voice + reflects on going full-time (bio) — add to voice.md. (b)
PERSONAL STUDY WORKFLOW: his own study system = Notion (notes) → Anki (flashcards) + labs —
a concrete methods datapoint (pairs with the earlier Pomodoro/Atomic Habits study frameworks).
(c) DEFENSIVE balance: "5 steps to secure Linux" (hardening: updates/sudo/SSH keys/UFW) — his
content isn't only offensive; capture the offense+defense balance in cybersecurity/beliefs. (d)
Career tactic: build a portfolio WEBSITE to get hired (extends the job playbooks). (e) Linux
for Hackers EP3 extends that free course. (f) Agents caught several title-vs-content mismatches
(WordPress not GitHub Pages; no fail2ban/tldr) — fidelity held. No inline persona edits. Debt now 5.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2021 P2, 7 ingested / 1 rate-limited
8 P2 (2021-04 → 2021-09). 7 ok, 0 skipped, 1 x 429.
- 2021-04-22 n_1wX7kKx7k — cloud phone system on AWS (3CX PBX)
- 2021-05-21 jwnvKOjmtEA — Linux for Hackers EP4 (sudo/users) ★
- 2021-06-03 HwSZe00ZSuU — will dad lose his job? (dad = trad IT infra eng) ★
- 2021-06-04 vX3krP6JmOY — Linux for Hackers EP5 (package mgmt) ★
- 2021-06-25 ZMsHCCyBqEQ — you need a NAS; his hybrid-cloud YouTube business (bio) ★
- 2021-08-06 wOWhfNB_r-0 — Linux for Hackers EP6 (services/systemctl) ★
- 2021-09-17 zV8KQNJMKS8 — i hate talking on the phone (personal trait) ★
Synthesis notes: (a) LINUX FOR HACKERS course fills out — EP4/5/6 now ingested (course now
EP1-6 + file-system); update the free-courses page episode list. (b) BIO/ENTITY: his DAD is
confirmed as Chuck Keith Sr., a TRADITIONAL IT INFRASTRUCTURE ENGINEER (reportedly at Supreme
Lending) — a datapoint for a future chuck-keith-sr entity page + biography (father-in-IT origin
detail). (c) BIO/CREATOR-INFRA: how he runs his OWN YOUTUBE BUSINESS = hybrid-cloud (NAS +
cloud) — add to creator-coffee-business + biography (his production stack). (d) PERSONALITY:
he openly says he HATES talking on the phone / prefers texting — a genuine personal-trait
datapoint (mild introversion) for persona (pairs with his people-skills-via-service belief).
No inline persona edits. Debt now 6.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2021 P2, 7 ingested / 1 rate-limited
8 P2 (2021-09 → 2021-12). 7 ok, 0 skipped, 1 x 429.
- 2021-09-21 IXr0-J5XXMA — Python course EP2 ★
- 2021-10-12 apC1bOLbzbY — bought a new server (VMware ESXi; homelab growth)
- 2021-10-16 QWQ-LQL1owE — free Kali in the cloud (AWS) ★
- 2021-10-26 T6OLDHAWjjA — Python EP3 (you don't need math; accessibility) ★
- 2021-11-02 XIoHFklOcVQ — Nvidia security/networking DPU (interview, guest K. Deierling)
- 2021-11-16 4c_rKOaTquM — 5G + MEC edge latency test ★
- 2021-12-10 befUVytFC80 — create a Solana crypto token (2021 blockchain; era-specific) ★
Synthesis notes: (a) Python course extends (EP2, EP3) — update free-courses page. (b) The
Python EP3 "you don't need to be good at math" message reinforces his NO-EXCUSES ACCESSIBILITY
belief (anyone can learn). (c) DATE-SENSITIVE: 2021 crypto/blockchain content (Solana token) —
mark era-specific; his content follows tech trends (crypto 2021, AI 2023+). (d) Homelab grows
(new ESXi server). (e) Some sponsored/interview content (Nvidia w/ guest Kevin Deierling; 5G/MEC)
— attributed to guests/marked sponsored. No inline persona edits. Debt now 7.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2021-12→2022-02 P2, 7 ingested / 1 rate-limited
8 P2. 7 ok, 0 skipped, 1 x 429.
- 2021-12-17 LfC6pv8VISk — Linux for Hackers EP7 (processes) ★
- 2021-12-22 rHCwI4K7afY — NFTs for Christmas (2021 NFT era) ★
- 2022-01-20 0scjy6Zxzwc — 24/7 study-with-me livestream (community) ★
- 2022-01-26 El19X-zHt-c — bandwidth mining (2022; decentralization values) ★
- 2022-01-28 UiO6uFHqwbU — hired my replacement (NetworkChuck → team/business, 2022) ★
- 2022-02-07 5-5Mf_L0UKw — Python EP4 (if/else) ★
- 2022-02-09 HSRghjwTTOQ — Linux for Hackers EP8 (web/curl/wget) ★
Synthesis notes: (a) BIO/BUSINESS: ~2022 NetworkChuck SCALES INTO A TEAM/BUSINESS (hiring
help/other creators) — the channel is no longer just Chuck; add to biography + creator-coffee-
business (business evolution). (b) COMMUNITY: launched a 24/7 "study-with-me" livestream —
community/study-help ethos (pairs with Twitch study streams). (c) VALUES: the bandwidth-mining
video surfaces DECENTRALIZATION / "did it for the tech not the money" values — a beliefs/voice
datapoint. (d) Free courses advance: Linux for Hackers EP7/EP8, Python EP4 — update free-courses
page. (e) DATE-SENSITIVE 2021-22 crypto/NFT content — mark era-specific. No inline persona edits.
Debt now 8 (checkpoint at 10 — ~2 batches out).

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2022-02→2022-04 P2, 7 ingested / 1 rate-limited
8 P2. 7 ok, 0 skipped, 1 x 429. CROSSED 250 L2.
- 2022-02-17 Ec9WQGw4lW0 — Python nested if/elif
- 2022-02-25 W2tTsjkX76o — top 5 entry certs for money (2022 picks) ★
- 2022-03-04 27Wn921q_BQ — Kali GUI apps on Windows (WSLg)
- 2022-03-07 1KEN1P7qyLM — taught wife Linux in 24h (anyone-can-learn) ★
- 2022-03-12 nD1REhS6e3Y — Python logical operators
- 2022-03-23 2MS5wnYnxPc — $10k PC challenge (entertainment style; editor Austin) ★
- 2022-04-12 7qd5sqazD7k — Bash scripting will change your life
Synthesis notes: (a) DATED CERT PICKS: his 2022 top-5 entry-level certs = A+, Security+, CCNA,
AWS Cloud Practitioner, PenTest+ — a concrete dated recommendation for certifications-career. (b)
"ANYONE CAN LEARN": he teaches his WIFE Linux in 24h to prove anyone can learn tech — strongly
reinforces the accessibility/anyone-can-do-it ethos (wife = context, self-reported). (c)
CONTENT-STYLE + TEAM: the $10k PC challenge shows the ENTERTAINMENT/CHALLENGE content style
(~2022, MrBeast-influenced) and names a TEAM MEMBER, video editor AUSTIN (context) — pairs with
the "hired my replacement" team-growth note; consider an austin/team note at synthesis. (d) Python
+ Bash courses continue. No inline persona edits. Debt now 9. >>> CHECKPOINT next batch → Stage S (pass 4).

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2022-04→2022-05 P2, 7 ingested / 1 rate-limited
8 P2. 7 ok, 0 skipped, 1 x 429. Mostly course content (Python + Bash + subnetting).
- 2022-04-15 1KLgcBcWCsE — Python lists (intro)
- 2022-04-18 8bhvn9tQk8o — private IP addresses / NAT (subnetting)
- 2022-04-29 rW5sCgSSpI8 — Python list add
- 2022-05-06 19nN9vgcgmU — Bash script "millionaire" (automation project)
- 2022-05-09 jdTwCSxNINA — Python EP9 (list deletion) ★
- 2022-05-13 Fq6gqi9Ubog — Bash script "kill you" (automation project)
- 2022-05-23 2-i5x8KCfII — You SUCK at Subnetting (VLSM practice) ★
Synthesis notes: Course-heavy batch — Python course fills out (lists, EP9), Bash scripting
series, and the "You SUCK at Subnetting" series continues. Update the free-courses page episode
lists (Python + Subnetting). Little new persona material this batch (steady teaching content).
No inline persona edits. Debt now 10. >>> SYNTHESIS CHECKPOINT DUE next iteration → Stage S (pass 4).

## [2026-07-22] lint | synthesis pass 4 — P2 long tail (batches 29–38, 2018-2022)
Fourth synthesis pass. Drained the 10-batch debt (~66 new L2 from the 2018-2022 P2 tail);
recompiled clone to v4. One agent per file.
PROMOTED:
- SEEDED persona/appearance.md (the last empty persona file): signature full beard (running
  "not real" joke), ever-present coffee mug/ritual, casual high-energy presenter in a homelab/
  RGB home-studio. ALL 5 persona files now populated.
- persona/biography.md +6 dated entries: completed CCNP (passed TSHOOT Feb 2019, failed-first);
  PURSUED the CCIE written 2019 (⚠️ not passed/held — uncertainty note strengthened); went
  FULL-TIME YouTube ~Jul 2020; NetworkChuck scales into a TEAM/BUSINESS ~2022; hybrid-cloud
  business infra; father Chuck Keith Sr (IT infra engineer) linked. (Linux+ 2020 already present.)
- persona/beliefs.md +6: anyone-can-learn (taught wife Linux in 24h), radical authenticity/
  normalize-failure, "just DO it", decentralization/own-your-data, 2022 top-5 entry certs
  (A+/Sec+/CCNA/AWS-CP/PenTest+), security-is-offense-AND-defense.
- persona/voice.md +4: warm community-gratitude tone, radical-authenticity register,
  ~2022 entertainment/challenge (MrBeast-style) energy, phone-hating-introvert quirk.
- free-courses.md — updated episode lists (Linux for Hackers EP3-8, Python EP2-4/EP9 + lessons,
  Security+ EP0+EP5 [gap filled], Subnetting VLSM, Bash extras).
- NEW entity chuck-keith-sr (father, IT infra engineer).
- persona/system-prompt.md — recompiled v4 (~890 words, compiled_from_sources ~257).
State: high-water mark advanced to batches 1–38; checkpoint 4 → Done. ALL persona files
populated; all 8 topic hubs populated.
Synthesis notes: none (this IS the pass; debt drained). DEFERRED: a possible "austin/team" note
(editor mentioned); minor collab entities still not pages (Jason Gooley, Susie Wee, Kevin
Wallace, etc.). Remaining open ingest: main P2 (~95) + P3 + v2 P2/P3 + 153 shorts.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2022-06→2022-08 P2, 7 ingested / 1 rate-limited
8 P2. 7 ok, 0 skipped, 1 x 429.
- 2022-06-01 3ytqP1QvhUc — Follina zero-day (CVE-2022-30190; topical) ★
- 2022-06-29 ugt3PBeqHIo — killed my Linux computer (learn-by-breaking) ★
- 2022-07-01 ifT6npY39Dw — private search engine (SearXNG; own-your-data) ★
- 2022-07-19 oZGZRtaGyG8 — what is a subnet mask
- 2022-08-10 NeIrWXIj1m4 — 30 Day Cert Challenge (community/accountability) ★
- 2022-08-24 nW9M0MQinfg — Bash pushup counter (fun project)
- 2022-08-29 5aYpkLfkgRE — Flask meme website (Python web dev)
Synthesis notes: (a) TEACHING STYLE: "learn by BREAKING then fixing" (intentionally kills a
Linux box to teach recovery) — a signature pedagogy datapoint (pairs with analogy-teaching +
build-a-lab). (b) OWN-YOUR-DATA: self-hosted private search engine (SearXNG, ditch Google) —
reinforces the decentralization/privacy belief. (c) COMMUNITY/ACCOUNTABILITY: the "30 Day Cert
Challenge" is another community-accountability format (pairs w/ 24-7 study stream). (d) Topical
security (Follina 2022 zero-day) shows he covers current threats. (e) Python extends into web
(Flask). Mostly reinforces existing persona threads. No inline persona edits. Debt now 1.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2022-09→2022-12 P2, 7 ingested / 1 rate-limited
8 P2. 7 ok, 0 skipped, 1 x 429.
- 2022-09-09 mJ_5qeqGOaI — You SUCK at Subnetting EP6 (home network) ★
- 2022-10-07 ZSADD1nYD5Y — the challenge is over (30-day wrap; community) ★
- 2022-11-01 6rpTjEpvUtc — automated homelab+cloud with Ansible (IaC)
- 2022-11-07 B2V_8M9cjYw — block all ads (DNS sinkhole; AdGuard/Pi-hole) ★
- 2022-11-14 GH6O3oBZLK8 — subdomain takeover (dangling DNS; bug bounty)
- 2022-11-21 qOrlYzqXPa8 — 50 macOS terminal tips (reference) ★
- 2022-12-07 DbF96IHOZig — monitor your stuff (self-hosted monitoring)
Synthesis notes: (a) COMMAND-REFERENCE genre extends to macOS (50 tips) — note he uses/covers
macOS too (not just Linux/Windows); add to the reference-trilogy→now-quartet. (b) Ansible/IaC
homelab+cloud automation reinforces the automation thread. (c) Ad-blocking (DNS sinkhole) +
private search + monitoring continue the self-hosting/own-your-data body. (d) 30-Day Cert
Challenge WRAP reinforces community-celebration ethos (already in voice). (e) Subnetting EP6.
Mostly reinforces existing threads. No inline persona edits. Debt now 2.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2022-12→2023-03 P2, 7 ingested / 1 rate-limited
8 P2. 7 ok, 0 skipped, 1 x 429. BIO-RICH.
- 2022-12-14 ey4u7OUAF3c — expose home network safely (Cloudflare Tunnel)
- 2022-12-23 1ZfO149BJvg — learn VS Code RIGHT NOW ★
- 2023-01-11 WRe46LISkTw — FIRST ChatGPT video (gen-AI era begins) ★
- 2023-01-13 KA_KPmTxPSg — i almost quit youtube (burnout/authenticity) ★
- 2023-01-26 InnFUrE73tU — best PC I've built
- 2023-02-23 fR_D_KIAYrE — Python tuples
- 2023-03-04 NDlQrK_QAzY — Cloud Browser OFFICIAL LAUNCH (Mar 2023; Kasm; $7/mo) ★
Synthesis notes: THREE big ones. (a) AI-ERA START, dated: "ChatGPT will make you better" (Jan
2023) is his FIRST ChatGPT/gen-AI video — the ChatGPT-specific pivot (pairs w/ the Mar-2023 ML
video; predates it in the ai-tools arc). Stance: AI as a productivity multiplier, "use it to
get better" (not replace you). Add to ai-tools hub + biography AI-era. (b) BIO/AUTHENTICITY:
"i almost quit YouTube" (Jan 2023) — candid burnout/almost-quit reflection; a strong
authenticity + mission-perseverance datapoint for biography + voice (he's open about the hard
parts). (c) PRODUCT DATE CONFIRMED: the "most secure browser" video is the OFFICIAL LAUNCH of
the NetworkChuck CLOUD BROWSER (Mar 2023, Kasm-based disposable browser, ~$7/mo) — he names it
as his product. This DATES the Cloud Browser launch (dossier said ~2023 → now Mar 2023) and
closes the loop with the 2022-01 Kasm precursor. Update biography + the cloud-browser entity.
No inline persona edits. Debt now 3.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2023-03→2023-07 P2, 7 ingested / 1 rate-limited
8 P2. 7 ok, 0 skipped, 1 x 429.
- 2023-03-29 799uhYUxtvA — build your own secure browser (DIY Kasm / Cloud Browser) ★
- 2023-03-30 Kq0BMVhbFkA — host your own helpdesk (ticketing)
- 2023-03-31 jAfQvMxcokI — password security (self-hosted Passbolt)
- 2023-04-28 IYmXPF3XUwo — the END of VPNs (ZTNA/zero-trust; 2023 take) ★
- 2023-05-05 pQrM5L6C-FQ — CPU/GPU/DPU explainer (SmartNIC offload) ★
- 2023-05-19 B1vqKQIPxr0 — subnetting my coffee shop ★
- 2023-07-19 3CaG2GI1kn0 — free cybersec tool: Wazuh SIEM
Synthesis notes: (a) BIO — PHYSICAL COFFEE SHOPS: "subnetting my coffee shop" confirms he is
LAUNCHING PHYSICAL NetworkChuck Coffee SHOP(S) (2023) — an expansion of NetworkChuck Coffee
beyond online sales into brick-and-mortar retail; add to biography + the networkchuck-coffee
entity. (b) Cloud Browser follow-up: a DIY "build your own Kasm secure browser" (2023-03), right
after the Cloud Browser launch — reinforces the product/Kasm thread. (c) DATED OPINION: "the END
of VPNs" (ZTNA/zero-trust replaces VPNs, 2023) — a dated networking-future take (flag for the
evolving-position trail). (d) Self-hosting continues (helpdesk, Passbolt password manager, Wazuh
SIEM) — own-your-data + security-tools body. No inline persona edits. Debt now 4.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 8) — 2023-07→2023-10 P2, 7 ingested / 1 rate-limited
8 P2. 7 ok, 0 skipped, 1 x 429.
- 2023-07-21 6zopTcQFhqM — subnetting in reverse
- 2023-08-15 Y_coOg6oHAc — top 10 IT jobs 2023 (dated) ★
- 2023-08-23 OD2vG5st4zI — You SUCK at Subnetting EP9 (SERIES FINALE) ★
- 2023-08-30 poDIT2ruQ9M — ntfy self-hosted push notifications
- 2023-09-07 SWyXQfiN_Vo — biggest server project (45Drives) ★
- 2023-10-02 083-46NVMd8 — secret server room project (personal on-prem infra; bio) ★
- 2023-10-30 tBnJRraXDc0 — run a Tor relay (internet-freedom/privacy values) ★
Synthesis notes: (a) "You SUCK at Subnetting" SERIES CONCLUDES at EP9 (final test) — mark the
course complete on the free-courses page. (b) BIO/INFRA: he builds a large-scale personal SERVER
ROOM / on-prem infra (45Drives storage, "secret server room") — documents his serious homelab→
data-center-scale infrastructure (add to biography + homelab hub). (c) VALUES: "the Dark Web
NEEDS You" = run a Tor RELAY to support internet freedom/privacy — reinforces the privacy/
decentralization values (add cited evidence to beliefs). (d) Dated career list (top 10 IT jobs
2023). Mostly reinforces threads. No inline persona edits. Debt now 5.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 44) — L2 292→299
@NetworkChuck P2, 2023-11 → 2024-05: 7 ingested / 1 rate-limited (deferred). Pages: Put your website on the Dark Web (Tor .onion hidden service), Google is forcing you to use their proxy (self-host your own — own-your-data ★), the most secure OS in the world (Qubes OS — assume-breach isolation model, rejects it for daily use ★), AI Networking is CRAZY (InfiniBand/RoCE GPU-cluster fabrics — networking-meets-AI ★), you STILL need a website (2024 portfolio-site career update), White House says NO DEGREE (2024 US cyber-workforce skills-based hiring — validates his certs>degree thesis ★), monitor all your stuff (infra monitoring via WhatsUp Gold, homelab-as-resume ★). 5 ★ L3-candidates.
Synthesis notes: NEW for next checkpoint — (1) White House 2024 skills-based-hiring news externally VALIDATES his long-standing "you don't need a degree, certs+skills win" belief → date this corroboration in beliefs.md; (2) Qubes OS take = explicit security-vs-usability philosophy (respects assume-breach/compartmentalization but rejects Qubes daily-driver for manual per-task VMs) → beliefs/cybersecurity hub; (3) AI-networking (InfiniBand/RoCE for GPU clusters) extends the networking hub into the AI-datacenter era → networking + ai-tools cross-link; (4) own-your-data reinforced (self-host proxy vs Google) — consistent with existing decentralization/privacy beliefs, likely a repeat.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 45) — L2 299→306
@NetworkChuck P2, 2024-05 → 2024-08: 7 ingested / 1 rate-limited (deferred). Pages: I use this everyday (xclip + pbcopy/pbpaste aliases feeding fabric), You've been using AI Wrong (Fabric system-prompt patterns + augment-not-replace mental model ★), Your Cable Management SUCKS (personal server-room: 80G MikroTik QSFP+ bond, 45Drives NAS, "Terry" dual-GPU server ★), Linux on Windows/Windows on Linux (WSL2 + Kali Win-KeX + VMs), I forced EVERYONE to use Linux (ThinLinc/Ubuntu 20.04 terminal server, pro-desktop-Linux stance ★), Using AI to become a Hacker (AI copilot: Notion AI/ChatGPT/Claude, HTB CPTS ★), What is DNS? (canonical explainer + teaching analogies ★). 5 ★ L3-candidates.
Synthesis notes: NEW for next checkpoint — (1) Fabric (Daniel Miessler) + "augment don't replace / don't take the weights out of the gym" = his articulated how-to-use-AI-well mental model → voice.md + ai-tools hub; (2) richer personal-infra spec (dual-rack, 80Gbps MikroTik bond, 45Drives, named GPU box "Terry") → homelab hub + appearance/biography studio detail; (3) pro-desktop-Linux advocacy WITH honest friction (forced team onto ThinLinc Linux) → beliefs.md (Linux-for-everyone) + linux hub; (4) AI-as-hacking-copilot extends the AI+cybersecurity crossover already in the ai-tools hub; (5) DNS teaching analogies (phone contacts / mafia bosses / HTTPS costume / Where's Waldo) = voice-training data → voice.md analogy pattern.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 46) — L2 306→313
@NetworkChuck P2, 2024-09 → 2024-12: 7 ingested / 1 rate-limited (deferred). Pages: never leave the terminal (links text browser, terminal-first philosophy ★), I built 24 Websites in 24 Hours (Hostinger + Claude/ChatGPT AI-first build ★), Hide your files like a hacker (5 methods: hidden attr, ext-rename, NTFS ADS, VeraCrypt, Steghide), my local AI Voice Assistant (HA + Ollama Llama3.2 + Whisper/Piper/Wyoming, replaces Alexa ★), Cloning my Voice Into an AI Assistant (Piper TTS + keep-it-local ethics ★), I started a blog in 2024 (Obsidian->Hugo->GitHub->Hostinger, own-your-platform ★), I built a phone system (self-hosted 3CX on Proxmox, Cisco voice-roots callback ★). 6 ★ L3-candidates.
Synthesis notes: NEW for next checkpoint — (1) terminal-first "I'm already there, why leave" philosophy → voice.md; (2) "build because it's fun / creating surfaces inspiration" + AI-first prompt->paste->deploy workflow → beliefs.md + creator hub; (3) self-hosted-AI thread deepens: fully-local private voice assistant replacing Alexa (own-your-data applied to smart-home) → ai-tools hub + homelab; (4) voice-cloning ETHICS stance (only clone with permission, keep it local, "not legal advice") → beliefs.md (AI ethics) — first explicit AI-ethics-of-cloning take in corpus; (5) own-your-platform + learn-in-public reinforced via blogging (Hugo stack) → beliefs/creator hub; (6) self-hosted 3CX phone system explicitly ties back to his Cisco Voice/Collaboration engineering roots → biography (voice-engineer origin) + homelab. Personal-infra named box "Terry" (GPU/AI server) recurs across multiple 2024 videos → homelab hub canonical-infra entry.

## [2026-07-22] ingest | yt batch (@NetworkChuck, 47) — L2 313→320
@NetworkChuck P2, 2024-12 → 2025-03: 7 ingested / 1 rate-limited (deferred). Pages: create your own Solana Token in the terminal (crypto-as-experiment/not-financial-advice ★), Access ANY Network remotely (Twingate ZTNA "not VPN" ★), the hacker's roadmap 2025 (updated cert/skill sequencing, John Hammond guest ★), the ONLY way to run Deepseek (local via Ollama/LM Studio for data-sovereignty ★), Deep Research but Open Source (Firecrawl+o3-mini self-hosted agent ★), ChatGPT Operator alternative (Browser Use OSS browser agent), I'm changing how I use AI (Open WebUI + LiteLLM router — his current AI workflow ★). 6 ★ L3-candidates.
Synthesis notes: NEW for next checkpoint — (1) 2025 hacker/IT ROADMAP EVOLVES cert sequencing: "Phase Zero" apply-before-you're-ready, Linux+Python woven through every phase, hacking ladder eJPT/PenTest+ -> HTB CPTS -> OSCP (OSCP now allows ChatGPT in-exam) — UPDATE beliefs.md cert-sequencing timeline (2019 -> 2022 -> 2025) and flag as latest position; John Hammond guest segment attributed separately (not subject beliefs). (2) Twingate ZTNA "not a VPN" advances the end-of-traditional-VPN take already noted -> networking + cybersecurity hubs, date it 2024-12. (3) Self-hosted/open-source AI thread now DOMINANT across 2025: local DeepSeek (data sovereignty vs China servers), OSS Deep Research, OSS Operator alt, and his CURRENT unified workflow Open WebUI + LiteLLM + Ollama (one-interface/control/own-your-data, explicitly NOT about saving money) -> ai-tools hub canonical "current AI stack" entry + beliefs (own-your-AI). (4) crypto-as-experiment/not-financial-advice framing = a stance worth a beliefs note (tech-curiosity, not investment advice).

## [2026-07-22] ingest | yt batch (@NetworkChuck, 48) — L2 320→327
@NetworkChuck P2, 2025-04 → 2025-06: 7 ingested / 1 rate-limited (deferred). Pages: everyone is putting AI in schools (pro-but-cautious AI-in-education stance ★), Why LLMs get dumb (canonical context-window/ai-literacy explainer ★), Saying Goodbye (LANDMARK memorial for pug Moses — deep biographical reflection ★), 37 INSANE Linux Commands 2025 (modern-CLI roundup), I'm worried about Network Engineers (future-of-network-engineering: adapt to AI ★), I went to the LARGEST networking event (Cisco Live 2025 San Diego vlog ★), got AI anxiety? Do this RIGHT NOW (AI-anxiety reframe/mindset ★). 6 ★ L3-candidates. **Synthesis debt now 10 → checkpoint due: next iteration runs Stage S synthesis pass 5.**
Synthesis notes: NEW for next checkpoint — (1) LANDMARK BIO from the Moses memorial (all SELF-REPORTED, kids unnamed): married 2009; got pug Moses in Galveston TX while driving to honeymoon cruise; sold everything for a ~3-month digital-nomad stint in Paris (pre-fame, Moses stayed with his brother); "let's just go" family ethos (tattooed); COVID -> put down roots, quit job for full-time YouTube; describes himself as "a dude with six kids"; homeschools his kids; core value = time is the only non-renewable resource, be intentional / steer don't drift; adopted new pug Mochi -> UPDATE biography.md (dated, self-reported) + appearance (tattoo) + beliefs (intentionality/anti-overwork). This corroborates SUBJECT.md's "count unstable" note with a primary self-report (six kids, 2025-04) — still self-reported, keep unnamed. (2) MAJOR 2025 BELIEF CLUSTER on AI + the future of IT work: "I'm worried about Network Engineers" (adapt or 'someone using AI will replace you'; keep fundamentals) + "got AI anxiety" (jobs change not vanish; know yourself/Telos; wield-not-fear AI) + "AI in schools" (pro-but-cautious; Socratic learning mode; illusory-knowledge caveat) -> beliefs.md AI-and-careers section, dated 2025, cross-linked to ai-tools + certifications-career hubs. (3) canonical context-window explainer = ai-literacy teaching + analogy -> ai-tools hub + voice. (4) Cisco Live 2025 = in-person-community/career value + pivot back to networking content; candidate entities: Chuck Robbins (Cisco CEO), Susie Wee, John Morgridge, Rachel (defer unless recur). (5) 37 Linux commands -> linux hub modern-CLI list (likely repeat-ish).

## [2026-07-23] lint | synthesis pass 5 — batches 39–48 promoted, system-prompt v5
Drained synthesis debt (10 → 0). Checkpoint 5: promoted the genuinely-new batch 39–48 material (2024-05→2025-06 recent era + landmark Moses biography + the 2025 AI-and-careers belief cluster) into topics + persona; 13 files edited by 12 single-file promotion agents + 1 recompile agent (concurrency-safe, one writer per file). High-water mark advanced to batches 1–48 / 327 L2 pages.
- biography.md: Moses-memorial landmark (self-reported, kids unnamed) — married 2009, got pug Moses in Galveston, ~3-month pre-fame Paris digital-nomad stint, "let's just go" ethos, COVID→roots (house/full-time YouTube/church), "a dude with six kids"/homeschool [⚠️ CONTRADICTION note on unstable child count], intentionality reflection, new pug Mochi; + Jan-2023 AI pivot; + physical NetworkChuck Coffee shop(s) ~2023 (cited 2023-05-19-yt-B1vqKQIPxr0); + Dec-2024 self-hosted 3CX (Cisco voice roots); + Cisco Live 2025.
- beliefs.md: +12 dated/cited entries. Cert-sequencing EVOLVED to 2025 roadmap (Phase Zero apply-early, Linux+Python throughout, eJPT/PenTest+→HTB CPTS→OSCP) with ⚠️ POSITION EVOLVED callout superseding 2017/2019/2022. New: AI-and-careers cluster (adapt-or-be-replaced, AI-anxiety reframe, AI-in-education), augment-don't-replace, own-your-AI (Open WebUI+LiteLLM+Ollama/local DeepSeek), voice-cloning ethics, pro-desktop-Linux, own-your-platform, build-for-fun, intentionality, crypto-as-experiment, White-House no-degree corroboration, Qubes verdict.
- voice.md: +learn-by-breaking teaching mantra, analogy bank (DNS: phone contacts/mafia/costume/Where's-Waldo; context-window), terminal-first register. appearance.md: +"let's just go" tattoo + personal server-room backdrop ("Terry", racks, 45Drives, Govee).
- Hubs extended: ai-tools (12 pages, current AI stack + AI-literacy + AI-networking subsections), certifications-career (2025 roadmap + AI-era outlook), networking (DNS/AI-fabrics/ZTNA/Cisco-Live), homelab (server-room/3CX/voice-assistant), linux-terminal (6), cybersecurity (6), creator-coffee-business (coffee shops/blog/intentionality); networkchuck-coffee entity (physical shops ~2023).
- system-prompt.md recompiled v4→v5 (compiled_from ~327): current cert roadmap, AI-and-careers stance, own-your-AI throughline, refreshed voice/appearance/personal grounding; CCIE guardrail preserved.
- FIDELITY: guest material excluded (John Hammond roadmap segment; Miessler "weights out of the gym" quote → guest, not Chuck); family/faith self-reported + kids unnamed.
Synthesis notes: none (this IS the pass; debt drained to 0). DEFERRED entities (create if they recur): Chuck Robbins (Cisco CEO), Susie Wee, John Morgridge, austin (editor), Jason Gooley, Kevin Wallace, Kris Bryant.

## [2026-07-23] ingest | yt batch (@NetworkChuck, 49) — L2 327→334
@NetworkChuck P2, 2025-07 → 2025-11 (post-synthesis-5 recent era): 7 ingested / 1 skipped (no-captions) / 0 rate-limited. Pages: I'm done with the AI hype (pro-AI but anti bolt-on hype; value=data/context; AI-native>bolt-on; balanced ★), THIS Is Where the Internet Lives (Equinix Dallas datacenter tour — cross-connects/carrier-neutral/Fabric/Groq LPU ★), This AI Supercomputer fits on your desk (NVIDIA DGX Spark GB10, 128GB unified, local models ★), DEFCON is Not What I Expected (first DEF CON; hacker-community value ★), The Dark Web EXPOSED (Robin OSS AI dark-web OSINT tool ★), You SUCK at Prompting AI (2025 prompting framework: prompt=program, personas, CoT/ToT ★), Hackers infected the wrong girlfriend (Bitdefender Draco team: GandCrab/REvil takedowns + AI-scam arms race ★). 7 ★ L3-candidates.
SKIPPED: yt-7FERCp7AtXg "i'm feeling stupid today" (2020-06-17) — captions unusably garbled (music/lyric mis-transcription + non-English fragments); stub+transcript removed, ledger=skipped, re-ingest if clean transcript found. (An impostor-syndrome/mindset video worth recovering later.)
Synthesis notes: NEW for next checkpoint (debt now 1) — (1) "I'm done with the AI hype" NUANCES his AI stance: pro-AI but skeptical of bolt-on "AI sticker" marketing; value comes from data/context; AI-native ML > bolt-on LLM; "grain of salt" balance -> beliefs.md (matures the AI enthusiasm with discernment; pairs with AI-anxiety reframe). (2) 2025 PROMPTING FRAMEWORK (prompt=program/prediction-engine, personas, context+permission-to-fail, CoT/ToT/adversarial, "think first prompt second") -> ai-tools hub + voice (ai-literacy; pairs with 2024 "using AI Wrong"). (3) DEF CON 2025 = hacker-community/culture value -> pairs with Cisco Live for an "in-person community matters" belief; MANY candidate entities (Gerald Combs/Wireshark, Chris Greer). (4) Equinix datacenter tour = canonical "physical internet"/interconnection teaching -> networking hub. (5) DGX Spark = local-AI-at-scale hardware milestone -> ai-tools/homelab (continues own-your-AI). (6) Bitdefender Draco story = real-world ransomware-takedown + AI-scam arms race -> cybersecurity hub (threat-intel/incident genre). Deferred entities if they recur: Gerald Combs, Chris Greer, Sal Gonzalez (Equinix).

## [2026-07-23] ingest | yt batch (@NetworkChuck, 50) — L2 334→342
@NetworkChuck P2, 2025-12 → 2026-02 (bleeding edge): 8 ingested / 0 skipped / 0 rate-limited. Pages: I'll never use n8n the same (n8n orchestrating Claude Code headless via SSH ★), stop trusting cloud cameras (self-hosted Frigate NVR vs cloud; own-your-data ★), Ethernet is DEAD?? (4x Mac Studio ExoLabs/MLX cluster, RDMA over Thunderbolt 5 ~100x; clickbait clarified ★), FREE Phone Calls with Claude Code (Claude Code as phone extension via 3CX/Whisper/ElevenLabs ★), Claude Code on your phone in 10 min (SSH to hardened VPS + tmux; canonical method ★), I Tried running in 3D printed shoes (personal/maker — Bambu H2D, running hobby, pug Mochi, closing prayer), become an AI HACKER (AI-security career: Gandalf/Lakera/CTFs; GUEST Jason Haddix split-attributed ★), Claude Code on your Phone is OFFICIAL (Anthropic /remote-control ★). 7 ★ L3-candidates.
Synthesis notes: NEW for next checkpoint (debt now 2) — (1) CLAUDE-CODE / AGENTIC-CODING ERA becomes a distinct 2026 thread (4 videos): n8n+Claude Code headless, Claude Code as a phone extension, Claude Code from your phone (SSH/VPS), and Anthropic's official mobile remote-control — "agentic coding from anywhere" -> ai-tools hub new subsection + beliefs (AI-agents/automation frontier extends 2025 MCP/n8n arc). (2) own-your-data DEEPENS to physical security: self-hosted Frigate NVR replacing cloud cameras (local AI object detection) -> homelab + cybersecurity + own-your-data belief. (3) Thunderbolt-5 RDMA Mac-Studio AI cluster = networking-meets-AI hardware frontier; "Ethernet is dead" is deliberate hyperbole (Ethernet demoted to discovery, TB5 carries inference) -> networking + ai-tools; note his clickbait-with-real-nuance pattern. (4) AI-SECURITY-AS-CAREER: "become an AI hacker" (prompt injection, Lakera/Gandalf, AI bug bounties) with guest Jason Haddix -> ai-tools+cybersecurity+career (extends AI-and-careers cluster; only Chuck-attributed trains persona). (5) minor bio/appearance: 3D-printing/running hobby, pug Mochi confirmed, signature closing prayer (Christian, self-reported) -> appearance/voice (closing-prayer sign-off) if it recurs. Candidate entity if recurs: Jason Haddix (AppSec/AI-security expert).

## [2026-07-23] ingest | yt batch (@NetworkChuck, 51) — L2 342→350
@NetworkChuck P2, 2026-03 → 2026-07 (newest, up to 3 days ago): 8 ingested / 0 skipped / 1 rate-limited (1 P2 straggler remains). Pages: I almost quit YouTube (AI burnout, Japan sabbatical, "relentless optimism" ★), OpenClaw (OSS personal-AI-agent harness ★), i didn't want to like this (reluctant Perplexity Computer review, "sharpen the axe" ★), you need to use Hermes (Nous Research harness replaces OpenClaw ~7wk later — fast tool-churn), Switching back to Windows?!? (OpenAI-sponsored "considering", still Mac; NUANCES 2024 pro-Linux ★), I was wrong about VPNs (consumer-VPN reversal ★), Fable 5 (satirical Anthropic-model sketch, guest Miessler ★), FIFA World Cup broadcast network tour (SMPTE ST 2110/HBS/IBC ★). 7 ★. @NetworkChuck P2 now essentially drained (1 rate-limited straggler).
Synthesis notes: NEW for next checkpoint (debt now 3) — TWO EXPLICIT POSITION EVOLUTIONS to reconcile in beliefs.md with ⚠️ callouts: (1) "I was wrong about VPNs" (2026-06-15) — corrects his earlier "HTTPS makes consumer VPNs useless" line: personal/consumer VPNs DO have event-driven value (metadata/DNS/SNI leak-hiding, anti-harassment, geo); scope is NARROW (consumer VPNs only; his ZTNA/corporate-VPN "not a VPN" take is untouched) -> beliefs + networking/cybersecurity hubs. (2) "Switching back to Windows?!?" (2026-06-01) — does NOT reverse pro-desktop-Linux; it's an OpenAI-sponsored "considering Windows for AI tooling (Codex Windows-native)" while still daily-driving Mac; still skeptical of desktop-Linux-for-gaming migration -> nuance the 2024 pro-Linux belief (his OS stance is pragmatic/tool-driven, not tribal). (3) BIO/BELIEFS: "almost quit YouTube" (AI-era burnout, Japan sabbatical, dropped guru posture -> "learn alongside you", motto "relentless optimism", IT skills still matter to steer AI) -> biography (2026 near-quit) + beliefs (relentless optimism; humans guide AI when it fails; ties to AI-anxiety reframe). (4) AI-AGENT-HARNESS churn: OpenClaw -> Hermes -> (Claude Code for serious work) = his "personal AI agent" four-pillar model (model+channels+memory+host-tools); note the rapid tool-churn as a voice/behavior trait -> ai-tools hub. (5) FIFA broadcast-network + earlier Equinix = a real-world "enterprise/broadcast networking field trips" genre -> networking hub. (6) VOICE: signature closing PRAYER sign-off now confirmed across multiple 2026 videos (Christian, self-reported) -> voice.md sign-off pattern. Candidate entities if recur: Daniel Miessler (recurs: Fabric + Fable 5), Jason Haddix.

## [2026-07-23] ingest | yt batch (@networkchuck_v2, 52) — L2 350→358
@networkchuck_v2 P2 (interview-heavy), 2022-03 → 2025-09: 8 ingested / 0 skipped / 0 rate-limited. Pages: What does a threat analyst do (interview clip; guest=context), Cheating is okay (Chuck's learning-philosophy: no shame in looking at solutions ★), talking with HakLuke (interview, Luke Stephens/Hakrawler; guest=context ★), How to get a job in IT according to the experts (4 experts=context ★), How I Accidentally Created a Viral Meme Coin (refused rug-pull, told viewers not to buy ★), The Future of Networking Certifications (CCNA stays gold-standard, run-toward-AI; Cisco guests context ★), Network Engineer lets AI run his Network (interview, guest Allan; AIOps/Marvis ★), How Long Do Network Engineers Have Left (interview, guest John Capobianco ★). 6 ★. @networkchuck_v2 P2 now drained.
Synthesis notes: NEW for next checkpoint (debt now 4) — (1) CHUCK's LEARNING PHILOSOPHY "no shame in looking at solutions/walkthroughs while learning (for the sake of learning) — training wheels" (2022-04-04) -> beliefs.md (learning-by-any-means; pairs with learn-by-breaking + learn-in-public). (2) MEME-COIN ETHICS: his Dec-2024 Solana tutorial token got pumped ~$148K; he REFUSED to sell/rug-pull and told viewers not to buy -> reinforces crypto-as-experiment/not-financial-advice + an integrity data point -> beliefs (creator ethics). (3) FUTURE-OF-NETWORKING reinforced by TWO more interviews (guests, context-only for their theses; Chuck's reactions = persona): "future of networking certs" (Chuck: CCNA still the entry gold-standard, run-toward-AI, colleges can't keep up) and "how long do network engineers have" (Chuck's existential-crisis reaction + distrust of AI making config changes) -> strengthens the AI-and-careers + certs cluster; pairs w/ main-channel "I'm worried about Network Engineers". (4) AIOps: "let AI run your network" (Marvis/agentic net automation) -> networking + ai-tools (Chuck cautious on trusting AI with live config changes — consistent trait). NOTE: v2 is interview-heavy — disciplined per-speaker attribution applied; guest theses NOT promoted to persona. Candidate entities if they recur: HakLuke/Luke Stephens, John Capobianco (network-automation evangelist), Kareem Escander + Joe Clark (Cisco). Deferred — do not create yet.
