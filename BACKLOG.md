# BACKLOG — everything still open in this project

**How to use this in a NEW session:** just say _"Read BACKLOG.md and summarize what's
still open."_ This is the single human-readable checklist of all planned work. Tick
`[x]` when done; keep it current after each work block. (Machine state of truth for
sources stays in `pipeline/ledger.csv`; this file is the plain-language overview.)

**Snapshot:** _(not bootstrapped yet — run `/clone-setup <Full Name>`)_

---

## A. Bootstrap — OPEN
- [ ] Run `/clone-setup <Full Name>` (identity check → SUBJECT.md → biography research
      → source map → taxonomy → channel enumeration → first commit)

## B. Video ingest — blocked on A
- [ ] Drain P1 (landmark), then P2 long-form per channel (ingest loop)
- [ ] P3 guest content with attribution pass
- [ ] Shorts dedup (dupes → skipped with `dup-of:`, new → L2)
- [ ] Retry rows flagged `429` / `no-captions` / `unavailable`
- [ ] Checkpoint synthesis every ~10 batches / channel boundary (see E)

## C. Books / courses / landmark documents — blocked on A
- [ ] Identify what exists (bootstrap research fills this in)
- [ ] Obtain texts from the user → `raw/books/` → L3 ingest

## D. Other sources — blocked on A
- [ ] Websites/blog · press · X · Instagram · LinkedIn · podcast feeds · newsletters

## E. Synthesis / persona — ongoing once B starts
- [ ] Keep synthesis debt drained (`python tools/synthesis_batch.py status`)
- [ ] Recompile `persona/system-prompt.md` after every persona-touching pass (bump version)
- [ ] Persona-QA sessions → feed `wiki/gaps.md`
- [ ] Final lint when the corpus drains

## F. Multi-clone future — see VISION.md
- [ ] More people, each in its own repo built from this template
- [ ] Clones as cooperating agents (shared data contract, knowledge never mixed)

## Deferred re-ingest (recorded 2026-07-23, Stage C complete)
The corpus is otherwise fully drained (445 L2 sources). These legit videos could NOT be fetched this run and are marked `skipped` with `DEFERRED`/`no-captions` notes — re-ingest when possible (ledger makes it exact):
- **Rate-limited (persistent 429, captions exist):** `yt-lUzSsX4T4WQ` pfSense (6.4M), `yt-Jfvg3CS1X3A` 40 Windows Commands (4.3M), `yt-BSplICgr7iU` block-adult-sites (P2), `yt-WhoTqIuURy4` CCNA Tips ft. Cioara (P3). Retry with authenticated yt-dlp / cookies / PO-token or after a longer cooldown.
- **No captions (would need Whisper — needs user approval):** `yt-croxobxz1bU` massive Twitter hack, `yt-BJFxMDxG_KY` tools to learn Python/Linux/Cisco, `yt-isMnWZqAh0k` What is SD-WAN, plus earlier: DDNS-Cloudflare, Puppet-for-Net-Engineers, CCNA-2-exams-or-1, 2020 'feeling stupid today'.
