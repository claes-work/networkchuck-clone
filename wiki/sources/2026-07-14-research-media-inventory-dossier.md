---
type: web-research
source_date: 2026-07-14
ingested: 2026-07-14
tags: [media-inventory, pipeline, enumeration, channels, podcast, socials, products, community]
---

# Media inventory dossier — Chuck Keith / NetworkChuck (as of 2026-07-14)

Phase-2 consolidation of the full media surface of the SUBJECT (Chuck Keith, publicly
known as **NetworkChuck**) — IT / networking / cybersecurity / Linux / homelab educator
and YouTuber. YouTube channel IDs and rough item counts come from yt-dlp enumeration on
2026-07-14 (authoritative for IDs; counts are yt-dlp `--flat-playlist` line counts, so
they lag the channel's live "videos" number slightly and exclude age-gated/region-blocked
items). Everything else was verified or extended via web research on 2026-07-14. Every
number carries its as-of date and source. Follower/subscriber counts are
platform-self-reported or third-party-tracker estimates unless noted; nothing here is
registry-verified.

## YouTube channels (yt-dlp enumeration, 2026-07-14)

Channel IDs obtained via
`yt-dlp --skip-download --playlist-items 1 --print channel_id "<url>"`; tab counts via
`yt-dlp --flat-playlist --print "%(id)s" "<url>/{videos,shorts,streams}" | wc -l`.

| Channel | Handle | Channel ID | Subs | Content (videos / shorts / streams) | Role | Status |
|---|---|---|---|---|---|---|
| NetworkChuck | [@NetworkChuck](https://www.youtube.com/@NetworkChuck) | `UC9x0AN7BWHpCDHSm9NiJFJQ` | 5.26–5.30M (2026-07-14) | 376 / 145 / 86 (= **607 items**) | **Main corpus** | **TARGET** |
| NetworkChuck (2) | [@networkchuck_v2](https://www.youtube.com/@networkchuck_v2) | `UCOuGATIAbd2DvzJmUgXn2IQ` | 77,200 (2026-07-14) | 38 / 8 / 1 (= **47 items**) | Second / overflow channel | **TARGET** |
| NetworkChuck Shorts | [@NetworkChuckShorts](https://www.youtube.com/@NetworkChuckShorts) | `UC_ItZIvwnRb_y1ludSDJo8g` | 109 (2026-07-14) | 0 / 4 / 0 (= **4 items**) | Near-dormant shorts stub | EXCLUDED (uncertain) — see below |
| (unnamed) | [@ChuckKeith](https://www.youtube.com/@ChuckKeith) | `UCE5hGeRUfyCA80BBHgvkYDg` | 65 (2026-07-14) | 0 / 181 / 0 | Auto-titled shorts, no branding | EXCLUDED (unverified) — see below |

Subscriber figures for the main channel: vidIQ 5.27M, Social Blade 5.26M (both
2026-07-14; [socialblade.com](https://socialblade.com/youtube/handle/networkchuck),
[vidiq.com](https://vidiq.com/youtube-stats/channel/UC9x0AN7BWHpCDHSm9NiJFJQ/)). The
channel's public "videos" tally is ~607 (Social Blade, 2026-07-14), consistent with the
376+145+86 tab split above (yt-dlp counts trailing videos it can list flatly).

**Channel-role notes (critical for the ledger):**
- **@NetworkChuck** is the primary corpus. Chuck Keith is the sole on-camera host on
  essentially all uploads; guest/collab episodes exist but Chuck fronts the channel, so
  speaker attribution is far simpler here than on multi-host channels — still apply
  fidelity rule 6 on interview/podcast crossposts and guest cameos.
- **@networkchuck_v2 ("NetworkChuck (2)")** is a genuine official second channel — its
  video descriptions cross-link back to main-channel uploads
  (`"Watch the main channel video: youtube.com/watch?v=…"`, verified via yt-dlp
  description field 2026-07-14). It carries overflow / experimental / longer-cut content.
  TARGET, but treat as a secondary tier: enumerate, ingest Chuck-fronted items.
- **@NetworkChuckShorts** (name "NetworkChuck Shorts", 109 subs, only 4 shorts) is
  **not** linked from the official Linktree and is effectively empty. Likely an
  abandoned official experiment or a same-name fan stub. Marked EXCLUDED-uncertain: near-zero
  corpus value either way; do not enumerate unless a later check confirms official
  ownership.
- **@ChuckKeith** (UCE5hGeRUfyCA80BBHgvkYDg) has **no channel name**, 65 subscribers, and
  181 shorts with auto-generated date-string titles (sample: "# # # 2026/7/14"; uploader/
  channel fields blank via yt-dlp, 2026-07-14). Despite matching Chuck's legal name, there
  is **no branding, no description, and no link from any official NetworkChuck property**.
  Treated as EXCLUDED (unverified / almost certainly not the subject). Do not enumerate.

No dedicated official **clips** channel exists as of 2026-07-14 (probed
`@NetworkChuckClips`, `@NetworkChuckClip(s/z)`, `@NetworkChuck2`, `@NetworkChuckPodcast`,
`@NetworkChuckLive` — all HTTP 404). Short-form clips live on the main channel's `/shorts`
tab, on TikTok, and on Instagram Reels.

## Podcast — "noobs // a NetworkChuck Podcast"

- **RSS feed**: `https://feeds.soundcloud.com/users/soundcloud:users:343336834` —
  hosted on **SoundCloud** (feedUrl returned by the Apple Podcasts Lookup API,
  `itunes.apple.com/lookup?id=1307833174`, fetched 2026-07-14).
- **Episode count**: **115** episodes as of 2026-07-14 (Apple Lookup API `trackCount`,
  and [feedspot](https://podcast.feedspot.com/audiochuck_podcasts/) / Spotify listing).
  Weekly cadence.
- **Directories**: Apple `id1307833174`
  ([podcasts.apple.com](https://podcasts.apple.com/us/podcast/noobs-a-networkchuck-podcast/id1307833174)),
  Spotify show `5M6OGk2kqVcjVrUR4MPKoT`
  ([open.spotify.com](https://open.spotify.com/show/5M6OGk2kqVcjVrUR4MPKoT)),
  Podtail / Podnews (`podnews.net/podcast/ia0s9`), Podbay (`podbay.fm/p/networkchuck`).
- **Format**: conversational IT/career/tech show; Chuck co-hosts with **Cameron**
  (recurring co-host — flag as a `wiki/entities/` context person). Guest interviews
  appear. Author field: "NetworkChuck" (Apple Lookup, 2026-07-14).
- **Dedup rule (binding for the ledger)**: many podcast episodes are also published as
  YouTube uploads/streams (main channel + @networkchuck_v2). **YouTube is the primary
  ingestion source.** Podcast feed items enter the ledger only when no matching YouTube
  upload exists (match on title + publish week); matched items stay L1 with
  `dup-of:<youtube-id>`. Attribute Cameron vs. Chuck before anything flows into
  `voice.md`/`beliefs.md`.

## Products, sites & community

### NetworkChuck Academy — [academy.networkchuck.com](https://academy.networkchuck.com/)
Paid membership learning platform. **700+ lessons** and growing; new FREE lessons every
Friday; member subscription tier ([academy.networkchuck.com/program/member-subscription](https://academy.networkchuck.com/program/member-subscription),
2026-07-14). Hosts flagship structured courses, incl. the **Cisco CCNA course**
(`academy.networkchuck.com/cisco-ccna`) and an **A+ series**. This is the productized,
paywalled version of the free YouTube teaching — high persona relevance for course
titles/structure, but lesson video content is gated (not enumerable via yt-dlp).

### NetworkChuck Coffee — [store.networkchuck.com](https://store.networkchuck.com/) / networkchuck.coffee
E-commerce store run by **NetworkChuck LLC** on Shopify (designed by Just Create It
Digital; fulfilled via Printful / SPOD / dropship — store footer, 2026-07-14). Sells
single-origin coffees with IT-pun names ("Default Route", "200 OK", "On-call", ~$16.99)
plus branded merch (tees incl. "NetworkGHOUL", mugs). Tagline: "the official coffee for
IT professionals." **Newsletter**: monthly ("Be the first to know about new products…
One newsletter every month.") — product/marketing newsletter, not an editorial content
newsletter.

### NetworkChuck Cloud Browser — [browser.networkchuck.com](https://browser.networkchuck.com/)
SaaS product: on-demand disposable browser instances running in cloud containers for
anonymity + malware isolation (zero-trust, remote execution, global locations). ~$7/mo.
Built on **Kasm Workspaces** (Kasm hosts a co-branded demo,
`kasm.com/networkchuck-demo-welcome`). Ships **Chrome** and **Firefox** companion
extensions ([Chrome Web Store](https://chromewebstore.google.com/detail/networkchuck-cloud-browse/biedjndngchodkcemghdooopmdmpjbdc),
[Firefox add-on](https://addons.mozilla.org/en-US/firefox/addon/networkchuck-cloud-browser/)).
Docs at `browser.networkchuck.com/docs/latest/`.

### networkchuck.ai — [networkchuck.ai](https://networkchuck.ai/)
AI-focused property (verified live 2026-07-14). Scope not fully enumerated; likely AI
tooling / AI-course front. Flag for later verification.

### Discord community
- **Main community**: [discord.com/invite/networkchuck](https://discord.com/invite/networkchuck)
  — **98,097 members** (2026-07-14).
- **Academy Discord**: [discord.com/invite/ntck-ac](https://discord.com/invite/ntck-ac)
  — **6,143 members** (2026-07-14).

### Other official links (from [linktr.ee/networkchuck](https://linktr.ee/networkchuck), 2026-07-14)
- **Amazon storefront**: [amazon.com/shop/networkchuck](https://www.amazon.com/shop/networkchuck) (gear recommendations).
- **ntck.co** — official URL shortener / affiliate-redirect domain (e.g. `ntck.co/boson`,
  `ntck.co/EpicPen`, `ntck.co/mobiledevices`). Not content; used to resolve affiliate/course links.
- Affiliate/partner links (Boson NetSim, Raspberry Pi, EpicPen, Hostinger, Bitdefender,
  SysAid, IPRoyal) — context for sponsor/monetization mapping, not corpus.

## Socials

| Platform | Handle | Count | As of | Source | Confidence |
|---|---|---|---|---|---|
| YouTube (main) | [@NetworkChuck](https://www.youtube.com/@NetworkChuck) | 5.26–5.30M subs | 2026-07-14 | yt-dlp + Social Blade + vidIQ | High. Flagship platform. |
| Instagram | [@networkchuck](https://www.instagram.com/networkchuck/) | 754,000 | 2026-07-14 | web search snippet of profile | Medium. |
| TikTok | [@networkchuck](https://www.tiktok.com/@networkchuck) | 622,900 | 2026-07-14 | web search snippet of profile | Medium. Primary short-form clip outlet. |
| Facebook | [/NetworkChuck](https://www.facebook.com/NetworkChuck/) | 475,000 | 2026-07-14 | web search snippet | Medium. |
| X / Twitter | [@NetworkChuck](https://x.com/networkchuck) | 255,500 | 2026-07-14 | web search snippet | Medium. X blocks scraping; treat as approximate. |
| LinkedIn (personal) | [/in/chuckkeith](https://www.linkedin.com/in/chuckkeith/) | 124,859 followers | 2026-07-14 | web search snippet | Medium. Posts as "Chuck Keith — NetworkChuck", Dallas-Fort Worth. |
| LinkedIn (company) | [/company/networkchuck](https://www.linkedin.com/company/networkchuck) | ~26,221 followers | 2026-07-14 | web search snippet | Medium. Brand page, tagline "Hack Your IT Career". |
| Twitch | [twitch.tv/networkchuck](https://www.twitch.tv/networkchuck) | count not established | 2026-07-14 | Linktree + TwitchTracker (numbers not fetchable) | Low. Used for live "study-with-me" / hangout streams; existence confirmed, follower count unresolved. |
| Linktree | [linktr.ee/networkchuck](https://linktr.ee/networkchuck) | n/a (link hub) | 2026-07-14 | direct fetch | High. Canonical index of official links. |

Aggregate self-description (2026-07-14): "6M+ followers across YouTube, TikTok,
Instagram, LinkedIn and X; Top 1% of cybersecurity creators"
([favikon.com](https://www.favikon.com/blog/who-is-chuck-keith), promotional — treat as
self-reported). Growth anchor: a LinkedIn post celebrated "200k subs and 5 years of
NetworkChuck" (~2019), useful for dating the channel's early trajectory.

## Enumeration universe — what feeds pipeline/ledger.csv

Ledger population order and dedup precedence (all counts as of 2026-07-14):

1. **@NetworkChuck YouTube** — 376 videos + 145 shorts + 86 streams = **607 items**
   (yt-dlp). Primary corpus. Shorts dedup against long-form (`dup-of:<id>`); streams are
   P3 long-tail (live study sessions, hangouts, Q&As — real persona value, low density).
2. **@networkchuck_v2 YouTube** — 38 + 8 + 1 = **47 items**. Secondary tier; cross-linked
   to main. Ingest Chuck-fronted items; dedup crossposts against the main channel.
3. **Podcast "noobs"** (SoundCloud feed `soundcloud:users:343336834`) — **115 items**;
   only episodes without a YouTube match get their own ledger rows; the rest L1
   `dup-of:<youtube-id>`. Attribute Chuck vs. co-host Cameron.
4. **NetworkChuck Academy** — 700+ gated lessons + named courses (CCNA, A+). NOT
   enumerable via yt-dlp; ledger the **course catalog** (titles/structure) as L1 metadata,
   not individual lessons.
5. **Excluded YouTube**: @NetworkChuckShorts (4 items, unverified/empty),
   @ChuckKeith (181 auto-titled shorts, unverified) — **do not enumerate**.
6. **Socials** — not primary corpus; short-form (TikTok/IG/Shorts) mostly re-cuts of
   long-form. Sample opportunistically for voice, dedup against source video.

Rough total primary enumeration universe: **~654 YouTube items** (main + v2) +
~115 podcast items (mostly dedup'd) + course-catalog metadata.

## Dedup & attribution rules (binding)

- **YouTube is canonical.** Podcast audio, Shorts, TikTok/IG/FB re-cuts that mirror a
  YouTube upload stay L1 with `dup-of:<youtube-id>`; match on title + publish week.
- **Shorts** (145 on main) are near-all clipped from long-form → dedup first.
- **Streams** (86) are P3 long-tail.
- **Co-host attribution**: the "noobs" podcast is co-hosted with **Cameron**; guest
  episodes and collab videos feature other creators (e.g. David Bombal, John Hammond
  crossovers appear in search) — attribute per speaker before persona ingest (fidelity
  rule 6). Only Chuck-attributed material trains the persona.
- **Self-reported vs. verified**: follower/subscriber counts and "6M+ / Top 1%" claims are
  self-reported or third-party-tracker estimates — always marked as such; none
  registry-verified.
