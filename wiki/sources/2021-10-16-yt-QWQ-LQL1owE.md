---
type: youtube-video
source_date: 2021-10-16
url: https://www.youtube.com/watch?v=QWQ-LQL1owE
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, cloud-devops, linux-terminal]
tags: [kali-linux, aws, cloud, hacking-lab, ec2]
---

# FREE Kali Linux in the Cloud (AWS)

## Summary

A fast, hands-on tutorial walking through how to run [[../topics/linux-terminal/kali-linux|Kali Linux]] — described as the best Linux hacking distro — on a free-tier [[../entities/aws|AWS]] EC2 instance, giving you an always-on cloud hacking box with a public IP. Chuck sets up a free-tier AWS account (using a privacy.com virtual card to cap spend, since a credit card is required), launches Kali from the AWS Marketplace as a `t2.micro` free-tier-eligible instance, and connects over SSH using a downloaded `.pem` key pair. He then goes beyond command line: he installs a desktop environment (XFCE + tightvncserver, plus gnome-core) and reaches the GUI securely by tunneling VNC over SSH. The video reinforces his cheap/accessible-lab ethos — a free, always-on box you can build a whole vulnerable-machine lab around, while learning both AWS and Kali as resume skills. Privacy.com is the video sponsor.

## Key claims (dated — setup)

All dated 2021-10-16 (paraphrase unless quoted):

- Kali Linux can be run for free on AWS as long as you stay within the free tier; going over incurs charges.
- A credit card is required to create a free-tier AWS account; a privacy.com virtual card lets you cap the spend (e.g. a $5/month limit) and toggle the card on/off as protection.
- Launch the box via EC2 (AWS's virtual machine service): select the AWS Marketplace, search "Kali," select the image, and choose the `t2.micro` free-tier-eligible instance type.
- Kali Linux in the Marketplace is free but still requires "subscribing" to it before use.
- AWS access uses an SSH key pair instead of a password; you create a key pair, download the `.pem` file, and must not lose it — without the key you cannot get into the box.
- Connect from the command line with `ssh -i <key>.pem kali@<public-ip>`, accepting the unknown host fingerprint on first connection. The command is identical on Linux and Mac.
- The Marketplace image is bare-bones; run `apt install kali-linux-full` for everything (slow) or `apt install kali-linux-top10` for just the top 10 security tools.
- To add a GUI: `sudo apt update`, then install `xfce4 xfce4-goodies tightvncserver`, then install `gnome-core` and Kali desktop defaults, choosing GDM3 or LightDM when prompted (Chuck picks LightDM).
- Configure the VNC server with `tightvncserver -geometry 1024x768` and set a VNC password; it runs on port 5901 (verify with `netstat -tulpn`).
- Reach the GUI securely by building an SSH tunnel — `ssh -L 5901:localhost:5901 -N -f kali@<ip> -i <key>.pem` — then point a VNC viewer (e.g. RealVNC VNC Viewer) at `localhost:5901`. The tunnel must be re-run every time you want to SSH/VNC in; that is the price of doing it securely.
- Why do this: it is free within the free tier, always-on with a public IP (great for learning hacking), lets you build a cloud lab with additional vulnerable/Windows machines, and teaches both AWS and Kali as resume-worthy skills.

## Notable verbatim quotes

> We're going to throw Kali Linux, the best Linux hacking distro up into the cloud on AWS, which if that doesn't sound cool, then why are you even here?

> I'm going to walk you through setting up a free tier account, which won't charge you a dang thing. Unless you go over the free tier stuff.

> I love this because I can turn this card on and off. When I need to, in case AWS is going crazy on me.

> I'm going to say it again. Don't lose the file. Don't lose that key. If you don't have the key, you can't get in just like your house.

> I'm in Windows and I'm VNC-ing or remotely accessing Kali Linux in the cloud on AWS. Powerful. How cool was that over a secure SSH tunnel.

> You can create your own lab environment in the cloud.

> It's just cool to learn AWS and Kali Linux all at the same time, both killer skills you can put on your resume.

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: canonical example of Chuck's cheap/accessible-lab ethos — a free, always-on cloud hacking box with reusable AWS/Kali setup steps and the privacy.com spend-cap trick; good source for topics/persona synthesis. -->
