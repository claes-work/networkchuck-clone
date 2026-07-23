---
type: youtube-video
source_date: 2021-07-15
url: https://www.youtube.com/watch?v=X9fSMGkjtug
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [homelab-selfhosting, cloud-devops, linux-terminal]
tags: [raspberry-pi, kubernetes, k3s, rancher, cluster, homelab]
---

# i built a Raspberry Pi SUPER COMPUTER!! // ft. Kubernetes (k3s cluster w/ Rancher)

## Summary

A canonical NetworkChuck homelab build tutorial: Chuck clusters eight Raspberry Pis
into a single "supercomputer" (16 cores / 56 GB RAM in his rig, later measured in
Rancher as 32 cores / 53 GB) by installing **k3s**, a lightweight Kubernetes
distribution created by Rancher Labs. The framing is deliberately beginner-accessible:
you only need **one** Raspberry Pi to follow along — the cluster is optional fun. The
pedagogical hook is that building this teaches you Kubernetes, "one of the most
sought-after skills in the IT industry right now."

The video walks the full end-to-end build:
1. **Headless Pi prep** — flash Raspberry Pi OS Lite (64-bit) with Raspberry Pi Imager;
   edit `cmdline.txt` (enable cgroups for memory, set a static IP) and `config.txt`
   (`arm_64bit=1`); create an empty `ssh` file to enable SSH; SSH in as `pi`, become
   root, enable legacy iptables, reboot.
2. **Install k3s** — one `curl` script on the first Pi makes it the **master /
   control-plane node**; the same script with a token + master URL + node name joins
   each additional Pi as a **worker node**. Verify with `kubectl get nodes`.
3. **Rancher** — optional GUI, installed on a separate Ubuntu 18.04 VM (RancherD on top
   of its own bundled k3s cluster). Import the Pi cluster ("Hogwarts") as an "other"
   (bare-metal) cluster, overriding the agent image to the **arm64** version so it pulls
   correctly on Pi hardware.
4. **Deploy apps** — apply a manifest (`kubectl apply -f`) deploying 6 nginx web
   servers, then 50 replicas of a "hello world" load-balancing visualizer, then a
   Minecraft server via a **Helm chart** through Rancher's Apps & Marketplace.
5. **Kubernetes networking** — explains ClusterIP (unreachable from outside), exposes
   apps with **NodePort** services, then adds an **Ingress** (`i love cows.com`) mapped
   via the local hosts file. Ends by connecting to the Minecraft server and playing on
   the cluster.

Recurring NetworkChuck teaching moves throughout: the coffee-break running gag, the
"pie/pod/room" analogies (containers as a kid locked in their room with Doritos), heavy
emphasis on how hard Kubernetes actually is (repeated credit to the boxboat engineers
who "held my hand"), and the closing "why do this?" pitch — bragging rights plus real,
resume-worthy skills learned through failure. Sponsors: Rancher Labs (now owned by
SUSE) and boxboat.

## Key claims (dated — the build)

All dated 2021-07-15 (publication), paraphrased unless quoted.

- You only need **one** Raspberry Pi to do the whole project; a single Pi becomes both
  master and worker node ("it'll have to tell itself what to do"). Multiple Pis (2, 3,
  8) are just for more fun.
- Recommended minimum hardware: a Pi with **at least 4 GB RAM** (8 GB "to really have
  some fun"), power supply, micro SD card, and a micro-SD-to-USB adapter. A multi-Pi
  cluster also needs a switch and ethernet cables. The install is **headless** — no
  keyboard, mouse, or monitor.
- **k3s** is a lightweight Kubernetes created by Rancher Labs; open source. Per the
  Rancher engineer quoted: the name was a play on "k8s" and "doesn't really mean
  anything." It strips the "fluff," is fast, and is ideal for Raspberry Pi / IoT / edge
  devices.
- Standard Kubernetes (k8s) is **hard to install on bare metal / on-prem**; it was
  built for the cloud (Linode, AWS, Azure), where installing it is comparatively easy.
  k3s makes the bare-metal Pi install fast and easy.
- A **cluster orchestrates** the Pis — it does NOT merge them into one machine you log
  into to play Call of Duty with all the combined RAM/CPU. Each Pi stays its own
  machine; Kubernetes distributes apps so no single Pi gets overloaded (load balancing,
  redundancy, scaling up).
- **Containers** isolate each app (like Docker); you don't need Kubernetes to run
  containers (Docker on one Pi works), but Kubernetes orchestrates containers across a
  cluster.
- **Pod = container(s)** — in Kubernetes a deployed container is nestled inside a pod
  ("POD container, POD container").
- Prep-file edits required for k3s on Pi: enable **cgroups** (memory) in `cmdline.txt`;
  set `arm_64bit=1` in `config.txt` for a 64-bit OS; enable **legacy iptables**; create
  an empty `ssh` file (`New-Item ssh` on Windows / `touch ssh` on Mac/Linux) to enable
  SSH on boot. Default SSH creds: user `pi`, password `raspberry`.
- Install k3s master: a single `curl` install script. Join a worker: same script passing
  the master **token**, the master URL (`https://<master-ip>:6443`), and a unique
  `K3S_NODE_NAME` (default all Pis are named "raspberrypi", which causes conflicts).
- **kubectl** ("cube cuddle") is the primary CLI tool and runs **only on the master**,
  not on worker nodes.
- **Rancher** (also by Rancher Labs) is a free, open-source GUI to manage one or many
  Kubernetes clusters; requires its own separate VM (Ubuntu 18.04, ≥4 GB RAM). Installing
  RancherD sets up its own bundled Kubernetes cluster underneath it — so you end up with
  two clusters.
- Raspberry Pi is **arm64** architecture — many public container images (e.g. Ubuntu,
  CentOS) won't run on it. When importing the Pi cluster into Rancher you must override
  the agent image to the arm64 variant.
- **Deployments** are defined in YAML manifests (`kind: Deployment`), applied with
  `kubectl apply -f`; `replicas:` controls how many pods (demoed 6 nginx, then 50 hello-
  world). A **replica set** keeps the desired count running.
- **Kubernetes networking**: deployed pods get a **ClusterIP** (e.g. 10.42.x.x) reachable
  only inside the cluster — not from your LAN by default. To expose an app, create a
  **NodePort** service, which opens a chosen high port (e.g. 31111) on every node that
  forwards to the app's target port; NodePort automatically load-balances across all
  matching pods on all nodes via label **selectors** (`app: nginx`, `app: hello-world`).
- **Ingress** maps a DNS name (demo: `i love cows.com`) to a service; requires the DNS
  name to resolve to a node IP (set via a home DNS server or the local hosts file at
  `Windows\System32\drivers\etc\hosts`).
- Apps can also be deployed via **Helm charts** (an alternative to raw manifests);
  Chuck installs a **Minecraft server** Helm chart through Rancher's Apps & Marketplace,
  changing `EULA` from false to true, then exposes it with a NodePort on Minecraft's port
  **25565**, and connects a real Minecraft client to play on the cluster.
- Credits Jeff Geerling (YouTube/blog) for arm64 Pi cluster guidance, including the
  Minecraft-on-Pi approach.
- Why do this: bragging rights ("a work of art") plus genuinely learning Kubernetes
  through hands-on failure — "real skills you can take with you into the workplace."

## Notable verbatim quotes

- "16 cores 56 gigs of RAM this is my Raspberry Pi super computer."
- "I am playing Minecraft on a Raspberry Pi cluster it doesn't get cooler than this guys."
- "we're going to learn one of the most killer skills most sought after skills in the IT industry right now kubernetes."
- "you don't need eight raspberry pies like I have all you need is really one."
- "kubernetes is kind of hard I relied heavily on the engineers a[t] boxboat to help me get this going they held my hand to walk me through the Blood Sweat and Tears of getting this set up."
- "the keyword here is orchestrate."
- "when you think about kubernetes and you hear the word pod I want your brain to go POD containers POD containers."
- "there's a tool we're going to use it's called Cube cuddle or kubectl we'll be using this a lot so I want you to know it memorize it become best friends."
- "kubernetes networking is not for the light of heart."
- "I don't play Minecraft but I'll play it on a Raspberry Pi cluster."
- "the other big reason is that it does teach you a ton I can't tell you how much I learned how much I failed through the process of getting this set up projects like this teach you."
- "real skills you can take with you into the workplace that you can add to your resume."
- "oh almost forgot the most important thing you need coffee everything in it requires Coffee."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT). (Brief on-screen/quoted
lines from an unnamed Rancher Labs engineer explaining the k3s name and a "susa"
pronunciation correction are third-party context, not Chuck, and are not persona
training material.)

<!-- ★ L3-candidate: Pi k3s Kubernetes cluster (canonical homelab + learn-k8s-on-a-Pi) -->
