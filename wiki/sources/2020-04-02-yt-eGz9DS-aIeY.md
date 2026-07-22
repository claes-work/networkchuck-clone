---
type: youtube-video
source_date: 2020-04-02
url: https://www.youtube.com/watch?v=eGz9DS-aIeY
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cloud-devops, linux-terminal]
tags: [docker, containers, devops, tutorial, learn-x-now]
---

# you need to learn Docker RIGHT NOW!! // Docker Containers 101

## Summary

A landmark entry in NetworkChuck's signature "you need to learn X RIGHT NOW" tutorial format. Chuck opens with the show-don't-tell hook — building a Docker container on camera in seconds ("done… want to see it again? done… man that was fast") — then argues that if you're in IT (cloud, AWS/Azure/Google, Linode, DevOps, networking, systems) you "got to know it." The video is structured around three stated objectives: (1) what Docker/containers actually are, (2) hands-on labbing via a sponsored Linode free lab, and (3) the "big why" — why containers beat virtual machines and why the viewer should care.

The teaching arc first defines what Docker is *replacing* — virtual machines — walking through bare-metal servers, hypervisors (VMware ESXi), and how VMs carve up hardware resources. Chuck then delivers the core conceptual "line": virtualization/VMs virtualize *hardware*, whereas Docker virtualizes the *operating system*. Containers are pitched as "crazy fast lightweight micro computers" that are isolated/quarantined/secure, each with their own OS, CPU, memory, and network. The hands-on segment spins up a Linode Docker instance and runs CentOS, Alpine, multiple Ubuntu flavors, Arch, and a custom `networkchuck/nc-coffee:french-press` web-app image to demonstrate portability. The video closes with the "big why": containers are fast and lightweight because they share the host's single Linux kernel (VMs each carry their own kernel + hypervisor overhead), they're portable ("no more 'it works on my machine'"), and they enable microservices. Sponsored by Linode; the coffee-themed brand energy runs throughout.

Solo Chuck teaching video — foundational Docker 101 content plus a textbook example of his format and delivery.

## Key claims (dated 2020-04-02)

- **Who needs this:** If you're in IT — cloud (Azure, AWS, Google), Linode, DevOps, networking, or systems — you need to know containers. (paraphrase)
- **To understand containers, first understand what they replace: virtual machines.** (paraphrase)
- **Bare metal (pre-virtualization):** traditionally you installed one OS on one physical server; all resources (CPU, RAM, disk) were dedicated to that single OS. Running two OSes (e.g., a Windows server and a Linux server) required two physical machines. (paraphrase)
- **Hypervisor:** virtualization installs a hypervisor instead of a normal OS; its one job is to carve up / divide a server's resources into multiple virtual servers. The most popular hypervisor is VMware, specifically **ESXi**. You allocate a slice of resources (e.g., 2 GB RAM, 2 CPUs, 100 GB disk) per VM until the server runs out. (paraphrase)
- **Core distinction (the big idea):** VMs/virtualization virtualize the **hardware**; Docker virtualizes the **operating system**. (paraphrase)
- **Docker's architecture:** you install one OS (e.g., Ubuntu) directly on the hardware, then Docker runs on top as a process/daemon (installed like any other Linux application) and virtualizes portions of that OS to create containers. (paraphrase)
- **Containers vs VMs:** containers do the same job as VMs and share many qualities, but Chuck considers them able to replace VMs (noted as his controversial opinion). (paraphrase)
- **What a container is:** a "crazy fast, lightweight micro computer" that can be as powerful as you want; it has its own OS, CPU processes, memory, and network, and is quarantined/isolated/secure — as isolated as if installed on bare metal. (paraphrase)
- **Speed:** containers are created and start far faster than a VM boots. (paraphrase)
- **Docker images come from a registry** — Docker Hub (hub.docker.com) — and images are what you use to run/create containers. (paraphrase)
- **Tags** let you pull different versions of a particular image (e.g., Ubuntu 16/17/18). Format shown: `image:tag`. (paraphrase)
- **Port mapping (`-p`):** maps a container port to a host port; in `-p host:container` (as Chuck frames it for CCNA/DevNet exam takers) the port on one side is the container's and the other the host's — he maps port 80 to port 80. (paraphrase)
- **Portability is the killer feature:** a custom image packages the OS, installed software (e.g., nginx web server), all website files, and all dependencies into one neat container that runs identically on any Linux-based machine — AWS, Azure, your computer, his computer. (paraphrase)
- **Why containers are fast:** they only need **one kernel** — all the Linux-based container OSes share the host's underlying Linux kernel, which is already up and running. (paraphrase)
- **Why containers are lightweight:** VMs each need their own guest OS + Linux kernel plus a (heavy) hypervisor; containers avoid that overhead by sharing one kernel. (paraphrase)
- **OS/kernel constraint:** you can only run Linux-based containers on a Linux host and Windows-based containers on a Windows host, because containers share the host's underlying OS/kernel. Docker also runs on Windows 10 / Windows Server (2016 and up). (paraphrase)
- **Under the hood:** containers use **control groups (cgroups)** to define how much CPU/memory/OS resource each container gets, and **namespaces** to isolate/segment everything. These concepts predate Docker; containers have existed a long time and Docker isn't the only container technology. (paraphrase)
- **Industry use — cloud:** you can deploy the same container to Linode, Azure, or AWS; it behaves like a web app you launch. (paraphrase)
- **Industry use — developers:** solves the "it works on my machine" problem — everything the app needs ships inside the container. (paraphrase)
- **Industry use — microservices:** instead of installing a whole app stack on one server (e.g., WordPress + MySQL together), you split components into separate containers (WordPress in one, MySQL in another) so they're isolated, non-conflicting, and independently updatable. (paraphrase)
- **Home/self-hosting use:** Chuck runs Docker on his Synology server with containers for Home Assistant (home automation), and mentions Pi-hole as another example. (paraphrase)
- **Commands demonstrated:**
  - `docker pull centos` — pull an image from Docker Hub
  - `docker run -d -t --name can't-contain-myself centos` — create and run a container from an image
  - `docker ps` — list running containers
  - `docker exec -it <name> bash` — connect into a container's shell (used `sh` for Alpine)
  - `exit` — leave the container shell
  - `docker pull networkchuck/nc-coffee:french-press` — pull a tagged image
  - `docker run -d -t -p 80:80 --name nc-coffee networkchuck/nc-coffee:french-press` — run with port mapping
  - `docker stop <name>` / `docker start <name>` — stop and restart a container
  - `docker stats` — live view of container CPU/memory/network usage (Ctrl+C to exit)

## Notable verbatim quotes

Signature hook / cold open:

> "hey — do you want to see me build a docker container? yeah let's do it, real quick… done. want to see it again? done. man that was fast."

> "containers — if you're in IT you got to know it. If you want to learn cloud, Azure, AWS, Google, Linode, DevOps, networking, systems… I think I said everything right. So I hope you have your coffee ready."

> "in this video we're covering three things. First: what the junk is Docker. Two: you're getting hands-on with Docker… and then three, we'll go a bit deeper — talk about the big why. Why Docker?"

Core teaching lines:

> "before we can define what a Docker container is, we have to first define what it's replacing: virtual machines."

> "where virtualization and virtual machines are virtualizing hardware, Docker virtualizes the operating system. What — what does that even mean?"

> "I like to think of them as crazy fast, lightweight micro computers. And don't let 'micro' fool you — they can be as powerful as you want them to be."

> "the most important thing… is that they're quarantined. They are isolated, they are secure. As far as they understand, they are their own thing."

> "these suckers are lightweight and they are wicked fast. Like you saw at the beginning of this video: click, bam — it's there."

> "the short answer is that you only need one kernel… all of these OS's are Linux based, they all share the underlying Linux kernel."

> "you have a website… that container not only has its own OS, CPU processes, memory, but it also has all the settings I applied… all the prerequisites, all the dependencies packaged together in a neat little package — a container."

> "I can move this same docker container to AWS, to Azure, to your computer, to my computer, to wherever, and it's going to run the same. And that's the power of Docker."

> "it worked on my machine, I don't know what you're doing — no more of that junk. No more of that. Because if you deploy in a docker container, everything that app needs is right there in its container. It's contained, it's isolated."

Signature humor / energy:

> "I'm so excited about this — you might say I can't contain myself. Sorry."

> "there she is, and she's so pretty — look at her. That is CentOS, isolated, secure, running with its own operating system, CPU, memory, network. Oh, it's quarantined."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: landmark 'you need to learn X RIGHT NOW' format (Docker) — voice + teaching pattern -->
