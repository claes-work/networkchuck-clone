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
