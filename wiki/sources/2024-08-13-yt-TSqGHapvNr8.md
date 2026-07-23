---
type: youtube-short
channel: "@NetworkChuck"
source_date: 2024-08-13
url: https://www.youtube.com/watch?v=TSqGHapvNr8
ingested: 2026-07-22
tier: L2
domains: [cybersecurity]
---

# Hackers are looking at your website (Short)

## Summary

A fast rundown of web-enumeration techniques attackers use to profile a target website: directory and subdomain brute-forcing, fingerprinting the tech stack, and mining publicly exposed files and source. Framed as reconnaissance Chuck is practicing while studying for Hack The Box's CPTS exam.

## Key points

- 2024-08-13 — Gobuster (with a wordlist such as SecLists) is used to find website directories, and in DNS mode to enumerate subdomains.
- 2024-08-13 — `curl -I` or WhatWeb quickly reveals what a website is running.
- 2024-08-13 — An SSL/TLS certificate can leak details about the site and its owner; `robots.txt` shows pages the developer wants hidden — which is exactly where an attacker looks.
- 2024-08-13 — Ctrl+U views a page's source code ("the Matrix of this website's code").
- 2024-08-13 — Chuck says he is studying for Hack The Box Academy's CPTS ("certified penetration testing specialist") exam. <!-- ★ L3-candidate: ongoing cert-journey / HTB CPTS study thread — candidate for certifications-career persona timeline -->

## Notable verbatim quotes

- "hit control U on your keyboard bam you're in The Matrix of this website's code"
- "the robots.txt file is used by web developers to tell Google what pages on your site it's allowed to crawl… hackers can look at that file and go I probably want to look at the ones you don't want me to look at"

## Guest attribution

No guest. Single speaker (Chuck Keith).
