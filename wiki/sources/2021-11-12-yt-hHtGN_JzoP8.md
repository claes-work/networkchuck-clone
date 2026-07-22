---
type: youtube-video
source_date: 2021-11-12
url: https://www.youtube.com/watch?v=hHtGN_JzoP8
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [homelab-selfhosting, linux-terminal]
tags: [cryptocurrency, mining, raspberry-pi, monero, duino-coin, fun]
---

# Cryptocurrency Mining on a Raspberry Pi (it's fun....trust me)

## Summary

Chuck walks through turning a $35 Raspberry Pi (a 3 or 4, ideally with 4GB+ RAM)
into a cryptocurrency mining machine. He is upfront from the first minute that this
is not profitable — the payoff is fun and learning, not money. Before the hands-on
build, he delivers a high-level primer on what crypto mining is: how transactions get
grouped into blocks and chained (the blockchain), how miners secure the chain by
solving a cryptographic hash puzzle via brute-force guessing (proof of work), and why
the fastest/luckiest miner wins the block reward.

He explains why a Pi cannot mine Bitcoin or Ethereum (too hard — those are dominated
by GPUs and purpose-built ASIC rigs like the ~$12,000 Antminer, which do ~104 terahashes/sec)
and why Monero (XMR) is the right choice: Monero's RandomX algorithm is deliberately
ASIC-resistant so anyone — even a tiny Pi — can mine, keeping the network decentralized.

The build: flash Raspberry Pi OS Lite 64-bit with Raspberry Pi Imager (headless — enable
SSH and Wi-Fi in the hidden Ctrl+Shift+X menu), SSH in, `apt update`, install prerequisites,
`git clone` the XMRig repo, build it from source (`cmake ..` then `make`), create a Monero
GUI wallet to get a wallet address, then run XMRig pointed at a mining pool
(`gulf.moneroocean.stream:10128`) with the wallet address as the user and a worker label.
He explains why you must join a pool — a lone Pi would never win a block — and shows the
in-console hotkeys: `h` (hash rate), `s` (accepted shares), `c` (connection/difficulty).
His Pi did ~44 H/s across four CPU cores. The honest bottom line: mining calculators show
you'd lose about a penny per day after electricity, so do it for fun, learning, and
bragging rights — plus the small chance XMR appreciates over time.

## Key claims (paraphrase; dated 2021-11-12)

- Concept — you *can* mine cryptocurrency on a Raspberry Pi, and you *should*, but it is
  not profitable; the real value is that it's fun and you learn a ton about crypto and
  crypto mining along the way. [honest framing]
- Honest framing — it is not profitable: after electricity costs, mining calculators show
  you lose about a penny per day. Don't do it to get rich; do it for fun, knowledge, and
  bragging rights. [honest framing]
- The project mines Monero (XMR), not Bitcoin or Ethereum, because those big coins are
  "too stinking hard" for a Pi — they're mined by massive GPUs and purpose-built ASICs
  (e.g. the ~$12,000 Antminer at ~104 TH/s), so a Pi would never win a block.
- Crypto mining = supporting/securing the blockchain: miners gather verified transactions
  from the memory pool, solve a cryptographic hash puzzle by brute-force guessing, and the
  first to solve it adds the next block and earns the block reward.
- This puzzle-solving process is called proof of work; it's used by Bitcoin, Ethereum,
  and Monero.
- Bitcoin's block reward at recording was 6.25 BTC (~$421,000); Monero's was 1.16 XMR
  (~$300). These numbers are time-of-recording snapshots and will change.
- Monero uses the RandomX algorithm with built-in ASIC resistance so anyone can mine —
  even something small like a Pi — keeping the blockchain more decentralized; Bitcoin
  uses SHA-256.
- Hardware needed: a Raspberry Pi 3 or 4 (4 is better; 4GB+ RAM needed for 64-bit fast
  mode), SD card, power supply, SD card reader — and coffee.
- Software build: Raspberry Pi OS Lite 64-bit (required), flashed headless via Raspberry
  Pi Imager (SSH + Wi-Fi enabled in the Ctrl+Shift+X hidden menu); then SSH in, `apt update`,
  install prerequisites, `git clone` XMRig, and build from source with `cmake ..` and `make`.
- You must mine into a wallet — the video uses the Monero GUI wallet; the mnemonic seed
  must be written down physically to back up/restore it.
- You must join a mining pool (video uses `gulf.moneroocean.stream:10128`) because a lone
  Pi would never win a block; the pool combines everyone's compute and distributes the
  reward proportional to shares (work) contributed.
- XMRig console hotkeys: `h` = hash rate (your guessing speed), `s` = accepted shares
  (work credited), `c` = connection info including RandomX algorithm and difficulty
  (pools auto-adjust difficulty to your machine — Chuck's weak Pi got dropped to 500).
- Performance: the demo Pi did ~44 H/s across 4 CPU cores; his weaker Pi underperformed
  because it only had 2GB RAM (couldn't use 64-bit fast mode).

## Notable verbatim quotes

> "But is it profitable? Not exactly... in this video, I'm going to show you how to mine cryptocurrency on this little credit card sized computer, a raspberry pie, and it's fun."

> "Not only is it just cool to say you've done this, but you'll learn a ton about cryptocurrency and cryptocurrency mining along the way."

> "The simple answer as to why we're not mining Bitcoin or Ethereum, is that it's just too stinking hard. Our little raspberry PI would just not be able to do it."

> "Crypto mining is all about supporting the blockchain."

> "This blockchain, this ledger, this cryptocurrency diary contains every single transaction ever for that cryptocurrency... everyone can see it and you can't change it."

> "In order to add a block to the blockchain and get that reward, you have to solve a really, really hard math problem. And you have to be the quickest to do it."

> "Monero's goal was to make it to where anyone can mine Monero, even something small, like a raspberry PI, and this makes it to where their system, their blockchain is more decentralized."

> "According to some mining calculators I saw, you lose about a penny per day mining with this. So if you plan on getting rich, forget about that. But if you plan on having fun and learning about cryptocurrency, and you have a spare pi laying around and you want to earn some cryptocurrency, just passively, go for it."

> "I know it's not worth the money. It's worth the fun though, and worth the knowledge and just the cool credits you get."

> "Do not forget to hack that YouTube algorithm today... make sure you hack YouTube today. Ethically, of course."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
