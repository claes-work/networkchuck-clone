---
type: youtube-video
source_date: 2023-03-31
url: https://www.youtube.com/watch?v=jAfQvMxcokI
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity]
tags: [passwords, phishing, password-manager, mfa, defense, awareness]
---

# stop giving your passwords to hackers

## Summary

Despite the title's framing, this video is primarily a hands-on tutorial for
**self-hosting the open-source password manager Passbolt** as the defensive answer to
password security. Chuck's core argument: you need a password manager, but if you don't
want to hand all your passwords to a third-party company, you can self-host one and keep
"godlike control" of them. He walks through deploying Passbolt via Docker on a Linux
server (his preferred option being a Linode cloud VM), configuring the app's base URL to
match the server's reverse DNS name, and adding Traefik as a reverse proxy to obtain a
free trusted TLS/SSL certificate from Let's Encrypt (versus running with an untrusted
cert). He then covers post-install hardening: creating the first admin user, installing
the browser extension, setting a passphrase, downloading the recovery kit, enabling
multi-factor authentication (TOTP), and using the mobile app with Face ID.

Chuck is transparent that he personally uses **Dashlane**, a hosted password manager, as
a matter of convenience — but presents Passbolt as a "killer" self-hosted alternative for
viewers who want full control. He praises Passbolt's security posture: open PGP
encryption, full private key control, end-to-end encryption, and regular audits. The video
is sponsored by Linode (Akamai). At the end he tests whether the cheapest $5/month 1 GB
Linode plan can run Passbolt, and confirms it works fine (with the caveat that a smaller
server supports fewer concurrent users).

## Key claims (dated — threats + defense)

- [2023-03-31] **Defense — use a password manager.** Chuck states flatly that you need a
  password manager "right now." (paraphrase)
- [2023-03-31] **Threat/concern — trusting a third party.** Many people don't want to give
  their passwords to another company; self-hosting removes that dependency and gives full
  control over your passwords. (paraphrase)
- [2023-03-31] **Defense — self-host Passbolt.** Passbolt is a free-forever, unlimited-user,
  open-source password manager you can self-host on any Linux-based server (a spare laptop,
  a Raspberry Pi, or a cloud VM); because it's Docker-based, the same deployment works
  anywhere. (paraphrase)
- [2023-03-31] **Defense — trusted TLS certificate.** Running Passbolt without SSL leaves it
  with an untrusted certificate; for real-world use you should add Traefik as a reverse
  proxy, which fetches a free trusted certificate from Let's Encrypt. (paraphrase)
- [2023-03-31] **Defense — enable multi-factor authentication.** A passphrase alone "isn't
  the most secure"; enable MFA via time-based one-time passwords (TOTP) using an app like
  Google Authenticator, YubiKey, or Duo when logging into the password manager. (paraphrase)
- [2023-03-31] **Defense — anti-phishing recovery detail.** Passbolt lets you set a unique
  recovery-kit detail you know you entered; it helps protect you from phishing attacks by
  letting you recognize a legitimate prompt. (paraphrase)
- [2023-03-31] **Security posture — why Passbolt is trustworthy.** Passbolt uses open PGP for
  encryption, full private key control, and end-to-end encryption, is regularly audited, and
  is transparent about how it keeps users secure. (paraphrase)
- [2023-03-31] **Personal practice.** Chuck himself uses Dashlane, a hosted password manager,
  as a personal choice made for convenience — not Passbolt. (paraphrase, self-reported)
- [2023-03-31] **Deployment sizing.** Passbolt recommends at least two CPU cores; Chuck
  confirms the 4 GB Linode plan works and, at the end, that even the smallest $5/month 1 GB
  Linode plan runs it fine, though a smaller server supports fewer simultaneous users.
  (paraphrase)

## Notable verbatim quotes

> You need to use a password manager right now or maybe don't, but seriously, you do need
> one and you probably don't wanna give your passwords to another company.

> I'm gonna show you how you can self-host your own password manager, giving you godlike
> control of all your passwords.

> It's called Passbolt. It's free forever, unlimited users, no strings attached, and it
> really doesn't take much to get started.

> The most important thing, you need coffee because everything in it requires coffee.

> Just pick something that you know you did and it'll protect you from phishing attacks.

> Having just a passphrase isn't the most secure.

> They're using open PGP for encryption, full private key control, end-to-end encryption,
> all kinds of stuff. And they're regularly audited.

> I personally do not use Passbolt because I like my hosted solution. For me it's a matter
> of convenience, but I know for a lot of you... this solution I think is killer.

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
