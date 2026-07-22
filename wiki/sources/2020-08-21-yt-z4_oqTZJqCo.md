---
type: youtube-video
source_date: 2020-08-21
url: https://www.youtube.com/watch?v=z4_oqTZJqCo
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, linux-terminal]
tags: [hashcat, password-cracking, kali-linux, hashing, ethical-hacking]
---

# how to HACK a password // password cracking with Kali Linux and HashCat

## Summary

A beginner ethical-hacking tutorial in which Chuck Keith demonstrates password
cracking against a "coffee server" whose only known account is `dwight.schrute`. He
walks through the progression from manually guessing passwords (a brute-force attack)
to two smarter, tool-driven methods: an **online dictionary attack** with **Hydra**
against a live SSH service, and an **offline hash-cracking attack** with **HashCat**
against captured password hashes. Along the way he explains what a hash is, why servers
store hashed (not plaintext) passwords, and how a dictionary attack works by hashing
each candidate word and comparing it to the stored hash. He frames the whole exercise
defensively — the lesson is why strong, uncommon passwords matter — and repeatedly
stresses that this is for educational use only and is illegal without explicit
permission. The video ends with a challenge inviting viewers to crack his server (first
five win coffee). Sponsored by ITProTV.

## Key claims (paraphrase unless quoted)

- **[2020-08-21] Technique — brute force is the baseline but inefficient.** Manually
  trying every possible password (000000, 000001, …) in sequence is technically a
  brute-force attack; every method shown is a form of brute force, but there are far
  more efficient variants. Trying passwords by hand could take years.
- **[2020-08-21] Technique — dictionary attack with Hydra (online).** Hydra automates
  login attempts against a live service. Instead of trying every possible string, you
  feed it a word list of likely passwords (a dictionary attack). Command shape shown:
  `hydra -l dwight.schrute -P wordlist.txt <host> ssh` — lowercase `-l` for a single
  username (uppercase `-L` for a username file), uppercase `-P` for a password file,
  and a service type (ssh, ftp, telnet, etc.). It cracked the password `bears beats`
  quickly from a small list.
- **[2020-08-21] Tool — the rockyou.txt word list.** Kali Linux ships with the
  `rockyou.txt` word list at `/usr/share/wordlists/`, containing ~14 million passwords.
  It comes from the 2009 RockYou breach, where passwords were stored in plain text and
  later released. Unzip with `sudo gzip -d rockyou.txt.gz`.
- **[2020-08-21] Defensive lesson — online attacks are noisy and detectable.** Many
  live login attempts can trip firewalls, get your IP blocked, hit timeouts, or lock
  out the account — which is both a limitation for the attacker and a defensive
  control that protects the target.
- **[2020-08-21] Concept — hashing and why passwords aren't stored in plaintext.**
  Servers don't store passwords like `bears beats`; they run them through a one-way
  hashing algorithm and store the resulting hash. On login the server hashes the
  submitted password and compares hashes. Common algorithms named: MD5, SHA-256,
  SHA-512, and NTLM (Windows). Hashes can't be reverse-engineered — but they can be
  brute-forced by hashing candidate words and comparing.
- **[2020-08-21] Defensive lesson — proper hashing limits breach damage.** If a site
  stores hashes (not plaintext like RockYou did) and gets breached, attackers get the
  hash list, not the actual passwords — buying time and protection. This is how sites
  *should* store passwords.
- **[2020-08-21] Technique — offline cracking with HashCat.** HashCat cracks captured
  hashes offline without touching the target. Key flags shown: `-a 0` selects attack
  mode 0 (straight/dictionary word list); `-m` selects the hash type by numeric code
  (e.g. `0` = MD5, `1000` = NTLM, `1800` = SHA-512 Unix, `5700` = Cisco); `-o
  <file>` writes cracked results to an output file. On Linux, password hashes live in
  the `/etc/shadow` file. It cracked `bears beats` from a small list almost instantly.
- **[2020-08-21] Technique — cracking a Windows/NTLM hash.** Demonstrated
  `sudo hashcat -a 0 -m 1000 -o crackedpasswords.txt "<hash>" wordlist.txt`, passing a
  single hash inline (in quotes) instead of a hash file, then reading the result with
  `sudo cat crackedpasswords.txt`.
- **[2020-08-21] Hardware — GPUs make offline cracking fast.** A beefy gaming PC with a
  strong CPU and GPU can grind through massive word lists of millions of passwords,
  making offline cracking far more powerful than online attempts.
- **[2020-08-21] Defensive lesson / ethics — cracking is illegal without permission.**
  These techniques are for educational use only; using them without explicit permission
  is illegal. Practice only on your own passwords, your own lab, or the server Chuck
  explicitly authorizes for the challenge.

## Notable verbatim quotes

> "please don't go hack somebody else without the permission... only hack me you need to learn learn learn hacking"

> "so what we were just doing is traditionally called a brute force attack... now to be fair every attack i'm going to show you is technically a brute force attack but we refer to them in different ways."

> "providing hydra with a list of passwords is called a dictionary attack and this is crazy effective because it has a list of common passwords that a lot of people might use."

> "this company rock you got hacked back in 2009 and these hackers released all their passwords they found which were stored in plain text."

> "this crazy mess of numbers and letters is called a hash. so when dwight created this password bears beats the coffee server hashed it basically put in his mouth chewed it up and spit it out."

> "this should be how most websites and services out there are storing your passwords, not in plain text like the roku server... so if they do get hacked and hackers get that list of usernames and passwords they don't have your password."

> "now again we can't reverse engineer it but we can brute force our way into it."

> "and again please do not use this in any way that's illegal... unless you have someone's explicit permission to do this it's illegal. hack yourself hack your own passwords hack me."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: password-cracking tutorial + defensive framing -->
