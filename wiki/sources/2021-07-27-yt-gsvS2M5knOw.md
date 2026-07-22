---
type: youtube-video
source_date: 2021-07-27
url: https://www.youtube.com/watch?v=gsvS2M5knOw
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [homelab-selfhosting, linux-terminal]
tags: [guacamole, remote-access, ssh, rdp, self-hosting, browser]
---

# access EVERYTHING from your web browser!! (Linux and Windows Desktop, SSH) // Guacamole Install

## Summary

Hands-on tutorial in which Chuck demonstrates Apache Guacamole, a free, open-source,
clientless remote-desktop gateway that lets you RDP into Windows, SSH into Linux, and
VNC into a Linux GUI entirely from a web browser — from any device (computer, phone,
tablet), no dedicated RDP/SSH/VNC client required. He gives two complete walkthroughs
of the same goal: a **cloud** install (on Linode, the video's sponsor) and an **at-home
home-lab** install (on an Ubuntu 20.04 VM running in Proxmox). In both cases he does not
install Guacamole "the normal way" (directly on the VM); instead he installs it through
**Cloudron**, an app-platform layer that turns the otherwise-fiddly Guacamole setup into
a one-click app-store install. A shared prerequisite section covers getting a free domain
from Freenom (`.tk`) and pointing it through Cloudflare for DNS. He closes by confessing
he is "super mad" at himself for not adopting Guacamole sooner, calling it life-changing
for consolidating all his remote connections into one browser tab.

## Key claims (dated — the build + concept)

All dated 2021-07-27, paraphrased from Chuck:

- **Concept.** Apache Guacamole is a free, open-source, clientless remote-access gateway:
  it puts RDP (Windows), SSH (Linux terminal), and VNC (Linux GUI) sessions inside a web
  browser, reachable from any device, with no local client software needed.
- **Two deployment paths, same tool.** Path 1 (cloud) suits people managing many cloud
  machines; path 2 (home lab) suits self-hosters. Both are shown end to end.
- **Install method.** Rather than installing Guacamole directly on the VM, he installs it
  via **Cloudron**, a platform that makes complex apps installable like app-store apps —
  and that hosts many other self-hostable apps besides Guacamole.
- **Cloudron limits.** Cloudron's free tier allows only two installed apps; more requires
  a monthly fee.
- **Shared prerequisite — domain + DNS.** Both paths need a domain name. He gets a free
  one from freenom.com (example: a `.tk` domain), then creates a free Cloudflare account,
  adds the site, and repoints the domain's name servers (set in Freenom) to Cloudflare's.
- **Cloudflare API automation caveat.** Cloudron can auto-manage DNS if you give it your
  Cloudflare **Global API Key** — but this does not work for free top-level domains like
  `.tk`, forcing manual A-record creation instead. Manual records must be set to **DNS
  only** (proxy off) so verification and Let's Encrypt certificate issuance succeed.
- **Cloud path (Linode + Cloudron).** In Linode, Create → Linode → Marketplace → select
  the Cloudron app, pick an image (Ubuntu 20.04), region, and the smallest plan (~$5/mo),
  then deploy. Cloudron's provisioning scripts take ~10 minutes after the VM shows
  "ready." Then browse to the public IP, run through the Cloudron domain/DNS setup, and
  Let's Encrypt issues a certificate for the `my.<domain>` subdomain.
- **Home-lab path (Proxmox VM + Cloudron).** On an Ubuntu 20.04 VM, SSH in, `sudo su -`
  to root, then install Cloudron by fetching its setup script, `chmod +x` it, and running
  it — after which the box reboots. Reach the Cloudron setup UI at the box's private IP.
- **Home networking requirements.** For outside-the-home access you must port-forward
  **443** (and **80**, which Let's Encrypt needs to issue the SSL certificate) on your
  router to the Cloudron server. A dynamic public IP needs **dynamic DNS** (he points to
  a separate Raspberry-Pi + Cloudflare-API video). If 80/443 are already in use, he
  points to his Kemp reverse-proxy/load-balancer video.
- **Using Guacamole.** Default login is username `guacadmin` / password `guacadmin`.
  Connections are added under Guac admin → Settings → Connections → New Connection.
  - **SSH:** protocol SSH, set hostname + port 22, username/password. (Demo: a Raspberry
    Pi, login `pi` / `raspberry`.)
  - **RDP (Windows):** protocol RDP, hostname/IP + port 3389 (he advises changing the
    default port for security but skips it "because I'm lazy"), username/password plus
    the domain name if joined to one; set security mode to **NLA** (network level
    authentication) and enable **ignore server certificate** unless you run your own
    certificate authority.
  - **VNC (Linux GUI):** protocol VNC, hostname/IP + port 5901 by default,
    username/password. He frames VNC as "RDP for Linux."
- **Payoff.** All connections live in one browser interface and switch instantly. It works
  on phones/tablets too — an on-screen "Chuck from the future" correction retracts an
  earlier caveat about the mobile keyboard, confirming mobile works fine.

## Notable verbatim quotes

> "I found this amazing tool ... that allows us to remotely access all of our stuff in our
> browser from anywhere. I'm talking RDP into your Windows machines ... SSH into Linux, VNC
> into Linux from a browser. It doesn't matter what device you're using."

> "It's actually a tool called Guacamole. And so these won't work. These are avocados. You
> have to make guacamole. But for real, it's a tool called Guacamole from Apache. It's an
> open source tool, so it's free."

> "I'm honestly super mad at myself for just now starting to use it cuz it saved me a ton
> of time."

> "The way we're going to install Guacamole is not the normal way ... we're going to use
> something called Cloudron. ... It's basically a platform that makes it super easy to
> install apps like Guacamole, which can be kind of complicated to set up."

> "I'm in my Windows machine. I can switch back to my Linux machine ... I'm in a browser
> right now. Are you freaking kidding me?"

> "This is the real power of this because you don't need an RDP client. You don't need an
> SSH client. You're just accessing it via a browser. How cool is that, man? And if you
> follow this tutorial, you can do it from anywhere."

> "Seriously, guacamole is life-changing."

> "You can't skip this with coffee just cuz you're doing it on prem in your house."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: browser-based remote access (Guacamole) — precursor to Cloud Browser interest -->
