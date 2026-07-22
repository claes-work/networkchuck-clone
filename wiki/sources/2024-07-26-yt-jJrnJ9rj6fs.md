---
type: youtube-video
source_date: 2024-07-26
url: https://www.youtube.com/watch?v=jJrnJ9rj6fs
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [homelab-selfhosting, cloud-devops]
tags: [ceph, distributed-storage, nas, cluster, homelab, proxmox]
---

# the FrankeNAS - (Raspberry Pi, Zima Board, Dell Server, Ugreen) // a CEPH Tutorial

## Summary

Chuck builds a NAS he calls the "FrankeNAS" out of a pile of mismatched spare hardware
(old laptops, a Zima Board, a Ugreen NAS, a TerraMaster NAS, an old Dell server, and
several Raspberry Pis) by joining them into a single logical storage system using
**Ceph**, an open-source, software-defined, distributed storage platform. The video is
two halves: a long conceptual explainer of how Ceph works, followed by a hands-on
tutorial deploying a Ceph cluster across the junk pile and putting real data on it.

The motivation: Chuck's production NAS was a 16-bay Synology that he filled up making 4K
videos. Buying a second Synology would mean managing two separate, non-combinable
servers — a scaling/management problem Ceph solves by letting heterogeneous hardware act
as one expandable cluster. His real production cluster (nicknamed "Hagrid") is four
servers working as one, giving him features like tiered storage (HDD vs SSD folders)
that a single traditional NAS can't.

Conceptual half explains: software-defined = hardware-agnostic; the cluster is built
from **manager**, **monitor** (quorum), **OSD** (object storage daemon = one per hard
drive), and **MDS** (metadata server) roles; data is written as **objects** via the
**RADOS** system into **pools**, routed through **placement groups (PGs)** to OSDs
(replicated x3 by default, or erasure-coded for archives), with the **CRUSH** algorithm
deciding placement/rebalancing without a central database; and **CephFS** is the
Ceph-native file system that decentralizes metadata onto MDS servers.

Tutorial half: prep hosts (Ubuntu 22.04, or 20.04 on the Pis; SSH, static IP, root
login, wipe disks with sgdisk/wipefs, install Docker + LVM2, sync time), distribute SSH
keys, bootstrap with **cephadm**, add hosts, turn all available disks into OSDs with one
command, create a CephFS volume, then share it via Samba/SMB to Windows and mount it
natively on Linux. Final cluster: 7 hosts, 22 OSDs, 38 TB.

## Key claims (dated)

Ceph concept (all as of 2024-07-26):

- Ceph is open-source, software-defined storage; being software-defined makes it
  hardware-agnostic, so a cluster can mix a laptop, Raspberry Pis, an old Dell server,
  etc. This breaks the vendor lock-in of appliance NAS boxes (e.g. Synology forcing
  Synology hardware + software).
- A Ceph cluster can serve object storage, file storage, and block storage.
- The **manager** role runs the cluster and provides the Ceph dashboard GUI; the
  **monitor** role forms a **quorum** (ideally 3+) that keeps the cluster healthy.
- Each individual hard drive becomes its own **OSD** (Object Storage Daemon) — a
  start/stop/restartable Linux service — rather than being merged into one RAID array;
  this decentralizes storage so it scales horizontally. Each OSD handles replication,
  recovery, rebalancing, and reporting to the monitors.
- Ceph relies on **RADOS** (Reliable Autonomic Distributed Object Store). Every file is
  written as an **object** (contrast: a traditional NAS writes files as blocks managed
  by the file system). Objects can be distributed, replicated, and balanced across all
  OSDs for scalability and fault tolerance — no single point of failure like a RAID
  array on one box.
- **Pools** are logical groupings of storage with defined rules — e.g. a "current
  projects" pool restricted to SSD OSDs with 3x replication, and an "archives" pool on
  spinning disks using **erasure coding** (similar to RAID 5/6: data chunks + parity
  chunks distributed; slower than replication but more space-efficient). This is Chuck's
  actual production setup.
- **Placement groups (PGs)** sit between pools and OSDs; there are many of them
  (a calculation based on OSD count and replica factor, e.g. ~128 PGs for one pool,
  scaling up as OSDs are added — Ceph usually computes this automatically). Each PG is
  assigned a set of OSDs, one designated primary. A written object is mapped to a PG,
  whose primary OSD stores it and replicates to the others; work is spread evenly across
  all PGs/OSDs.
- Reads/writes connect directly to the OSD holding the data (via that server's IP), so
  client traffic from multiple editors is distributed across servers rather than
  hitting one box.
- **CRUSH** (Controlled Replication Under Scalable Hashing) is the algorithm Ceph/RADOS
  use to decide where data goes and to find it — decentralized, using hashing rather
  than a central database. The **CRUSH map** stores cluster structure and rules (e.g.
  write a pool only to SSDs, or place replicas in different racks/geographies for high
  availability). CRUSH continuously balances/rebalances data when OSDs are added or lost,
  minimizing data movement.
- **CephFS** is Ceph's native file system (analogous to ZFS on Linux / NTFS on Windows).
  It introduces the **MDS** (Metadata Server) role, which decentralizes file metadata
  (name, size, permissions, ownership) instead of storing it alongside the data, enabling
  high availability and parallel processing. Give MDS to a server with some horsepower.

The build (2024-07-26):

- Hardware requirements stated: ARM or x86 CPU supported (better CPU = better
  experience); at least 4 GB RAM (more is better); external or internal HDDs/SSDs work,
  but USB flash drives do NOT (recent Ceph rejects removable devices); don't use the OS
  disk; and a network switch — the cluster communicates and replicates over the network.
- Lab used a 1 Gbps switch (one port fine for a lab). Chuck's production cluster uses
  four servers each with four 10 Gig NICs into a 10 Gig MikroTik switch, typically
  devoting two ports to front-end (client) traffic and two to back-end (replication /
  rebalancing) traffic.
- OS: Ubuntu 22.04 on everything, paired with the Ceph **Reef** release (18.2.0.2 /
  18.2.2 at time of video). Exception: install Ubuntu 20.04 on Raspberry Pis with Reef —
  22.04 fails because the Ceph Docker container won't run the ARM image and tries x86.
- Host prep: install `openssh-server`, set a static IP via netplan, `apt update`/
  `upgrade`, set a root password + enable root SSH login (`PermitRootLogin` in
  `sshd_config`), because Ceph favors the root user.
- Disk prep: identify disks with `lsblk` (ignore the OS disk), then wipe each target with
  `sgdisk --zap-all /dev/sdX` and `wipefs --all /dev/sdX`.
- Software prep: install Docker on every host (Ceph runs in many containers; default is
  Podman but Chuck prefers Docker), ensure LVM2 is installed, and verify time sync
  (`timedatectl status` — NTP active, clock synchronized) since clusters need synced
  clocks.
- Distribute the manager's root SSH key to every host (`ssh-keygen`, then
  `ssh-copy-id root@<ip>`) for passwordless login.
- Deploy with **cephadm**: set `CEPH_RELEASE=18.2.0.2`, download and `chmod +x` cephadm,
  `./cephadm add-repo --release reef`, `./cephadm install`, then
  `cephadm bootstrap --mon-ip <manager-ip>` — which checks prerequisites, pulls the Ceph
  container, and stands up the first node (manager + dashboard on port 8443).
- Install `ceph-common` to get the `ceph` command; check health with `ceph -s`.
- Add hosts: copy the Ceph-generated cert (`ssh-copy-id -f -i /etc/ceph/ceph.pub
  root@<ip>`), then `ceph orch host add <hostname> <ip> --labels admin`. Ceph
  auto-assigns monitor/manager roles (in the demo, five monitors formed a quorum, one
  manager primary + one backup).
- Create OSDs from every wiped disk with a single command:
  `ceph orch apply osd --all-available-devices` (check candidates first with
  `ceph orch device ls`; watch with `ceph osd tree`). Result: 22 OSDs, 38 TB, health OK.
- Create the file system with one command: `ceph fs volume create cephfs` — which creates
  a metadata pool + a data pool, auto-creates placement groups, and assigns MDS roles
  (one active, one standby). Demo ended with 529 PGs.
- Mount CephFS natively on Linux (baked into the Linux kernel, "blazingly fast"); for
  Windows, install Samba and expose the mounted CephFS as an SMB share. Key distinction:
  SMB ties the client to one server connection (that SMB server then distributes to OSDs),
  whereas native Linux CephFS mounting connects dynamically to individual OSDs. To mount
  CephFS on a remote Linux host, install `ceph-common` and copy `/etc/ceph` credentials
  over.
- Ceph can integrate with Proxmox and provide block storage / RBD images; Chuck's live
  production cluster showed ~9 million objects with data distributed evenly across OSDs.

## Notable verbatim quotes

> "That's my mission in this video to build what I'm calling the FrankeNAS."

> "It actually makes it to where all of these devices can connect together and act as one big giant storage server, one NAS, the FrankeNAS."

> "Software-defined storage is hardware agnostic. Meaning you can pretty much use any hardware you want within reason."

> "Instead of making every hard drive come together as one, they treat every hard drive like its own thing. Every individual hard drive becomes its own unique component within cluster called an OSD, an object storage daemon."

> "Every file in Ceph is written as an object to the OSDs. And this is in contrast to a typical NAS where files are written as blocks managed by the file system."

> "These objects can be distributed, replicated, and balanced across all OSDs in your cluster, providing high scalability and fault tolerance."

> "Ceph would never do anything centralized. That's a sin."

> "The more I learn about it, the more I'm like, why haven't we always done this?"

> "Sorry, I'm a dad of six daughters. You're going to hear plenty of dad jokes in my videos."

> "If you know how to do that, you can get a pretty cool job. Yeah, that's a job, a storage admin."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: canonical deep-dive homelab tutorial capturing Chuck's full Ceph mental model + his real production "Hagrid" cluster architecture; rich voice/teaching-style material (coffee-break asides, dad jokes, employee/mafia analogies) and a flagship topic page candidate for distributed storage. -->
