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
