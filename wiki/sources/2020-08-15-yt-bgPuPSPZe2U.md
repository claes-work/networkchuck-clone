---
type: youtube-video
source_date: 2020-08-15
url: https://www.youtube.com/watch?v=bgPuPSPZe2U
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cloud-devops, certifications-career]
tags: [aws, cloud, learn-x-now, ec2, tutorial]
---

# you need to learn AWS RIGHT NOW!! (Amazon Web Services)

## Summary

A landmark entry in Chuck's signature "you need to learn X RIGHT NOW" format, this one
aimed at AWS / cloud computing. The video has two halves: a motivational "why" pitch for
learning the cloud, followed by a hands-on "get your hands dirty today" walkthrough that
takes the viewer from zero to a running virtual machine in AWS.

The pitch: the cloud is "basically someone else's computer" — in AWS's case, Amazon's
huge fleet of servers, which companies rent instead of buying hundreds of thousands (or
millions) of dollars of hardware. Chuck argues companies move to the cloud for cost,
freedom, near-endless capacity to scale rapidly, and features they couldn't run in their
own data centers — and that this migration wave is exactly why they need skilled IT
people who know AWS (both to migrate and to manage). He backs the "hottest skill" claim
with cited sources (LinkedIn's Top Skills 2020, Business Insider's Top 20 Tech Skills,
Global Knowledge's most-important IT skills) and a salary datapoint (Dice: ~$128,000/yr
average for a cloud engineer).

The how: Chuck recommends getting certified and names two AWS certs — the entry-level
**AWS Certified Cloud Practitioner** and the next step, **AWS Certified Solutions
Architect – Associate** — noting his brother Cameron switched from network engineer to
cloud engineer via the cert. He then walks through creating a free AWS account (12-month
free tier, personal option, credit card only for overages), signing into the console as
root user, and launching an **EC2** virtual machine: choosing a free-tier-eligible AMI
(Amazon Linux), the **t2.micro** instance size, creating and downloading a public/private
**key pair** for authentication, launching the instance, connecting via the browser, and
finally terminating it. He closes by urging viewers to learn the cloud generally (AWS,
Azure, or Google Cloud — ideally all three) to future-proof themselves.

## Key claims (dated 2020-08-15 — paraphrase unless quoted)

- The cloud is essentially **someone else's computer**; with AWS, that computer belongs
  to Amazon, which rents out its servers to companies and individuals.
- Companies move IT infrastructure to the cloud instead of buying their own servers
  (which can cost hundreds of thousands to millions of dollars). Drivers include cost,
  freedom, and Amazon's effectively endless resources for rapid scaling.
- The cloud offers features a company wouldn't have in its own data center.
- The cloud migration wave is why companies need skilled IT people who know AWS — both to
  move infrastructure to the cloud and to manage it once it's there — making AWS/cloud one
  of the hottest IT skills right now.
- Third-party rankings back the demand claim: LinkedIn's "Top Skills Companies Need Most
  in 2020" put cloud computing at #2 (behind blockchain); Business Insider's "Top 20 Tech
  Skills That Employers Want" put AWS at #6 (behind Python #3, Linux #4, JavaScript);
  Global Knowledge's most-important IT skills list topped out with cloud computing.
- Per the Dice Tech Salary Report, a cloud engineer makes on average ~**$128,000/year**.
- Two AWS certifications to target: **AWS Certified Cloud Practitioner** (entry-level, for
  people brand new to cloud or IT) and **AWS Certified Solutions Architect – Associate**
  (the next level, which gets your foot in the door as a cloud admin).
- Getting certified can change careers: Chuck's brother Cameron switched from network
  engineer to cloud engineer by earning the certification.
- AWS offers a **free tier** with 12 months of free access; you sign up at
  `aws.amazon.com`, can choose a personal account, and a credit card is required only in
  case you exceed the free tier — you won't be charged as long as you stay within it.
- You sign into the AWS Management Console as the **root user** with your signup email and
  password. Selecting the **free** support plan avoids charges.
- **EC2** (Elastic Compute Cloud) is the AWS service for launching virtual machines in the
  cloud.
- When launching an EC2 instance you choose an **AMI** (machine image) — options include
  Amazon Linux, Red Hat, SUSE, and Ubuntu — and should look for the **"free tier
  eligible"** label to avoid charges. Chuck picks Amazon Linux.
- Instance **size** controls resources: the free-tier **t2.micro** is the safe default,
  while larger sizes (e.g. **t2.2xlarge** with 8 virtual CPUs and 32 GB RAM) show the
  cloud's ability to scale up on demand to whatever you need.
- To connect to a Linux EC2 instance from your own computer you authenticate with a
  **public/private key pair** instead of a username and password. You create a new key
  pair, name it, and download the private key — which must be saved somewhere safe, as
  it's what authenticates you.
- After launching, the instance takes a moment to build; you can then connect to it,
  including directly **via the browser** (EC2 Instance Connect), where the username
  defaults to the one set up with the image.
- You can manage an instance's lifecycle from **instance state** — stop, reboot, or
  **terminate** it. Terminating makes the virtual machine go away (good practice for
  tearing down test resources).
- The demo (account → EC2 VM → connect → terminate) is only "step one"; deeper settings
  and features are the fun part you learn as you go further into AWS.
- Learn the cloud generally — it could be AWS, Azure, or Google Cloud, and ideally all
  three; once you learn one cloud, the others are relatively easy to pick up. The point is
  to start, because the cloud is the future and learning it future-proofs you.

## Notable verbatim quotes

> "You need to learn AWS right now. If you're in IT, you've got to learn the cloud, and
> AWS is the biggest player out there."

> "The cloud is basically someone else's computer. And in this case, this computer belongs
> to Amazon."

> "More and more companies are moving their stuff to the cloud, and this is why they need
> you. They need skilled IT people, people who know AWS, to help them move their stuff to
> the cloud."

> "I don't know about you, but when I first start learning something, I just want to get my
> hands dirty. I just want to do it. Well, that's what we're doing right now."

> "That's the beauty of the cloud. We can go huge to accommodate what you want, or what you
> need."

> "You are now signing in to the cloud."

> "You just set up a cloud account in AWS. That's amazing. And not only that, but you set up
> a virtual machine in the cloud."

> "Look, guys, you need to learn the cloud. It could be AWS, it could be Azure, it could be
> Google Cloud. It should be all three. Once you learn one cloud, it's pretty easy to pick
> up the others. But the point is to start learning this stuff because it's the future. You
> want to future-proof yourself."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: 'you need to learn X RIGHT NOW' format (AWS/cloud) -->
