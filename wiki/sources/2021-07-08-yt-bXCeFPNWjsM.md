---
type: youtube-video
source_date: 2021-07-08
url: https://www.youtube.com/watch?v=bXCeFPNWjsM
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, linux-terminal]
tags: [reverse-shell, netcat, pentest, ethical-hacking, lab]
---

# how to get remote access to your hacking targets // reverse shells with netcat (Windows and Linux!!)

## Summary

Chuck teaches the concept of a **reverse shell** using **netcat** (`nc`), framed
strictly as an ethical-hacking skill to practice against your OWN lab machines. He
opens and closes with the ethics disclaimer: this is for educational purposes only,
you have no permission to hack anyone, try it only on yourself / your own home
network.

The core concept: the goal is remote command-line ("shell") access to a target, but
the target usually sits behind a home/enterprise **router firewall** that blocks most
inbound connections. Firewalls, however, generally allow **outbound** connections (a
target visiting a website is trusted). A reverse shell flips the direction — instead
of the attacker connecting to the target, the target connects out to the attacker,
sliding past the firewall. The attacker sets up a **listener** (waiting on a port);
the target runs a payload that dials home and hands over a shell.

He demos this conceptually in three lab scenarios, all with a cloud VM (Linode) as the
attacking/listening machine: (1) a Linux target (Kali) connecting back; (2) a Windows
target using built-in **PowerShell** to pull and run a script that connects out; and
(3) a Hak5 **LAN Turtle** — a small USB-powered Linux dongle running netcat — plugged
into a network to auto-phone-home. He ties the idea to real-world malware: a reverse
shell/payload is a basic form of a **RAT (remote administration tool)**, which is how
"grandma clicking a phishing link" gets compromised — motivating the sponsor pitch for
endpoint protection (Bitdefender). He stresses this is an entry point to a big topic
(payloads, Metasploit/Meterpreter) and a skill used constantly on CTFs (TryHackMe,
Hack The Box) and in professional pentesting.

## Key claims

- (2021-07-08) A **reverse shell** is remote shell access achieved by having the
  *target* connect out to the *attacker*, rather than the attacker connecting in — the
  workaround for firewalls that block inbound but permit outbound connections.
  (paraphrase)
- (2021-07-08) A home/enterprise **router firewall** normally protects the target by
  blocking most *inbound* connections; outbound connections (e.g. visiting a website)
  are generally trusted and allowed through. (paraphrase)
- (2021-07-08) The attacker's role in a reverse shell is passive: set up a **listener**
  on a chosen port and *wait* for the target to connect, rather than initiating the
  connection. (paraphrase)
- (2021-07-08) **netcat** (`nc`) is a long-standing, general-purpose tool — the
  "network Swiss army knife," used by sysadmins for scanning and file transfer — whose
  most popular hacking use is reverse shells; it ships by default on most Linux
  distros. (paraphrase)
- (2021-07-08) Choosing a listener port under the ~1000 well-known ports helps avoid
  firewall detection. (paraphrase)
- (2021-07-08) On Windows, no netcat install is needed — built-in **PowerShell** can be
  used to download and run a script that opens the outbound connection back to the
  listener. (paraphrase)
- (2021-07-08) In practice the connect-back command is delivered as a **payload** —
  e.g. dropped via a phishing email/script and run automatically — and may go far
  beyond simple netcat (Metasploit, Meterpreter, etc.). (paraphrase)
- (2021-07-08) A reverse shell is a basic form of a **RAT (remote administration
  tool)** — the mechanism by which real malware gains persistent remote access to
  victims. (paraphrase)
- **Ethics (2021-07-08):** This is for educational purposes only; you do NOT have
  permission to hack anyone for any reason — practice ONLY on yourself, your own home
  network, or intentionally-vulnerable lab platforms (TryHackMe, Hack The Box, CTFs).
  (paraphrase)
- (2021-07-08) It's a required, frequently-used skill for anyone becoming an ethical
  hacker / penetration tester. (paraphrase)

## Notable verbatim quotes

> "as always when i'm showing you these hacking tools this is for educational purposes
> only you do not have permission to hack anyone for any reason so just don't do it but
> i do want you to try this on yourself i want you to try it on your own home network"

> "since we can't connect to our target and access his shell what if we had our target
> connect to us ... yeah that's what a reverse shell is where instead of us trying to
> connect to him he connects to us"

> "the firewall is blocking most inbound connections blocking us but you know what he's
> not blocking he's not blocking connections going out"

> "netcat is not a new tool it's been around for a long time ... the network swiss army
> knife"

> "we're going to set up a listener ... hey we're listening for a connection for anyone
> to come here and we're going to specify a certain port that we're listening on"

> "this is a basic form of what's called a rat or a remote administration tool it's
> what hackers use to gain remote access to their victims"

> "we gotta hack youtube today but we gotta do it ethically like everything we do"

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: reverse-shell concept teaching (lab/ethics) -->
