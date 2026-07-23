---
type: youtube-video
source_date: 2025-11-26
url: https://www.youtube.com/watch?v=pwWBcsxEoLk
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [ai-tools]
tags: [prompting, prompt-engineering, ai-literacy, llm, workflow]
---

# You SUCK at Prompting AI (Here's the secret)

## Summary

A 2025 prompt-engineering masterclass in which Chuck argues that bad AI results are
almost always a "skill issue" on the user's side, not a failure of the model. He
frames the whole video as a running demo: taking a garbage one-line prompt
("Write a CloudFlare apology email") and improving it step by step by layering
foundational and advanced techniques.

Chuck says he "went deep, too deep" to prepare — taking the top prompting courses on
Coursera (Vanderbilt's Dr. Jules White course and the Google prompting course, TCREI
framework), reading the official prompting docs from Anthropic, Google, and OpenAI,
and asking expert prompt engineers he knows (Daniel Miessler, Eric Pope, Joseph
Thacker "the prompt father"). Coursera sponsored the video.

The core mental model: a prompt is **not a question, it's a program** — you are
programming the LLM with words. LLMs don't think; they are **prediction engines**
("super advanced autocomplete"). A prompt starts a pattern and you're "hacking the
probability" — vague patterns get vague guesses, focused patterns get better results.

He then walks a progression of techniques (foundations → advanced), and finally
reveals the **meta skill** that makes all of them work: **clarity of thought**. Every
technique is really just a forcing function for expressing yourself clearly. "The AI
can only be as clear as you are." The video ends (as his do) with a prayer for the
viewer.

## Key claims (dated — the framework + mental model)

Chuck's progressive prompting framework, as taught 2025-11-26:

**Mental model / mindset:**
- A prompt is a "call to action" to the LLM (Dr. Jules White's definition), but more
  importantly it's **a program, not a question** — you program the AI with words.
- LLMs are **prediction engines / advanced autocomplete**; results are called
  "completions" because the model is statistically completing a pattern, not thinking.
- You're **starting a pattern**, not asking a question — vague pattern = wild guesses,
  focused pattern = better results. This is "hacking the probability."
- Treat every bad result as a **personal skill issue** (from Joseph Thacker): assume
  you didn't explain it well enough or give enough context.

**Foundational techniques (in order):**
1. **Personas** — tell the AI who is writing / what expertise to draw from (e.g. "you
   are a senior site reliability engineer for CloudFlare"). Narrows the model's focus
   so it guesses better. Google course: persona = "what expertise you want the
   generative AI tool to draw from." Note: in APIs / Claude Code the persona normally
   lives in the **system prompt** (vs. the user prompt); there are two prompts at work.
2. **Context** — the single most important technique; "context is king," the C in
   Google's **TCREI** framework. Supply all the necessary facts/details; whatever you
   omit, the model fills in (hallucinates) because LLMs are eager to please and rarely
   return nothing. More context = fewer hallucinations. Be detailed, be specific.
   - **Tools**: LLMs are "frozen in time" (trained to a cutoff, e.g. Haiku to July
     2025); enable **web search / external tools** to fetch current info — but be
     careful, tools can pull wrong or outdated sources.
   - **Memory**: built-in chat memory can help but also misleads you into assuming the
     model knows more than it does. "Always be contexting" — never assume; provide
     context every time.
   - **Give the AI permission to fail** (from Anthropic's docs): explicitly tell it to
     say "I don't know" if the answer isn't in the context. Chuck calls this "the
     number one fix for hallucinations." Otherwise it will lie to please you.
3. **Output requirements** — specify exactly how the result should look (format,
   length, tone), e.g. "clear bulleted list, under 200 words, professional/apologetic,
   radically transparent, no corporate fluff." Chuck says this one is easy to forget
   but "packs the biggest punch."
4. **Zero-shot vs. few-shot** — the above is zero-shot (just ask and let it guess).
   **Few-shot prompting** = show it examples of what good output looks like rather than
   describing it. "We're not describing the output, we're showing the output." Give
   representative example snippets (not entire documents, which get noisy/confusing).
   Dr. White: teaches the LLM to follow a pattern via few-shot examples.

**Advanced techniques:**
5. **Chain of Thought (CoT)** — tell it to "think step by step" before answering
   (Dr. White: "showing your work"). Raises accuracy and trust (you see the reasoning).
   Now baked into platforms as **extended thinking / thinking**; models that do it are
   **reasoning models**. Chuck cites Ethan Mollick (Wharton): ~95% of practical
   problems can be solved just by turning on extended thinking. Still useful to
   describe the steps for repeatable processes / system design.
6. **Tree of Thoughts (ToT)** — explores multiple reasoning paths at once (vs. CoT's
   single linear path), enabling self-correction and diverse options. Demo: "brainstorm
   three distinct tonal/strategic approaches… evaluate each branch, synthesize them and
   find the golden path."
7. **The "playoff method" / adversarial validation ("battle of the bots")** — force
   the model to generate competing options with distinct personas instead of averaging.
   Demo: a 3-round competition (engineer vs. PR crisis manager draft; angry customer
   critiques both; then collaborate on a final email). Works because **AI is better at
   critiquing/editing than at original writing**, so this taps its superpower.

**The meta skill — clarity of thought:**
- The single concept that makes every technique work. From Daniel Miessler: before
  building any prompt/AI system, sit down and **describe exactly how you want it to
  work** and **red-team it** (attack it from different angles for robustness), spending
  a lot of time up front. "If you can't explain it clearly yourself, you can't prompt it."
- Every technique is really a forcing function for clarity: persona = who's answering /
  source of knowledge; context = the facts; CoT = how the logic flows; few-shot = what
  good looks like. Using them doesn't make the AI smarter — **it makes you clearer**.
- Practical advice: "Think first, prompt second." Get a notebook/blank note and describe
  what you want before prompting. Imagine handing it to a human — is it enough info?
- **Build a prompt library** (Google course recommends it; Daniel Miessler's **Fabric**
  is a prompt library). Save good prompts.
- The "meta meta skill": use a **prompt-enhancer prompt** (or a provider's built-in
  prompt improver, e.g. Anthropic's) to structure raw ideas — but only after your own
  thinking is clear.
- Broader belief: many people use AI as a crutch and their skills atrophy; but if you
  get good at AI, your ability to **think, design systems, and describe problems**
  increases. That is "the skill right now to learn."

## Notable verbatim quotes

> "You suck at prompting. It's okay. I did too, but I got tired of asking AI to do things and getting garbage."

> "A prompt just isn't a question, it's a program. You aren't asking the AI, you're programming it with words."

> "When you understand that an LLM is just super advanced autocomplete, that'll change your perspective."

> "You're not asking a question. You're starting a pattern… If your pattern is vague, the AI guesses anything, but if it's more focused, you'll get way better results. You're hacking the probability."

> "Whatever context or information you don't include, it's going to fill in those gaps itself… So more context equals less hallucinations."

> "Give your AI permission to fail… If it's not in the context, you can't find the answer, say, I don't know. If you don't say that, it will lie to please you. And this is the number one fix for hallucinations."

> "A, B, C, always be contexting."

> "We're not describing the output, we're showing the output, and it's one of the best things you can do."

> "The reason this works is because AI is normally better at critiquing or editing than original writing. So asking it to do this is actually tapping into its superpower."

> "If you can't explain it clearly yourself, you can't prompt it. And that's the key. That's the skill."

> "My garbage prompts… were messy because my thinking was messy."

> "So using all these techniques doesn't make the AI smarter, although it feels like it. All that's happening here is you got clearer."

> "The AI can only be as clear as you are, so the next time you're getting frustrated with AI and you're tempted to yell at chat GPT, look in the mirror, it's you. It's a skill issue."

> "Think first, prompt second."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT). External experts
(Dr. Jules White, Daniel Miessler, Eric Pope, Joseph Thacker, Ethan Mollick) and
course/doc frameworks (Vanderbilt/Coursera, Google TCREI, Anthropic docs) are cited
by Chuck as sources; their positions are relayed through him, not independently
attributed here.

<!-- ★ L3-candidate: 2025 prompting framework (ai-literacy; pairs with 'using AI wrong') -->
