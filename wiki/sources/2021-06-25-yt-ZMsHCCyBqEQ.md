---
type: youtube-video
source_date: 2021-06-25
url: https://www.youtube.com/watch?v=ZMsHCCyBqEQ
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [homelab-selfhosting, cloud-devops, creator-coffee-business]
tags: [nas, hybrid-cloud, youtube-business, self-hosting, learn-x-now, bio]
---

# You need a NAS RIGHT NOW!! (How I run my Hybrid-Cloud YouTube business)

## Summary

A "learn X RIGHT NOW" homelab explainer in which Chuck makes the case that everyone —
personal users and businesses alike — needs a NAS (network attached storage) instead of
relying on external USB hard drives. He defines a NAS as networked storage accessed over
the home network/Wi-Fi (no USB), and frames three reasons he ditched his external drives:
(1) he ran out of storage, (2) he was scared of losing data on a single point of failure,
and (3) he needed access to his files everywhere, all the time, from any computer — for
himself and his video editors.

The video doubles as a reveal of how Chuck runs his own YouTube business on a hybrid-cloud
setup. He walks through his Synology hardware ladder (from the ~$200 single-/dual-bay
DS-series he gives editors, up to his own 16-bay enterprise RS4021xs+ rackmount), explains
RAID/RAID 5/SHR redundancy, and demonstrates his hybrid-cloud workflow: a private cloud
(Synology NAS) plus public cloud (Google Drive via Google Workspace) using Synology Cloud
Sync. He shows how files dropped on his NAS auto-sync to the cloud AND auto-sync directly
to his editors' own Synology units at their houses (Drive ShareSync), giving both instant
delivery and off-site backup. He also demos QuickConnect remote access, secure file
sharing, Active Backup for Business (PC/VM/ESXi/Hyper-V backup), Central Management System
for managing multiple NAS units, and "bonus" homelab uses (Plex, Docker, VMs, LDAP, DNS,
iSCSI datastore for ESXi, Synology Drive, high availability). The video is a paid
collaboration with Synology (disclosed).

## Key claims (paraphrase unless quoted; dated 2021-06-25)

**NAS concept**
- A NAS (network attached storage) is like an external hard drive, but the key difference
  is it is accessed over the network/Wi-Fi rather than plugged in via USB.
- The most common RAID level he recommends for a NAS is RAID 5: it combines multiple disks
  into one logical disk and survives a single drive failure without data loss (you replace
  the failed drive and the array rebuilds).
- On his personal NAS he uses SHR (Synology Hybrid RAID) instead, which he says adds
  redundancy while helping save space.
- "Two is one, one is none" — a single drive is a single point of failure; he has lost data
  this way before, which is why he switched to NAS.

**His hardware ladder (Synology)**
- His enterprise NAS is a Synology RS4021xs+: 16 built-in drive bays (expandable to 40),
  an 8-core Xeon, and two 10-gig Ethernet ports.
- It reports ~20.9 TB available in a RAID 5 with data protection (a "danger" flag shown is
  only because he uses non-official-list drives, which he does not recommend).
- The small unit he gives his video editors is a Synology DS220j (~$200, two internal
  drives, 4 TB each = 8 TB); he also cites a DS120j single-bay as the smallest entry point.
- He positions the product tiers as: J-series (home) → Plus series (small/mid business) →
  SA/XS/FS series (enterprise, measured by IOPS).

**How he runs his YouTube business (hybrid-cloud — BIO)**
- His NAS is "crucial to how I run my YouTube business"; he depends on Synology for his
  business every single day.
- He runs hybrid cloud: private cloud (his Synology) + public cloud (Google Drive), using
  Synology Cloud Sync so anything placed on the NAS is immediately uploaded to the cloud.
- He has ~17 TB stored in Google Drive.
- He runs his business on Google Workspace (business Gmail + Drive); paid business accounts
  gave unlimited Drive storage at ~$10/month per user — he calls it a "hack" and notes for
  a while it was just him with unlimited storage.
- He has gigabit internet and a 20-gig internal link, making local NAS transfers "wicked fast."
- Workflow with editors: he keeps folders on his NAS synced (Synology Drive ShareSync)
  directly to a Synology NAS he bought and installed at his editor Austin's house — files
  land there automatically with no download link/wait, and it doubles as an off-site backup.
- He is adding the same setup for a second video editor's house.
- The NAS-to-NAS sync runs over the plain internet (no VPN required); Synology handles the
  security. Remote access to his own NAS uses Synology QuickConnect (no NAT hole-punch /
  router config needed).
- He prefers Synology file sharing over Google Drive sharing because it is often faster and
  because Google Drive zips multi-file downloads and reorders/renames files — annoying for
  video editing projects.
- He manages his fleet (two NAS units in his house, two off-site at editors' houses) via
  Synology's Central Management System (CMS).
- The very video being produced uses this process; Synology (the sponsor) reviewed the
  video via a shared file before release.

**Backup + bonus/homelab uses**
- Active Backup for Business backs up his PCs (scheduled weekly), physical/file servers,
  and VMs; it integrates directly with VMware vSphere (ESXi) and Hyper-V — he backs up two
  ESXi hosts and his home domain controllers.
- A NAS can also run Plex (personal Netflix), Docker containers (he runs Ubuntu + a test
  website), VMs (he runs the KEMP load balancer from his previous video), LDAP, DNS, its
  own VPN, iSCSI storage / an ESXi datastore, Synology Drive (self-hosted Google Drive),
  and high availability (two identical units).
- He recommends always enabling two-factor authentication on the NAS.

## Notable verbatim quotes

> "okay yeah this might seem a little crazy but i just put an enterprise nas in my house"

> "this thing it's my new baby and it's crucial to how i run my youtube business"

> "there's an old saying in i.t two is one one is none"

> "that's why i'm a big proponent for hybrid cloud hybrid cloud's great for business no matter what size you are small medium large enterprise"

> "for me it means that i'm using both a private cloud which for me is my synology and some public cloud which might be google drive which is actually what i'm using right now"

> "i do run a lot of my business using google workspace business gmail and drive and if you do happen to pay for that you get unlimited drive storage which by the way is kind of a hack ... it's only 10 bucks a month per user"

> "i just synced a two gig video file to my video editor's house he's not even there ... at austin's house lives one of these i bought him a synology nas"

> "i'm like hey austin work on this video for me it's already at your stinking house how cool is that"

> "i depend on my synology nas for my business every single day"

> "i've had too much coffee i want to keep drinking i don't care"

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: how he runs his YouTube business (hybrid-cloud NAS infra) — bio/creator-infra -->
