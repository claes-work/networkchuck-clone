---
type: youtube-video
source_date: 2021-12-10
url: https://www.youtube.com/watch?v=befUVytFC80
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cloud-devops, cybersecurity]
tags: [crypto, solana, blockchain, token, learn-x-now, 2021]
---

# you need to create a Cryptocurrency RIGHT NOW!! (Solana token)

## Summary

A hands-on "learn X RIGHT NOW" tutorial in which Chuck walks the viewer through
creating their own cryptocurrency **token** on the **Solana** blockchain, entirely
from the Linux command line. He frames it as an educational blockchain exercise —
explicitly **not** financial advice — motivated by three reasons: it's fun and cool,
you learn something, and you can build something useful with it (his running example
is paying his five daughters in his own "cakes"/tokens instead of chore tickets,
redeemable for TV/Roblox time).

The technical core is a clear conceptual distinction plus a step-by-step build:

- **Concept**: You are not creating a cryptocurrency (that means building your own
  blockchain, huge effort). You are creating a **token** that piggybacks on an
  existing blockchain via smart contracts. Tokens and coins behave similarly for
  buying/sending. He chooses Solana over Ethereum because Ethereum gas fees are
  "astronomical" (he cites ~$128 average gas at recording time) and slow (15s–5min),
  while Solana is near-instant (milliseconds) with sub-penny fees, thanks to
  proof-of-history (built on proof-of-stake) rather than proof-of-work.
- **The build (CLI on a Debian/Ubuntu Linux box, e.g. a $5/mo Linode)**: install
  Solana CLI tools → create a wallet (`solana-keygen new`) → fund it with ~$5 of SOL
  from an exchange (Coinbase) → install prerequisites (Rust, `libudev-dev`,
  `libssl-dev`, `pkg-config`, `build-essential`) → install the SPL token program
  (`cargo install spl-token-cli`) → create the token (`spl-token create-token`) →
  create an account to hold it (`spl-token create-account <token>`) → mint tokens
  (`spl-token mint`) → transfer to another wallet (Phantom/Solflare/Slope) with
  `spl-token transfer --fund-recipient --allow-unfunded-recipient`.
- **Making it look legit**: to replace "unknown token" with a name, symbol, and logo,
  you add your token to the Solana token registry on GitHub — fork the repo, edit in
  the browser-based VS Code (press `.`), add your token folder + `logo.png` (must be
  <200KB, square PNG) and a JSON entry, then open a **pull request** which Solana Labs
  auto-merges roughly every 30–60 minutes. This doubles as a first taste of DevOps
  (fork, commit, PR, auto-merge). Verify everything on **solscan.io**.

He closes by demoing how anyone can buy his real **NetworkChuck Coin** for fun at
mint.network chuck.com (~10–18 cents), reiterating it is not an investment. The video
is also a paid sponsorship slot for Snyk ("Grammarly for your code" — scans code,
dependencies, containers, configs and auto-fixes vulnerabilities via a fix PR).

## Key claims (dated — the concept + how)

All statements below are as of **2021-12-10** and reflect a peak-2021-crypto-era view;
prices, fees, and tooling details are time-sensitive.

- **A "token" is not a "cryptocurrency."** A cryptocurrency has its own blockchain
  (Bitcoin, Ethereum, Solana); a token piggybacks on an existing blockchain using
  smart contracts. Example given: the SHIB meme coin runs on Ethereum. (paraphrase)
- **Tokens and coins operate similarly** for buying and sending; the differences are
  "under the hood" (smart contracts define send/receive behavior). (paraphrase)
- **Solana is chosen over Ethereum** because Ethereum transactions are slow (15s–5min)
  and gas is very expensive (average gas cited as ~$128 at recording), while Solana
  transactions are near-instant with fees under a penny (~$0.00108 typical).
  (paraphrase)
- **Why Solana is fast**: it uses proof-of-history (which depends on proof-of-stake)
  instead of the proof-of-work used by Ethereum and Bitcoin. (paraphrase)
- **Solana launched in 2019** and is relatively new. (paraphrase)
- **What you need**: a Debian-based Linux machine (Docker container, VM, or cloud
  instance such as a $5/mo Linode), about $5 of SOL to cover fees, and coffee.
  (paraphrase)
- **Fee nuance (Chuck "from the future" correction)**: normal transaction fees are
  sub-penny, but creating a new token or a new token account costs extra — a new
  token account runs about 50 cents; ongoing transactions stay sub-penny afterward.
  (paraphrase)
- **The full CLI build path**: install Solana tools → `solana-keygen new` (wallet;
  save the mnemonic/seed phrase to recover it) → fund with SOL → install Rust +
  build prereqs → `cargo install spl-token-cli` → `spl-token create-token` →
  `spl-token create-account <token>` → `spl-token mint <token> <amount> <account>` →
  `spl-token transfer --fund-recipient --allow-unfunded-recipient <token> <amount>
  <wallet>`. (paraphrase)
- **Minting = "printing money"**: you can mint as many tokens as you want (he mints
  1 billion, then another billion for 2 billion supply). (paraphrase)
- **Sending to a wallet that has no account for your token** requires
  `--fund-recipient` and `--allow-unfunded-recipient`, which pays to create that
  token account for the recipient. (paraphrase)
- **Naming/branding a token** requires adding it to the Solana token registry on
  GitHub: fork the `token-list` repo, add a folder named for your token address with
  a square `logo.png` under 200KB, add a JSON entry (address, symbol, name, logo URL,
  tags), then open a pull request; Solana Labs auto-merges valid PRs about every
  30–60 minutes. A too-large logo (his was 722KB) fails auto-merge. (paraphrase)
- **A lot of apps rely on the registry** to pull a token's name, symbol, and logo.
  (paraphrase)
- **Buying vs. sending**: with just a token, the only way for others to get it is for
  you to send it to them. For people to *buy* it, the token must be listed on an
  exchange with a market and liquidity pools — a convoluted, costly process he did
  only for NetworkChuck Coin, and which he says viewers do not need to do.
  (paraphrase)
- **Exchange minimum**: Coinbase would not let him send less than ~$12 worth of SOL.
  (paraphrase)
- **Repeated disclaimer**: none of this is financial advice; do not buy NetworkChuck
  Coin as an investment — buy only for fun, and expect to lose money if you treat it
  as one. He is "just a tech guy." (paraphrase)
- **Verification/exploration**: solscan.io lets you view your token, its supply, and
  every transaction on the Solana blockchain. (paraphrase)

## Notable verbatim quotes

> "Disclaimer, none of this is financial [advice]. I'm showing you this because the
> tech is really cool and it's worth learning, but by no means, am I telling you this
> so you can make money."

> "We are not creating a cryptocurrency... but we are creating a cryptocurrency token."

> "Tokens will piggyback off an existing blockchain. For example, the popular meme
> coin [SHIB] is based off of the Ethereum blockchain."

> "The average gas price for Ethereum is $128... if you wanna send things with
> Ethereum and Ethereum tokens, it's gonna cost you some money, some gas."

> "Solana. Whoa. It's like milliseconds... And the best part is that the fees are
> nothing seriously. When you send something with Solana, the fees are less than a
> penny."

> "Instead of proof of work, which is what Ethereum and Bitcoin and a lot of
> cryptocurrencies use, Solana uses proof of history. This mind bending concept."

> "We just created a token. That's it? That's it."

> "Minting basically means we're printing money. We can just make as many tokens as
> your heart desires, which is kind of cool."

> "If this is your first ever taste of DevOps, it's really cool."

> "This is very important that you pay attention to the details here, cuz this is
> JSON. If you messed up the JSON syntax in this file, they will not like you.
> They're not gonna accept your changes."

> "Setting it up on an exchange and creating a market and liquidity pools and all that
> jazz. You don't need to do that. Trust me."

> "Not an investment, but just fun to do."

> "To the moon. No, don't... nothing's going to the moon. It's just for fun. For real."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: 2021 crypto/blockchain content (Solana token) — era-specific -->
