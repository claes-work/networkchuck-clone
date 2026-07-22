---
type: youtube-video
source_date: 2022-05-09
url: https://www.youtube.com/watch?v=jdTwCSxNINA
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cloud-devops, certifications-career]
tags: [python, lists, remove, pop, free-course, ep-9]
---

# deleting stuff from Python Lists // Python RIGHT NOW!! // EP 9

## Summary

Episode 9 of NetworkChuck's free "Python RIGHT NOW!!" beginner course, continuing
the running "camping supplies list" project from prior episodes. Having previously
learned to *add* items to a list, this episode teaches how to *remove* them. Chuck
covers four deletion techniques, framing them with his usual dramatics ("obliterate,
destroy Python data") while reassuring viewers that they are just removing items
from a list.

The four methods, in the order taught:

1. **`clear()`** — the "nuclear" option; empties the entire list, leaving an empty
   list `[]`. Chuck uses this to segue into the concept that empty lists are valid
   and useful for programmatically building a list up from nothing.
2. **`remove(value)`** — the most intuitive method; you specify the actual *value*
   (must match exactly, e.g. `tent`, not `tents`, or you get an error). Removes only
   one item per call; you cannot pass multiple comma-separated values.
3. **`pop(index)`** — removes by *index* rather than value. Chuck highlights the
   critical-thinking gotcha that indexes shift after each removal (removing index 0
   twice removes the first two items, because the list re-indexes after the first
   pop).
4. **`pop()`'s hidden feature** — `pop` also *returns* the item it removed, so you
   can capture or print the deleted value (e.g. a deletion confirmation). Chuck calls
   it a "one-two punch" / "combo move."

The episode also mentions `del` conceptually is not the focus (Chuck sticks to
methods), notes that removing *multiple* items at once is a harder concept saved for
later, and teases the next episode's topic: **tuples** (like a list but faster /
"almost better in every way" for running programs). Standard NetworkChuck framing
throughout: free in-browser Python lab linked below, IT Pro TV sponsor read
(code `networkchuck` for 30% off), coffee breaks, and Network Chuck Academy for
extra quizzes/labs.

## Key claims (dated — concepts)

All concepts as taught 2022-05-09 (paraphrase):

- `clear()` empties an entire list, leaving an empty list `[]` — the "nuclear"
  option that removes everything at once.
- Empty lists are valid and useful: you often define an empty list first, then
  programmatically add items to it later in a script.
- `remove(value)` deletes an item by its **value**, not its position; the value
  must match exactly (`tent` works, `tents` throws an error because it isn't there).
- `remove()` can only delete **one** item per call; passing multiple comma-separated
  values throws an error.
- Removing multiple items from a list at once is not simple and is deferred to a
  later point in the course.
- `pop(index)` deletes an item by its **index** rather than its value.
- List indexes **shift** after a removal: popping index 0, then index 0 again,
  removes the first two original items (after the first pop, the second item moves
  into index 0). You must account for re-indexing when using multiple index-based
  removals.
- `pop()` has a hidden feature: it **returns** the item it removed, so you can print
  or reuse the deleted value (e.g. wrapping `supplies.pop(0)` in `print()`, or
  concatenating it to a confirmation string like "this item was just deleted").
- Next-episode teaser: a **tuple** is similar to a list but faster and better for
  running programs.

## Notable verbatim quotes

> We are about to use Python to destroy, obliterate data. Please try this at home,
> in your lab, like not in production.

> So clear is nuclear.

> You can have empty lists, which seems pointless, right? But no... it does come in
> handy when you're programmatically adding things to a list but you don't have
> anything for that list to have in it yet.

> Now one key thing to note with the remove method is that when we wanna remove
> something, we specify the actual value, the actual name of the data. And obviously
> it has to be correct. 'Cause if you put instead put tents, we're gonna get an
> error 'cause tents aren't there. It's just tent.

> We can only remove one piece of data with our remove method which is important to
> remember.

> Well, because when I removed pop, the index changed, right? That required a bit of
> critical thinking, didn't it?

> When you remove something with pop it not only just, you know, takes it out, it
> will also return that same data.

> It's like a combo move. Bam, delete, bam, let me show you what I just deleted.
> One, two punch, I love it.

> There's something weird, something that's just like a list, almost identical to
> it, but it's faster. It's almost better in every way as far as running programs,
> it's something called a tuple.

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: Python course EP9 — list deletion -->
