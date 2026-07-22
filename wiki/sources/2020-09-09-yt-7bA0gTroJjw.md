---
type: youtube-video
source_date: 2020-09-09
url: https://www.youtube.com/watch?v=7bA0gTroJjw
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cloud-devops, linux-terminal]
tags: [kubernetes, k8s, containers, orchestration, learn-x-now, tutorial]
---

# you need to learn Kubernetes RIGHT NOW!!

## Summary

A signature "you need to learn X RIGHT NOW" tutorial in which Chuck teaches Kubernetes (K8s)
from the ground up, framing it as the solution to the scaling pain of managing many Docker
containers by hand. He builds the entire lesson around a running story: he and the viewer sell
"NetworkChuck Coffee" from a website deployed in a Docker container, traffic explodes, and the
manual work of adding servers, spinning up containers, and configuring load balancers becomes
unsustainable. Kubernetes is introduced as a **container orchestrator** that automates all of it.

Chuck walks through the core architecture — a **master node** (the boss that calls the shots)
and **worker nodes** running a container runtime (Docker, though it could be containerd, rkt,
etc.) plus the `kube-proxy` and `kubelet` components — and stresses it is "not Kubernetes *or*
Docker, it's yes both." He then labs it live using the sponsor **Linode** (Linode Kubernetes
Engine), which offers a $100/60-day credit and bakes in the master node for free. He creates a
cluster, installs `kubectl` on Kali Linux, wires up the kubeconfig YAML, and deploys the coffee
site. Concepts covered hands-on: **pods** (containers live inside pods, usually one container per
pod), **deployments** and **manifests** (YAML describing desired infrastructure), **desired
state** / replicas (declare "always 3 pods" and the master enforces it), the **scheduler**
distributing pods across nodes, **services** of type LoadBalancer to expose pods to the internet
(which also provisions a Linode NodeBalancer), **selectors/labels** for automatic load balancing,
scaling pods up (3 → 10 → 20), and rolling updates by editing the image in the manifest. He closes
with further-learning pointers (a Pluralsight course by Nigel Poulton, the book *Kubernetes in
Action*, and `minikube` for local labs), a reminder to delete the cluster and NodeBalancer to
avoid charges, and his recurring teaching philosophy: learn something new, then turn around and
teach it.

## Key claims (dated — K8s concepts)

All paraphrased from the video (2020-09-09) unless quoted:

- Kubernetes (K8s) is a **container orchestrator**: it can deploy 100 Docker containers with one command and automates the manual work of scaling containers and load balancers.
- Kubernetes is **complementary to Docker, not a replacement** — you still need a container runtime (Docker, containerd, rkt, etc.) on the worker nodes; Kubernetes makes Docker better.
- You should **learn Docker before Kubernetes** — they go hand in hand, and K8s builds on container knowledge.
- A cluster has a **master node** (the boss / "helmsman" that calls the shots and keeps workers in line) and **worker nodes** where containers actually run.
- Worker nodes run three things: the **container runtime** (Docker), **kube-proxy**, and the **kubelet** — installing these makes a server a worker node ("team Kubernetes").
- The **master runs four components/roles**, including the **kube-apiserver** (how you talk to the master) and the **scheduler** (decides which worker node gets each pod based on how busy they are).
- A **pod** is the unit Kubernetes creates: a container lives *inside* a pod, you can technically have multiple containers per pod, but typically it's one container per pod. Every pod gets its own **private IP** only reachable from within the cluster's nodes.
- `kubectl` (cube-cuddle) is a cross-platform (Windows/Mac/Linux) command-line tool, very similar to Docker's CLI, used to tell the master what to do; the master then tells the worker nodes.
- `kubectl run` creates an ad-hoc pod; a **deployment** is the more powerful, organized, intentional approach, described in a YAML file called a **manifest**.
- **Desired state**: a deployment declares how many replicas (e.g. "always 3 pods") should run, and the master continuously reconciles reality to that state — not two, not four, exactly three.
- You can run **more pods than nodes** (e.g. 10 pods on 3 servers); the scheduler distributes them roughly evenly and reassigns pods away from overworked nodes.
- To reach pods from outside, deploy a **service** — a `LoadBalancer` type exposes pods to the internet and load-balances across them; in the cloud it also provisions a real load balancer (a Linode **NodeBalancer**).
- Services use a **selector/label** (e.g. app `nc-coffee`) to pick which pods to load-balance; whether there are 2 pods or 2,000, any pod with that label is automatically included.
- **Scaling**: edit the deployment's replicas (3 → 10 → 20) and Kubernetes creates/terminates pods to match; it can also **autoscale** on metrics (e.g. scale out when pods exceed ~75% CPU utilization).
- **Rolling updates**: change the container image in the manifest and Kubernetes terminates old pods and spins up new ones with the new image automatically.
- Kubernetes terminology is **nautical** — "Kubernetes" is Greek for helmsman/captain who steers the ship; hence terms like "manifest."
- Learning Kubernetes is a **valuable, in-demand cloud skill** because most cloud providers have Kubernetes built in.
- You can run Kubernetes locally for a lab via **minikube** (one workstation), or on bare metal / VMs, not just in the cloud.
- Cloud Kubernetes bills for what you use — remember to **delete the cluster and the NodeBalancer** afterward (the NodeBalancer, ~$10/month, does not auto-delete) to avoid charges.

## Notable verbatim quotes (signature hook)

> "you need to learn kubernetes right now but why well kubernetes can deploy 100 docker containers with one command"

> "in this video i'm going to teach you kubernetes we're going to walk through what it is how do you use it and you'll even get a chance to lab this up for free"

> "it's not kubernetes or docker it's yes both we're gonna use both kubernetes is gonna help us make docker better"

> "when you think about kubernetes think about pods as containers"

> "here's the cool part about kubernetes it's the concept of desired state ... i want there to always be three pods with this image running always not two not four not twelve i want three and he will constantly make sure that's the case"

> "the commander the helmsman kubernetes the master he was like oh we got to update a manifest let me check it out oh g willow curse we need 10. he talks like that we need 10 of these"

> "when i update my website i update it in one place my my docker image and then i just update my manifest file and the rest is history"

> "i had to learn kubernetes from the ground up but it's fun learning new things and i encourage you to do what i did when you learn something new like this turn it around and make a video about it or make a blog post teach someone about it ... you learn it better when you teach it"

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: 'you need to learn X RIGHT NOW' format (Kubernetes) -->
