---
type: youtube-video
source_date: 2024-09-16
url: https://www.youtube.com/watch?v=VcqtWsbSbgU
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, linux-terminal]
tags: [steganography, encryption, file-hiding, opsec]
---

# Hide your files like a hacker (5 Ways)

## Summary

A tutorial walking through five progressively more advanced techniques for hiding
files on a computer, "starting with the simplest methods that anyone can do and ending
with hacker level techniques." Chuck demonstrates each method live (on Windows, with
Linux/Mac notes), covers cross-platform tools (VeraCrypt, Steghide via WSL), and then
reverses each method to show how a defender can detect the hidden files. Framed around
his usual coffee-brewing interludes and Harry Potter / Jurassic Park file names. The
closing pitch is stacking all five methods together for maximum concealment. Sponsored
by hCaptcha Enterprise.

## Key claims (dated — the 5 methods)

All dated 2024-09-16 (paraphrase unless quoted).

1. **Basic hidden attribute / visual obfuscation (Method 1).** Set a file's "hidden"
   attribute via right-click > Properties > Hidden (Windows), which removes it from
   normal view. A folder can also be made effectively invisible by renaming it with the
   blank special character `ALT + 255` and swapping its icon to a blank icon. On
   macOS/Linux, prefixing a file name with a dot (`.`) hides it; `ls -a` reveals it.
   Detection: enable "show hidden files, folders, and drives" on Windows, or use
   `ls -a` on Linux/Mac; scripts (PowerShell/Linux) can search for hidden files.
2. **Misdirection via file extension (Method 2).** Rename a file to a misleading
   extension so the OS can't open it and observers are fooled — e.g. rename a `.jpg` to
   `.txt`, or zip a file and rename the archive to `.pdf`. Detection: scripts that
   inspect file signatures / magic bytes (e.g. JPEG headers starting `0xFF 0xD8`) reveal
   a file masquerading as another type.
3. **Alternate Data Streams (ADS) (Method 3, Windows-only).** An NTFS feature that
   stores additional data inside a file without changing its visible size or primary
   content. Hide with `type secret.txt > host.txt:secret.txt` in Command Prompt (cmd,
   not PowerShell); read it back with `notepad host.txt:secret.txt`. Described as "a fan
   favorite of hackers." Detection: `dir /r` lists the alternate data streams.
4. **Encrypted hidden containers (Method 4).** Use VeraCrypt (open-source,
   cross-platform, downloaded from veracrypt.fr) to create an encrypted file container
   that mounts as a virtual drive. Chuck creates a *hidden* VeraCrypt volume — a volume
   inside a volume with two separate passwords — so under coercion you can reveal a
   decoy outer volume while the real data stays hidden ("plausible deniability").
   Setup: AES encryption, SHA-512 hashing, 1 GB outer / 500 MB hidden volume. Detection
   is hard, but the container file is unusually large; a script listing files over
   ~100 MB can flag suspicious files — though without the password the contents stay
   inaccessible, and the hidden inner volume may never be discovered.
5. **Steganography (Method 5).** Hide a file inside a picture or audio file using
   Steghide (open-source, cross-platform). On Windows, Steghide doesn't install
   natively, so run it via WSL (`sudo apt install steghide`); on Mac it's difficult
   (alternatives like OpenStego exist). Embed with
   `steghide embed -cf <coverfile> -ef <file-to-hide>`; extract with
   `steghide extract -sf <coverfile>`. It alters the least significant bits (LSBs) so
   changes are imperceptible to eye or ear. The hidden file must be smaller than the
   cover file. Chuck nests it: a diary inside a photo, then the photo inside a `.wav`
   audio recording. Detection: tools like StegDetect scan images/files for traces of
   steganography — hard to find, but it "does leave a trace."

Closing recommendation: for maximum concealment, chain all five — rename the file, put
it in an alternate data stream, hide it inside a photo with steganography, then place it
inside a hidden encrypted VeraCrypt container.

## Notable verbatim quotes

> "Here are the top five ways you can hide your files in your folders on your computer,
> starting with the simplest methods that anyone can do and ending with hacker level
> techniques and we'll also reverse it. I'll show you how you can detect hidden files."

> "This method is a fan favorite of hackers."

> "This is a virtual drive mounted on our computer masquerading as a text file. It's wild."

> "So the idea is that if you've been caught, you're being held hostage and you've got
> secret information and someone's like put in the password... And you put in the fake
> password for the outer shell and it opens up and they're like, what is this for fun?
> This is an empty file. Okay, I guess you had nothing to hide."

> "With steganography, we're hiding a file inside things like pictures and even audio
> like a song."

> "It'll use the least significant bits or the LSBs to alter these files to store some
> data inside, but alter it in a way to where no one would really notice."

> "If you want to go crazy, you can use all five in one. Go. Hide your files, rename
> them, put them inside an alternate data stream, hide them inside a photo with
> steganography, and then put them inside a virtual container with VeraCrypt."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
