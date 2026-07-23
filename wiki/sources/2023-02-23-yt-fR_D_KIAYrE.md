---
type: youtube-video
source_date: 2023-02-23
url: https://www.youtube.com/watch?v=fR_D_KIAYrE
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cloud-devops, certifications-career]
tags: [python, tuples, data-structures, free-course]
---

# why are TUPLES even a thing?

## Summary

A lesson from Chuck's free Python course, framed as an investigative "journey"
to figure out why Python has tuples when they seem almost identical to lists.
Chuck creates a list (with brackets) and a tuple (with parentheses), notes they
both hold an ordered collection of data, and confirms their types via
`type()` (`class list`, `class tuple`). He then researches the difference by
Googling, asking ChatGPT, and asking his Discord community.

The core distinction he lands on is **mutability**: lists are mutable (you can
change them), tuples are immutable (you can't). He demonstrates by reassigning
index 0 of a list ("Bernard" → "Chuck") successfully, then trying the same on a
tuple and getting an error. He then addresses the "so what?" question with two
justifications for tuples: (1) tuples are **faster** than lists — demonstrated
with the `timeit` tool creating 1 million of each (≈1.43 s for lists vs ≈0.13 s
for tuples), which he explains comes from lists being stored in two blocks of
memory (to allow change) while tuples use one; and (2) tuples have real **use
cases** — storing heterogeneous data (mixed types grouped as a record, e.g. a
YouTuber's name, subscriber count, and video types), being effectively forced on
you by SQL libraries (`fetchone`, `fetchall` return tuples), and read-once /
function-return data for speed.

He closes with "weird things" you can do with tuples: **unpacking** a tuple into
multiple variables at once (noting lists can do this too), and the fact that a
tuple doesn't require parentheses — a trailing **comma** alone makes a tuple. He
also shows tuples and lists can be nested inside each other, and that a tuple can
be converted to a list. The video ends with a "like, comment, subscribe" tuple
joke. Credits to Discord members (Labret, Grau) for answers.

## Key claims (dated — concepts)

- [2023-02-23] Lists and tuples both hold an ordered collection of data
  (strings, integers); lists are created with square brackets, tuples with
  parentheses. Paraphrase.
- [2023-02-23] The one key difference is mutability: lists are mutable (can be
  changed), tuples are immutable (cannot be changed). Paraphrase.
- [2023-02-23] Reassigning an element by index works on a list but raises an
  error on a tuple. Paraphrase.
- [2023-02-23] Tuples are faster than lists; in a `timeit` demo creating 1
  million of each, the list took ≈1.43 s and the tuple ≈0.13 s. Paraphrase.
- [2023-02-23] The speed difference is due to storage: a mutable list is stored
  in two blocks of memory (to accommodate changing/new data), while an immutable
  tuple is stored in one block. Paraphrase.
- [2023-02-23] The millisecond-scale difference is negligible in small examples
  but can save time (and money) in large, bulky programs. Paraphrase.
- [2023-02-23] Use lists for homogeneous data (same type — e.g. a list of names,
  coffees, or YouTubers) and tuples for heterogeneous data (mixed types grouped
  as one record — e.g. a YouTuber's name, subscriber count, and video types).
  Paraphrase.
- [2023-02-23] SQL libraries in Python effectively force tuples on you — methods
  like `fetchone` and `fetchall` return tuples. Paraphrase.
- [2023-02-23] Tuples suit read-once / quick data and function returns for faster
  loading speed. Paraphrase.
- [2023-02-23] A tuple can be unpacked to assign its values to multiple variables
  at once, provided they're in the correct order; lists can be unpacked the same
  way. Paraphrase.
- [2023-02-23] Parentheses aren't required to make a tuple — a trailing comma
  after a value is enough for Python to treat it as a tuple. Paraphrase.
- [2023-02-23] Tuples and lists can be nested inside one another, and a tuple can
  be converted to a list (and vice versa). Paraphrase.

## Notable verbatim quotes

> "So it turns out immutable is just a fancy word for you can't change it.
> Whereas mutable means you can change it."

> "It changed. Mutable. Let's try to change our tuple, same process. ... and
> can't do it. It's immutable. Can't touch this."

> "The results are in and it's obvious, 1.43 seconds for a list and 0.13 seconds
> for a tuple. Dude, that made a list cry."

> "Because a list is mutable, you can change it. It's stored in two blocks of
> memory to allow for new data, change data. Whereas a tuple, it's stored in one
> block of memory, it's not gonna change."

> "In a list you wanna store what's called homogenous data. That's just kind of
> fun to say. Go ahead and say it, homogenous."

> "It's all different, but it's all data pertaining to a certain YouTuber.
> Basically it's how we're grouping our different types of data."

> "You don't actually need to use parentheses to make a tuple. ... All I have to
> do is just add a comma."

> "Tuples have their place. They're a thing. I might start using them, probably
> not, but they're also kind of weird."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
