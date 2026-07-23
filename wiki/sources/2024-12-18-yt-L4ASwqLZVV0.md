---
type: youtube-video
source_date: 2024-12-18
url: https://www.youtube.com/watch?v=L4ASwqLZVV0
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [linux-terminal, cloud-devops]
tags: [solana, crypto, blockchain, cli, spl-token]
---

# create your own Solana Token...in the terminal (2025 edition)

## Summary

Chuck walks through creating a custom cryptocurrency token on the **Solana blockchain**,
entirely from the command line, framed explicitly as a fun tech-curiosity project rather
than an investment. The through-line is a family project: he and his daughters each mint
their own competing tokens ("battle it out"), and he reveals a real token, **KES / "Keith
Coin"**, that he uses to automate his kids' allowance — when they mark a chore complete in
a habit-tracking app, a webhook triggers a token transfer to their wallet.

The tutorial covers the full workflow: setting up a Solana CLI environment inside a Docker
container (with Rust and the Solana CLI), doing everything first for free on the **Solana
DevNet** (developer test network) before optionally going to **Mainnet Beta**. Steps
include generating vanity keypair "accounts"/wallets (a `dad` boss/owner account and an
`mnt` mint/"factory" account), airdropping test SOL from the faucet, creating the token
with `spl-token create-token` (metadata enabled, 9 decimals like SOL), uploading a logo
and metadata JSON to decentralized IPFS storage via **Pinata**, minting supply, and
transferring tokens between wallets (using **Phantom** wallet in testnet mode).

The second half covers taking a token to Mainnet (~59 cents in SOL to create the token),
then optionally making it tradeable: disabling mint authority and freeze authority to make
the token "legit," adding a **liquidity pool** on **Radium** (~0.2 SOL / ~$50–60), and
burning the resulting LP tokens (via the Sol Incinerator site, since the CLI burn didn't
work for him) to lock liquidity. He closes with the allowance-automation show-and-tell: a
Python app in Docker listens for Habitica webhooks, runs `spl-token transfer`, and posts a
Slack notification, with day-streak multipliers on the reward.

Sponsored by Dashlane (used to store the wallet private keys / secure notes).

## Key claims (dated — how + framing)

All from the 2024-12-18 video; all paraphrase unless quoted.

- **Framing — for fun, not financial advice.** Chuck repeatedly stresses the project is a
  tech experiment, not an investment play — "We're doing this for fun. Get that out of
  your head." He tells viewers their token will *not* become the next meme coin, and that
  the whole liquidity/market step is "totally optional."
- **Blockchains vs. cryptocurrencies.** Bitcoin, Ethereum, and Solana are blockchain
  *platforms*, not cryptocurrencies; each has a native token (BTC, ETH, SOL). A blockchain
  is described as a shared, decentralized public digital ledger running across many
  computers — secure, transparent, and (he jokes) "better than banks."
- **Personal preference.** Chuck says Solana was his "first love" and is very fun to play
  with; he likes it partly because transactions are fast and cheap.
- **DevNet first.** Beginners should practice on the Solana DevNet, where a token behaves
  like a real one (send/receive) but costs no real money — only Mainnet supports actual
  buying/selling.
- **Tooling.** The whole build runs in the terminal via the **Solana CLI** and
  **`spl-token`** CLI, installed (along with Rust) inside a **Docker** container; on
  Windows he uses **WSL2 / Ubuntu**. Wallet management uses **Phantom**; block exploration
  uses explorer.solana.com and Solscan; metadata/logo hosting uses **Pinata** (IPFS
  decentralized storage); liquidity pools use **Radium**; LP-token burning uses **Sol
  Incinerator**.
- **Accounts / keypairs.** A Solana "account" is a keypair stored as a JSON file
  containing the private key; anyone with that JSON can load the wallet, so it must be kept
  safe (his sponsor pitch: store it in Dashlane). He generates vanity addresses beginning
  with `dad` (the token owner/boss) and `mnt` (the mint address, which becomes the token's
  official address).
- **Token creation command.** `spl-token create-token` with metadata enabled and
  `--decimals 9` (matching SOL). Metadata (name, symbol, description, image URL) is stored
  on-chain now, rather than the old GitHub-upload method.
- **Minting.** After creating a token account for the mint, `spl-token mint` prints tokens
  "out of thin air" into the owner's wallet — "You're printing money. You're the
  government." He mints a billion as total supply.
- **Costs (Mainnet).** Creating the token cost him ~0.0025 SOL (~59 cents); every on-chain
  action costs a small amount of SOL — "It's a toll road." A liquidity pool needs ~0.2 SOL
  (~$50–60).
- **Making a token "legit."** To reassure holders you: disable the mint authority
  (`spl-token authorize ... mint --disable`, irreversible, so no more supply can be made)
  and disable the freeze authority (`spl-token authorize ... freeze --disable`, so you
  can't freeze others' wallets). Then add liquidity on Radium (he cites following a "Baird
  Business" tutorial: put ~95% of supply into the pool, backed with SOL) and burn the LP
  tokens to permanently lock liquidity.
- **Allowance automation.** Habitica task completion → API webhook → a Python app (in
  Docker) that runs `spl-token transfer` to send KES ("Keith Coin") to the kid's wallet
  and posts a Slack message; habit streaks over 10/20 days apply 1.5×/2× reward
  multipliers. He mentions wanting to later teach them staking.

## Notable verbatim quotes

> "We're going to make our own cryptocurrency for fun because the technology is amazing."

> "Yours might become the next big meme coin. No, no, it won't. We're doing this for fun.
> Get that out of your head."

> "And yes, we'll be doing all of this via command line because it's just cooler. Sure,
> there are gooey options, but let's rise above that."

> "A blockchain is like a shared digital ledger that runs across a bunch of computers
> making transactions secure, transparent, and impossible to mess with better than banks.
> That's what I say."

> "Personally, I like Solana. It was my first love and it's very fun to play with."

> "You're printing money. You're the government."

> "So anytime you do anything on the salon at blockchain, it's going to cost you. It's a
> toll road."

> "So I'm showing you this, not to say do this exact thing, but to show you that with
> cryptocurrency and Solana and tokens and stuff, you can have as much fun as you want."

> "This is my token KES that I made for my daughters and family. It's our currency. It's
> actually worth something if you want to buy some... I'm not saying you should buy some,
> I'm just saying you can."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT). (His daughters appear on
camera choosing token art and reacting, but they are not sources of persona/knowledge
material.)

<!-- ★ L3-candidate: crypto-as-experiment framing (not financial advice) -->
