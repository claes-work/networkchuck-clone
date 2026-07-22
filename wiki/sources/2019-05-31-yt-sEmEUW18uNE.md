---
type: youtube-video
source_date: 2019-05-31
url: https://www.youtube.com/watch?v=sEmEUW18uNE
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [certifications-career]
tags: [it-career, school-district, network-engineer, interview, guest]
---

# Network Engineer for a School?? // Working in IT for a School District — CCENT/CCNA

## Summary

A long-format interview (Chuck's first "different type of video") in which Chuck sits
down with **Dallas** (surname unclear in the captions — rendered "Blonde"/"spline"), an
**infrastructure administrator at a Texas Panhandle education service provider (Region
16, Amarillo)** that acts as a managed service provider for ~50–60 area school
districts. Chuck's role is interviewer/framer; almost all career-history and
technical-environment detail comes from the guest and describes the guest's job, not
Chuck's.

Dallas walks through his career arc (grocery-store meat-market job → A+ self-study →
flash/PC-tech job → credit union → megachurch part-time IT → back to a credit union →
Region 16), then describes what IT for school districts actually looks like:
access-layer switching (2960-X, some layer-3 3560/3650), firewalls (moving from ASA
toward Firepower/FTD), heavy Wi-Fi (iPads, Chromebooks/Google), VoIP as a
life-safety-critical service, video/telepresence for remote classes, BGP peering with
AT&T and a Texas education ISP ("LEARN"), Nexus (93128) + ASR9k core with EIGRP-based
failover, content filtering, DDoS mitigation, and an emerging SD-WAN evaluation. They
close with Dallas's cert journey (CCNA R&S, CCDA, CCNA Collaboration, A+, Network+,
grinding on CCNP ROUTE after three fails) and a personal "speed round."

The recurring career theme both men share: be a broad generalist who "loves it all,"
stay humble, keep a hunger to learn, and don't do IT only for the money.

## Key claims (dated; attributed per speaker)

**Guest (Dallas) — career history / job description (context; NOT Chuck's bio):**
- [2019-05-31] Dallas's title is **infrastructure administrator**; he is a deliberate
  jack-of-all-trades touching routing/switching, security, data center (Nexus/ASR),
  and voice/collaboration, though dedicated security and VoIP admins now exist on the team.
- [2019-05-31] He got into IT via his father (a retired schoolteacher who worked in a
  church tech department and gave him an "A+ for Dummies" book and computer parts to
  build his own PC at age 11).
- [2019-05-31] Career path: quit a supermarket meat-market job (~age 19, ~2000) over a
  facial-hair rule → a "flash developer" listing that turned out to be a PC-tech job →
  credit union (entry-level troubleshooting) → part-time IT at an Amarillo megachurch
  (~7,000–8,000 attendees) with no health insurance, family on government healthcare →
  simultaneously held three jobs (~3 years) → full-time network/IT specialist at a
  credit union (where he got his CCNA via CBT Nuggets) → Region 16.
- [2019-05-31] He entered Region 16 as a **voice/unified-communications specialist**
  (~4 years) after a friend vacated the role, later adding network-specialist duties.
- [2019-05-31] Region 16 is effectively a not-for-profit managed service provider for
  school districts; management are ex-educators/coaches/principals; pricing is
  cost-plus-salary, so adding customers lowers everyone's per-handset price.

**Guest (Dallas) — school-district IT environment (context):**
- [2019-05-31] Typical district edge: 2960-X access switches (L2/L3), firewall on-site
  (project underway to backhaul firewall to the data center), L2 MPLS handoff from the
  provider, heavy Wi-Fi for iPads/Chromebooks.
- [2019-05-31] Security priorities: kids using VPNs to bypass web filters (IPS detects
  disguised HTTP), DDoS mitigation via a "black hole" subscription service, and rising
  concern over student-data protection. Web filter used: "Nessie/Lightspeed"-type
  (caption unclear).
- [2019-05-31] Core moved ASA→FTD/Firepower; Cisco reps signaled ASA code will
  eventually be deprecated; FTD gives more throughput-per-dollar past ~1 Gbps.
- [2019-05-31] VoIP is treated as life-safety-critical (9-1-1 from a cafeteria) — "just
  as important as having fire extinguishers." Video/telepresence enables remote classes
  (e.g., a Spanish class taught by one district to others).
- [2019-05-31] Summer is the busy season (big maintenance windows while school is out).

**Guest (Dallas) — certifications & study habits (context):**
- [2019-05-31] Holds CCNA R&S, CCDA, CCNA Collaboration, A+, Network+; working toward
  CCNP ROUTE (failed SWITCH once then passed; failed ROUTE three times).
- [2019-05-31] Pursues CCNP for confidence, not because the job requires it; studies
  ~from evening gym until 11:00–11:30pm, rests weekends to avoid burnout.
- [2019-05-31] Credits CBT Nuggets and Jeremy Cioara for getting him through his first
  voice years; also cites Kevin Wallace's QoS material and Rob Riker's advice.

**Chuck (SUBJECT) — framing, opinions, career preference (persona data):**
- [2019-05-31] Chuck strongly prefers being a broad generalist who "touches everything"
  over being siloed into one specialty; recounts a job where he was limited to voice +
  network only and "felt so handicapped, like someone cut off my hands."
- [2019-05-31] Chuck argues network engineering is a creative craft — "a million and
  one ways to do one thing" — and that this creativity is what people don't realize.
- [2019-05-31] Chuck frames programmability/automation (Python on Nexus) as an enhancer,
  not a replacement: it lets overloaded engineers deploy switches faster and do their
  real job, and knowing the underlying infrastructure makes you a better programmer.
- [2019-05-31] Chuck insists voice/telephony isn't going away despite cloud/hybrid
  pushes; on-prem voice still matters for emergency calling and reliability.
- [2019-05-31] Chuck endorses QoS learning as crucial even outside Cisco, and admits he
  is heavily Cisco-biased ("the most biased person you'll see... if I'm talking about a
  Cisco product it means I haven't looked at anything else").
- [2019-05-31] Chuck's own backstory references: inspired to start his channel by a
  mentor who replied to him on LinkedIn (name garbled in captions, `attribution: uncertain`);
  went from food stamps / government healthcare to joining CBT Nuggets ("I'm major league
  now, I'm in the NFL"); off-camera he is quiet and shy, distinct from "NetworkChuck mode."

## Notable verbatim quotes

**Chuck (SUBJECT — voice/persona data):**
> "that's what people don't realize is how creative you can be as a network engineer
> there's a million and one ways to do one thing and it's just so fun to come up with
> solution like that"

> "it's not gonna replace you it's not gonna ruin your network engineers lives it's
> gonna make it so much better because... we just can't do it all right now"

> "when I'm not like on network Chuck mode I'm a very quiet person like i i'm like you i
> like to absorb the information i don't want to talk"

> "if I'm talking about a Cisco product it means I haven't looked at anything else"

> "there are so many guys [who] have the ego who want to be the one with the idea and
> get credit for it but staying humble and just being that team player will take you
> really far"

**Guest (Dallas — CONTEXT, not persona/voice data):**
> "don't do this for the money and that's not just IT... if you're doing everything
> solely for the money you'll never be happy because money won't buy you happiness"
> (Dallas attributes the "fall in love with it" version of this to Jeremy Cioara)

> "go to your local church or... any type of organization that... works off of like
> those types of funds and ask them... if they need any volunteer IT help... that'll get
> your foot in the door"

> "for school districts that's absolutely important that's like just as important as
> having fire extinguishers"

> "[CCNP] gives me the confidence that hey I know how to do this stuff"

## Guest attribution

The interviewee is **Dallas** (surname garbled in the auto-captions as "Blonde" /
"spline" — `attribution: uncertain`), an **infrastructure administrator at Region 16**,
an education service provider / managed service provider for school districts in the
Texas Panhandle (Amarillo). **All of Dallas's career history, study routine,
certifications, and the school-district technical environment described above are the
GUEST's biography and workplace — they are NOT Chuck's** and must not flow into
`persona/` as subject facts. He is a **context person** (a community member / audience
member who had previously donated IT/phone equipment to Chuck's courses). Only Chuck's
interview framing, opinions, and self-references (the SUBJECT rows above) are persona
data. Other people named are all context: Jeremy Cioara, Kevin Wallace, Keith Barker,
Rob Riker (trainers Chuck/Dallas admire), and colleagues at Region 16 (Jeff Rogers —
video admin; David Calabrese — Canadian ISD; "Austin McDaniel" — Cisco engineer).

<!-- ★ L3-candidate: Chuck's explicit generalist-over-specialist career stance ("felt handicapped, like someone cut off my hands") + school-district / education-service-center IT as a distinct career niche — a certifications-career angle not yet in the persona. -->
