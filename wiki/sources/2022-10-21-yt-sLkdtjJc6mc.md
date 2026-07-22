---
type: youtube-video
source_date: 2022-10-21
url: https://www.youtube.com/watch?v=sLkdtjJc6mc
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, linux-terminal]
tags: [steganography, exif, image-forensics, osint, privacy]
---

# i hacked this photo

## Summary

Chuck demonstrates **steganography** — the technique of embedding or hiding secret
messages and files inside innocent-looking carrier files such as photos. He frames it
with a real-world case: an espionage-focused threat actor that targeted Middle Eastern
governments by hiding malware inside the Windows logo image, which inspired him to test
whether he could hide malware in a photo and sneak it past anti-malware software
(sponsor: Bitdefender).

The tutorial uses the `steghide` tool (available for Mac, Windows, and Linux) to hide a
secret text message inside a photo, then extract it. As a running gag / real prize,
Chuck hides GPS coordinates inside a photo and sends it to his daughters — decoding it
leads to a physical location with two Apple Watches. He installs `steghide` on Linux via
`sudo apt install steghide -y` and on Windows via the downloaded package, then uses
`steghide embed -ef <file> -cf <photo>` to embed and `steghide extract -sf <photo>` to
extract, both protected by a passphrase. `steghide` compresses and encrypts the hidden
payload by default.

He then explains the underlying mechanics: many steganography tools use the **LSB (least
significant bit)** method — flipping the last bit of each pixel's color bytes so the
change is imperceptible, spreading the payload's bits across the whole image. Because
only a tiny amount of data hides per pixel, a large cover file is needed (roughly an
8 MB photo to hide 1 MB of data with LSB). `steghide` itself does not use LSB (LSB is
easily detected) but instead uses a **graph-theory**-based approach that resists
detection. Finally he embeds real malware in a photo, uploads it to GitHub to sneak it
past storage-provider scanning, downloads it on a Windows machine — and when he extracts
the payload, Bitdefender immediately catches and quarantines it, closing on the privacy
and protection sponsor message.

## Key claims

- (2022-10-21) **Steganography** is a technique used to embed or hide secret messages
  and secret files inside innocent-looking carrier files such as photos; the hidden data
  is invisible to the eye and often to malware-detection software. (paraphrase)
- (2022-10-21) A real espionage-focused threat actor targeting Middle Eastern
  governments hid malware inside the Windows logo image — the inspiration for the video.
  (paraphrase)
- (2022-10-21) Tool: **`steghide`** — available for Mac, Windows, and Linux — hides
  (embeds) a file inside a cover file and extracts it back out. (paraphrase)
- (2022-10-21) Install on Linux: `sudo apt update` then `sudo apt install steghide -y`;
  on Windows: download the package, unzip/extract, and open the folder in a terminal
  (command becomes `steghide.exe`). (paraphrase)
- (2022-10-21) Embed command: `steghide embed -ef <embed file> -cf <cover file>`, then
  set a passphrase. By default `steghide` **compresses and encrypts** the hidden payload.
  (paraphrase)
- (2022-10-21) Extract command: `steghide extract -sf <stego file>` (plus a `-xf`
  switch to name the output file), then enter the passphrase; the recipient also needs
  `steghide` installed to decode it. (paraphrase)
- (2022-10-21) The embedded photo looks identical to the original. (paraphrase)
- (2022-10-21) `steghide` can hide files inside audio files too, not just photos.
  (paraphrase)
- (2022-10-21) **LSB (least significant bit)** method: computers represent image pixels
  as binary; tools flip the last (least significant) bit of each color byte — an
  insignificant change — and spread the file's data across all the pixels. (paraphrase)
- (2022-10-21) Because only one small piece of data is stored per pixel, a large cover
  file is required — roughly an 8 MB photo to hide 1 MB of data via LSB; too-small cover
  files fail. (paraphrase)
- (2022-10-21) `steghide` does not use LSB (which is easily detected by anti-malware);
  it uses a **graph-theory**-based method that is harder to detect. (paraphrase)
- (2022-10-21) A photo with malware hidden inside can be uploaded to services that
  normally scan for and remove malware (e.g. Amazon) because the payload is concealed —
  detection can be avoided at the storage/transfer stage. (paraphrase)
- (2022-10-21) Lesson: the malware stayed undetected inside the photo through download,
  but **Bitdefender detected and quarantined it the moment it was extracted** — endpoint
  protection catches the payload when it is unpacked. (paraphrase)
- (2022-10-21) Ethics/awareness: "this right here is for educational purposes only" —
  don't hack anyone; know that attackers can hide payloads in images so you protect
  yourself. (paraphrase)
- (2022-10-21) OSINT angle: GPS coordinates hidden in a photo can be pasted into a phone
  Maps app to navigate to a physical location. (paraphrase)

## Notable verbatim quotes

> "inside this image I've hidden a virus malware you probably can't tell can you and
> neither can your computer or most malware detection software this is steganography a
> technique used to embed or hide secret messages and secret files inside stuff like
> this something that isn't secret"

> "the goal of steganography is to hide these files in this photo to where you don't
> notice it but they do still have to change something to be able to hide it"

> "they're changing all the pixels code to hide bits and pieces of that data that is nuts"

> "if our malware was one megabyte with LSB we would need an eight megabyte photo to hide
> it in"

> "steghide it doesn't actually use LSB you see LSB it can be pretty easily detected by
> computers by anti-malware software so steghide will use something called graph theory"

> "this is something I recommend you not do don't hack anyone for any reason this right
> here is for educational purposes only"

> "bitdefender got it it was quick too like immediately oh and it moved that sucker right
> into quarantine so we were able to actually get the photo onto our computer undetected
> but once extracted bitdefender was like no not today"

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
