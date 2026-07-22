---
type: youtube-video
source_date: 2022-11-01
url: https://www.youtube.com/watch?v=6rpTjEpvUtc
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cloud-devops, homelab-selfhosting]
tags: [ansible, automation, homelab, cloud, infrastructure-as-code]
---

# i automated my home lab (and CLOUD) with Ansible

## Summary

A sponsored (Red Hat) tutorial in which Chuck automates end-to-end VM deployment
across both cloud and on-prem homelab infrastructure using [Ansible](https://www.ansible.com/),
framed as an escalating story of "laziness." He walks through progressively harder
levels: (1) deploying cloud VMs (Linode, AWS) with community Ansible modules and API
tokens; (2) deploying on-prem VMs to a [[../entities/proxmox]] server; (3) making
playbooks generate randomized VM names to work around Ansible's idempotency; (4)
pushing Slack notifications with the finished VM's IP address when done; and (5) a
full voice-driven pipeline where "Alexa → Zapier → Red Hat Ansible Automation
Platform API → Linode/AWS/Proxmox → Slack → phone." The core infrastructure-as-code
lesson is that a single tool (Ansible playbooks) can uniformly automate provisioning
across heterogeneous targets — public cloud and on-prem — and that the Ansible
community fills documentation gaps for the harder, less-documented targets.

The most involved segment is a "madness" workaround for Proxmox not knowing the IP
of VMs it creates: Chuck chains Ansible shell commands to pull the VM's MAC address
from Proxmox, runs an Nmap scan to populate the ARP cache across the network, then
uses ARP to resolve MAC → IP so Slack can report the address. He also notes Ubiquiti
UniFi (Dream Machine Pro) cannot be automated via Ansible (no module, no reliable
CLI), which forced the Nmap/ARP approach.

## Key claims (dated — the automation)

- (2022-11-01) Ansible is Chuck's favorite IT automation tool; this video is a
  Red Hat–sponsored piece built around it. (paraphrase)
- (2022-11-01) Chuck deploys cloud VMs manually for his lab and for videos, which is
  slow; Ansible automates it. Cloud is the *easy* target because of abundant
  documentation. (paraphrase)
- (2022-11-01) An Ansible **playbook** is described as the tool's "magic" — a set of
  tasks/"spells" that get run. (paraphrase)
- (2022-11-01) Linode automation: one Google search found a Linode node module that
  "did all the heavy lifting"; Chuck only had to copy/paste and insert his API token
  to bake a fresh VM. (paraphrase)
- (2022-11-01) AWS automation: deploying Windows machines to AWS was easy thanks to
  extensive documentation. (paraphrase)
- (2022-11-01) On-prem: Ansible can deploy to Proxmox via a community-created module,
  but with little documentation. Deploying a Proxmox VM first requires a VM template,
  which is non-trivial; Chuck credits a Jay LaCroix video for the template. (paraphrase)
- (2022-11-01) Idempotency problem: rerunning the Proxmox playbook creates no new VM
  because Ansible ensures a named state exists rather than always creating. Chuck
  worked around it by using the password/random-character generator function to make
  a random VM name each run, so a new "fresh baked VM" is created every time; he
  applied the same fix to Linode and AWS. (paraphrase)
- (2022-11-01) Slack notification: the Slack module is well documented; adding a few
  tasks to the playbook lets Ansible message him the finished VM's name and IP. (paraphrase)
- (2022-11-01) Proxmox does not assign/report the VM's IP (unlike cloud providers,
  which assign it); the router assigns it and only the router knows it. (paraphrase)
- (2022-11-01) Ubiquiti UniFi Dream Machine Pro cannot be automated with Ansible —
  no module, unusable CLI/role — which blocked asking the router for the IP. (paraphrase)
- (2022-11-01) IP-discovery workaround: get the VM ID → use a Proxmox shell command
  (via Ansible's shell module) to grab the MAC address → format it for ARP → wait →
  ARP. ARP alone failed because the Proxmox host's ARP cache only knows devices it has
  talked to, so Chuck ran an **Nmap** scan of the whole network to populate the ARP
  cache, then resolved the IP. (paraphrase)
- (2022-11-01) Ansible's ability to fall back to plain shell/CLI commands when no
  module exists is highlighted as a strength. (paraphrase)
- (2022-11-01) Voice pipeline: Ansible by default has no API/webhooks, so Chuck used
  the **Red Hat Ansible Automation Platform** (which adds a GUI and an API) purely for
  its API — signed up for a 60-day free trial (a sandbox is also available), installed
  Red Hat then the platform on top, and plugged in his playbooks. (paraphrase)
- (2022-11-01) Final architecture: Alexa → Zapier (running Python code) → Ansible
  Automation Platform API → Linode/AWS/Proxmox → Slack → his watch/phone; he can
  provision a VM by voice command. (paraphrase)

## Notable verbatim quotes

> I did it. I automated everything. I went a little crazy for this video.

> Now like all great IT automation, conquest, my idea was born from laziness. I'm
> lazy and I think you are too. That's what makes us great.

> See automation, it's easy unless you go offroad a it.

> Community is key. And more often than not someone has walked the path you're about
> to walk. So before you lose your mind research and reach out.

> When I create a VM with it, it does nothing with the networking, it simply spits it
> out into my network here and says, You're on your own kid.

> You cannot automate with the Dream machine pro. You just can't do it. I tried. I
> tried for hours. There's no module.

> If I can get the Mac address from Prox Ox, then I can use ARP to find the IP address.

> How can I populate my [ARP] cache with every IP address and MAC address mapping on
> my network[?] Hacking? Of course. I will use Nmap.

> Ansible by default doesn't have an api, doesn't have web hooks, which is normally
> how Alexa would talk to things.

> It's called the Red Hat Ansible Automation Platform. This thing, it's Ansible but
> Ansible that's gone crazy... it's got a beautiful gooey, it does so many things,
> but it has an API and that's just what I needed.

> Alexa will talk to [Zapier]. Zapier will run some Python code to interact with the
> Red Hat Ansible automation platform api, which will kick it off to [Linode], AWS
> and [Proxmox], then to Slack. And then to me.

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
