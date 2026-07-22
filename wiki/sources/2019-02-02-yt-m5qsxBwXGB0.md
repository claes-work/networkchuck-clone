---
type: youtube-video
source_date: 2019-02-02
url: https://www.youtube.com/watch?v=m5qsxBwXGB0
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [certifications-career]
tags: [ccnp, tshoot, 300-135, milestone, passed, failed-first, bio]
---

# I PASSED THE TSHOOT EXAM!! - CCNP TSHOOT (I also failed)

## Summary

Chuck documents passing the CCNP TSHOOT exam (300-135) — the final exam of the CCNP
routing-and-switching track — which **completes his CCNP** (Feb 2019). He is candid
that he **failed his first attempt** before passing on the second, and opens the video
in his car after that failure. He dissects why he failed (hadn't studied routing and
switching seriously since 2016; only crammed ~4 days), walks through his exam-prep
tools (Boson NetSim, CBT Nuggets' Keith Barker TSHOOT Hands-On Labs course, and Boson's
ExamSim practice environment), demonstrates a live troubleshooting-ticket lab, and
closes with the second-attempt pass a week later. The video is sponsored by Boson.
Side news: he won the Cisco IT Blog Awards (best video/podcast), earning a free pass to
Cisco Live US in San Diego, and is now building a Microsoft Azure AZ-900 course for CBT
Nuggets.

## Key claims (paraphrase, dated)

- **[2019-02-02] MILESTONE — Passed CCNP TSHOOT (300-135), completing his CCNP.** TSHOOT
  was the final exam of his CCNP; passing it means he has now completed the CCNP
  certification.
- **[2019-02-02] Failed the first attempt before passing.** He openly states he failed
  his first TSHOOT attempt and that it "sucked"; it was not the first exam he had ever
  failed. He passed on his second attempt, exactly one week later.
- **[2019-02-02] Scores.** First (failed) attempt: 834 vs. a passing score of 846 —
  missed by 12 points. Second (passing) attempt: 916.
- **[2019-02-02] Why he failed (his own diagnosis).** He had not seriously studied
  routing and switching since 2016 (when he passed his ROUTE exam), and had not worked
  with it professionally for about a year (only tinkering in his lab). He set the CCNP
  challenge for himself in December, giving ~1.5 months, but was busy with Christmas /
  the giveaway and did not actually study until ~4 days before the exam, taking time off
  work to cram.
- **[2019-02-02] Tip — prep tools that carried him.** He credits Boson NetSim (Cisco IOS
  simulation, better than Packet Tracer, with lab grading) and CBT Nuggets' Keith Barker
  "CCNP TSHOOT Hands-On Labs" course (built in GNS3) for taking him from unprepared to
  nearly passing.
- **[2019-02-02] Tip — do the troubleshooting tickets, not just labs.** With limited
  time he went straight to Boson's troubleshooting tickets because they most closely
  mirror the exam; he felt he aced the ticket-style scenarios and lost points on tricky
  multiple-choice theory questions.
- **[2019-02-02] Tip — use exam-simulation software before your first attempt.** The
  single biggest difference for the second attempt was Boson's ExamSim, which reproduces
  the exam's clunky interface (no configuration-terminal mode, only show commands, no
  going back after clicking done). He wishes he'd used it before attempt one.
- **[2019-02-02] Troubleshooting methodology demonstrated.** On every ticket he first
  confirmed the PC had an IP (ipconfig / DHCP) and pinged the default gateway, then
  traced the path hop by hop (switch → VRRP routers → EIGRP/OSPF routers), checking
  routing tables (show ip route), neighbor relationships (show ip ospf neighbors), and
  running protocols (show ip protocols). The demo bug: OSPF authentication was
  configured on one router's interface but missing the `ip ospf authentication
  message-digest` command, so the neighborship never formed.
- **[2019-02-02] Coffee is "essential for networking"** — recurring persona motif,
  invoked while complaining the testing center gives you no water or coffee.
- **[2019-02-02] Career/side news.** Won the Cisco IT Blog Awards (best video/podcast) →
  free pass to Cisco Live US in San Diego; working on a Microsoft Azure AZ-900 beginner
  course for CBT Nuggets ("cloud is amazing"). He works for CBT Nuggets.

## Notable verbatim quotes

> "All right I failed, dude. That was a bear of a test — like, it was tough. And golly,
> it sucks."

> "Well, Chucky says you passed — well, I failed first, and it sucked, dude. It sucked.
> It's not the first time I failed an exam, but it never feels good. Like, you felt like
> you prepared, you felt strong, you studied, and then you just fall short. But I did
> pass — I did pass my second attempt."

> "The passing score was 846 and my score was 834. I missed it by 12 points, which can
> boil down to just like one question or one little thing you did wrong in the
> simulation."

> "I have not studied routing and switching for a very long time... I haven't really
> like dedicated study time for routing and switching since 2016 when I passed my ROUTE
> exam."

> "I did not study until like 4 days before the exam. I know, I know, really bad on me,
> but I had projects I had to complete, so I actually took time off of work to study for
> this."

> "I owe my success — well, the initial failure and then the success — to two things:
> first was Boson NetSim... and the second one was CBT Nuggets, Keith Barker's course."

> "You don't have water or coffee. Coffee is essential for networking, so why don't they
> include that?"

> "I used it before my second attempt, and that made all the stinking difference — and
> then I passed my TSHOOT. What a freaking load off."

> "All right guys, I passed. I freaking passed. I got a 916... I'm glad this is over.
> Freaking A, but I passed. Now I'm going to go to Fry's and buy me a toy to celebrate."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: COMPLETED CCNP (passed TSHOOT, Feb 2019); openly failed-before-passing (persistence/honesty) -->
