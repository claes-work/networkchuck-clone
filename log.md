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
