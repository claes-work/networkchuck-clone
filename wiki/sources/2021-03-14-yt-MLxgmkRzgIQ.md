---
type: youtube-video
source_date: 2021-03-14
url: https://www.youtube.com/watch?v=MLxgmkRzgIQ
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [networking, certifications-career]
tags: [free-ccna, poe, power-over-ethernet, ep-12]
---

# why Power over Ethernet (PoE) is amazing!! // FREE CCNA // EP 12

## Summary

Episode 12 of the FREE CCNA series (sponsored by Boson Software) covers Power over
Ethernet (PoE): delivering both power and data to a device over a single Ethernet cable.
Chuck traces PoE from its origin — Cisco's proprietary Inline Power (2000) built to power
IP phones — through the successive IEEE standards and their power budgets, then demonstrates
PoE live in Cisco Packet Tracer and on a real switch.

The teaching arc has three parts: (1) the **how** — power was originally sent over the two
unused twisted pairs (pins 4/5 and 7/8) on early cabling, and later standards use all four
pairs; (2) the **why** — running one cable instead of separate power and data runs is
cheaper and simpler (no electrician needed, network engineer does it all, devices are easy
to relocate); (3) the **standards ladder** — af/Type 1, at/Type 2, and bt Types 3 and 4,
each roughly increasing the wattage. Chuck also distinguishes **active vs. passive** PoE,
explains negotiation via CDP/LLDP, walks a Boson CCNA courseware section, shows the
`show power inline` command, and closes with a Boson CCNA practice-exam question.

## Key claims (paraphrase, dated concepts — 2021-03-14)

- PoE delivers **both power and data over one cable**, replacing the need for a separate
  power run and data run to an end device.
- Cisco invented the technology in **2000** and called it **Cisco Inline Power** — its own
  proprietary name before any standard existed. Chuck (born 1990) notes he was 10 then.
- PoE terminology: the switch supplying power is the **PSE (Power Sourcing Equipment)**;
  the end device receiving power is the **PD (Powered Device)**.
- Early cabling (Cat5 and older) used only two twisted pairs (pins 1/2 and 3/6) for data;
  the unused pairs (pins 4/5 and 7/8) were repurposed to carry power.
- **IEEE 802.3af (Type 1 PoE)** — ratified **2003**; provides **15.4 watts** per port.
  Cisco's original Inline Power delivered only ~4–6 watts (enough for a basic phone).
- Standardization opened PoE beyond Cisco — Ubiquiti, Aruba, Juniper and others can all
  interoperate. On Cisco gear the commands are still labeled "inline power," a nod to
  Cisco's invention.
- **IEEE 802.3at (Type 2 PoE / "PoE+")** — came out **2009**; doubled the budget to
  **30 watts** per port. It is by far the most common standard.
- **Cisco UPOE (Universal Power over Ethernet)** — ~**2011**, Cisco-only (non-standard);
  **60 watts**. This is where Cisco began using **all four twisted pairs** for power.
- **IEEE 802.3bt (Type 3)** — the standardized version of ~60W four-pair PoE; also called
  "PoE++" or "4PPoE" (four-pair PoE). Delivers **60 watts**.
- **IEEE 802.3bt (Type 4)** — **2018**; **90 watts** per port. Same 802.3bt / 4PPoE /
  PoE++ family as Type 3, just the higher-power type.
- Use cases scale with wattage: phones, wireless access points (WAPs), and security cameras
  at lower tiers; **switch-powering-a-switch** (a beefy central switch powers smaller access
  switches) at 60W; and small computers/laptops over USB-C, building LED lighting, and even
  HVAC at 90W.
- **Two types of PoE — active and passive.** *Active* PoE negotiates with the end device
  to deliver the appropriate wattage (and gives no power to devices that don't need it, like
  a PC); it is what runs on Cisco and most other brand switches. *Passive* PoE is
  always-on power with no negotiation — often called **24-volt PoE** — and can fry a device
  that isn't meant to receive it.
- Sending too much power to a device (e.g. a camera) fries it, which is why active
  negotiation matters. Some legacy devices need 24V passive because they don't support
  negotiation. Ubiquiti switches (Chuck uses one he calls "the golden snitch") support both
  PoE+ and 24V passive, configurable per port.
- Negotiation protocols: **CDP (Cisco Discovery Protocol)** — Cisco proprietary, still used,
  defaults for Cisco phones/APs; **LLDP (Link Layer Discovery Protocol)** — the industry
  standard used for third-party devices. Cisco switches support both and fall back to LLDP
  for non-Cisco gear.
- All PoE standards are **backwards compatible** — a switch supporting PoE+ supports every
  earlier standard.
- **Device power classes 0–4** define how much a PD draws from the PSE. Class 3 draws
  between **6.49 and 12.95 watts** (shown in the lab, where phones pulled ~10W).
- CCNA exam nugget: if a device attempts to draw more power than a port is configured to
  provide, a **syslog message is issued and the port is shut down / enters the
  error-disabled state**.
- Standards to memorize for the CCNA: **802.3af**, **802.3at**, **802.3bt** — their types
  and per-port wattages (wattage figures are per port).
- Lab (Packet Tracer, Cisco 3650): connecting phones triggers syslog "power device detected
  (IEEE PD)" → "power granted"; **`show power inline`** displays available/used/remaining
  wattage and per-port draw. Example switch: **780W total**, ~40W used by 3–4 phones, 740W
  remaining; each port capable of 30W.
- A switch's **total power budget can be less than the sum of all ports at full power** — a
  780W / 24-port switch (24 × 30W = 720W) has headroom, but a 48-port switch may not power
  every port fully. Chuck recounts phones on a floor that wouldn't power up because the
  switch had run out of available wattage (0W remaining) — visible in the syslog.
- **Cable loss**: a device fed a configured 15.4W may only actually receive ~13W because
  some power is lost over the cable during transport — normal, nothing to worry about.
- Practice-exam answer: issuing `power inline police` on an interface means that when a PD
  draws more than its allocated power, the **port enters an error-disabled state and a log
  message appears in the console** (answer C).

## Notable verbatim quotes

> "here comes my favorite sound in the world oh yeah — and boom with one cable power and data"

> "any good IT engineer is really lazy that's why we automate things ... because we're lazy"

> "so the lazy engineers at Cisco are like what if we could just do everything on one cable
> power and data — and that's why we have it"

> "we always add a plus to everything to make it seem better ... I should come out with
> NetworkChuck plus"

> "passive is kind of stupid — um no it has its place — passive is always on power"

> "passive just says you're getting power you're getting power you're getting power you're
> all getting power — it's like an evil Oprah"

> "if you put out too much power to this camera here ... it fries it doesn't work anymore"

> "we're using a switch to power a switch — which what what — yes"

> "pretty soon we'll only have PoE we won't have actual power run through our houses just
> all ethernet cable and I'm game for that"

> "the fact that we can send both gigabit internet down a cable and power blows my mind"

> "do attempt to answer it without googling it ... if you have to google around and figure
> this out, do it — that doesn't mean you're dumb, that just means you're an IT person"

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: FREE CCNA EP 12 — Power over Ethernet -->
