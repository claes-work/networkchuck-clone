---
type: youtube-video
source_date: 2024-08-28
url: https://www.youtube.com/watch?v=NiQTs9DbtW4
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [networking]
tags: [dns, name-resolution, fundamentals, internet]
---

# What is DNS? (and how it makes the Internet work)

## Summary

A canonical NetworkChuck fundamentals explainer walking through the Domain Name
System (DNS) end to end: why browsers need it, how a name resolves to an IP address,
and every server in the resolution chain. Chuck frames DNS as a phone contacts app —
you know a name (`academy.networkchuck.com`) but not the "phone number" (IP address),
so your browser has to look it up. He then traces a full query for
`academy.networkchuck.com`: stub resolver → cache check → recursive DNS server
(e.g. Google `8.8.8.8`) → root servers ("mafia bosses") → TLD servers (`.com`) →
authoritative name server (CloudFlare, "Pablo") → the A record and IP address.

The second half covers DNS security (plaintext UDP port 53, sniffing, DNS spoofing,
ISP visibility; and defenses DoH, DoT, DNSCrypt, DNSSEC), a tour of common record
types (A, NS, AAAA, MX, PTR, CNAME, TXT/SPF/DKIM/DMARC), how domain registration works
(registrar, ICANN, WHOIS, name-server delegation), and running your own recursive DNS
server at home (AdGuard on a Raspberry Pi, Pi-hole). Twingate is the sponsor, featured
for its Secure DNS (enforced DoH) and DNS filtering features.

## Key claims (dated — the concepts)

_All dated 2024-08-28 (video publication). Paraphrase unless quoted._

- To visit a website you need the IP address of the server it lives on; the browser
  doesn't know it, so DNS maps human-readable domain names to IP addresses. [analogy: name→phone number]
- DNS is vital to the internet — without it websites, email, and most internet services break; DNS failures are a common cause of outages.
- **Stub resolver**: the DNS client running on your own machine. It first checks the local cache; if the IP for a recently visited site is cached, no external query is needed.
- If not cached, the stub resolver queries a configured **DNS server** — set manually or handed out by the network's DHCP server. A common public one is Google at `8.8.8.8`.
- **Recursive DNS server**: may not know a given IP directly, but resolves it by making multiple requests to other DNS servers on your behalf (and may also serve from its own cache).
- **Root servers** ("mafia bosses"): top of the DNS hierarchy. Run by 12 organizations (e.g. NASA, DoD, Verisign), operating 13 named server authorities across ~1,865 servers worldwide. They only handle **top-level domains (TLDs)** and delegate — they return the list of TLD servers responsible for, e.g., `.com`, rather than any final IP.
- **TLDs**: the rightmost label (`.com`, `.net`, `.co`, `.coffee`) plus country codes (`.jp` Japan, `.ph` Philippines).
- **TLD servers** (e.g. `gtld-servers.net` for `.com`): keep a database of the authoritative name servers for **second-level domains (SLDs)** — e.g. `networkchuck` in `networkchuck.com`. They return which server is authoritative for that SLD.
- **Authoritative name server** (CloudFlare, nicknamed "Pablo" for `networkchuck.com`): holds the **zone file**, starting with an **SOA (Start of Authority)** record, and knows the actual A record / IP address. It answers the final query.
- Once resolved, the recursive server caches the answer and returns the IP to the stub resolver. Example resolved IP: `104.18.40.42` / `104.18.41.39`.
- A **subdomain** (the `academy` in `academy.networkchuck.com`) is to the left of the SLD and can point that URL to a different location than the main site.
- All of this happens on every visit to a new site, effectively instantly and invisibly.
- **Security problem**: by default the stub resolver queries DNS over **UDP port 53 in plaintext** (unencrypted). An attacker in the middle can sniff which sites you visit, and can perform **DNS spoofing** (impersonate a DNS server and return a malicious IP). Your ISP can also see your DNS queries.
- **DoH (DNS over HTTPS)**: sends DNS queries over the encrypted HTTPS channel — hidden and disguised among normal web traffic, so it can't be identified by filtering on UDP port 53. Requires both client (browser) and DNS server support; CloudFlare/Google support it.
- Other DNS-security options: **DoT** (DNS over TLS), **DNSCrypt**, **DNSSEC** (a suite validating that queries/responses are authentic, not just encrypted), and filtering resolvers like **Quad9** that block known-malicious domains.
- **Record types**: A (name→IPv4), NS (authoritative name server for an SLD), AAAA (name→IPv6), MX (mail exchanger — which servers handle a domain's email), PTR (pointer / reverse DNS — IP→domain, used for verification/security), CNAME (canonical name — alias one domain to another; `www.` is typically a CNAME), TXT (text records).
- **TXT records** were originally admin notes; now vital for email security: **SPF** (lists which mail servers are legitimate for a domain), **DKIM** (verifies mail wasn't altered in transit), **DMARC** (policy for handling mail failing SPF/DKIM). NetworkChuck Academy has a DMARC course.
- **Registering a domain**: buy from a **domain registrar** (e.g. Squarespace, which acquired Google Domains). **ICANN** (Internet Corporation for Assigned Names and Numbers) sits above the root servers — it governs DNS, delegates who can be a TLD server, and accredits registrars.
- You can use the registrar as your name server, or delegate to another (e.g. CloudFlare) by setting NS records; the registrar then updates the TLD registry with those NS records. Owner details are stored in the **WHOIS** database (can be made private for a fee).
- You can run your own **recursive DNS server** at home — it caches A records and forwards unknown lookups to an upstream server. Chuck runs **AdGuard** on a Raspberry Pi (upstreams to Quad9/CloudFlare/Google); **Pi-hole** is another popular option, and both can block ads.

## Notable verbatim quotes

> "Your web browser is kind of dumb."

> "You have to know the IP address of the server it lives on. It's essentially its phone number and your web browser doesn't know it."

> "That is DNS the domain name system. Your browser doesn't know Bernard's phone number or the IP address for academy.network chuck.com, so it has to check its contacts, and in this case that'll be a DNS server."

> "He'll use his stub resolver, which sounds hilarious. I love saying that."

> "He may not know all the IP addresses for every website, but he knows a guy who knows the guy who can tell him."

> "Now the next step involves some mafia bosses. Yes, DNS does have a hierarchy, and at the very top are the DNS mafia bosses. I'm not kidding. They're called the Roots."

> "These are the bosses. They don't deal with the peasant work of domain to IP address mapping. They're all big picture."

> "What does it mean they handle the top level domains? Well, it means they're lazy. They delegate everything."

> "This is done in plain text, meaning it's not encrypted. It's naked for all the world to see."

> "Not only is it hidden, it's wearing a costume. It's wearing an H TT PS costume."

> "DNS is hiding in a crowd of people. It's like, where's Waldo? Except he's not wearing a bright shirt. He's just as a regular person, you would never know."

> "At the risk of making this video way too long. I don't care. It's my video. And if you're still here, thank you so much. You're awesome. Let's take a little sip of coffee together."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: canonical DNS explainer + teaching analogy (voice) -->
