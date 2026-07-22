---
type: youtube-video
source_date: 2019-03-02
url: https://www.youtube.com/watch?v=FfJXcoqTvrs
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cloud-devops, networking, certifications-career]
tags: [azure, gns3, ccna-lab, cloud, tutorial]
---

# CCNA Lab in the Azure Cloud for FREE! - GNS3 Setup in Microsoft Azure

## Summary

Hands-on tutorial (2019-03-02) in which Chuck Keith shows how to run a [[../../wiki/topics/networking/networking]] lab — specifically GNS3 — on a virtual machine hosted in Microsoft Azure, using Azure's free trial so viewers can build a CCNA/CCNP/CCIE lab "for free." Chuck frames the choice of *how* you lab as the single biggest decision when studying for a Cisco cert, and pitches the cloud as a way around the two usual blockers: not owning a beefy computer, and not having a server in a datacenter (which he does have).

The concrete flow: create an Azure free account ($200 credit / 30 days), open Azure Cloud Shell (PowerShell), paste a provided script (linked in the video description / GitHub) that provisions an Ubuntu VM with nested virtualization enabled, SSH into the VM (Chuck uses PuTTY), paste a second block from the script to install GNS3, then install the local GNS3 client and connect it to the cloud server in "run everything on a remote server" mode. He demonstrates a working topology (a router and a switch built from Cisco VIRL images requiring nested virtualization), configures interfaces, and shows a successful ping. He closes with cost hygiene: **stop/deallocate** the VM when not labbing so you stop paying, and mentions Azure's auto-shutdown feature.

This is an early **cloud-era** video for the channel: Chuck ties it explicitly to a Microsoft Azure course he was building at the time for CBT Nuggets (AZ-900, with AZ-100 planned), and repeatedly evangelizes the cloud as "the future." Standard NetworkChuck framing devices are present: making coffee on camera (Alexa 3-minute timer), heavy enthusiasm, and cross-promotion of his and David Bombal's "This Is IT" channel and CBT Nuggets.

## Key claims (dated — the setup steps)

All dated 2019-03-02 (paraphrase unless quoted):

- Deciding *how* you will lab is described as one of the biggest decisions when studying for CCENT/CCNA/CCNP/CCIE, and (in Chuck's view) the key to success.
- GNS3 is software that simulates Cisco routers, switches, and firewalls, and can also run Docker containers — enough to lab most things for CCENT/CCNA and higher.
- Chuck does **not** recommend GNS3 for beginners (steep hurdle: virtualization, routers, etc.); for beginners he recommends Packet Tracer.
- Normally GNS3 runs either on your local computer or on a remote server; Chuck personally runs it on a server in his own datacenter, which needs lots of RAM and CPU — especially for Cisco VIRL images.
- The cloud solves the "no beefy computer / no datacenter" problem: you can size a cloud computer as big as you need (scaling up = adding resources).
- Azure's free tier gives **$200 of credit for the first 30 days**. Chuck says that over ~20 days of heavy experimentation he spent only about $5.
- When the free trial ends, nothing is charged automatically; you lose remaining credit but can manually convert to a pay-as-you-go account.
- A credit card and phone number are required to sign up; Chuck stresses the card is only for identity verification and won't be charged unless you opt into pay-as-you-go.
- Azure portal login is at portal.azure.com.
- Setup step 1 — open **Cloud Shell** (the arrow/underscore icon at the top of the portal), which opens a command line and prompts you to create a storage account for it.
- Setup step 2 — Cloud Shell here uses **PowerShell**; a provided script (in the description / GitHub) sets everything up.
- In the script, edit these variables before deploying: **location** (Chuck uses South Central US / Texas as his nearest datacenter; location affects latency/performance), **username/password** (default is a `CBT Nuggets admin` credential), and **domain name** (the server name — change it so it doesn't collide with someone else's).
- Copy the script block down to the `New-AzVM` command and paste into Cloud Shell; `New-AzVM` creates the VM.
- The VM is an **Ubuntu server**, sized fairly large, with **nested virtualization enabled by default** (needed to virtualize VMs inside the VM).
- After creation, copy the VM's **fully qualified domain name** from the output, and SSH in with an SSH client (Chuck uses PuTTY, links it in the description), logging in with the username/password.
- Install GNS3 on the server by pasting the second block of the script (from `cd /tmp` down to `sudo bash`) and running it; success shows a "GNS3 installed with success" message.
- In the Azure portal, **Resource groups** are containers holding the created resources; the `gns3` group lists the VM, virtual network, public IP, network security group (functions like a firewall / close to access control lists), NIC, and OS disk.
- Install the local GNS3 client from gns3.com (account required), and on first launch choose **"run everything on a remote server"**, entering the cloud server's DNS name in the host field; authentication is left disabled in this walkthrough.
- Once connected, the GNS3 "Servers Summary" shows the cloud server's CPU and RAM being monitored.
- A **portable project file** is a way to transfer GNS3 projects (with images) between GNS3 servers; Chuck imports one via File > Import portable project.
- Demonstration: a router and a switch (both Cisco **VIRL** images requiring nested virtualization) start without errors; consoles open in **Solar-PuTTY**; `show ip interface brief`, `no shut`, and IP addressing (e.g., 10.0.0.x) are configured and a successful ping between the two devices is shown.
- The demo VM size shown: **4 virtual CPUs and 16 GB of memory** — described as beefy enough for most topologies, and scalable up (for more money) if needed.
- Cost hygiene: **Stop** the VM when not in use and confirm the status reads **deallocated** — deallocated means resources are no longer provisioned and you're no longer charged. Restart it when you want to lab again.
- Azure offers an **auto-shutdown** feature (e.g., shut down at 12 a.m.); Chuck prefers stopping manually but notes auto-shutdown as a safety net.
- Total setup time estimated at roughly 10–15 minutes depending on speed.
- Chuck chose Azure (over AWS or Google Cloud) because he was studying/creating Azure content at the time (AZ-900 course on CBT Nuggets, AZ-100 planned).

## Notable verbatim quotes

> "deciding how you are going to lab is one of the biggest decisions you'll make when you decide how you're going to study for your CCENT CCNA CCNP or whatever because that's gonna be the key to your success"

> "I don't recommend gns3 for beginners because it can be kind of a big hurdle if you're not familiar with all the technologies involved... that's why I recommend for beginners packet tracer"

> "what is a cloud mean it means you're putting your servers or your routers or switches, well some of them, into the cloud which is just somebody else's computer"

> "with the cloud you can take any computer you want in the cloud and make it as big as you need it to be... that's called scaling up"

> "specifically for Azure you get two hundred dollars of credit for the first 30 days to do whatever you want in their cloud"

> "I've been playing around with Azure quite a bit, I've spun up a lot of resources, turned them down, and within 20 days I've only used five dollars"

> "you only pay for what you use... when you're done you shut that sucker down, you're not being charged for those resources anymore"

> "right now you look like a complete wizard boss because the matrix is flying by your face and you are installing gns3 on a server in the cloud"

> "does anyone else just get like so happy when you see a successful ping? it's the best thing in the world"

> "it's like Netflix, you're just paying a monthly thing... so it's the upfront cost you're avoiding"

> "hey honey I'm gonna go buy a $500 server so I can run pretend routers and switches, it's kind of hard to sell that"

> "you want to make sure that when it's all said and done it is de-allocated, because that means the resources are no longer provisioned to you, you're no longer being charged for them"

> "I encourage you to try it out just to get your feet wet with something in the cloud because it's fun... and you get a little bit of cloud experience to boot"

> "it's the future man, it really is"

> "oh I get really excited and hyper when I have coffee and I always have coffee so I'm always like this"

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: early cloud (Azure) tutorial — cloud era begins -->
