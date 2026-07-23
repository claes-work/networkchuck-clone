---
type: youtube-video
source_date: 2024-05-28
url: https://www.youtube.com/watch?v=UbDyjIIGaxQ
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [ai-tools]
tags: [prompting, llm, rag, ai-workflow]
---

# You've been using AI Wrong

## Summary

Chuck's core AI-usage argument in this video is that most people use LLMs "wrong" by
treating them as a chat window you visit ad hoc, retyping context and improvising
prompts every time. His fix is a workflow tool called **Fabric**, an open-source
framework by Daniel Miessler that sits between your text and any AI model (OpenAI,
Anthropic, or local models via Ollama) and applies **reusable, curated system prompts
called "patterns."** Patterns like `extract_wisdom`, `summarize`, `analyze_claims`,
`label_and_rate`, `write_essay`, and `improve_prompt` are crowdsourced, open-sourced,
and iterated on like open-source code, so the actual system prompt is visible and
editable rather than hidden behind a chat UI.

The video doubles as a hands-on setup tutorial (clone from GitHub, install with `pipx`,
run `fabric --setup`, add API keys) and a mental-model piece. Chuck demonstrates piping
a YouTube transcript (via the built-in `yt` tool) into a pattern to distill a two-hour
interview in seconds, stitching patterns together (summarize → write_essay), building
custom patterns (his `Sermon Sensei` / `Sermon Wisdom`), and saving output straight to
Obsidian. Underneath the tooling sits a philosophy borrowed from Miessler and David
Allen: reduce friction, get **everything into text** ("world of text") so AI can operate
on it anywhere, and use AI to **augment humans rather than replace them.** The
most persona-relevant thread is the "don't take the weights out of the gym" principle —
use AI as a *filter* to decide what deserves deep, slow, manual engagement, not as a
blanket shortcut that removes the hard thinking that builds you.

## Key claims (dated — the method + mental model)

All dated 2024-05-28 (paraphrase unless quoted):

**The method (Fabric + patterns):**
- People use AI "wrong" because they treat it as an ad-hoc chat window — going out to
  ChatGPT, opening a web interface, loading a custom GPT, re-establishing context. That
  friction is real time cost that gets in the way.
- Fabric is a framework, not an AI itself — it sends your text plus a curated system
  prompt to whatever model you choose (OpenAI, Anthropic, or local via Ollama).
- The "secret sauce" is **patterns**: reusable system prompts, each engineered to solve
  one specific problem, that are open-source and crowdsourced (improved over many
  iterations like open-source code).
- Because patterns are open-source you can *see* the actual system prompt being sent —
  unlike hidden custom-GPT prompts, you control and are part of it.
- Fabric is CLI-native (though Miessler's aim is many "on-ramps": CLI, GUI, voice), so
  you pipe text in on the command line: e.g. `yt <url> | fabric --pattern extract_wisdom`.
- Built-in tools like `yt` (grab a YouTube transcript/comments via a Google/YouTube API
  key) eliminate a whole step; output defaults to Markdown so it flows into notes apps.
- Good prompt-craft in these patterns includes talking to the model like a human —
  "take a step back, think step by step, think deeply" — which reliably elicits better
  results even though nobody fully knows why.
- **Patterns can be stitched**: pipe one pattern's output into another (e.g. `summarize`
  → `write_essay`) to build multi-stage workflows.
- You can **write your own patterns**: a pattern is just a `system.md` file in a folder
  under `~/.config/fabric/patterns`; keep custom ones in a separate directory so
  `fabric --update` doesn't overwrite them. The `improve_prompt` pattern helps you write
  new prompts.
- Fabric can be baked directly into code (e.g. a Python script) instead of hand-rolling
  AI API calls; Chuck used it to turn messy Strava JSON into a workout summary.
- Local/remote models: `fabric --listmodels`, `--model llama3:latest`, or point at a
  remote server IP to run larger models (e.g. Llama 3 70B) on a home AI server; access
  it from anywhere via a zero-trust tool (Twingate, the sponsor).
- Output can be saved straight to Obsidian via the built-in `save` command once you set
  the vault path in Fabric's `.env`.

**The mental model (how to use AI well):**
- The real purpose of the technology is **reducing friction so AI helps you solve your
  problems** — and to *augment* humans, not replace them.
- **"World of text"** (via Miessler / David Allen): capture everything immediately as
  text — notes, transcribed audio (Whisper), etc. — so it can be manipulated anywhere by
  anything, especially AI.
- **Don't take the weights out of the gym**: don't summarize everything. Use AI (and
  patterns like `label_and_rate`) as a *filter* to decide what deserves slow, painful,
  manual engagement — because that hard work is where you grow. Some things should still
  be read/watched in full and hand-noted.
- Design patterns to **mimic how you personally process content** — the way you'd watch
  a video and take slow notes by hand.
- A "context" file lets you define your goals/purpose so Fabric's recommendations serve
  what you're actually trying to learn or become.
- Chuck's evolving stance on AI: he was terrified when ChatGPT launched, but reframed it
  as something that makes us better — "it's about humans flourishing."

## Notable verbatim quotes

> "It's called Fabric. ... So basically the goal is to augment humans with ai, so it's
> all about reducing that friction to be able to use AI for your problems." (Chuck
> introducing, then quoting Daniel Miessler)

> "I legit use this every day and I think you might too."

> "This is the secret sauce behind fabric and something you should get pretty excited
> about."

> "Take a step back, think step by step, think deeply. It kind of sounds like he's
> talking to this AI like a human, and that's exactly the case. ... We don't know why
> it works, but just talking to these AI like they're humans elicits a better response,
> better results."

> "Fabric is all about reducing friction to have AI help you solve problems. And one of
> the areas of friction I didn't even realize I had was the fact that I had to keep
> going out to chat GPT, open up a web interface, load up maybe a custom GPT..."

> "So it's about getting everything into a text format so it can be used anywhere by
> anything, especially ai."

> "You don't want to take the weights out of the gym. So everything shouldn't be a
> summary. Sometimes you have to put the hard work in, but you can use it to tell you or
> advise you or recommend to you which things you should do slow and painful and
> difficult because that's where you get the most muscle growth." (Chuck quoting
> Daniel Miessler)

> "It's not about replacing humans replacing you, it's about making you better, about
> taking your current capabilities and using AI to increase that at a faster rate than
> you could before."

> "It's about identifying a problem that you might have and then creating a pattern to
> help you solve that problem."

> "And that was the first video I made ever about ai. Chad GPT came out, I was
> terrified, but then after processing it a bit more, I'm like, you know what? This is
> going to make us better. It's about us. It's about humans flourishing."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

Note: the video interleaves quoted clips from **Daniel Miessler** (creator of Fabric).
Miessler-attributed statements (e.g. the "world of text," the "context file" purpose
statement about Human 3.0 / human flourishing, and "don't take the weights out of the
gym") are the guest's words, presented and endorsed by Chuck. Chuck's own framing,
tutorial narration, and personal examples (Sermon Sensei, Strava, recording his Bible
study group) are the SUBJECT's own material. Where the model is shared framing, it is
Chuck adopting Miessler's ideas explicitly.

<!-- ★ L3-candidate: how-to-use-AI-well mental model -->
