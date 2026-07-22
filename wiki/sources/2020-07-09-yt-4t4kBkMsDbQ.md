---
type: youtube-video
source_date: 2020-07-09
url: https://www.youtube.com/watch?v=4t4kBkMsDbQ
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, networking]
tags: [nmap, scanning, vulnerabilities, pentest, ethical-hacking, tutorial]
---

# Nmap Tutorial to find Network Vulnerabilities

## Summary

A hands-on introductory tutorial on Nmap (Network Mapper), framed as part of Chuck
Keith's ongoing "journey to become a hacker." He positions Nmap as a free, essential
tool used by hackers (and IT pros generally) for the **scanning and enumeration** phase
of hacking. Working from Kali Linux against hosts on his own lab networks, he
demonstrates progressively richer scans: host discovery (ping sweep), port scanning
(full-open TCP connect vs. stealth SYN scan), OS detection, aggressive all-in-one
scanning, decoy obfuscation, timing control, and finally the Nmap Scripting Engine to
run vulnerability (CVE) checks. Along the way he teaches the underlying networking
concept — the **TCP three-way handshake** — and shows the actual packets in Wireshark
to contrast a full connect scan against a stealth scan. He maps the workflow to the
EC-Council CEH scanning/enumeration methodology (modules three and four) and repeatedly
plugs sponsor IT Pro TV. He targets a deliberately vulnerable VM (KioptriX from
VulnHub) for the vuln-scan demo, and stresses this is a quick overview, not a deep dive.

## Key claims (dated 2020-07-09 unless noted; paraphrase)

- Nmap (Network Mapper) is a free tool used to scan networks to find live hosts
  (targets) and to gather more information about them — a process called
  **enumeration**. It installs on Windows, macOS, and Linux; the demo uses Kali.
- **Host discovery / ping sweep:** `nmap -sP <network>` performs a ping scan across a
  whole network. Against his home network `10.7.1.0/24` (a /24 = up to 254 possible
  hosts) it found 15 hosts up in ~2.71 seconds — far faster than pinging each host by
  hand with `ping`.
- **Scanning methodology:** he follows the EC-Council model — step one is checking which
  systems are alive; step two is checking for open ports.
- **Port scanning (full/TCP connect):** `sudo nmap -sT -p 80,443 <network>` scans for
  specific ports across the network. Ports 80 and 443 are the typical web ports; if a
  host shows them open it is probably a web server. `-sT` is a **TCP connect scan** (aka
  full-open scan) that completes the full TCP three-way handshake.
- **TCP three-way handshake (the mechanism behind port scanning):** the client sends a
  **SYN** ("are you there, on this port?"), a listening host replies **SYN-ACK** ("yes,
  I'm here"), and the client replies **ACK** to establish the connection. Nmap uses this
  exchange to determine whether ports are open.
- **Stealth / SYN scan:** `sudo nmap -sS -p <ports> <network>` is a stealth scan (aka
  SYN scan or half-open scan). Instead of completing the handshake, after receiving the
  SYN-ACK Nmap does not send the final ACK — it "walks away," never establishing a full
  connection, to try to avoid firewalls/IDS (intrusion detection systems). Caveat: modern
  security/firewalls have gotten more advanced and can sometimes still detect this.
- **Default port scan:** if you don't specify ports, Nmap scans the top 1,000 (most
  popular) ports by default; scanning a single host this way took ~0.17 seconds in the demo.
- **Wireshark validation:** capturing a full-connect (`-sT`) scan shows SYN → SYN-ACK →
  ACK, then an **RST** flag (reset) to end the TCP conversation. A stealth (`-sS`) scan
  shows SYN → SYN-ACK → then Nmap resets/backs out without completing the connection.
- **OS detection:** `sudo nmap -O <host>` enables OS detection. It first pings, then
  checks ports via the handshake, then guesses the OS (fairly accurately). It correctly
  identified a Linux machine, and on a Windows domain controller it detected **Windows
  Server 2012 R2** (and found many open ports typical of a domain controller).
- **Aggressive scan:** `sudo nmap -A <host>` is a combo scan — it runs OS detection
  (`-O`), version detection of protocols, script scanning, and traceroute. On a Linux
  target (~128 seconds) it revealed the SSH host key and SSH version, Apache on port 80,
  Red Hat Linux, file sharing, and a traceroute. On a Windows host (~307 seconds) it
  surfaced protocol versions, SSL certificate details including the common name and
  expiration, and SMB (file share) information. Pressing Enter during a long scan shows
  progress percentage.
- **Decoy / obfuscation:** `sudo nmap -sS -D <decoy_IP> <target>` adds decoy source
  addresses. Nmap sends the real scan packets plus duplicated packets spoofing the decoy
  IP as the source, so anyone reviewing traffic sees scans coming from multiple hosts and
  can't easily tell which one is the real scanner.
- **Nmap Scripting Engine (NSE) — vuln scanning:** `sudo nmap --script vuln <host>` runs
  every script in the `vuln` category (instead of naming a single script), checking hosts
  for known vulnerabilities via **CVEs** (Common Vulnerabilities and Exposures). The demo
  run took ~106 seconds and found multiple vulnerabilities that could then be exploited.
- **Timing / speed control:** scan speed can be lowered to avoid detection; the default
  timing template is **T3** (normal). Slower templates reduce the chance of detection
  (Chuck admits he lost patience with slower speeds and went faster).
- **Target VM:** the deliberately vulnerable box used for the vuln demo is **KioptriX**,
  a downloadable VM from **VulnHub** designed to be legally hacked for practice (comes in
  five versions with walkthroughs and challenges).
- **Certification context:** to earn the CEH (or other hacking certs) you need to know
  Nmap well beyond this overview; scanning and enumeration are EC-Council course modules
  three and four. He advises putting the switches on note cards, practicing them, and
  labbing them while understanding the underlying networking.

## Notable verbatim quotes

> "in map or network mapper is the tool used by hackers to scan network so we can find
> live host or find targets to hack and we can also use this tool to find out more
> information about these targets a process called enumeration"

> "S is for stealthy that's actually the type of scan that says it's a stealth scan or
> often referred to as a sin scan or a half-open scan as opposed to the full open scan
> that we just did"

> "the rules for starting and establishing this conversation are often referred to as
> the three-way handshake and it's what nmap actually uses to do all its magic"

> "psych nevermind I don't want to have that connection that session established I don't
> want to get caught I'm just poking my head in the window looking around and I'm coming out"

> "it'll scan to see if they have vulnerabilities that we could exploit that's what I'm
> talking about that's hacking automation right there"

> "I'm not a hacker yet I know that but I got just a little bit closer today by studying
> in map scanning and enumeration"

*(Note: "in map" is a caption artifact for "nmap"; "sin scan" is the caption's rendering
of "SYN scan.")*

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: Nmap scanning tutorial (ethical-hacking teaching) -->
