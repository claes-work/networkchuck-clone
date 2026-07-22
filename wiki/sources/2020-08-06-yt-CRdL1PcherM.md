---
type: youtube-video
source_date: 2020-08-06
url: https://www.youtube.com/watch?v=CRdL1PcherM
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [networking, certifications-career]
tags: [free-ccna, tcp-ip, osi-model, ep-3]
---

# what is TCP/IP and OSI? // FREE CCNA // EP 3

## Summary

Episode 3 of NetworkChuck's FREE CCNA course (sponsored by Boson Software). This is
the concept-introduction episode for the two foundational networking models: the
**TCP/IP model** and the **OSI model**. Chuck frames the models through a short history
lesson — before standardized networking, devices from different companies literally
could not talk to each other, because each vendor (e.g., IBM) invented its own
**proprietary** network that only worked with its own equipment. He traces the origin
to 1969 and ARPANET (built by the US Department of Defense), which invented **packet
switching** but hadn't yet ironed out *how* computers would agree to communicate.
Eventually, through committees and standards work, the industry converged on
networking models so that any vendor's computer (Microsoft, Apple, IBM) could
interoperate using the same standards.

Chuck explains that we ended up with **two** models: TCP/IP (the one actually
implemented in every computer, also called the "TCP/IP stack") and OSI (the model
that lost the standardization "war" but whose layer terminology network engineers
still use daily). He walks the layers, tying them back to concepts from earlier
episodes (physical = cables/electricity/NICs = layer 1; data link = MAC addresses,
switches = layer 2; network = IP addresses, routers = layer 3), and shows how OSI
adds **session** and **presentation** layers above transport, giving OSI seven layers
vs. the TCP/IP model's layers. He teaches two mnemonics for the OSI layers and closes
with two practice exam questions on which devices operate at which layers. He plugs
that EP 4 (releasing the same day) will trace a packet through a network layer by
layer.

Cross-reference: [[2020-08-06-yt-3kfO61Mensg]] (EP 4 — the real-life packet walkthrough).

## Key claims (paraphrase, dated 2020-08-06 — the concepts)

- Networking models like the **TCP/IP model** and **OSI model** are what allow devices
  built by different companies to communicate; without them, a device from one vendor
  could not talk to a device from another.
- **1969**: ARPANET, built by the US Department of Defense (DoD), was the first
  network. It invented **packet switching** (which is still used today) but had not
  yet defined the *how* — the actual method for making computers talk.
- After the idea spread, companies like **IBM** built their own **proprietary**
  networks that only worked with their own equipment; because different vendors'
  networks were proprietary, they could not communicate with each other (analogy:
  speaking different languages; like trying to charge an iPhone with an Android cable).
- This was primitive — it predates **Ethernet cables** and standardized Ethernet
  ports; each company had its own incompatible cabling/versions.
- The industry eventually agreed to use common networking standards (via meetings and
  committees), producing a networking model so all vendors put the same technology
  inside their computers to interoperate.
- Two models resulted: **TCP/IP** (aka the TCP/IP stack) — the one actually
  implemented in every computer — and **OSI** (Open Systems Interconnect) — the one
  that was widely believed would win but ultimately lost adoption.
- A model is a set of rules/guidelines/standards for how computers communicate;
  functions are divided into **layers** to make them simpler and more digestible.
  Each layer defines a protocol or standard.
- Layer mapping (Cisco/CCNA view): **physical** = Ethernet cables, NICs, electrical
  signals (layer 1); **data link** = MAC addresses, switches (layer 2); **network** =
  IP addresses, routers (layer 3); **transport** = TCP, UDP, port numbers (layer 4);
  **application** = protocols used by apps (e.g., opening a web browser to a site).
- Before the IP standard, using IP addresses wasn't a rule — you theoretically could
  have used any addressing scheme (Chuck jokes: "names from Star Wars").
- For the CCNA 200-301, the physical layer may be shown split into two separate layers
  (physical + data link) — a version Chuck says he prefers.
- The **OSI model** shares TCP/IP's lower layers (physical, data link, network,
  transport) but adds a **session layer** and a **presentation layer** above transport,
  for **seven** layers total. The concepts of those two extra layers don't disappear in
  TCP/IP — they're absorbed into the application layer.
- Even though TCP/IP won and OSI "died," network engineers still use **OSI layer
  terminology** day-to-day (e.g., always calling the application layer **layer 7**),
  because OSI was expected to win and its layers became the standard vocabulary.
- To pass the CCNA you must know **both** models. OSI is also the most-referenced
  framework when engineers troubleshoot ("that's a layer 7 issue," "that's a layer
  1/2/3/4 issue").
- Mnemonics for the seven OSI layers: top-down (Application→Physical) "**All People
  Seem To Need Data Processing**"; bottom-up (Physical→Application) "**Please Do Not
  Throw Sausage Pizza Away**."
- Exam Q1 — which device operates **primarily at layer 2** (data link): the **switch**
  (routers = layer 3; hubs = layer 1/physical, unaware of MAC addresses, just repeat
  electrical signals out all ports; a wireless access point operates at both layer 1
  and layer 2, so "primarily layer 2" is only half-right).
- Exam Q2 — which devices operate **primarily at the physical layer** (select two):
  **repeaters** and **hubs** (both just repeat electrical signals; bridges, by
  contrast, deal with layer 2 like switches).

## Notable verbatim quotes

> once upon a time a long time ago in a galaxy far far away if you had a device that
> was made by two different companies they could not talk. this is where things like
> the tcp ip model or the osi model networking models save the day like for real.

> 1969, the birth of the first network. we called this — or they called this ARPANET.
> the USDOD or the department of defense came up with it and it was revolutionary.

> they actually invented what's called packet switching which is what we do today. but
> what they didn't have yet is the how — how do we make these computers talk to each
> other.

> you ever try to charge your iphone with an android charging cable? it doesn't work,
> it's just not compatible. that was the networks of yesteryear.

> the model we use today is called tcp ip. this is what every computer supports and has
> implemented into their system, the tcp model — and they also call the tcp ip stack.

> tcp ip is just a list of rules or guidelines, standards on how computers can
> communicate, how we design those systems.

> when network engineers talk about it, osi always wins. we will always always always
> refer to the application layer as layer 7.

> all people seem to need data processing — i'm sure there are better ones, that's just
> how i learned it.

> please do not throw sausage pizza away. makes me hungry every time.

> oh, that's a layer 7 issue, application, hands off, not my problem. or hey, that's a
> layer 1 layer 2 layer 3 or layer 4 issue.

> hubs are stupid, they got no smarts. they don't operate at layer two, they're not
> even aware of mac addresses. all they do is just repeat electrical signals when they
> receive them out all ports.

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: FREE CCNA EP 3 — TCP/IP & OSI models -->
