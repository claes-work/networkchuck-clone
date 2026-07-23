---
type: youtube-short
channel: "@NetworkChuck"
url: https://www.youtube.com/watch?v=PbDtgXRsCuE
source_date: 2023-07-13
ingested: 2026-07-22
tier: L2
domains: [cybersecurity]
tags: [steganography, steghide, encryption, ctf]
---

# "can my daughters decode this?!?" (2023-07-13)

## Summary

A quick demo of **steganography** using the `steghide` tool on the Linux terminal.
Chuck hides secret GPS coordinates (leading to a prize — two Apple Watches) inside a
photo, then sends the photo to his daughters as a decode challenge. He shows both the
embed and extract sides of the workflow: `steghide embed` with a `-ef` (embed file) and
`-cf` (cover file) plus a passphrase, and `steghide extract` with `-sf` (stego file) and
the same password to recover the hidden file. The recipients also need `steghide`
installed to extract. (Family framing is self-reported; the daughters are not named.)

## Key points

- 2023-07-13 — `steghide embed` uses `-ef` for the embedded (secret) file and `-cf` for
  the cover file (the carrier photo); a passphrase is set at embed time.
- 2023-07-13 — Extraction uses `steghide extract -sf <photo>` plus the passphrase to
  recover the hidden file.
- 2023-07-13 — The recipient must also have `steghide` installed to extract the secret.
- 2023-07-13 — Practical use shown: hiding secret coordinates / a prize challenge inside
  an innocuous-looking image (self-reported family demo).

## Notable verbatim quotes

> "I'm gonna hide secret coordinates inside this photo at these coordinates will be a prize two apple watches"

> "now this is important in order for them to decode this they will also need stag hide installed to extract that secret file"

## Guest attribution

No guests. Single-speaker short; all statements attributed to Chuck Keith (NetworkChuck).
Family reference (daughters) is self-reported; children are intentionally left unnamed.
