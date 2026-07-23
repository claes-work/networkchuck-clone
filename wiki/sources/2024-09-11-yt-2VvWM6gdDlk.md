---
type: youtube-video
source_date: 2024-09-11
url: https://www.youtube.com/watch?v=2VvWM6gdDlk
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cloud-devops, ai-tools, creator-coffee-business]
tags: [hostinger, claude, chatgpt, ai-coding, web-hosting, api, ship-fast, build-challenge, sponsored]
---

# I built 24 Websites in 24 Hours

## Summary

A Hostinger-sponsored build-challenge video in which Chuck rapidly ships 24 small,
mostly-silly websites in a single sitting, deploying every one on Hostinger's $4/month
business plan (up to 100 sites, free domain, unlimited databases, cron jobs, Git
integration, and an AI website builder). The core method is the same loop repeated 24
times: describe a website idea, have an AI (Claude, occasionally ChatGPT) generate the
HTML/CSS/JS or PHP, paste the code into Hostinger's file manager, register a domain, and
preview it live. Many builds bolt a public API onto the AI-generated frontend (OMDb for
movies, a recipe API found via an API-list/RapidAPI-style directory, the YouTube Data
API for comments, a Reddit meme API). A running contest threads through the video: each
of the first 23 sites hides a secret phrase; combined with periods they form the world's
longest-URL site (site 24), and the first three viewers to reach it win a $500 Amazon
gift card.

The build catalog includes: a John Hammond fan page, a Pomodoro coffee-drip timer, a
YouTube "comment of the day" (YouTube API + Claude), a movie picker (OMDb), a random
recipe/dinner picker, an "Is it Halloween?" page, a bidet advocacy site (Hostinger AI
builder), a recreated looping-video site (sanger.dk via the Wayback Machine, redeployed
as "pug stuck"), a limited 24-shirt store (Hostinger's builder + store, Stripe/PayPal),
a shopping-list site, a "you shouldn't send this" venting page, the encrypted
secret-prize countdown (crypto-js AES with a time-based, split, separately-encrypted
key), an HTML5 "Mike game," a "NetworkChuck quote of the day" (yt-dlp to pull his own
transcripts → LLM extracts quotes → stored in MySQL → PHP frontend), an ethernet-cable
wiring reference, a "big old cursor" game (ChatGPT), a Chemex/drip coffee ratio
calculator, a colorblindness color-namer, a visitor counter (PHP), joke Ryan Reynolds
and pineapple-pizza sites, a random meme site, and a Koki fan site (Hostinger AI
builder). Chuck opens with a security disclaimer (the sites were built fast and are not
secure — e.g. don't expose API keys) and notes a follow-up "we hacked our websites"
video. The closing lesson: build anyway, because the act of creating surfaces ideas and
inspiration.

## Key claims (dated — stack + lesson)

- (2024-09-11) The full deploy stack: **Hostinger** business plan ($4/month) hosts every
  site — advertised as up to 100 websites, a free domain, WordPress, Hostinger's AI
  website builder, WooCommerce store, backups, email, unlimited databases, cron jobs, and
  Git integration. Sites are deployed by pasting code into Hostinger's file manager or via
  its AI/builder tools. (paraphrase; sponsored placement — treat feature figures as ad copy)
- (2024-09-11) Code generation is done primarily with **Claude**, with **ChatGPT** used on
  a couple of builds (the "big old cursor" game). The repeated workflow: prompt the AI to
  write HTML/CSS/JS or PHP → copy the code → paste into a new file in Hostinger → register a
  domain → preview. (paraphrase)
- (2024-09-11) Several sites combine an AI-built frontend with a public **API**: **OMDb**
  (Open Movie Database) for the movie picker, a food/recipe API discovered through an
  API-directory site for the dinner picker, the **YouTube Data API** (requires a free API
  key) for "comment of the day," and a Reddit-scraping meme API. (paraphrase)
- (2024-09-11) The "quote of the day" build's real pipeline: **yt-dlp** ("YTDL") pulls his
  own YouTube video transcripts → an **LLM** extracts the best quotes → quotes stored in a
  **MySQL** database → an **HTML/CSS/JS + PHP** frontend serves a random one; tested via the
  **NetworkChuck Cloud Browser**. (paraphrase)
- (2024-09-11) For the secret-prize countdown, hiding a code client-side is hard: a plain
  crypto-js **AES** example leaves the key visible in the source, so the AI's fix was a
  **time-based encryption key** with the secret split into multiple separately-encrypted
  pieces. Chuck is upfront that he is "not a programmer" and leans on the AI for the
  security design. (paraphrase)
- (2024-09-11) The world's-longest-URL mechanic relies on DNS limits: a second-level domain
  label caps at ~63 characters, so length is gained by chaining subdomains up to the ~253
  character total domain limit (including the periods). (paraphrase; Chuck states these as
  his understanding)
- (2024-09-11) **Ship-fast / creativity lesson**: the point of building isn't utility —
  "because I can, it's fun" — and the act of doing and creating is itself where you find
  ideas and inspiration; so just go build something, no matter how dumb. (paraphrase)
- (2024-09-11) Security caveat: sites built this fast are not secure (don't expose API
  keys); a follow-up video covers hacking them. (paraphrase)

## Notable verbatim quotes

> Now, joking aside, you get a lot of features for four bucks a month, a free domain. You
> can build your website with WordPress, be hosting your website builder with AI or just
> code your own website and upload it.

> Now, I know you're probably wondering, Chuck, why are you creating all these websites?
> What's the point? Because I can, it's fun.

> And in the process of building a website like this, you might actually find some really
> great ideas. Sometimes just by the act of doing and creating, you find your inspiration.
> So go create some right now.

> All these websites we made were made very quickly and they're not exactly secure, so
> don't do things like exposing your API keys.

> First, I used YTDL to pull down some of my YouTube video transcripts. Then I pasted all
> those transcripts into an LLM and it found all my good quotes, which I then stored into a
> MySQL database, a website with HTML, CSS, JavaScript, and a PHP script.

> That's 24 websites in 24 hours. This was a dumb idea and way too much work. I'll see you
> in the next one.

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: crystallizes a recurring Chuck belief — "just by the act of doing and creating, you find your inspiration" / build-because-it's-fun — plus his AI-first, non-programmer "prompt → paste → deploy" workflow; both are persona-relevant for beliefs.md and ai-tools topics. -->
