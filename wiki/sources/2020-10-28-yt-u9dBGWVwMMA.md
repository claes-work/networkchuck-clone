---
type: youtube-video
source_date: 2020-10-28
url: https://www.youtube.com/watch?v=u9dBGWVwMMA
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, certifications-career]
tags: [free-security-plus, phishing, social-engineering, awareness, ep-2]
---

# Phishing attacks are SCARY easy to do!! (let me show you!) // FREE Security+ // EP 2

## Summary

Episode 2 of NetworkChuck's FREE Security+ series (co-produced with Jeremy Cioara and
David Bombal, sponsored by This Is IT / itpro.tv). Chuck teaches phishing and social
engineering by demonstrating an attack against a fictional target — "Bernard Hackwell,"
the CEO of NetworkChuck Coffee — so that viewers can **recognize and defend against**
these attacks. He opens and closes with an explicit ethics disclaimer: everything shown
is for educational purposes only, and must never be used against anyone without
permission.

The demo has two phases, framed entirely around defensive awareness rather than as an
operational playbook. Phase one is **credential harvesting**: standing up a fake
LinkedIn login page (using a public tool on Kali Linux with a tunneling service) so that
when the target enters a username and password, the attacker captures them while the
victim is bounced back to the real LinkedIn, "none the wiser." Phase two is the
**delivery** — the phishing email that lures the target into clicking. Chuck uses this
to walk through the vocabulary of the domain: a mass phishing email (net cast wide) vs.
**spear phishing** (one specific target) vs. **whaling** (targeting a high-value person
like a CEO). He also names the sibling delivery channels: **smishing** (phishing over
SMS text), **vishing** (phishing over a voice phone call), and **spim** (spam/phishing
over instant messaging) — noting texts can be more dangerous than email because people
don't expect threats on their phones.

He then extends the concept: instead of a link, a phishing email could carry a malicious
file (e.g. a Word document containing malware). One such payload could modify the
victim's **hosts file**, which overrides DNS, so that typing `linkedin.com` silently
redirects to the attacker's fake site — a technique he names **pharming** (and, at the
server level, **DNS poisoning**). This is especially nefarious because a careful user
who avoids email links and always logs in via a fresh tab could still be caught if their
DNS/hosts file is compromised without their knowledge. He also flags **invoice scams**
(impersonating a known vendor, using reconnaissance from the prior episode) as a common
real-world social-engineering play that preys on emotions.

The final third is pure **defense**: use good spam filters; don't click links or
download attachments from unsolicited messages — instead log into the bank/service
directly in a new tab; verify the sender by inspecting the email header/source; and stay
alert across all channels (email, SMS, voice, IM). Chuck stresses social engineering
"hacks the human OS," that these attacks don't require a genius ("a kid in his basement"),
and urges viewers to educate vulnerable family members — especially older relatives — to
never click links or give information away over the phone. Cross-reference: EP 1
[[2020-10-19-yt-vyqSdJLVQgg]] (reconnaissance / footprinting is what makes a targeted
phishing email convincing).

## Key claims (dated — technique concept + defensive lesson)

- **[2020-10-28]** Phishing/social-engineering attacks are alarmingly easy to run and
  don't require advanced skill — which is exactly why everyone needs to be able to
  recognize them.
- **[2020-10-28]** Everything demonstrated is for educational/defensive purposes only and
  must never be used on anyone without explicit permission.
- **[2020-10-28]** **Credential harvesting** is a social-engineering attack that tricks a
  victim into entering their username and password on a fake login page that looks
  identical to the real service.
- **[2020-10-28]** The danger is that a convincing fake page can bounce the victim back
  to the legitimate site after capture, so the victim never realizes their credentials
  were stolen.
- **[2020-10-28]** A **phishing email** gives the victim a reason (urgency, an important
  message) to click a link and log in on the fake page; subject lines are crafted to
  provoke the click.
- **[2020-10-28]** A mass phishing email targets anyone; **spear phishing** targets one
  specific individual; **whaling** targets a high-value/high-influence person such as a
  CEO.
- **[2020-10-28]** Phishing isn't only email: **smishing** is phishing via SMS text,
  **vishing** is via voice phone call, and **spim** is via instant messaging.
- **[2020-10-28]** Text-based (smishing) attacks can be more dangerous than email because
  people are trained to distrust email links but rarely expect threats on their phones.
- **[2020-10-28]** A phishing payload can be a malicious file (e.g. a Word document
  hiding malware) rather than just a link.
- **[2020-10-28]** The **hosts file overrides DNS** — a machine checks it before asking a
  DNS server — so tampering with it lets an attacker redirect a legit domain to a fake
  site; this is **pharming** (server-level equivalent: **DNS poisoning**).
- **[2020-10-28]** Pharming is especially dangerous because even a cautious user who
  always logs in via a fresh tab can be caught if their DNS/hosts file was silently
  poisoned.
- **[2020-10-28]** **Invoice scams** — impersonating a known vendor and pressuring the
  victim to pay a fake invoice — are a common real-world social-engineering attack that
  preys on emotions.
- **[2020-10-28]** Social engineering works by "hacking the human OS" (the human brain),
  which in many cases is easier than hacking a machine.
- **Defense [2020-10-28]:** Use good spam filters; modern email systems route unsolicited
  mail to a spam folder automatically.
- **Defense [2020-10-28]:** Don't click links or download attachments in unsolicited
  messages — if you get a "secure message" notice, log into the bank/service directly
  yourself.
- **Defense [2020-10-28]:** When you must engage, verify the sender by inspecting the
  email header/source and confirm it comes from a known, reputable source.
- **Defense [2020-10-28]:** Stay alert across every channel (email, SMS, voice, IM), and
  proactively educate vulnerable family members — especially older relatives — to never
  click links or give out information.

## Notable verbatim quotes

> "it is terrifying how easy it is to do a phishing attack or a fishing hack"

> "this is for educational purposes only never do this to anyone for any reason at all
> unless you have permission"

> "we're going to trick him of course social engineering here we go"

> "this is called credential harvesting one of many social engineering attacks"

> "when i target someone specifically with a phishing email that's called a spear
> phishing attack"

> "when hackers target important people in a company people who have influence and power
> this is called whaling bernard's my whale i'm gonna get him"

> "we're used to defending ourselves against emails right don't click on links and emails
> unless you can verify where the email is coming from but texts are different"

> "social engineering is amazing it's terrifying because again they're hacking the human
> brain the human os"

> "if i got a link in there tell me to check my account hey check your bank account ... i
> never click that link i will go to a new tab log into my bank account the same way the
> normal way i always do and that way i know i'm safe"

> "say hey grandma don't click on anything please ever under any circumstances do not
> click that link don't answer phone calls and give information away"

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: FREE Security+ EP 2 — phishing/social-engineering awareness -->
