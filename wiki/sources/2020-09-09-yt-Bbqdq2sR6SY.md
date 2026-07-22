---
type: youtube-video
source_date: 2020-09-09
url: https://www.youtube.com/watch?v=Bbqdq2sR6SY
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [networking]
tags: [5g, wireless, latency, edge-computing, cloud-gaming, 2020]
---

# 5G will change gaming FOREVER

## Summary

A Verizon-sponsored (2020) networking explainer in which Chuck Keith uses a road-trip
analogy to teach **latency** and argues that the combination of **5G** and **the cloud**
is what finally defeats it. Latency is framed as the "biggest problem with the internet
right now" — not raw speed. Chuck walks through why latency accumulates (physical
distance to the data center plus the cumulative delay of every router, switch, and
firewall hop, plus congestion/detours) and then presents two fixes stacking together:
(1) Verizon's 5G Ultra Wideband (millimeter-wave spectrum) shortens and virtualizes the
trip inside the carrier network, and (2) AWS Wavelength puts AWS cloud servers *inside*
Verizon's network at the edge, so traffic never has to cross the "big bad wild internet"
at all. He names the overall pattern **MEC — mobile edge computing** and stresses the
"edge = where you are" idea. Two guest case studies illustrate the payoff: ShotTracker
(real-time basketball sensor analytics) and an AI colon-cancer/polyp-detection trial.
Forward-looking 2020 predictions: autonomous cars advancing, and finally being able to
game online in VR — which he says latency currently makes impossible.

## Key claims (dated — 5G concepts + prediction)

_All paraphrase unless quoted. Dated 2020-09-09; sponsored by Verizon._

- Latency — how long it takes to reach a website/service — is the biggest current problem
  with the internet, distinct from bandwidth/speed. (2020)
- Websites live in physical data centers; the closer that data center is to you, the lower
  your latency; the farther, the higher. Distance is a primary but not the only factor. (2020)
- Latency also accumulates from every device on the path — routers, switches, firewalls —
  each adding a little delay, plus congestion and rerouting (road-trip analogy). (2020)
- Verizon's 5G Ultra Wideband uses the millimeter-wave spectrum and reduces latency by
  shortening the path and **virtualizing** the network equipment inside their network. (2020)
- 5G is ~10x faster than 4G LTE and lets you connect more devices to a network. (2020)
- Even with very fast internet, latency stays high if the destination is far or the path
  is congested — speed alone does not solve latency. (2020)
- AWS **Wavelength** places AWS cloud servers directly inside a network operator's data
  centers (e.g., Verizon), removing the need to traverse the public internet — this is a
  new infrastructure service, generally available as of **August 6, 2020**. (2020)
- The overall approach is called **MEC — mobile edge computing**; the "edge" is as close
  to the user as possible, making latency effectively a non-issue. (2020)
- At launch, Wavelength edge zones were available in **Boston** and the **Bay Area**, with
  more cities coming soon. (2020)
- Use case — ShotTracker: sensor-based basketball tech delivering real-time stats/analytics
  at sub-second latency; over 5G + Wavelength it tracks ball movement far better than 4G-to-
  distant-cloud, which is visibly slow/jittery. (2020, guest demo)
- Use case — healthcare: a Verizon/AWS trial uses 5G + edge + AI to draw real-time bounding
  boxes around polyps during a colonoscopy; if the system isn't fast enough it misses the
  polyp, so low latency is essential. (2020, guest demo)
- **Prediction (2020):** as Verizon expands 5G and AWS adds Wavelength zones, autonomous/
  driverless cars will get more advanced and online VR gaming — currently blocked largely by
  latency — will finally become possible.

## Notable verbatim quotes

> "why is it that sometimes your internet is slow even when it should be fast ... it's
> dragging why is it doing that one word ... latency"

> "latency is how long it takes you to access a website on the internet or anything really"

> "traveling across the internet going to your favorite website is often like taking a road
> trip"

> "each device each network adding just a little bit of time to your trip ... you know those
> bathroom breaks add up"

> "5g is also fast 10 times faster than 4g lte so let's trade in our rv for a rocket"

> "what verizon and aws are doing is called mec or mobile edge computing and i want you to
> focus on the edge computing part ... the edge is where you are as close to you as possible
> so we don't even have to think about latency it becomes a non-issue"

> "this is actually a new infrastructure service they're offering it's called aws wavelength
> and as of august 6 2020 it's available"

> "maybe we'll finally get to game online in vr because we can't right now latency is one of
> the biggest reasons we can't"

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

> ⚠️ Note: the video embeds two third-party guest testimonials — **Davion Ross**
> (co-founder/president, DD Sports / ShotTracker) and **Dr. Shannon Shull**
> (gastroenterologist, Raleigh, NC). Their quoted statements are NOT Chuck's and must not
> flow into `voice.md`/`beliefs.md` as the subject's own; they are context/demo attribution
> only.
