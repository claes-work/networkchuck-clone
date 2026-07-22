---
type: youtube-video
source_date: 2022-06-01
url: https://www.youtube.com/watch?v=3ytqP1QvhUc
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity]
tags: [follina, zero-day, cve-2022-30190, msdt, vulnerability, defense]
---

# let's play with a ZERO-DAY vulnerability "follina"

> ⏳ DATE-SENSITIVE: This is a live-reaction analysis of a 2022 zero-day (Follina /
> CVE-2022-30190) recorded days after its public discovery, when **no patch existed**.
> Microsoft has since patched MSDT. Treat all "no fix / no patch" statements as accurate
> for **early June 2022 only**, not as a current description of the vulnerability.

## Summary

Chuck reacts to the then-brand-new **Follina** zero-day (**CVE-2022-30190**), a Microsoft
Office / Windows remote code execution vulnerability that the security-research community
had only become aware of "over the weekend." He frames it as a rare on-the-ground look at
a live zero-day — a hack with "no fix, no patch" — and partners with hacking researcher
**John Hammond** (a guest/context figure, not the subject) to explain the mechanism at a
conceptual level before walking viewers through reproducing it in a free virtual lab.

Conceptually, the attack starts with a phishing email carrying an innocent-looking Word
document. What makes Follina notable is that it does **not** rely on macros (which are
disabled by default) — instead it abuses the **Microsoft Support Diagnostic Tool (MSDT)**.
Word reaches out to an external reference staged with an HTML payload, invokes MSDT via a
file/URI protocol handler, and that mechanism is tricked into executing attacker-supplied
commands (PowerShell / command prompt), yielding a reverse shell and full remote control
of the victim machine. Chuck deliberately keeps the demo at "baby stuff" level (popping
Calculator / Notepad, then a simple reverse shell) and repeatedly stresses that the real
in-the-wild malware — which stages further payloads that could be a RAT, cryptominer, or
ransomware — is unknown and far more dangerous.

The video doubles as a lab tutorial (VirtualBox + Kali + Windows 11 + Office, all free) and
carries strong ethics framing: do this only in disposable virtual machines you don't mind
destroying, never on live systems or on friends and family. It closes on the defensive
lesson: the best mitigation for this class of attack is user behavior — don't open weird
attachments — plus a nod that Windows Defender already detected the (older, related) MSDT
signature in his lab, which he had to disable to force the demo.

## Key claims (dated — concept + defense)

Concept (as understood early June 2022):
- Follina is tracked as **CVE-2022-30190** and is a **remote code execution** zero-day —
  Chuck calls RCE "the crown jewel," rated high/critical severity. (2022-06-01)
- At time of recording there was **no patch and no fix available**; the research community
  had only learned of it over the prior weekend. (2022-06-01)
- The attack does **not** depend on Office **macros** — which is what makes it notable,
  since macros are disabled by default in most setups; attackers found an unblocked path.
  (2022-06-01)
- The unblocked path is the **Microsoft Support Diagnostic Tool (MSDT)**: a legitimate
  troubleshooting tool that, when invoked this way, can be made to run attacker commands.
  (2022-06-01)
- Delivery: a phishing email → a harmless-looking Word document → on open, Word reaches out
  to an **external reference** staged with an **HTML payload**, invoking a file/URI protocol
  handler (an `msdt:`-style scheme rather than `http:`) that kicks off code execution. (2022-06-01)
- Impact escalates from trivial (launching Calculator/Notepad) to a **reverse shell** giving
  the attacker full remote control, enabling lateral movement and privilege escalation "in
  the hands of a skilled hacker." (2022-06-01)
- The real in-the-wild payload was still unknown: researchers had the malicious Word document
  (the "bomb") but not the "detonator"; the final staged executable could be a remote-access
  Trojan, cryptominer, or ransomware. (2022-06-01)
- Researchers like John Hammond reverse-engineered the document to recreate a working
  proof-of-concept script (written in Python) that reproduces the vulnerability for study.
  (2022-06-01)

Defense / mitigation:
- The greatest mitigation for this class of attack is **user behavior / security awareness**:
  don't open weird emails or download weird documents; teach users the same. (2022-06-01)
- Standard security best practices, consistently followed, prevent falling for this hack.
  (2022-06-01)
- **Windows Defender already detected** the demo in Chuck's lab (flagged as the older,
  related MSDT CVE signature); he had to turn off real-time protection to force the exploit
  to fire — a reminder that endpoint protection catches known signatures. (2022-06-01)
- Ethics/safety: only perform this in **disposable virtual machines** you're willing to
  destroy — never on live/production systems or on friends' and family's machines. (2022-06-01)

## Notable verbatim quotes

> "What you just saw was a zero day vulnerability, a hack that has no fix, no patch. Yeah,
> it's kind of crazy."

> "The scariest thing about this attack is that it's pretty simple."

> "In most situations, macros are disabled. And that's what makes this hack so interesting.
> Hackers found another way, another path — a path that is still unblocked."

> "It all comes down to this thing right here, the Microsoft Support Diagnostic Tool, or
> MSDT for short. For some reason, this tool, which is meant to help you troubleshoot issues,
> when it's run, it allows you to run commands. And when I say you, I mean the attacker."

> "Once you're in, you're in. This is insane."

> "Yes, we're doing this in a virtual environment — boxes that I don't mind destroying. You
> should do that too. Don't do this on live environments that you need, or your family or
> friends. Don't do that to them."

> "The greatest mitigation for situations like this is: don't open weird stuff. Teach your
> users not to open up weird emails or to download weird documents."

> "This is my first kind of on-the-ground, first realization of an issue and talking about it
> — a little stressful to get it out this fast, but I thought it was pretty fun."

## Guest attribution

Solo — but with a **guest expert** present. John Hammond (hacking researcher) appears as a
collaborator who explains the mechanism and wrote the Python proof-of-concept script. John
Hammond is a **context/guest figure, not the SUBJECT**; his technical explanations are
attributed to him, not cloned into the persona. All persona-relevant statements — the ethics
framing, the "don't open weird stuff" mitigation, the coffee-and-lab enthusiasm, and the
overall framing — are attributable to **Chuck Keith (the SUBJECT)**.

<!-- ★ L3-candidate: topical zero-day analysis (Follina, 2022) -->
