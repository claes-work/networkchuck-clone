---
type: youtube-short
channel: "@NetworkChuck"
url: https://www.youtube.com/watch?v=YFKhcnMjliI
source_date: 2023-06-08
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, networking]
tags: [https, tls, chrome, lock-icon, certificates, disposable-browser]
---

# "Chrome is removing the lock icon!?" (2023-06-08)

## Summary

A myth-busting short: the browser **lock icon does not mean a website is safe** — it only
means the connection uses HTTPS. Chuck notes that most malicious sites now also use HTTPS
/ signed certificates, so the lock gives false assurance. He explains that Google Chrome
(as of version 117) will remove the lock icon and replace it with a new icon you can still
click to check the HTTPS/certificate status. He shows how to preview the change early via
Chrome Canary by enabling the `chrome-refresh-2023` flag at `chrome://flags`, then closes
by recommending testing sketchy links in a disposable cloud browser that spins up a
throwaway Docker container.

## Key points

- 2023-06-08 — The lock icon only indicates HTTPS is in use; it does NOT mean the site is
  safe.
- 2023-06-08 — Most malicious sites now also use HTTPS / signed certificates, so the lock
  is not a trust signal.
- 2023-06-08 — Chrome 117 removes the lock icon, replacing it with a new clickable icon
  that still shows HTTPS/certificate status.
- 2023-06-08 — You can preview the change now in Chrome Canary: `chrome://flags` →
  `chrome-refresh-2023` → set to Enabled → relaunch.
- 2023-06-08 — Recommends testing sketchy links in a disposable cloud browser that launches
  a throwaway Docker container in the cloud.

## Notable verbatim quotes

> "the lock icon the thing you see when you visit a website and it tells you it's safe and secure to visit that website false it doesn't mean it's safe"

> "that lock icon does mean you're using https but it doesn't mean the website is safe most bad websites now use science certificates they use https"

## Guest attribution

No guests. Single-speaker short; all statements attributed to Chuck Keith (NetworkChuck).
The closing "networks.cloud browser" mention is a self-promo for his own disposable-browser
service, not a paid third-party sponsor. Transcript renders "signed certificates" as
"science certificates" (auto-caption artifact); quoted verbatim as heard.
