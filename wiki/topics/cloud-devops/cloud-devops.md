---
type: hub
domain: cloud-devops
created: 2026-07-14
updated: 2026-07-22
---

# Cloud & DevOps — hub

Cloud platforms, containers, Kubernetes, Ansible, and automation — the DevOps side of
modern IT. This is the domain where Chuck's teaching pivots from "pass the CCNA" toward
"the network engineer of the future writes code." It overlaps heavily with
[[../linux-terminal/linux-terminal]] (the OS these tools run on) and
[[../networking/networking]] (the gear being automated).

## Key ideas & topics

- **The late-2018 pivot to network automation.** In an October 2018 channel update,
  Chuck reframed where the channel — and network engineering itself — was heading:
  toward automation and coding, not just CLI configuration by hand
  ([[../../sources/2018-10-25-yt-O8HDIRtMvwI]]). Days later he made the thesis concrete
  in "HOW to Start Coding as a Network Engineer," arguing that Python and
  intent-based / programmable networking are becoming core network-engineer skills, and
  that engineers should start coding now rather than wait for their job to demand it
  ([[../../sources/2018-10-30-yt-eAdrnTOcPOg]]). (Paraphrase; positions dated to 2018-10.)

- **The signature "you need to learn X RIGHT NOW!!" tutorial format.** By 2020 Chuck's
  breakout technology tutorials settled into a repeatable, high-energy format: an
  urgent title ("you need to learn Docker RIGHT NOW!!", "you need to learn Ansible RIGHT
  NOW!!"), a fast "101" walk-through, and a hands-on lab the viewer can follow along
  ([[../../sources/2020-04-02-yt-eGz9DS-aIeY]], [[../../sources/2020-05-07-yt-5hycyr-8EKs]]).
  This is a defining piece of Chuck's creator playbook — see
  [[../creator-coffee-business/creator-coffee-business]] for how the format ties into the
  channel's growth. (Paraphrase; format observed 2020.)

- **Docker / containers 101.** "you need to learn Docker RIGHT NOW!!" frames containers
  as an essential foundational skill for modern IT and DevOps, teaching the basics of
  what containers are and how to run them as a beginner-friendly lab
  ([[../../sources/2020-04-02-yt-eGz9DS-aIeY]], 2020-04-02). (Paraphrase.)

- **Ansible / Linux automation.** "you need to learn Ansible RIGHT NOW!!" introduces
  configuration management and infrastructure automation — using Ansible to control many
  machines from one control node — as the next step after Docker for aspiring DevOps and
  network engineers ([[../../sources/2020-05-07-yt-5hycyr-8EKs]], 2020-05-07). Builds on
  Linux fundamentals ([[../linux-terminal/linux-terminal]]). (Paraphrase.)

- **Running a CCNA lab in the cloud (Azure + GNS3).** Chuck demonstrated spinning up a
  free CCNA study lab in Microsoft Azure by running GNS3 network emulation on a cloud VM,
  showing that you can practice for certs without buying physical gear or a powerful home
  PC ([[../../sources/2019-03-02-yt-FfJXcoqTvrs]], 2019-03-02). An early example of using
  public cloud as practical infrastructure for learning. (Paraphrase.)

- **DevNet + Arduino / Raspberry Pi / Python network-monitoring builds.** Bridging
  hardware, code, and networking, Chuck built a project using Arduino, a Raspberry Pi,
  and Python to monitor a Cisco router — a hands-on take on the DevNet / programmable-
  network direction, connecting physical-computing gadgets to network telemetry
  ([[../../sources/2018-12-16-yt-7UkkrNoZUwU]], 2018-12-16). Reinforces the same
  "network engineers should code" thesis from the 2018 pivot. (Paraphrase.)

- **The full "you need to learn X RIGHT NOW!!" cloud/DevOps curriculum (2020–2022).**
  What began as Docker in 2020 grew into a signature series covering the whole modern
  cloud/DevOps stack: Docker ([[../../sources/2020-04-02-yt-eGz9DS-aIeY]], 2020-04-02),
  Ansible ([[../../sources/2020-05-07-yt-5hycyr-8EKs]], 2020-05-07),
  AWS ([[../../sources/2020-08-15-yt-bgPuPSPZe2U]], 2020-08-15),
  Kubernetes ([[../../sources/2020-09-09-yt-7bA0gTroJjw]], 2020-09-09),
  Virtual Machines ([[../../sources/2021-01-18-yt-wX75Z-4MEoM]], 2021-01-18),
  Load Balancing ([[../../sources/2021-06-18-yt-LlbTSfc4biw]], 2021-06-18),
  Python ([[../../sources/2021-08-14-yt-mRMmlo_Uqcs]], 2021-08-14),
  Google Cloud ([[../../sources/2021-11-04-yt-YJwhQowT84A]], 2021-11-04),
  Bash scripting ([[../../sources/2022-03-25-yt-SPwyp2NG-bE]], 2022-03-25), and
  SQL ([[../../sources/2022-08-17-yt-xiUTqnI6xk8]], 2022-08-17). Chuck frames these as
  the concrete skill checklist for the "network engineer of the future" and for anyone
  moving into DevOps/cloud roles — each an urgent-titled 101 plus a follow-along lab.
  The programming entries (Python, Bash, SQL) overlap with
  [[../linux-terminal/linux-terminal]] and the free-course model in
  [[../certifications-career/free-courses]]. (Paraphrase; series dated 2020–2022.)

- **Docker becomes a multi-video subtopic and Chuck's self-hosting backbone.** Beyond
  the original containers-101 intro ([[../../sources/2020-04-02-yt-eGz9DS-aIeY]]), Chuck
  expanded Docker into deeper follow-ups: Docker networking — how the default bridge,
  custom bridges, and macvlan give containers their own addressing
  ([[../../sources/2022-08-06-yt-bKFMS5C4CG0]], 2022-08-06) — and Docker Compose for
  defining multi-container stacks declaratively in a single YAML file
  ([[../../sources/2022-08-31-yt-DM65_JyGxCo]], 2022-08-31). Docker also underpins much
  of his self-hosting/home-lab content (e.g. running Pi-hole in a container), tying this
  domain to [[../homelab-selfhosting/homelab-selfhosting]]. (Paraphrase.)

- **Kasm container-streaming (Kali-in-the-browser).** Chuck showcased Kasm Workspaces
  to stream a full Kali Linux desktop into a web browser as disposable, containerized
  sessions — building "the ultimate hacking lab" you reach from any device
  ([[../../sources/2022-01-17-yt-U7e-mcJdZok]], 2022-01-17). This container-streaming
  pattern is a direct precursor to his later Cloud Browser product. (Paraphrase.)

## Source pages

- [[../../sources/2018-10-25-yt-O8HDIRtMvwI]] — What's next for NetworkChuck? *UPDATE* (automation pivot) (2018-10-25)
- [[../../sources/2018-10-30-yt-eAdrnTOcPOg]] — HOW to Start Coding as a Network Engineer (2018-10-30)
- [[../../sources/2018-12-16-yt-7UkkrNoZUwU]] — Arduino + Raspberry Pi + Python to Monitor Cisco Router (DevNet) (2018-12-16)
- [[../../sources/2019-03-02-yt-FfJXcoqTvrs]] — CCNA Lab in the Azure Cloud for FREE! (GNS3) (2019-03-02)
- [[../../sources/2020-04-02-yt-eGz9DS-aIeY]] — you need to learn Docker RIGHT NOW!! (Containers 101) (2020-04-02)
- [[../../sources/2020-05-02-yt-dH3DdLy574M]] — BLOCK EVERYTHING w/ PiHole on Docker (2020-05-02)
- [[../../sources/2020-05-07-yt-5hycyr-8EKs]] — you need to learn Ansible RIGHT NOW!! (2020-05-07)
- [[../../sources/2020-08-15-yt-bgPuPSPZe2U]] — you need to learn AWS RIGHT NOW!! (2020-08-15)
- [[../../sources/2020-09-09-yt-7bA0gTroJjw]] — you need to learn Kubernetes RIGHT NOW!! (2020-09-09)
- [[../../sources/2020-10-24-yt-6aLyZisehCU]] — VMware on a Raspberry Pi!?!?! (ESXi Install) (2020-10-24)
- [[../../sources/2021-01-18-yt-wX75Z-4MEoM]] — you need to learn Virtual Machines RIGHT NOW!! (2021-01-18)
- [[../../sources/2021-02-05-yt-37tyxaQbtN4]] — you need to learn Hybrid-Cloud RIGHT NOW!! // FREE CCNA // EP 10 (2021-02-05)
- [[../../sources/2021-04-27-yt-_u8qTN3cCnQ]] — Virtual Machines Pt. 2 (Proxmox install) (2021-04-27)
- [[../../sources/2021-06-18-yt-LlbTSfc4biw]] — you need to learn Load Balancing RIGHT NOW!! (2021-06-18)
- [[../../sources/2021-08-14-yt-mRMmlo_Uqcs]] — you need to learn Python RIGHT NOW!! // EP 1 (2021-08-14)
- [[../../sources/2021-11-04-yt-YJwhQowT84A]] — you need to learn Google Cloud RIGHT NOW!! (2021-11-04)
- [[../../sources/2022-01-17-yt-U7e-mcJdZok]] — create the ULTIMATE hacking lab (Kasm Kali-in-browser) (2022-01-17)
- [[../../sources/2022-03-25-yt-SPwyp2NG-bE]] — you need to learn BASH Scripting RIGHT NOW!! // EP 1 (2022-03-25)
- [[../../sources/2022-05-16-yt-UtMMjXOlRQc]] — i created malware with Python (2022-05-16)
- [[../../sources/2022-06-03-yt-4xJDDUt4Wq8]] — the $0.30 Hacking Lab (2022-06-03)
- [[../../sources/2022-08-06-yt-bKFMS5C4CG0]] — Docker networking is CRAZY!! (2022-08-06)
- [[../../sources/2022-08-17-yt-xiUTqnI6xk8]] — you need to learn SQL RIGHT NOW!! (2022-08-17)
- [[../../sources/2022-08-31-yt-DM65_JyGxCo]] — Docker Compose will BLOW your MIND!! (2022-08-31)
