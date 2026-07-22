---
type: youtube-video
source_date: 2023-06-19
url: https://www.youtube.com/watch?v=xBIowQ0WaR8
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [homelab-selfhosting, cloud-devops]
tags: [self-hosting, personal-cloud, nextcloud, data-ownership, homelab]
---

# build your own cloud

## Summary

A long-form homelab tutorial in which Chuck argues for replacing "the triad" (Google
Drive, OneDrive, Dropbox) with a self-hosted personal cloud so you own and control your
own data. He walks through two free self-hosting platforms with different target
audiences: **FileCloud** (the video's sponsor — an enterprise file-sharing / EFS
solution with a free Community Edition, targeting large companies and installable even
on Windows) and **Nextcloud** (open-source, more home-lab / consumer oriented). The
core pitch blends a data-ownership philosophy with a "learn by cosplaying as a company"
homelab ethos: run enterprise-grade tools in your own lab to build hireable skills.

The build itself is substantial and hands-on:
- **FileCloud on AWS**: launch an EC2 instance from the FileCloud AMI (T2 medium
  recommended, T2 micro free-tier eligible), create an SSH key pair, log in at
  `/admin` (default user `admin`, password = the EC2 instance ID), apply the free
  Community Edition license.
- **Offloading storage to Amazon S3**: create an S3 bucket, create an IAM user with an
  inline S3 policy (JSON copied from FileCloud's docs), generate access keys, edit
  `cloud_config.php` via SSH/nano to change storage implementation from `local` to
  `Amazon S3`, copy the sample S3 config file, plug the keys/bucket into FileCloud, and
  enable AES-256 encryption at rest and in transit. Argues S3 (~$0.023/GB/month
  standard, cheaper infrequent-access and Glacier tiers — e.g. ~$10/month to archive
  10 TB) is more economical than growing the EC2 volume, and cheaper than the triad at
  large scale.
- **FileCloud on-prem**: Docker/Docker-Compose install (pull only the needed images,
  skip Solr/preview), direct Ubuntu 20.04 LTS package install, or a prebaked VirtualBox/
  ESXi OVF image; Windows via MSI.
- **Adding an external hard drive (Linux)**: identify with `lsusb`/`lsblk`, format
  `ext4` with `mkfs`, mount to `/mnt/filecloud`, fix permissions with `chmod -R` so
  Apache can read/write, point FileCloud's storage path at the mount.
- **Domain + SSL**: point a Cloudflare subdomain (proxied) at the public IP, generate a
  CSR with `openssl` on the EC2 box, get an origin certificate signed by Cloudflare,
  enable SSL in Apache (`a2enmod`), install the cert/key, edit the Apache vhost (port 80
  → 443, add `ServerName` and the SSL engine block), restart Apache, and update
  FileCloud's server URL. For on-prem, recommends Cloudflare Tunnels (`cloudflared`)
  instead of port-forwarding.
- **Apps / sharing**: FileCloud Sync vs. FileCloud Drive (mounts your cloud as a mapped
  network drive, e.g. `L:`), plus "hyper-secure" file sharing (password, expiry,
  download-count limits) done straight from File Explorer.
- **Nextcloud**: quickest via a single `docker run`, AIO installer (a Docker container
  that installs the other containers), notes it needs a constant internet connection
  and tries to be an everything-suite (contacts, calendar, notes, tasks, office).

He closes with an honest verdict: FileCloud limits Community Edition to 5 users but
gives enterprise-grade governance and the mapped-drive/download-limit sharing nobody
else does; Nextcloud is unlimited-user, open-source, feature-maximalist, great for
tinkerers. He personally still uses Google Drive and Dropbox as backups (redundancy) but
keeps personal data self-hosted for control.

## Key claims (dated — the build + self-hosting philosophy)

- (2023-06-19) Paying the triad (Google Drive, OneDrive, Dropbox) means giving them
  control of your data; the solution is to build and host your own cloud so the data is
  yours. — *self-hosting philosophy / data ownership*
- (2023-06-19) The triad's risks are real and have all happened: price changes,
  outages, hacks, and the provider deciding your data "shouldn't be" accessible. —
  *data ownership*
- (2023-06-19) Building your own cloud is "crazy simple" — all you really need is a
  computer (a spare laptop + external hard drive, a VM, a Docker container, or a cloud
  VM you host yourself), plus coffee.
- (2023-06-19) Both featured tools are completely free but target different audiences:
  FileCloud is enterprise-focused (government, finance, education), Nextcloud is more
  home-lab/open-source.
- (2023-06-19) FileCloud is roughly the only self-host-your-own-cloud solution that
  installs on Windows (Windows 10+ and Windows Server), which is a reason enterprises
  like it; it was historically known as an EFS (enterprise file sharing) solution.
- (2023-06-19) Self-hosting gives features the triad never gave us: hyper-secure sharing
  (password-protect a link, limit its lifetime, limit the number of downloads) and
  mounting your cloud as a network share/drive that behaves like local storage.
- (2023-06-19) Chuck's core homelab rationale: he builds his lab to "cosplay as a
  company" and get hands-on experience with the enterprise tools companies actually
  use, so those companies will then pay him for the skills — the homelab is for
  learning. — *homelab philosophy*
- (2023-06-19) On-prem hosting is completely free (you use your own hardware); AWS
  charges because you're renting someone else's hardware.
- (2023-06-19) For AWS storage, use S3 rather than enlarging the EC2 volume: S3 is
  ~$0.023/GB/month (standard tier), billed only for what you use, with cheaper
  infrequent-access and Glacier archive tiers — e.g. ~$10/month to archive 10 TB. The
  triad may beat it on consumer price, but S3 wins on control and, at very large scale,
  on cost.
- (2023-06-19) FileCloud enterprise capabilities include data governance: retention
  policies, smart DLP (data leak prevention), zero-trust file sharing, antivirus
  scanning, content classification, legal holds, compliance center (GDPR, HIPAA, ITAR),
  if-this-then-that workflows on files, and integrations (Active Directory, SSO,
  Salesforce, SIEM, reCAPTCHA, McAfee, Microsoft Teams/Office).
- (2023-06-19) FileCloud Community Edition is capped at 5 users; go past that (or need
  enterprise features/governance) and it's a paid/business decision — otherwise
  Nextcloud's unlimited users may fit better.
- (2023-06-19) Nextcloud needs an essentially always-on internet connection and doesn't
  do the mapped-drive-with-download-limits sharing that Chuck loves about FileCloud;
  it can run almost anywhere including a Raspberry Pi (Nextcloud Pi), Synology NAS, and
  TrueNAS.
- (2023-06-19) Chuck's own practice: he still uses Google Drive and Dropbox as backups
  because he likes his data in as many places as possible (his videos are public
  anyway), but keeps personal/private data self-hosted for control — and businesses
  with regulations especially need that control. — *personal data practice*

## Notable verbatim quotes

> "Most of us paid Dropbox, Google Drive, OneDrive to host and keep our data in the
> cloud, giving them control of our data."

> "So the solution is to create your own, create your own cloud, host your own stuff.
> Now, this is actually crazy simple. All you're gonna need seriously is a computer."

> "Like gimme my data. No one can have it. It's not leaving my house unless I can share
> it securely."

> "The reason I build my home lab is so I can kind of pretend to be a company, cosplaying
> as a company, right? Because I wanna get hands on the skills and experience with stuff
> companies might use and then pay me for those skills."

> "My home lab is to learn."

> "Nowadays, data is the name of the game. Keeping your data safe and secure, making sure
> you're not sharing it with someone you shouldn't."

> "I hope I encourage you to possibly kick the triad to the curb. Now I still use Google
> Drive and I use Dropbox. I use 'em as backup... I like my data being everywhere."

> "But now for personal things, no, I don't put everything up there. I like control of
> that. So for you, you may want to be very much in control of your personal data."

> "I just want to make sure you guys know there's an option besides going with the triad.
> It does require a bit of IT knowledge, a bit of tinkering."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: build-your-own-cloud / data-ownership self-hosting philosophy -->
