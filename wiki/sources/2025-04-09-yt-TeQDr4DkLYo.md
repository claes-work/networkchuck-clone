---
type: youtube-video
source_date: 2025-04-09
url: https://www.youtube.com/watch?v=TeQDr4DkLYo
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [ai-tools]
tags: [context-window, llm, tokens, ai-literacy, fundamentals]
---

# Why LLMs get dumb (Context Windows Explained)

## Summary

Chuck explains **why LLMs "get dumb"** in long conversations — they start hallucinating,
forget earlier context, and slow down — and pins the cause on the **context window**: the
finite short-term memory of a model, measured in **tokens**. Using [[LM Studio]] running a
local **Gemma 3 4B** model, he demonstrates live how a small 2,048-token context window
causes the model to forget the first thing it was told (a book he mentioned) once the chat
fills up, and how bumping the context to 4,096 restores that memory.

He walks through the fundamentals: what tokens are (how an AI counts words — not the same
as characters or words, and different models tokenize differently), what fills a context
window (user messages, model replies, system prompts, uploaded documents/PDFs, and code
during vibe coding), and the trade-offs of large context. Cloud models advertise huge
windows (GPT-4o 128K, Claude 3.7 200K, Gemini 2.5 1M, and a noted-from-the-future Llama 4
Scout at 10M), but running big context locally hammers **VRAM** and **compute**.

The deeper lesson is about **attention**: citing the "Lost in the Middle" paper, Chuck
shows LLMs recall info at the beginning and end of a long context well but drop off badly
in the middle (a **U-shaped** accuracy curve) — like his wife falling asleep mid-movie.
He previews (but defers to a future video) **self-attention mechanisms**: the model runs
expensive semantic math every message to assign **attention scores** to relevant words,
and that math grows with the conversation, which is why long chats get slow and unreliable.
His practical rule: **when you significantly shift topics, start a new chat.** He closes
with local-inference optimizations (**Flash Attention**, **KV cache quantization**, **paged
cache**) that let his RTX 4090 hold the full 128K window, and flags a security angle: longer
conversations mean a **larger attack surface** for prompt injection / jailbreaks hidden in
the forgotten middle. The Twingate-sponsored coffee break introduces **r.jina.ai** for
converting webpages to clean LLM-friendly markdown.

## Key claims (dated — concepts + advice)

Concepts (2025-04-09):
- LLMs (ChatGPT, Gemini, Claude, local models like Llama or DeepSeek) have a **short-term
  memory** with a hard limit; that limit is the **context window**. (paraphrase)
- A **token** is how an AI counts the words you give it; tokens are not the same as
  characters or words, and different LLMs tokenize differently (a token may be a whole word,
  a space + word, or a single comma). (paraphrase)
- Demonstrated live: a Gemma 3 4B model with a 2,048-token window forgot the earliest info
  it was given (the book) once the chat exceeded the window (~118%); raising the window to
  4,096 tokens restored the memory. (paraphrase)
- The context window is filled by more than user + model messages: **system prompts**
  (instructions, often hidden/default), uploaded **documents** (PDFs, spreadsheets), and
  **code during vibe coding** all consume tokens. (paraphrase)
- Advertised cloud context windows (as of the video): **GPT-4o 128K**, **Claude 3.7 200K**,
  **Gemini 2.5 ~1M** (with 2M "around the corner"); a from-the-future note adds **Llama 4
  Scout at 10M tokens** (a local model). (paraphrase)
- A large context window does not prevent the model from freaking out — it can still become
  less accurate, hallucinate, or go slow. (paraphrase)
- The **"Lost in the Middle"** paper: with large context, models are more accurate on info
  at the **beginning and end** but drop off sharply in the **middle** — a **U-shaped** curve.
  (paraphrase)
- **Attention / self-attention mechanisms**: the model uses semantic math to assign
  **attention scores** ranking which words are relevant to the whole conversation (e.g.
  "coffee," "caffeine," "jittery" score high; "I," "me" score low), mirroring how humans
  focus. (paraphrase)
- This attention math re-runs on **every** message and grows with the conversation, so
  long chats demand more GPU compute — a key reason they slow down and hallucinate.
  (paraphrase)
- Running big local context is bounded by **VRAM**, not just the model's stated max; a 4090
  with 24 GB VRAM maxes out loading a full 128K window and becomes very slow. (paraphrase)

Advice / practical (2025-04-09):
- **Start a new chat when you significantly shift topics** — performance improves markedly;
  some LLMs (e.g. Claude) even prompt you to do this. (paraphrase)
- Don't keep one endless conversation covering unrelated topics (coffee, weather, quadratic
  equations) — the model wastes effort weighing irrelevant context and hallucinates.
  (paraphrase)
- For running full local context: enable **Flash Attention** (skips storing the full token
  comparison matrix; big memory + speed gains), **KV cache quantization** (compresses cache;
  lower quant = smaller footprint), and be aware of **paged cache** (offloads attention
  cache from VRAM to system RAM — works but is slower, like a page file). (paraphrase)
- Longer conversations enlarge the **attack surface**: attackers can hide malicious prompts
  in the forgotten middle to bypass safety systems. (paraphrase)
- To feed a webpage into an LLM cleanly, prefix the URL with **`r.jina.ai/`** to convert it
  to markdown rather than copy-pasting messy human-formatted content. (paraphrase)

## Notable verbatim quotes

> "Did you know that LLMs like ChatGPT, Gemini, Claude, even local models like Llama or
> DeepSeek, they're kind of like us, you and me, in that they have memories. Short-term
> memory."

> "It kind of reminds me of how sometimes when I fight with my wife, we fight for so long
> that we forget what we're fighting about to begin with."

> "That short-term memory has a limit. That limit is its context window."

> "Tokens are how an AI counts the words you say to it."

> "It's like that lazy kid in class who always got straight A's. It'll actually skip
> building the full table of token comparisons by processing tokens in chunks with
> optimized GPU routines." [on Flash Attention]

> "Just like my wife, once she watches a long movie, she'll watch the first part, then fall
> asleep and then wake up at the end. And that's the context she has."

> "The models were more accurate with info at the beginning and even with info at the end.
> But in the middle, huge drop off. And across the board we saw this U shape." [on "Lost in
> the Middle"]

> "LLMs are falling asleep during our conversation. Kind of. I'm telling you, LLMs have
> problems paying attention just like us."

> "But that would increase the context window of this video, making it harder for people to
> pay attention to. And given this is probably the middle of the video, you would forget
> it."

> "When you change an idea, when it's a significant shift from what you're currently talking
> about, start a new chat. The performance will be so much better."

> "It's kind of like you having a notebook with a bunch of stuff you've written down. You've
> got the ability to have all that stuff with you. That's your context. But the ability to
> quickly find what you need in that notebook might be kind of limited. You can't remember
> every page."

> "Anyways, our context window is way too big. We're going to end it right now."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: canonical context-window explainer + analogy (ai-literacy, voice) -->
