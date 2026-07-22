---
type: youtube-video
source_date: 2022-05-16
url: https://www.youtube.com/watch?v=UtMMjXOlRQc
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, cloud-devops]
tags: [python, malware, ethical-hacking, education, defense, lab]
---

# i created malware with Python (it's SCARY easy!!)

## Summary

Educational security video in which Chuck builds a simple ransomware proof-of-concept
in Python to demonstrate — conceptually — how malware works, so viewers can understand
and ultimately defend against it. The whole exercise is framed as lab-only and
educational, opening with an explicit disclaimer and closing with a "don't be evil"
message.

The teaching arc has two parts. First, Chuck walks through the *concept* of ransomware:
a program that walks a directory, encrypts every file it finds using a symmetric key
(the video uses Python's `cryptography` Fernet, which Chuck notes is AES-128 symmetric
encryption), and then demands payment for the key. He emphasizes the mechanics that
make it dangerous — it hits essentially every file it can access across a computer or
network, and victims can only recover with the key. He also builds a matching decrypt
script (adding a "secret phrase" gate) to complete the loop and show that encryption is
reversible only when you hold the key. Second, he points viewers to a public GitHub
"malware showcase" repository containing labeled example categories (adware, droppers,
file infection, ransomware, spyware, Trojan, worms) as a study resource for seeing how
different malware families are structured in code.

The defensive/ethical throughline is heavy and repeated: run only on a disposable Linux
box you're willing to destroy (Chuck spins up a cheap cloud Linux server for exactly
this), keep everything backed up and recoverable, never point it at anyone, and treat
the whole thing as learning how attacks work in order to defend. The recurring practical
lesson for defenders: backups and recoverability are what neutralize ransomware, since
the attack's power is denying access to your only copy of the data.

## Key claims (paraphrase; dated 2022-05-16)

- Ransomware works by encrypting/locking a victim's files and withholding the decryption
  key until a ransom (often cryptocurrency/Bitcoin) is paid. [concept]
- Ransomware is one of the most damaging malware types; Chuck says companies he has
  worked at spent days recovering from ransomware attacks. [concept]
- Its danger comes from scale — it will encrypt essentially every file it can access,
  which on a server or network can mean nearly everything. [concept]
- Fernet (Python `cryptography`) is a symmetric encryption method using AES-128; the
  same key both locks and unlocks, so whoever holds the key controls the data. [concept]
- Real-world ransomware is far more complex than this demo, but the underlying mechanism
  is the same "encrypt files, hold the key" pattern shown here. [concept]
- Understanding how malware is written and structured is the point of the exercise —
  learning the offense in order to defend against it. [defense]
- Recoverability is the counter: the demo only "works" as an attack because the victim
  loses access to their data; if everything is backed up and recoverable, the leverage
  is gone. [defense]
- This is for educational purposes only — learn it, play with it, but never use it for
  malicious purposes; "don't be evil." [ethics]
- Only run malware on a throwaway/disposable Linux box (Chuck uses a cheap cloud Linux
  server), or otherwise inside an isolated Python virtual environment — never on a
  machine you care about. [ethics/lab]
- Even joking with friends/family requires making sure everything is recoverable and
  backed up first. [ethics]

## Notable verbatim quotes

> "This is for educational purposes only. Sure. Learn it, play with it. Go crazy with
> it, but never use it for malicious purposes."

> "You'll need a Linux computer or a Linux server. And preferably one you feel
> comfortable blowing up... 'cause you're gonna be installing malware and running it."

> "Ransomware is one of the most dangerous and devastating malware out there. It's taken
> down companies, even companies I've worked at. We've spent like days and days trying
> to recover from malware ransomware attacks."

> "It'll take files, any file, and it will encrypt them or lock them up. And the only
> way you can access your data is if you have the key."

> "Typical ransomware does get much more complex, but at the bones of it, this is how it
> works."

> "So don't do it to anybody, please. Like maybe as a joke to your friends and family,
> but like, make sure everything's recoverable and backed up."

> "The purpose of this video was to help you understand kind of how it works and how
> it's written in code."

> "Please only play with it if you're using a throwaway Linux box, like we just did...
> otherwise they do show you how to set up a virtual environment."

> "This is for educational purposes only. Don't hurt anybody. Don't be evil."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT). (A brief scripted
"professor Bernard" voice-over defines Fernet as symmetric AES-128 encryption; this is a
narration device within Chuck's own video, not an independent guest.)

<!-- ★ L3-candidate: Python-for-security (understand malware to defend) — lab/ethics framing -->
