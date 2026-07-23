---
type: youtube-video
source_date: 2023-03-30
url: https://www.youtube.com/watch?v=Kq0BMVhbFkA
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [homelab-selfhosting, certifications-career]
tags: [help-desk, ticketing, osticket, self-hosting, it-support]
---

# host your own HelpDesk

## Summary

A self-hosting tutorial in which Chuck walks through standing up two open-source
help-desk / ticketing systems for personal use: **Peppermint** (his simpler pick) and
**UVdesk** (the more feature-rich pick). Both are deployed with Docker / Docker Compose,
either on-prem (server, NAS, or spare laptop) or in the cloud (his preferred host,
Linode / Akamai). The framing ties directly to IT careers: the help desk is "the first
step most of us take" into IT, and dealing with tickets is the core of that job, so
Chuck encourages viewers to self-host a ticketing system for family and friends both as
practice and as a resume line. Running gag throughout: an office printer that coworker
"Michael" still hasn't fixed, and the demand "Do you have a ticket?"

## Key claims (dated — setup + concept)

Concept:
- The help desk is usually the first/entry-level job people take when getting into IT,
  and it revolves around answering and dealing with tickets. (2023-03-30)
- Getting familiar with the *idea* of a ticket and documentation matters more than
  knowing the ins and outs of any one ticketing product. (2023-03-30)
- Naming other ticketing tools that exist in the field: CIS Aid, ServiceNow, Zoho, and
  "a million others" — the two he demos are just accessible self-host options. (2023-03-30)
- Self-hosting your own ticketing software for family and friends is a resume-worthy
  talking point. (2023-03-30)
- A knowledge base (a UVdesk feature) is valuable because solved tickets can be
  documented so junior admins / teammates can search and self-solve recurring issues. (2023-03-30)

Setup — hardware / host:
- Self-hosting needs hardware: either on-prem (server, NAS, spare laptop — anything that
  can run Docker) or the cloud. Chuck runs both ticketing systems on Linode. (2023-03-30)
- Everything is Docker-based to keep it easy. (2023-03-30)
- On Linode's marketplace, Peppermint is available as a one-click app; he picks Ubuntu,
  a nearby region (Dallas), and the Nanode 1GB shared-CPU plan (~$5/month). (2023-03-30)

Setup — Peppermint:
- One-click Linode deploy runs as a Docker container; confirm with `docker ps` and note
  the port. On the Linode marketplace deploy it serves on port 5001, reachable via the
  Linode's reverse DNS (rDNS) name plus `:5001`. (2023-03-30)
- To install anywhere else: install Docker and Docker Compose (`apt install
  docker.io docker-compose -y`), make a `peppermint` directory, `cd` in, create a
  `docker-compose.yml`, paste the config from Peppermint's GitHub, and run
  `docker-compose up -d`. In that Compose deploy it serves on port 5000. (2023-03-30)
- Peppermint default login: username `admin@admin.com`, password `1234`. (2023-03-30)
- Peppermint demo flow: add a user (Michael), create a ticket assigned to an engineer,
  set urgency; the engineer's dashboard shows open tickets and lets him add notes, edit,
  transfer, or mark complete. Chuck praises it for being simple / not overly complex —
  good for family and friends. Creator credited: Jack Andrews (a side project). (2023-03-30)

Setup — UVdesk:
- Deployed via SSH to the Linode using a Docker Compose file adapted from a Marius
  Hosting guide; same pattern (mkdir `uvdesk`, cd, nano `docker-compose.yml`, paste,
  `docker-compose up -d`). (2023-03-30)
- UVdesk runs two containers (it uses MySQL) and serves on port 80 (reached via rDNS);
  a web installer walks through DB connection and creating a super-admin account. (2023-03-30)
- UVdesk is more feature-filled — including a built-in knowledge base — aimed at users
  who "really want to geek out." (2023-03-30)

## Notable verbatim quotes

> Say this with me. Do you have a ticket?

> if you're wanting to get into it, which is the best job in the entire world, the help desk is usually the first step most of us take. And on the help desk, you're gonna be answering and dealing with a lot of tickets. So why not start now?

> put on your resume, Hey, I self-host my own ticketing software for my family and friends. That's pretty cool.

> one of my goals in this video is not for you to like know the ins and outs of every single ticketing software, but just to become familiar with the idea of a ticket documentation

> as you solve tickets for your company, there might be a certain ticket you solved that needs to go into the knowledge base cuz you might see that issue over and over and over. So new people that come in, junior admins or even other people on your team can be like, oh, I'll just search the knowledge base and I can solve that problem.

> be your own it for your family and friends, but always say, do you have a ticket.

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
