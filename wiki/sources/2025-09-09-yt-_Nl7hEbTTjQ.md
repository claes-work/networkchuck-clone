---
type: youtube-video
source_date: 2025-09-09
url: https://www.youtube.com/watch?v=_Nl7hEbTTjQ
channel: "@networkchuck_v2"
ingested: 2026-07-22
tier: L2
domains: [certifications-career, networking, ai-tools]
tags: [network-engineering, future-of-work, ai-automation, career]
---

# How Long Do Network Engineers Have Left?

## Summary

An interview on the second channel (@networkchuck_v2) between Chuck Keith (NetworkChuck)
and guest **John Capobianco** ("John Capo" / "Cappo Biano"), a network-automation-and-AI
specialist known for MCP (Model Context Protocol) and agent-to-agent (A2A) content. The
conversation is a career-future piece pairing directly with Chuck's 2025-06-13 main-channel
video "I'm worried about Network Engineers." Its central question: how long does network
engineering have before AI and automation reshape or displace it?

Capobianco supplies the technical thesis — MCP as "the USB-C of software," an abstraction
layer over REST APIs that lets an LLM drive network tooling (subnet calculators, Cisco
pyATS, Catalyst Center, RFC lookups) through natural language. He argues the CLI is
becoming "less and less important," that networking as a career won't diminish but will
specialize (especially "networks for AI" — GPU farms, RoCEv2, high-performance-computing
fabrics), and that there is roughly a **3-to-5-year "safety net"** beyond which prediction
gets hard. His adapt-or-else framing: everyone using AI now has an advantage over those who
aren't, a "parity gap" is opening, and the people he worries about are the ones "asleep"
and "not paying attention." His concrete first step: get any AI account (or run Ollama
locally for free), do "an hour of AI a day," and start with safe read-only tasks like
pasting syslogs into a context window.

Chuck plays the skeptic/audience proxy: he recalls that ChatGPT triggered an "existential
crisis" for him rather than excitement, voices a trust issue about letting AI make config
changes, and raises the concern that heavy AI use is making his brain "atrophy." The
thesis material here is predominantly Capobianco's; Chuck's persona-trainable content is
his framing, worries, and questions.

## Key claims (dated — thesis + advice, attributed)

- **[2025-09-09] (Capobianco — thesis)** Networking as a career will not diminish but will
  become "more and more specialized," splitting into "AI for networks" (using AI to run
  networks) and "networks for AI" (building the GPU/HPC infrastructure — racks of GPUs,
  RoCEv2 and related protocols — that AI runs on). Paraphrase.
- **[2025-09-09] (Capobianco — timeline)** Network engineers have roughly a **3-to-5-year
  safety net**; he doesn't think disruption will be "that revolutionary and that fast"
  within that window, but beyond 3-5 years it is "really hard to project or predict."
  Paraphrase.
- **[2025-09-09] (Capobianco — protection/skills)** The CCNA plus Cisco's newer automation
  certification together are still a valid path into the field. Employers don't hire for
  memorized CLI commands; they hire for the outcome — "building a solid robust network"
  that adheres to good standards. The CLI is becoming "less and less important." Paraphrase.
- **[2025-09-09] (Capobianco — adapt-or-else)** Everyone using AI now has an advantage over
  those who aren't; a "parity gap" is opening. The people he worries about are those "asleep
  on this," not paying attention, who will "wake up one day to a whole new reality that
  they're not prepared for." "The time for skepticism is behind us." Paraphrase + quotes.
- **[2025-09-09] (Capobianco — first step / advice)** Get an AI account with any vendor, or,
  if $20/month isn't feasible (early career, students on CCNA), download **Ollama** (not
  Llama) and run a model locally for free and private. Do "an hour of AI a day," or just
  fold it into everyday problem-solving. Paraphrase.
- **[2025-09-09] (Capobianco — safe on-ramp)** Read-only activities are safe: paste syslogs
  into a context window and ask the AI to interpret them (e.g. find interface flaps between
  2-3am), or feed `show interfaces` counters and ask "is this interface healthy?" Network
  automation for documentation, visualization, and testing is non-intrusive — people
  conflate automation with change management. Paraphrase.
- **[2025-09-09] (Capobianco — MCP explainer)** MCP is a client-server protocol for LLMs,
  "the USB-C of software" and "an abstraction of an API" — it hides the endpoint, body, and
  payload structure behind natural-language tools (e.g. a 30-line subnet-calculator server,
  or a `@tool`-decorated Catalyst Center call via FastMCP). He layers it onto the OSI stack
  for viewers: GPUs as layer 1 (physical), MCP as layer 2, agents (A2A) above. Paraphrase.
- **[2025-09-09] (Capobianco — trust)** Unlike Chuck, he *is* comfortable letting AI/MCP
  make actual configuration changes, citing an RFC MCP that reads a standard and generates
  a valid, standards-referenced config "better than even me doing it on my own." Paraphrase.
- **[2025-09-09] (Capobianco — jobs outlook)** He is optimistic overall and self-describes
  as an "outlier" who believes "AI is going to take all the jobs" yet expects a "utopian
  outcome": some jobs displaced, but new categories emerge (machine-learning engineer didn't
  exist two years ago). Cites Nvidia's Jensen Huang that the future IT department is "an HR
  department for agents." Paraphrase.
- **[2025-09-09] (Chuck — framing)** His first reaction to ChatGPT was an "existential
  crisis" ("What's my role now?"), not excitement. He recalls the 2018-2019 "network
  engineers are developers now" scare that didn't end the field — "we just learned a bit of
  code." But AI "feels different… happening too fast… becoming smarter than we were ready
  for." Paraphrase + quotes.
- **[2025-09-09] (Chuck — trust + concern)** Chuck is NOT yet comfortable trusting AI/MCP
  with making real config changes. He also worries that the more he uses AI, the more his
  brain, reasoning, and idea-generation "atrophy." Paraphrase.
- **[2025-09-09] (Chuck — audience stance)** Chuck notes his audience skews skeptical of AI
  and he wants them to be "okay with it"; he positions the interview as a way to "wake up"
  network engineers who aren't paying attention. Paraphrase.

## Notable verbatim quotes

**Chuck (NetworkChuck):**
- "My first reaction was, 'Oh, no. Existential crisis. What What's my role now? It can do all of this.'"
- "But AI feels different. AI is happening too fast and it feels like it's becoming smarter than we were ready for."
- "The more I use AI, I feel my my my brain starting to atrophy. Some of my reasoning capabilities atrophy, some of my idea ability atrophies. Do you feel that?"
- "Are we are we at Vibe networking now?"
- "Is the CLI dead?"

**John Capobianco (guest):**
- "I think we still have 3 to 5 years of a safety net. I don't think that it's going to be that revolutionary and that fast. Beyond 3 to 5 years, it's really hard to project or predict."
- "I don't think that networking as a career is going to diminish. I think it's going to become more and more specialized."
- "Right now I don't think employers are paying or are hiring you because you've memorized every single CLI command… It's the outcome of building a solid robust network."
- "The time for skepticism is behind us. I think that everyone who is using AI has an advantage over people who are not using AI."
- "That is what I'm worried about are the people here that aren't using it, that aren't paying attention, that are going to wake up one day to a whole new reality that they're not prepared for."
- "They call them the USBC of software."
- "an hour of AI a day."

## Guest attribution

**Multi-voice interview — NOT solo Chuck.** Host: **Chuck Keith (NetworkChuck)**. Guest:
**John Capobianco** ("John Capo"/"Cappo Biano"), an external network-automation/AI/MCP
specialist. Only Chuck-attributed statements train the persona; Chuck's role here is mostly
interviewer and skeptic (existential-crisis reaction, atrophy worry, distrust of AI making
config changes, "is the CLI dead?" / "vibe networking?" framing). The core career-future
thesis — the 3-to-5-year safety net, specialization, CCNA + automation cert as the path,
the parity gap, "an hour of AI a day," MCP-as-USB-C — is **Capobianco's** and is context,
not persona training data. Attribute accordingly before any promotion into beliefs/voice.

<!-- ★ L3-candidate: 'how long do network engineers have' (beliefs; reinforces future-of-network-engineering) -->
