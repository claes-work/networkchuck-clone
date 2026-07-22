---
type: youtube-video
source_date: 2021-10-12
url: https://www.youtube.com/watch?v=apC1bOLbzbY
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [homelab-selfhosting, cloud-devops]
tags: [vmware, esxi, server, homelab, virtualization]
---

# i bought a new SERVER!! (VMware ESXi Setup and Install)

## Summary

Chuck buys a used enterprise server — a Dell PowerEdge R710 rackmount unit — off Amazon (~$645, with cheaper options noted on eBay) to expand his home lab, and walks through installing VMware ESXi / vSphere on it. The core pitch: to "beef up" a home lab, buy older enterprise-grade servers that data centers retired — they are cheap but still run great, and they teach the real enterprise IT skills that companies actually use. Chuck adds this as his third such server (he already runs two).

A running gag/lesson of the video is a hardware-compatibility wall: he intended to install the latest vSphere 7 / ESXi 7, but a "Chuck from the future" cut-in reveals the R710 hardware is too old to support ESXi 7, so he falls back to ESXi 6.7 — the same version already running on his other old servers. He frames VMware as "being jerks" about their hardware requirements while conceding 6.7 is fine.

The tutorial covers the full build: prerequisites (server, 8GB+ USB drive, free VMware account, monitor + keyboard, and — of course — coffee), installing a 10-gig ethernet NIC "because why not," writing the ESXi 6.7 ISO to USB with Rufus, configuring a RAID 5 array on the Dell PERC controller via the boot-time system services menu, booting the ESXi installer, setting a root password, assigning the free license key, setting a static IP via the DXi/ESXi console (F2 → configure management network), reaching the ESXi web UI, and finally creating a first virtual machine (an Ubuntu VM) — including uploading an ISO into the datastore. The video is sponsored by Vessi footwear, and the ad plays out live when Chuck has to run to the store for a VGA cable he forgot (the old server has VGA, not HDMI).

## Key claims (paraphrase; dated 2021-10-12)

**The homelab / hardware angle**
- The way to beef up a home lab is to buy the massive enterprise servers data centers use, but buy the *older* generations — they are cheaper yet still run great.
- Chuck's new server is a used Dell PowerEdge R710 rackmount bought off Amazon for ~$645; comparable units can be found cheaper on eBay (he cites ~$360 and ~$201 listings, some gutted / without HDD).
- This is now Chuck's third old enterprise server in his lab — he already had two (he references an R720 among them) and wanted one more "because why not."
- A lot of the stuff he runs and features in his videos runs off servers like this — Docker containers, a couple of domain controllers, "hacky labs," and actual company-style infrastructure.
- These machines are not the fastest, but that does not matter — he is not gaming on them, just running services in his house.
- Old enterprise hardware is recommended over an old laptop/desktop precisely because not all consumer hardware is supported by VMware (he hit this trying to install on his laptop, and used Proxmox there instead).
- The point of the whole exercise: it is great practice for real enterprise IT skills and great for a home lab.

**The ESXi setup**
- Intended install was vSphere 7 / ESXi 7, but the R710 hardware does not support ESXi 7; he falls back to ESXi 6.7 — the same version on his other servers.
- VMware ESXi 6.7 is free with a registered VMware account, which issues a license key.
- Prerequisites: a server, an 8GB+ USB flash drive, a free VMware account, a monitor and keyboard, and coffee.
- He installs a 10-gig ethernet NIC into the server as an optional extra.
- Use Rufus (Windows) to write the ESXi ISO to the USB drive; partition scheme MBR, target BIOS/UEFI. Mac/Linux users need other tools.
- On the Dell server, configure RAID before install via the boot F10 system services → hardware configuration → configuration wizards → RAID configuration; his controller is a PERC 7/700-series; he sets up RAID 5 with no hot spare. (This RAID step is Dell-specific / old-Dell-specific.)
- Boot the server to the USB (F11 boot menu on Dell if it does not auto-boot), run the ESXi installer, accept the EULA, let it scan for compatible devices, install onto the RAID controller / datastore, pick keyboard layout, set a root password, then F11 to install.
- After install, remove the USB and reboot; the hypervisor loads.
- Set a static IP from the ESXi console: F2 to log in with root → configure management network → IPv4 configuration → spacebar to set static → enter address → escape and apply/restart network.
- Access ESXi via a web browser at its IP; the browser warns the connection is unsafe — proceed anyway, and log in with root and the password you set.
- ESXi starts in evaluation mode; assign the free license under Manage → Licensing → Assign license.
- Security note: the free/older ESXi is flagged as vulnerable, so do not expose the server to the internet.
- The install datastore on his machine is almost 4 TB and is where VMs and their virtual disks live.
- To create a VM: Virtual Machines → Create/Register VM → new VM → name it, pick guest OS (Ubuntu 64-bit), pick datastore, allocate resources (he uses 2 vCPUs, 2 GB / 2048 MB RAM, 50 GB disk).
- Boot the VM from an ISO: change the CD/DVD device to "Datastore ISO file," create an ISOs directory in the datastore, upload the ISO there, select it, and check "connect at power on."
- Power on the VM and install the Linux distro as normal; he demonstrates logging into the finished Ubuntu VM to prove it works.

## Notable verbatim quotes

> "I got a new toy. You want to see it here? It is. It's a server, the big boy."

> "This is what you want to do when you want to beef up your home lab. You'll buy an awesome, massive, amazing server that enterprises have in their data centers. But we buy the older ones. They're cheaper, but they still run great."

> "I actually already have two in my lab. And I wanted one more because why not?"

> "Hey Chuck, from the future here. It turns out you can not install vSphere seven on old hardware, like the R seven ten. What? The junk VMware, why are you doing this man?"

> "You can pick up a server like this for not too bad... you can buy enterprise IT hardware and put this in your house and it's not too expensive."

> "It's a great way to learn enterprise IT skills."

> "You're gaining valuable skills. That's the whole big idea, right? That's why we're here doing this."

> "And you're going to need some coffee. Espresso, French press, pour over. I don't care. You just need some network dot chuck dot coffee."

> "Nice and quiet, huh? So quiet. Nice, serene... Sounds like a jet plane."

> "We installed an enterprise hypervisor on old enterprise hardware that we bought off of Amazon, or maybe eBay. Now why do this again? It's great practice to learn actual enterprise IT skills. Secondly, it's awesome for your home lab."

> "A ton of stuff I run and feature in my videos runs off of servers like this."

> "You don't need something crazy to run Docker containers, a couple domain controllers. I mean, come on. And what you can learn on these things, it's insane."

> "Sure, they're not the fastest machines in the world. No, they're not, but I'm not gaming on these bad boys. They're just running some stuff in my house."

> "Just don't expose your server to the internet."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
