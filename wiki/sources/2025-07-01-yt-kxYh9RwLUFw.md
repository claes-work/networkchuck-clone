---
type: youtube-video
source_date: 2025-07-01
url: https://www.youtube.com/watch?v=kxYh9RwLUFw
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [ai-tools, certifications-career]
tags: [ai-hype, opinion, ai-skepticism, nuance, fundamentals]
---

# I'm done with the AI hype

## Summary

An opinion/investigation video in which Chuck Keith voices fatigue with the "AI-enabled / AI-powered / AI-driven" marketing sticker slapped on every product since ChatGPT "broke everything in 2022," and sets out to test whether AI in networking is real value or just "AI slop." Framed as a journey — starting at Cisco Live (the world's largest networking conference, 22,000+ people) and pivoting to a Juniper Networks event a mile and a half away — the video contrasts two approaches to adding AI to networking products.

The core nuance: Chuck pushes back on the *hype and the marketing*, not on AI itself. His thesis is that most vendors are doing "bolt-on AI" — dumping massive telemetry (packet captures, router/switch data) into an LLM and hoping it figures things out, which he argues fails because LLMs "get very confused with too much data" and hallucinate under large context. He contrasts this with Juniper (via its 2014-founded Mist acquisition), which he presents as "AI native": a specialized, machine-learning-based system trained narrowly on network data, with all context consolidated in one place (the Mist AI cloud / contextual graph database). His recurring lesson is that **AI is only as good as the data and context you feed it** — the same principle whether asking ChatGPT what to have for dinner or asking a system why a CEO's Zoom call was bad.

Chuck stays deliberately balanced: repeatedly saying "grain of salt," noting he hasn't used the product himself, and pointing to real customers (a partner integrator, Allan from his own Discord) as evidence. He ends optimistically — the automation of a network engineer's most stressful moments (the 3 a.m. outage call) sounds genuinely good — while reminding viewers this is his snapshot of the landscape, not an endorsement. Sponsored segment: Twingate (zero-trust remote access), tied to a personal story of a power outage killing his Proxmox servers. Note: the video was filmed before the HPE acquisition of Juniper.

## Key claims (paraphrase; dated 2025-07-01)

- **The hype fatigue thesis:** Chuck is tired of the "AI-enabled / AI-powered / AI-driven / AI-enhanced" sticker being slapped on every product, driven by the fact that "that's all investors care about right now" — networking included. He wants "off" the AI hype train. *(This nuances his generally pro-AI/pro-tinkering stance — he's now explicitly separating genuine AI value from marketing glitter.)*
- **The real question:** Is adding AI to products actually solving real problems and delivering real results for IT/network engineers, or is it "AI slop"? He genuinely wants it to work (uptime, no 3 a.m. calls).
- **AI predates ChatGPT:** It only *feels* like there was no AI before ChatGPT (Nov 2022). AI was very much a thing in the early-to-mid 2010s — not generative text/chat but machine learning: narrow, specialized, pattern-finding and prediction on one domain.
- **Data/context is everything:** AI quality depends entirely on the data and context fed to it — true "across the board." You can't ask an LLM about your network unless it has your network's context; the dinner-recommendation analogy (pineapple/nut allergy) illustrates missing context.
- **Bolt-on AI (the hype pattern):** Most vendors "slap the sticker on" by dumping all telemetry into an LLM and saying "figure it out." Chuck argues LLMs — "even the greatest ones right now" — get confused with too much data and hallucinate under large context. More moving parts = more complexity = more breakage.
- **AI-native as the contrast:** Juniper (via Mist, founded 2014, acquired 2019 for $45M) built around specialized ML trained only on network data, with all context consolidated in one place (Mist AI cloud + Marvis, a contextual graph database, "Marvis minis" digital-twin clients, intent-based Apstra). Chuck frames this as structurally different from bolt-on AI, though he explicitly declines to declare one "better."
- **Deliberate skepticism / balance:** Chuck repeatedly hedges — "grain of salt," "conceptually it sounds cool," "if it works," "I have not played with it or used it myself." He leans on customer testimony (integrator partner Nexum; Allan from his Discord) rather than vendor claims for evidence.
- **The upside for engineers:** Self-healing/self-driving networks that catch anomalies before users do (and predict cable/optic failures before they fail) would remove a network engineer's worst stressors. He acknowledges this automates parts of the job (scary), but frames it as net-positive for uptime and sanity.
- **Framing, not verdict:** His stated goal was just to show the current landscape, deeper on Juniper (he got hands-on access) and lighter on Cisco (only a keynote; Cisco's AI still pending, expected later in 2025).

## Notable verbatim quotes

> "AI enabled, AI powered, AI-driven, AI enhanced, AI slop. I'm getting tired of this. This is what we're seeing with every product we use since ChatGPT broke everything in 2022."

> "Everyone's jumping on this AI hype train, and I want to get off. I mean, come on. Is adding AI to all of our products actually solving real problems? Is it making us better?"

> "Is this all just AI slop? Or are there real use cases?"

> "ChatGPT came out in November 2022. There was no AI before that, right? That is kind of how it feels, but AI was very much a thing before ChatGPT."

> "One thing I've learned about AI so far is that it all depends on the data you feed it, the context you provide. This is true across the board for anything."

> "In the same way, we can't ask an LLM about our network unless it has the context of our network."

> "What we're seeing right now is a lot of bolt-on AI, again slapping that sticker on. We're feeding our LLMs a ton of data about our network... Here you go, friend. Figure it out for me, please."

> "Let's be honest, we know LLMs, even the greatest ones right now, get very confused with too much data."

> "The more moving parts, the more complex, the more often it breaks and the harder it is to troubleshoot."

> "It looks shiny. I'm excited. I'm also like grain of salt, you know?"

> "I have not played with it or used it myself, experienced an outage or anything like that, but their customers have. And conceptually, it sounds cool."

> "Do you think we're at a point now to where AI is finally delivering on the promises? Do you think it's all marketing glitter shiny tools or is it real?"

> "If we can avoid those situations and bring an AI to bring better uptimes, that's going to be phenomenal."

> "My goal for this video was just to show you what the landscape is right now."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT). Note: the video quotes several Juniper/Mist figures (Sudhir, CEO "Rammy," co-founder Bob Friday, Kyle, integrator "Allan/Alan" from Nexum) as interview/keynote material; those statements are third-party and are NOT attributable to Chuck — only Chuck's own framing and commentary trains the persona.

<!-- ★ L3-candidate: AI-hype-skepticism / balanced-AI stance (beliefs; nuances earlier position) -->
