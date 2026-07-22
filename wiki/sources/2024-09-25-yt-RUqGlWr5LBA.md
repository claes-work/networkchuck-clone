---
type: youtube-video
source_date: 2024-09-25
url: https://www.youtube.com/watch?v=RUqGlWr5LBA
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [homelab-selfhosting, cloud-devops]
tags: [docker, self-hosting, homelab, containers, services]
---

# 18 Weird and Wonderful ways I use Docker

## Summary

A Docker-sponsored (Chuck stresses he would have made it anyway) showcase of 18 ways
Chuck uses Docker in his day-to-day workflow, spanning three loose categories:
GUI-in-a-container apps, Docker management/security tooling, and a hacking-lab / OS-experimentation
section. He runs everything on Windows with WSL 2 (Ubuntu), and repeatedly notes most
containers work on Mac, Linux, and Windows. The recurring theme is that Docker's
lightweight isolation makes it his default way to run apps, isolate tools, build a
hacking lab, and experiment with operating systems — cheaper and easier than a VM.
Many of the GUI containers come from LinuxServer.io, which he shouts out repeatedly.
The video is deliberately conversational/looser in style, and he loses count of whether
he actually hit 18.

## Key claims (2024-09-25)

Grouped by category. All paraphrase unless quoted below.

**GUI-app-in-a-container (via LinuxServer.io images, GUI access through Kasm VNC):**
1. Full GUI web browser (Firefox) running inside a container — the same idea as the Kasm-powered
   NetworkChuck Cloud Browser, giving Docker isolation while feeling like a normal browser.
2. Obsidian (his favorite notes app, used daily) in a container with GUI access.
3. LibreOffice (open-source Microsoft Office alternative) in a container — one he says he
   might actually use.
4. Folding@home in a container — donates idle compute to cancer/humanitarian research;
   optionally GPU-accelerated with NVIDIA switches plus the NVIDIA Container Toolkit/runtime.
5. Kali Linux in a GUI container (Kasm VNC) — a fast, browser-accessible pentest box he
   argues beats a VM for quick testing.

**Docker management & security tooling:**
6. Docker Desktop (Mac/Linux/Windows) as a GUI to see containers, CPU, and memory; integrates
   with an existing WSL 2 Docker install.
7. Portainer installed as a Docker Desktop extension for richer container management.
8. Dangerzone — an app that uses containers/sandboxes to convert untrusted PDFs, Office docs,
   and images into safe PDFs (rasterizes to pixels in one sandbox, rebuilds in another);
   requires Docker Desktop running.
9. Building your own images with a Dockerfile — he wraps GitHub CLI tools (example: fabric,
   which moved from Python to Go) in their own container so dependencies never collide,
   then aliases the `docker run` command. Calls building your own containers "a superpower."
   Notes he used ChatGPT to help write the Dockerfile.
10. Docker Scout for image vulnerability scanning — analyzes images for CVEs, flags outdated
    images, and can be driven from the Docker Desktop terminal / Scout CLI (`docker scout cves`);
    he fixes an Express CVE by bumping the version and re-scanning.

**Hacking lab, networking & OS experimentation:**
11. Docker Networks — creating isolated networks (`--internal`) to safely contain vulnerable
    machines; his separate favorite feature (has a dedicated video).
12. DVWA (Damn Vulnerable Web Application) as a vulnerable target container, reachable only
    from Kali via the isolated hacking-lab network, not from the host.
13. Docker Compose — declaring the whole lab (network + Kali + DVWA) in one `docker-compose.yml`
    and bringing it up/down with `docker compose up -d` / `down`.
14. Trying out other Linux distros quickly — e.g. Rocky Linux pulled straight from Docker Hub.
15. Running macOS in a container (Docker-OSX / sickcodes) — notes the project got an Apple
    DMCA/cease-and-desist; he risks it and reaches a Mac boot/recovery screen via X11 forwarding.
16. Running Raspberry Pi OS (Raspbian Buster Lite) in a container.
17. IT-Tools — a self-hosted web collection of developer/IT utilities (bcrypt, hash generators,
    date/time & IP converters, RSA keypair generator, token generator, crontab generator,
    text diff, Outlook SafeLink decoder, QR generator, docker-run-to-compose converter, emoji picker).

**Environment & philosophy:**
- He runs all of this on Windows + WSL 2 (Ubuntu); most containers are cross-platform.
- Containers are meant to be ephemeral/temporary — losing them (e.g. when he broke WSL
  integration) is fine by design.
- Volume mapping keeps data consistent between the host and a container.
- Port mapping (host port : container port) must be varied so stacked GUI containers don't
  collide (3000/3001 → 3003/3004 → 3005/3006, etc.).
- Overarching stance: he "uses Docker for everything" and jokes he has a "Docker addiction" —
  Docker's lightweight isolation replaces VMs for apps, tool isolation, hacking labs, and OS testing.
- He recommends Docker as a starting point for anyone learning: "you can do so much."

## Notable verbatim quotes

> "I think I have a Docker addiction. I use Docker for everything."

> "this video is sponsored by Docker, which is kind of cool because I would've talked about them for free. Don't tell them that."

> "a Docker container is separate from the os it's running on and has inherent security. So calm down. I saw you commenting. I saw you."

> "Containers are designed to be ephemeral, temporary."

> "when you know how to build your own containers, it's like gaining a superpower. It really is."

> "You don't have to start from scratch on anything. Don't waste time. Use ai, let it make you better, but also you should understand what's going on. So use AI to explain it to you."

> "in my humble opinion... if you just need something quick to test out some stuff, this is better than a vm."

> "You guys maybe wonder, is Chuck really like this? Is he faking it for YouTube? No. Ask my friends, ask my family. I'm like this all the time, especially with coffee."

> "I would honestly start with Docker containers because you can do so much."

> "I would've made the video anyway if they hadn't have sponsored this. I just love Dockers so much."

> "I'm not sure if that was 18. I lost count."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: self-host-everything (18 Docker services) — homelab identity -->
