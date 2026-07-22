---
type: youtube-video
source_date: 2014-10-19
url: https://www.youtube.com/watch?v=8rVzrPzhXnA
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [networking]
tags: [cucm, cisco, voip, collaboration, hunt-group, early-era]
---

# How to Create a Hunt Group - CUCM 8/9/10

## Summary

One of Chuck Keith's earliest YouTube videos — a hands-on Cisco Unified
Communications Manager (CUCM) VoIP tutorial recorded from his day job as an
enterprise voice/collaboration engineer. This is origin-era content that documents
his professional specialty before the later networking/homelab/IT-career brand: he
walks through building a **hunt group** in the Cisco Unified CM Administration web
portal (running CUCM 10.5, noted applicable to 10.0, 9, 8 and earlier).

The tutorial teaches the three-tier, bottom-up structure Cisco requires — **line
group → hunt list → hunt pilot** — using real production examples from his workplace
(a sales team, a call center, a help desk). He covers distribution algorithms
(top-down, circular, longest idle, broadcast), RNA (Ring No Answer) reversion
timeout, no-answer/busy hunt options, voicemail overflow, and the queuing feature
introduced in CUCM 9/10 (with its gotchas around broadcast and automatic hunt-member
logout). He ends by placing a live test call to his iPad to demonstrate the finished
hunt pilot.

The delivery is already recognizably his — casual, first-person, self-deprecating
about his own testing mess, promising a follow-up video and asking viewers to comment
and subscribe.

## Key claims

All dated 2014-10-19 (paraphrase unless quoted):

- **Why use a hunt group instead of a shared line.** With a shared line, everyone
  has the same extension; an incoming call appears on hold across every phone that
  has that extension, which is messy. A hunt group gives each person their own
  extension and "hunts" through numbers based on the configured routing, so a
  connected call exists only on the phone that answered — cleaner.
- **Hunt groups have three elements, built bottom-up.** Line group (bottom tier) →
  hunt list → hunt pilot. You must create the line group first, then the hunt list,
  then the hunt pilot; you cannot start in the middle or from the top.
- **Configuration path.** Cisco Unified CM Administration → Call Routing → Route/Hunt →
  Line Group / Hunt List / Hunt Pilot.
- **RNA reversion timeout.** Sets how many seconds a call rings at a phone before
  moving on. For anything other than broadcast, keep it short (he uses ~10–15
  seconds, roughly 3 rings ≈ 3–4 seconds each); for broadcast he uses ~30 seconds.
- **Distribution algorithms.** Top-down (rings members in listed order — his most
  common choice), circular (starts from where the last call left off), longest idle
  time (call goes to whoever hasn't taken a call the longest), and broadcast (rings
  every phone in the line group simultaneously for the specified time — used for his
  sales group's first-come-first-served handling).
- **Hunt options on no answer / busy / not available.** Try next member, try next
  member then try next group in hunt list, skip remaining members and go to next
  group, or stop hunting. He keeps the defaults ("try next member, then try next
  group in the hunt list") and says he's never needed to change them.
- **Automatic logout on no answer (CUCM 9/10).** A new option that logs a hunt member
  out of the group if they don't answer. It does NOT work with broadcast, but works
  with top-down, circular, etc.
- **Adding line group members.** Search by directory number (DN) or select a
  partition, add to line group, and reorder with the up/down arrows (order matters
  for top-down); the down-arrow removes a member. Save.
- **Hunt list.** Add New, name/describe it, check "Enable this Hunt List", then add
  the line group(s) to it. "For Voice Mail Usage" is only for Cisco Unity voicemail
  integration (voicemail ports), not used here. After adding a line group you must
  Save and Reset to apply changes; resetting drops any calls currently ringing
  through but not calls already connected.
- **Hunt pilot.** Add New, enter the hunt pilot DN (any directory number you want
  routed to it, e.g. via a translation pattern), choose the route partition matching
  your calling search space / class-of-control rules, add a description, and select
  the hunt list it will use.
- **Alerting name (CUCM 9/10).** A feature he loves for his 20–30-hunt-pilot call
  center: it lets the answering agent see what the call is for / where it's from,
  which previously required tricky workarounds.
- **Hunt pilot forward/overflow options.** On no answer or busy after the hunt
  process ends, you can drop the call, use the line group member's settings, or route
  to a specified destination (he typically sends to a voicemail port, e.g. 7777, with
  the correct calling search space). Maximum hunt timer defaults are typically 120
  seconds — total time to hunt the entire process, useful when a large top-down list
  with per-member reversion times would otherwise run too long.
- **Queuing (CUCM 9/10).** Configure music-on-hold (MOH), maximum number of callers
  allowed in queue (default 32), what to do when the queue is full (typically
  voicemail), maximum wait time in queue (~15 minutes by default, can be lowered), and
  what happens when max time is met or no members are logged in/registered (voicemail).
- **Queuing gotchas.** Queuing does NOT work with the broadcast distribution
  algorithm, and it will NOT work unless "automatically log out on no answer" is
  checked in the line group. Without that checkbox, an unanswered call obeys the
  no-answer settings (goes to voicemail) instead of staying in the queue. The downside:
  users get logged out and need a way to know and to log back in — e.g. a dedicated
  hunt-group login/logout line button that lights when logged in and dims when out
  (and can show hunt-group stats on CUCM 9/10). He warns queuing was unworkable for
  his help desk because agents forgot they'd been logged out and stopped getting calls.
- **Route Plan Report.** Gives a bird's-eye view of the hunt pilot, hunt list, and
  line group numbers together, and lets you jump to and edit each — his recommended
  way to view the phone system.
- **Follow-up promised.** A future video on creating a hunt-group login/logout button
  on the phone.

## Notable verbatim quotes

> "welcome to uh Network Chuck um today I'm going to show you how to ... create hunt
> groups um and Hunt groups comprised of hunt Pilots hunt list and line groups"

> "a hunt group everyone gets their own extension and a hunt group will ... kind of
> hunt through the numbers uh based on whatever routing you have configured"

> "so Cisco kind of does things in a hierarchical um view of things especially with
> their phone system so to create a hunt group there's really three elements first is
> your line Group which is kind of the bottom tier then your hunt list and then your
> hunt pilot you have to create your line group first then your hunt list and then
> your hunt pilot otherwise you can't ... start in the middle you have to start at the
> bottom"

> "longest idle time very cool feature it will catch uh John ... whoever ... hadn't
> taken a call in the longest amount of time is going to get that call first"

> "queuing does not work on broadcast ... also if you do not have the checkbox for
> automatically log out on no answer in your line group it will not work"

> "when I did set it up for like my help desk ... they would often not answer calls
> because they were working on something and they would forget and they would never
> get calls and then people be in the queue and just be a nightmare so ... you got to
> have caution you might have to train your users a little bit"

> "and that ladies and gentlemen is how you create a hunt pilot and or a hunt group"

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: earliest era — Cisco CUCM/collaboration VoIP tutorial (his origin specialty) -->
