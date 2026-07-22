---
type: youtube-video
source_date: 2019-03-16
url: https://www.youtube.com/watch?v=8cmmVEoftEM
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [networking]
tags: [wifi-6, 802-11ax, wireless, ofdma, mu-mimo]
---

# WI-FI 6, Why it's the BIGGEST update to Wi-Fi EVER! - 802.11ax

## Summary

Chuck explains why Wi-Fi 6 (802.11ax) is, in his view, one of the most important
updates to Wi-Fi in a long time — framing it not as a speed bump but as a fundamental
change to how access points share airtime. He opens with a relatable pain point:
public Wi-Fi in malls, schools, and airports fails, so people switch to 4G/cellular,
which works far better in high-density places. The core of the video walks through why
current Wi-Fi is inefficient — an access point can only talk to one device at a time,
gives the entire channel to that one device regardless of how little bandwidth it
needs, and constantly fights for airtime with all the devices trying to talk back
(contention/collisions, like a four-way stop). He explains that speed gains from
each standard (n → AC) masked this inefficiency on small networks but did not fix it.

The headline feature is OFDMA (Orthogonal Frequency-Division Multiple Access), the
evolution of OFDM: the channel is divided into smaller sub-channels called Resource
Units (RUs), and the AP can allocate right-sized pieces to multiple devices and
transmit to them all at once in a single transmit opportunity — plus it gains control
over uplink scheduling (who sends, how much, when). Chuck compares the leap to going
from a network hub to a switch. He then covers three more features: Target Wake Time
(TWT) for IoT/phone battery savings, the return of the 2.4 GHz spectrum (absent since
802.11n, better range, cheaper radios for IoT), and BSS Coloring to reduce co-channel
interference. He closes with practical buying advice (buy ax as soon as it ships; ax
devices act like "wireless purifiers" cleaning up your air), notes ax is the most
backwards-compatible standard, and touches on 5G and VR as future drivers.

## Key claims (dated — the concepts)

All dated 2019-03-16 (source publication).

- Wi-Fi 6 is the marketing name from the Wi-Fi Alliance for the 802.11ax standard;
  the Alliance also renamed AC to Wi-Fi 5 and n to Wi-Fi 4 to make naming easier for
  most people. (paraphrase)
- Cellular (4G) often outperforms standard Wi-Fi in public/high-density places
  (malls, schools, airports); Wi-Fi 6 is positioned as the answer to those wireless
  problems. (paraphrase)
- The core inefficiency of pre-ax Wi-Fi (802.11ac and earlier): the access point can
  only talk to one device at a time. (paraphrase)
- Devices and the AP contend for airtime like cars at a four-way stop — they must wait
  for the all-clear or they collide, causing congestion in dense environments.
  (paraphrase)
- Each Wi-Fi generation improved throughput (bigger channels: 20/40/60+ MHz), which
  made small networks feel fine, but never fixed the one-device-at-a-time
  inefficiency. (paraphrase)
- Under the old model the AP hands the entire channel/highway to one device at a time
  even when that device (e.g. a Twitter refresh or a light-bulb color change) needs
  only a tiny bit of bandwidth. (paraphrase)
- OFDM (Orthogonal Frequency-Division Multiplexing) in AC/earlier divided a channel
  into sub-channels ("lanes") to avoid interference, but each device still got all the
  sub-channels one at a time. (paraphrase)
- OFDMA (Orthogonal Frequency-Division Multiple Access) adds the "A" (multiple access):
  the AP can talk to several devices at once by dividing the channel into smaller
  chunks called Resource Units (RUs) sized to each device's bandwidth need, sent in one
  transmit opportunity. (paraphrase)
- OFDMA also gives the AP control over uplink: it can schedule when devices send data
  and how much of the channel they may use, giving it control over both downlink and
  uplink. (paraphrase)
- Chuck analogizes the shift as going from a network hub to a switch. (paraphrase)
- OFDMA enables guaranteed quality-of-service for latency-sensitive traffic (e.g. a
  VoIP call gets a reserved sliver of the channel on downlink and uplink), which people
  compare to a virtual circuit / virtual tunnel / HOV lane. (paraphrase)
- OFDMA is especially valuable for IoT: many small devices each needing little
  bandwidth can be given slivers of the channel and served all at once, instead of each
  monopolizing the whole highway. Use cases: factories, conferences (Cisco Live),
  airports, schools, hospitals with sensitive medical devices. (paraphrase)
- Target Wake Time (TWT): the AP and device negotiate a schedule so a device can power
  down its radio and wake only when needed (e.g. a smart candle reporting wax level
  once a day), saving battery; aggregated across many IoT devices this is a large power
  saving. Phone manufacturers can also use TWT to extend phone battery life without
  improving battery hardware. (paraphrase)
- The 2.4 GHz spectrum returns in ax; AC only supported 5 GHz, so 2.4 GHz support had
  required falling back to 802.11n. 2.4 GHz gives longer range and lets cheap low-end
  IoT radios connect — the first advancement to 2.4 GHz since 802.11n (~10 years).
  (paraphrase)
- BSS Coloring: assign each Wi-Fi network a "color" so an AP ignores transmissions from
  other-colored networks it can faintly hear, reducing co-channel interference (Chuck
  calls it CCI). (paraphrase)
  > ⚠️ Note (curator): Chuck says the old behavior of stopping to listen to distant
  > SSIDs is "CCI or common channel interference." The standard industry term is
  > *co-channel interference* (CCI); "common channel" is a caption/verbal slip.
- Throughput figures cited: ~866 Mbps max throughput for a single device/one antenna
  under 802.11ac, rising to ~1200 Mbps under ax — but Chuck treats raw speed as an
  afterthought next to OFDMA's efficiency gains. (paraphrase)
- Buying advice: buy 802.11ax/Wi-Fi 6 APs as soon as they ship, even with few ax
  endpoints, because ax devices become far more efficient (OFDMA) and stop contending
  with your AC/n devices — "wireless purifiers" that clean up your air. (paraphrase)
- ax is described as the most backwards-compatible standard, supporting all devices.
  (paraphrase)
- If running old 802.11n APs and needing to upgrade now, upgrade rather than wait —
  unless the environment is unique (lots of IoT or huge Wi-Fi bandwidth needs), in
  which case waiting for ax may make sense. (paraphrase)
- 5G and Wi-Fi 6 are similar (higher performance, larger capacity in theory) and should
  eventually hand off seamlessly; VR (collaboration, gaming) is another big future
  driver needing more bandwidth/capacity. (paraphrase)
- Status as of publication: the standard is nearly finalized by the IEEE; some pre-ax
  gear exists; devices announced at Mobile World Congress (new Samsung phones, LG) will
  support ax. (paraphrase)

## Notable verbatim quotes

> "why is it that 4G cellular technology is so much better in public places ... it feels like cellular technology has gone so far where Wi-Fi is kind of still on a stone Age's well I got good news for it that's about to change"

> "the access point can only talk to you one device at a time"

> "the AP still has to give the entire channel the whole highway to one device at a time"

> "with Wi-Fi 6 we take that OFDM ... and we add one more letter to make it amazing we add an a so now it's orthogonal frequency-division multiple access"

> "the AP can now talk to multiple several devices at once whereas before you can only talk to one device"

> "these are also referred to as resource units or our use"

> "once the ap is figured out how much of the channel to give each device based on their bandwidth needs we can then send it all at once in one transmitted opportunity now that is stinkin efficient"

> "up until now the way we've been using Wi-Fi has been more like a network hub ... but with this new Wi-Fi six ... it's like we've gone from a hub to a switch"

> "he now has kind of ultimate control over the downlink and uplink insane"

> "the more ax devices you add to your environment the cleaner your air is they're like little air purifiers to your Wi-Fi wireless purifiers I'm gonna trademark that"

> "with Wi-Fi 6 ... it introduces a thing called BSS coloring which basically means you assign your Wi-Fi network a color you color your network"

> "not only is ax the most backwards compatible standard out there so it'll support all your devices no matter what"

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
