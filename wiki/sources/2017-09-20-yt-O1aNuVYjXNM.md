---
type: youtube-video
source_date: 2017-09-20
url: https://www.youtube.com/watch?v=O1aNuVYjXNM
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [networking]
tags: [voice-vlan, vlan, voip, qos, cisco, ccna]
---

# Voice VLANs - What are they and why do we need them?

## Summary

An early NetworkChuck networking tutorial aimed at CCNA/CCNP/CCIE candidates (and IT newcomers) explaining the concept of the voice VLAN: what it is, why it is needed, and the puzzle of how a phone and a PC share one switch port. Chuck frames a voice VLAN as a boundary that separates voice (VoIP) traffic from data traffic so the voice traffic can be prioritized and secured. He gives three reasons voice VLANs matter: (1) security — on a shared VLAN a PC can sniff and reconstruct voice calls; (2) QoS — voice needs priority so packets are not dropped or delayed; (3) practicality — offices often have a single wall port, so the phone plugs into the wall and the PC plugs into the phone's built-in PC port. He teases the apparent paradox that this configured access port carries two VLANs yet Cisco insists it is not a trunk, promising a follow-up video on "the magic that makes it work." The lesson bridges Chuck's networking and VoIP backgrounds, using homespun analogies (a pediatric office with separate healthy/sick-kid entrances; an amusement-park Fast Pass line).

## Key claims (dated — the concept)

_All dated 2017-09-20; paraphrase unless quoted._

- A voice VLAN puts a boundary between voice traffic and data traffic so the voice traffic can be prioritized and kept secure — the same core reason you use any VLAN.
- On a Cisco switch you configure a port with both an access VLAN (data) and a voice VLAN so a phone and a computer work on the same physical port.
- Security is one of the biggest reasons: if Cisco phones share a VLAN/subnet with data devices, a PC on that subnet can sniff the voice packets and reconstruct the call — Chuck names tools like Cain and Abel and "vomit" that can turn sniffed voice traffic into a playable WAV file. Isolating voice on its own VLAN protects against this.
- QoS (Quality of Service) is another key reason: you decide which traffic is important and give it priority so it gets through without dropped or congested packets. Voice traffic gets the priority "fast pass" to the front of the line; data stays in the regular line.
- A major practical driver is the single-port cubicle: rather than adding a separate switch, you connect the phone to the wall and connect the PC to the phone's built-in PC port, serving both devices over one wall jack.
- The configured port carries two VLANs (voice + data) but Cisco is adamant it is an access port, not a trunk — how that works is left for the next video.

## Notable verbatim quotes

> voice VLANs these things are magical and I would love to tell you more about them

> that's essentially what a voice [VLAN] is it's putting a boundary between the voice traffic and the data traffic and making sure we can prioritize it making sure we can keep it safe

> this PC can actually listen in on voice traffic if it's on the same subnet you can use these little programs one called Cain and Abel and vomit to actually turn it into a WAV file you can sniff those packets and play back the voice call that's insane

> QoS is essentially a line at the amusement park

> because they've been deemed as special their prioritize[d] ... that's QoS in a nutshell you decide what traffic is important and then you give it priority

> let's get certified together thanks for stopping by

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
