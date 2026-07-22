---
type: youtube-video
source_date: 2021-02-09
url: https://www.youtube.com/watch?v=bsCsuoIzyTg
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity]
tags: [breaches, kill-chain, attack-chain, enterprise-security, awareness]
---

# How Big Companies Get Hacked

## Summary

An educational explainer on why large companies with well-resourced security teams keep getting breached. Chuck's thesis: most modern breaches are **application-based** — attackers go after the code developers write, not some exotic new zero-day — and the root cause is that most developers were never taught to write secure code, universities don't teach it, and we are now writing more code faster than ever, which means more vulnerabilities. He frames the whole problem as "we've taken the burden of securing our apps and put it on the shoulders of our developers."

He unpacks two structural trends (sponsored by BoxBoat and GitLab) that have made this worse. **Trend one — the death of the slow, siloed pipeline.** Using his fictional dev team (Beatrice, Bernard, Betty, Bob) building networkchuck.coffee, he contrasts the old way (a monolith app that has to pass through the server team, network team, quality-control team, and security team — slow, could take up to "two years") with the modern "right now" culture. To go faster, companies break the monolith into **microservices**, adopt **containers / Docker / Kubernetes**, and deploy to the **public cloud** ("someone else's server"). The danger: developers absorb the roles of the server team, network team, and increasingly the QC team — a phenomenon he calls **"shifting left."** Deploying and securing servers and networks is its own skill; developers are great at code but not necessarily at hardening infrastructure, so they ship containers and networks that aren't built to best practices, creating openings hackers scan for (misconfigurations, human error).

**Trend two — the agile / CI/CD velocity trend**, which he calls even scarier. Instead of waiting until a whole feature is finished and pushing it through manual review, developers commit tiny changes constantly and ship them (potentially every few hours) via **continuous integration / continuous deployment**. He demos this in GitLab: editing Beatrice's Python login microservice in the web IDE, committing to the master branch, and watching an automated CI/CD pipeline run tests, quality checks, and security scans. Constant deployment means constant new attack surface for hackers to probe.

His defensive framing is that the answer is **not** to turn developers into security/server/network admins, nor to go back to the slow old way. It's a **DevOps engineer** ("dev" + "ops") — a rare "unicorn" who understands both development and IT operations and can shift-left responsibly — and, because those are hard to hire, companies like BoxBoat (DevOps consulting/training) and tools like GitLab that **automate security into the pipeline**: SAST scanners (Bandit for Python, ESLint SAST for JavaScript), container scanning for known CVEs (e.g. an out-of-date Alpine Linux), scheduled scans, and a security/compliance dashboard. Automation gets the feedback to the developer immediately instead of weeks later. Core takeaway: automation is what makes us fast but also leaves room for error — "make sure you have security baked into your automation and your CI/CD pipeline."

## Key claims (dated — attack-chain concepts + defense)

All 2021-02-09 (paraphrase unless quoted):

- **Attacks target the application/code.** Most of the world's greatest exploits in the last five years have been application-based; attackers go after the code developers write.
- **Root cause is insecure code.** Most developers don't know how to write secure code; universities don't teach secure coding, vulnerabilities, or exploits — and the problem is getting worse.
- **More code, faster = more vulnerabilities.** The "right now" culture demands constant updates; writing more code faster inherently produces more vulnerabilities ("the nature of the beast").
- **Misplaced burden.** Companies have shifted the burden of securing apps onto developers, who aren't security experts — that's the scary core of the problem.
- **The old pipeline was slow but layered.** A monolith app historically had to pass through separate server, network, quality-control, and security teams — slow, but each layer was a dedicated skill and safety check.
- **Microservices + containers + cloud remove those gates.** Breaking the monolith into microservices and deploying containers (Docker/Kubernetes) to the public cloud lets developers bypass the server and network teams entirely.
- **"Shifting left"** = moving later-stage responsibilities (testing, security scans, server/network admin) earlier, into the developer's hands during code production. Chuck broadens the term to mean IT-operations responsibilities shifting onto developers.
- **Bypassed gates create attack surface.** Developers deploy containers/networks that aren't secured to best practices; hackers constantly scan apps, networks, and servers for any misconfiguration, weakness, or human error.
- **Hackers mostly reuse existing vulnerabilities.** They aren't usually reinventing the wheel — they look for known/existing vulnerabilities in your app or containers.
- **CI/CD velocity is a bigger risk than trend one.** Agile / continuous integration / continuous deployment lets teams push tiny code changes constantly (possibly every 3–4 hours instead of every 3–4 months) — far more frequent deployment means far more opportunity for hackers to probe fresh code.
- **Container scanning matters as much as code scanning.** A container can run an out-of-date Alpine Linux or old software with open vulnerabilities; scanning containers is the microservice-world equivalent of the server team hardening a server.
- **CVE = Common Vulnerabilities and Exposures**, the standard identifier for a known security flaw found in code or a container.
- **Defense — don't overload developers.** The fix is NOT to make developers into security/server/network admins, nor to revert to the slow old way ("once you go fast you can't go slower").
- **Defense — the DevOps engineer.** The real answer is a rare "unicorn": someone who understands IT operations, security, servers, cloud, Kubernetes, containers AND development, and who knows how to shift-left properly by automating quality/bug/security checks. DevOps engineer is a lucrative but hard career to break into.
- **Defense — automate security into the pipeline.** Tools like GitLab automate security scanning on every commit: SAST (Bandit for Python, ESLint SAST for JavaScript/Node.js), container vulnerability scanning against CVEs, scheduled scans, and a security/compliance dashboard tracking critical/high/medium issues.
- **Automation is faster AND safer** because it catches vulnerabilities at the source and notifies the developer immediately, instead of a security or QC person kicking it back weeks later (a bottleneck).
- **Final takeaway:** automation is cool and fast but leaves room for error — make sure security is baked into your automation and CI/CD pipeline.

## Notable verbatim quotes

> "It's impossible to deploy 100 percent secure code because most of the time when hackers hack a company when they attack them they attack the application the code the developers write."

> "Most developers don't know how to write secure code. Universities don't teach writing secure code, they don't teach about vulnerabilities and exploits."

> "We're taking the burden of securing our apps and we're putting that on the shoulders of our developers. That scares me. Does that scare you?"

> "Now what I've just described here is a term called shifting left. This is a term that we often use in the development world to describe things that we do later in the process like quality control, testing, security scans."

> "Just because something works doesn't mean it's secure."

> "That's a ton of opportunity for hackers to look at your stuff as soon as it's out and see if something's broken."

> "This is precisely why this is the scariest thing in the world to me... my biggest fear is that in trying to automate and make things faster we're actually making ourselves insecure."

> "For the most part hackers aren't always reinventing the wheel finding the newest latest and greatest vulnerabilities. No, they're just looking for existing ones."

> "Don't make them become security admins, don't make them learn networking. No no, let them be really great at code."

> "This person is called a DevOps engineer. Dev for developer, ops for IT operations. DevOps."

> "Make sure you have security baked into your automation and your CI/CD pipeline."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: attack-chain / how-breaches-happen explainer -->
