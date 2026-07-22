---
type: youtube-video
source_date: 2022-09-23
url: https://www.youtube.com/watch?v=iX0HbrfRyvc
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cloud-devops, homelab-selfhosting]
tags: [docker, portainer, containers, self-hosting, tutorial]
---

# learning Docker is HARD!! (this makes it easy)

## Summary

Chuck argues that Docker on the command line is hard enough that he made three prior
videos just to explain it — and then tells viewers to "throw those videos out" because
he found [[../entities/portainer]] (a web GUI for Docker) that makes deploying and
managing containers "stupid, easy" and even "delightful." The video is a hands-on
install-and-tour: he stands up a cheap Linode cloud VM, installs Docker, then runs
Portainer as a Docker container itself, and finishes in roughly 30 seconds of actual
setup time. He then tours the Portainer web UI (dashboard, containers, images,
networks, volumes, an in-browser container terminal, Add Container, and Stacks =
Docker Compose) and demonstrates the standout feature: managing Docker hosts across
locations — including a home lab behind a firewall — from one central Portainer
server, without exposing any ports, by using the Edge agent.

The pedagogy is classic Chuck "make-it-hard-easy": acknowledge the tool is intimidating,
promise you'll be running in 30 seconds, walk every step live, insert coffee-break
beats where a command runs, and hand off segments to his colleague Abby as a teaching
try-out. The recurring thesis: the GUI gives you a "window" into Docker so you can
actually see what's running instead of squinting at `docker ps`.

## Key claims (dated — the concepts)

_All dated 2022-09-23; paraphrase unless quoted._

- Portainer is a free web GUI that makes deploying and managing Docker containers far
  easier, and setup takes roughly 30 seconds.
- Portainer is itself deployed as a Docker container, so it runs anywhere Docker runs —
  a Raspberry Pi, WSL, the computer you're already on, or a cloud VM.
- The installation steps are identical regardless of where you run it, because it all
  rides on Docker.
- Portainer has two elements: the Portainer **server** and the Portainer **agent**. A
  single-host setup needs only the server, which auto-discovers and starts managing the
  existing Docker environment on that host.
- The agent is what you install on **remote** hosts so the central Portainer server can
  manage them.
- Prerequisite install sequence on Ubuntu: `sudo apt update`, then
  `sudo apt install docker.io -y` to install Docker.
- Verify Docker works by running a test container (`docker run` with `-d`, ports
  `80:80`, the nginx image) and confirming with `docker ps`.
- Create a Docker **volume** before deploying Portainer so its data persists
  (`docker volume create`); Portainer is then deployed with a single `docker run`
  command.
- The Portainer deploy command exposes ports **9443** and **8000**, uses a `-v` bind
  mount to give Portainer access to the host's Docker socket/environment, and mounts the
  persistent volume for Portainer's own data.
- Access the Portainer web UI over HTTPS at the host IP on port **9443**; first-run
  setup is creating a secure admin username and password.
- Chuck's framing: once Portainer is up, it's effectively the last time you'll need to
  run Docker via the CLI (he softens this to "you'll use them a lot less").
- The Portainer UI exposes containers, images, networks, volumes, and a dashboard; you
  can start/stop/restart containers and open an in-browser terminal into a running
  container.
- Add Container lets you search Docker Hub inline, set port mappings, expose all ports
  to random host ports, set access control, auto-remove, volumes, networks, restart
  policies, and interactive/TTY console — then deploy, all from the GUI.
- **Stacks** is Portainer's name for Docker Compose; you can paste or upload a compose
  file and deploy many containers (he deploys ~14) as one stack, managed from Portainer.
- To manage a home lab behind a firewall from a cloud-hosted Portainer server, the
  default agent would require opening firewall ports; the **Edge agent** avoids that —
  it connects outbound and needs no exposed ports.
- Edge agent workflow: in the Portainer server, add an environment → Docker → Edge
  agent → name it → create → copy the generated `docker standalone` command → run it
  (with `sudo`) on the remote host; it then connects automatically and shows a green
  "heartbeat" status.
- Result demonstrated: Chuck opens a console into a Kali Linux container running on his
  home lab from his cloud Portainer, with no ports exposed.
- Chuck runs his lab and business on Linode; a test VM (Nanode 1GB, the cheapest) costs
  about $0.0075/hour, or about $5/month if left running.

## Notable verbatim quotes

> "Docker can be a little hard, right? I mean, I've had to make three videos just to
> explain how to do stuff with it, but throw those videos out. We've been doing things
> the hard way. I can't believe I wasn't using this tool before."

> "It's a beautiful web gooey that makes deploying and managing Docker. Not only stupid,
> easy, but delightful."

> "Literally you can put it on a raspberry pie... It can be WSL. It can even be on the
> computer you're using right now. Anywhere you can run a Docker container it'll work."

> "And that my friends is the last time you'll ever, ever, ever have to run Docker via
> the CLI. You're done. Forget all those commands. You don't have to think about 'em
> anymore. Probably not, but you'll use them a lot less."

> "Yes, Docker is cool, but it's like when you deploy... okay, I don't really see it.
> How's it going? I don't know. I can do a Docker PS, but it feels kind of like weird.
> This gives you a window. You can see everything. I love that."

> "I am accessing a Cali Lenox box from my Clouder to my home lab. That's amazing,
> right? No port's exposed."

> "I love how it makes Docker more approachable to people with Porter. You can do a ton
> of stuff with ease."

> "You always need coffee for everything in it, right? Never check, do coffee and make
> sure you hack that YouTube algorithm... Ethically of course."

_Caption note: the auto-caption consistently renders "Portainer" as "Porter," "nginx"
as "engine X," "Kali Linux" as "Cali Lenox," and "Linode" as "Le node / Leno / ode."
Tool names are corrected in the paraphrased claims above; quotes are left as captioned._

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT). (Abby, a colleague,
appears on screen performing some install steps at Chuck's direction, but the narration
and all claims are Chuck's.)
