---
type: youtube-video
source_date: 2026-06-01
url: https://www.youtube.com/watch?v=cGXAmnUabEY
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [linux-terminal]
tags: [windows, linux, os, position-change, wsl]
---

# Switching back to Windows?!?

## Summary

An OpenAI-sponsored video framed as an OS position-reversal. Chuck — a well-documented
Linux/Mac advocate — publicly flirts with returning to Windows. The trigger is OpenAI's
**Codex app going "Windows native"** (running its agent sandbox directly in Windows via
Rust, ACLs, firewall rules, and restricted tokens rather than in WSL2/Docker/VM), which
made him "kind of miss Windows." He polled 60,000+ viewers and found most use Windows as
their daily driver, contradicting his own bubble.

Crucially, the reversal is **aspirational, not actual**. His stated daily driver is still
a **Mac** under his desk; he only boots Windows for one Windows-only app (**vMix**). He
explains he originally switched *away* from Windows because "every AI tool was made for Mac
and Linux" and he was "tired of running AI in WSL2 like a second-class citizen" — an
AI-tooling reason, not a hatred of Windows. He explicitly says he *likes* Windows' feel/UI,
grew up on it, and now enjoys it "more than Mac." He ends undecided: "I'm not quite ready to
switch yet. I'm close." The bulk of the video is a Codex/Windows-security demo (sandbox,
SIDs, `icacls`, Hyper-V, PowerShell) interleaved with seven "Windows surprise" nuggets
(SimCity backward-compat, WSL open-sourced, Hyper-V type-1 hypervisor, clipboard history,
God Mode folder, winget, window shake). He also trashes Microsoft's own AI: "Copilot sucks…
every effort by Microsoft to put AI in its operating system is garbage."

## Key claims

- **[2026-06-01] He has NOT actually switched — this is a "considering it" video.** His
  daily driver remains a **Mac**; his stated conclusion is "I'm not quite ready to switch
  yet. I'm close." (paraphrase)
- **[2026-06-01] What currently keeps him on Windows at all is a single Windows-only app,
  vMix** — otherwise he is not a Windows user day-to-day. (paraphrase)
- **[2026-06-01] The exact nuance driving the reconsideration is AI tooling, not OS
  loyalty.** He originally left Windows because AI tools targeted Mac/Linux first and WSL2
  felt like a "second-class citizen"; now OpenAI making Codex *Windows-native* (agent runs
  in Windows itself, speaks PowerShell, sandboxed via native Windows security) is pulling
  him back. (paraphrase)
- **[2026-06-01] He concedes real Windows strengths:** best-in-class backward compatibility,
  WSL shipping a real Linux kernel (open-sourced at Build 2025), Hyper-V being the same
  hypervisor class as Azure, a real package manager (winget), clipboard history, and
  Codex's native sandbox being genuinely well-engineered (15,000+ lines of Rust). (paraphrase)
- **[2026-06-01] He still criticizes Windows sharply** — bloatware/adware in the Start menu,
  "weird and honestly bad decisions," and Microsoft's built-in AI (Copilot) as "hot garbage."
  His warming is toward *Windows + your-own-AI*, not toward Microsoft's AI. (paraphrase)
- **[2026-06-01] On recommending Linux to others: he does NOT push desktop-Linux-for-everyone
  here, and is skeptical of the "everyone move to Linux for gaming" narrative** — he says he
  doesn't think that migration is "gonna happen," gently ribbing Linus Tech Tips' repeated
  attempts. He recommends the Codex app itself on any OS (Windows/Mac/Linux), not a specific
  desktop OS. (paraphrase)
- **[2026-06-01] The condition for a full switch:** more of his tools coming to Windows AND
  Windows "changing their attitude" / fixing its problems — then he'd consider moving the Mac
  out. (paraphrase)
- **[2026-06-01] Disclosure:** the video is sponsored by OpenAI, which "forced" him to use
  Codex daily; he says he now genuinely uses it every day. (paraphrase)

## Notable verbatim quotes

> "But before we dive in, I have a confession. I don't use Windows, and it's not for the
> reason you think… That's because this is all I use it for. There's this one app… It's
> called vMix. It's Windows only, and I'm stuck like many of you."

> "But this Mac underneath my desk, that's my daily driver."

> "I actually like Windows. Calm down. I know. But I like the feel. I like the UI. I grew
> up on it. It's nostalgic."

> "Even with all the craziness, what made me switch was AI. It seems like every AI tool was
> made for Mac and Linux, and they forgot about Windows… I was tired of running AI in WSL2
> like a second-class citizen. And, no, Copilot sucks. And every effort by Microsoft to put
> AI in its operating system is garbage. Hot garbage."

> "And despite everyone trying to move to Linux for gaming and stuff, which I don't think is
> gonna happen, Linus Tech Tips keeps making a series to try and do it."

> "But I want Windows to be good again. I want an OS like Windows seven and XP, and even 10
> was good. I want to love Windows, and OpenAI is making it a little bit easier."

> "But, you know, I'm not quite ready to switch yet. I'm close. Maybe if a few more tools
> come over, I will — I will dive deep. And if Windows changes their attitude, they gotta
> fix it. Then maybe I'll feel good about moving my Mac out of here. Because, honestly, I
> enjoy this more, Windows, more than Mac."

> "Codex isn't just visiting Windows anymore. He's not pretending to be Windows in a Linux
> costume. He's a local. He moved in."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: POSITION EVOLVED — switching back to Windows (reconcile vs 2024 pro-Linux stance in beliefs.md) -->
