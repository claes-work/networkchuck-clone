---
type: youtube-video
source_date: 2021-11-16
url: https://www.youtube.com/watch?v=4c_rKOaTquM
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [networking, cloud-devops]
tags: [5g, mec, edge-computing, latency, aws-wavelength]
---

# putting 5G and MEC to the test!! (does it even matter??)

## Summary

A hands-on, sponsored explainer (thanks to Verizon) in which Chuck sets out to answer
whether 5G + MEC (Mobile Edge Computing) actually make a measurable difference or are
just marketing hype. He first teaches the underlying concepts from scratch — how the
internet works (phone → server → back), why physical distance to a server creates
**latency**, and why latency is the biggest factor in perceived internet performance.
He then walks up the ladder of solutions: the **cloud** (AWS) moves your content
closer; **CDNs** (content delivery networks) cache static content (images/video) even
closer; but CDNs can't help with **dynamic compute** like AI, which still lives far
away (e.g. Northern Virginia). **MEC / AWS Wavelength zones** (AWS partnering with
Verizon) solve this by placing compute at the edge of the mobile network, right next to
the user.

Chuck then runs a real-world test: he drives to Deep Ellum in downtown Dallas with a 5G
phone, his wife, and his Tesla, locks onto an ultra wideband 5G radio, and uses an AI
object-identification app. For each photo he compares a traditional-cloud round trip to
Virginia against an MEC (Wavelength) round trip. Across all samples MEC was consistently
faster (~2.0s cloud vs ~1.1–1.3s MEC). He concludes MEC does make a measurable
difference — milliseconds that don't matter to human perception but matter enormously
for real-time computer workloads (AI, AR/VR, autonomous vehicles).

The back half is an interview with Sebastian, co-founder/CTO of a company ("YBVR")
using 5G + MEC to deliver immersive 360° video of live sports and concerts, covering
their architecture, latency gains (40s → sub-0.7s), adaptive bitrate / foveated
streaming, on-edge video stitching, cost economics of pay-per-use edge compute, and the
future of VR live events. The guest's statements are attributed to the guest, not the
subject.

## Key claims (dated — concepts + findings)

- (2021-11-16) The internet works, simplified, as your phone reaching out to a server
  somewhere and asking for content, which the server sends back — but that server "could
  be anywhere in the world," which is a fundamental problem.
- (2021-11-16) **Latency** = the round-trip time for internet traffic to reach a server
  and come back; it is "the biggest factor when it comes to internet speed or
  performance." Chuck's rule: "If your latency sucks, your internet sucks."
- (2021-11-16) The cloud (e.g. AWS) reduces latency by letting content owners rent space
  on servers physically closer to users, instead of self-hosting far away.
- (2021-11-16) The internet was designed as a **best-effort service** — reliable
  connectivity but no performance guarantees.
- (2021-11-16) **CDNs (content delivery networks)** cache/serve content from servers very
  close to the user, but can only handle **static content** (images, video), not dynamic
  compute logic.
- (2021-11-16) Dynamic **compute** (e.g. an AI app identifying an object in a photo)
  can't be cached by a CDN, so it typically lives far away (Northern Virginia); the
  round-trip delay to it is what separates a real-time experience from a laggy one.
- (2021-11-16) **MEC (Mobile Edge Computing)** extends the cloud computing environment to
  the edge of the network to deliver lower latency — you move the latency-sensitive part
  of an app (the compute/AI) right next to the user.
- (2021-11-16) **AWS Wavelength zones** are AWS + Verizon placing servers at the edge of
  the 5G network ("in your backyard"); developers put the latency-sensitive part of their
  app there, and combined with 5G you get very fast upload/process/return.
- (2021-11-16, TEST RESULTS) Using an AI image-ID app, cloud (Virginia) vs MEC per photo:
  car 2.019s vs 1.314s; baby (person) 1.998s vs 1.251s; parking meter 2.014s vs 1.128s;
  Instagram/person 2.10s vs 1.262s; car-behind-Tesla 2.082s vs 1.156s; person/beard
  2.102s vs 1.291s. **Finding: MEC is consistently faster** — a difference of
  milliseconds that is negligible to human perception but "huge" for real-time computer
  workloads (AI, AR/VR, autonomous cars).
- (2021-11-16) Real-world use cases needing low latency: AI object recognition, augmented
  reality, autonomous vehicles (Chuck notes he "went low latency" on his Tesla for
  fast person-vs-trash identification), and immersive live-event 360° video.
- (2021-11-16, guest — Sebastian, YBVR) Their traditional centralized-AWS-region
  architecture had ~40 seconds of latency; a new low-latency architecture over 5G/MEC
  reached sub-0.7s (they aim for sub-second). Much of the gain comes from a different,
  more efficient architecture the new network enables, not just the network itself.
- (2021-11-16, guest) They use **foveated/filigree streaming** (only stream the part of
  the 360° sphere you're looking at) plus **ABR (adaptive bitrate)** to deliver the best
  quality for your view direction under any network condition, supporting zoom into 8K.
- (2021-11-16, guest) Moving video stitching and processing from on-site gaming PCs onto
  MEC simplifies deployments, is cheaper (pay only for compute used), and scales to more
  cameras/stadiums with as few as one on-site person.

## Notable verbatim quotes

> "So 5g and mech or mobile edge computing. I've been hearing a lot about this. I've
> talked about it, but what I'm curious about is does it actually work? Like, does it
> even matter?"

> "I'm more of a hands-on person. I have to actually test it out."

> "The time it takes for your internet traffic to get there and back it's called latency.
> And it is the biggest factor when it comes to internet speed or performance ... If your
> latency sucks, your internet sucks."

> "What is the cloud? Really? Honestly, it's just someone else's computer or someone
> else's server."

> "The internet was designed as a best effort service. Another way to put that is you get
> what you get and you don't get upset because that's how it's designed."

> "That is what we're doing with mobile edge computing. We're taking the compute, the
> part of the app that you need super fast access to. And we move it closer to you to the
> edge of the network."

> "AWS partnering with Verizon, put some of those servers super close to you. These are
> called wavelength zones and man they're right in your backyard."

> "So what this test does demonstrate is that yeah, MEC definitely makes a difference and
> sure, at the end of the day, we're talking milliseconds, which to ... humans and how we
> perceive time. It's like, that's not that big of a deal, but for computers who are
> processing crazy amounts of data ... that's a huge thing."

> "I'm tired of all the marketing speak. Let's get beyond that. Okay. Let's actually test
> it."

## Guest attribution

Not fully solo — the first half (concept explainer + Dallas MEC test) is Chuck Keith
(the SUBJECT). The second half is an interview with **Sebastian, co-founder/CTO of YBVR**
(immersive 360° live-event VR). All VR/architecture/company statements are attributable
to the **guest (Sebastian)** and must NOT flow into `persona/`. Only Chuck-attributed
statements (the concept teaching, the test framing/findings, and his interviewer
commentary) train the persona.

<!-- ★ L3-candidate: clean, canonical Chuck explainer of latency → cloud → CDN → MEC/edge with a self-run empirical test; strong voice quotes and a reusable networking/cloud teaching framework worth promoting to topics. -->
