---
type: youtube-video
source_date: 2022-04-29
url: https://www.youtube.com/watch?v=rW5sCgSSpI8
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cloud-devops, certifications-career]
tags: [python, lists, append, free-course]
---

# Adding stuff to a Python List

## Summary

An episode of NetworkChuck's free beginner Python course, focused on how to add
items to an existing Python list using **methods**. Chuck frames the lesson with a
running "we're going camping" analogy: a `supplies` list was built in the previous
episode, but he "forgot" to pack toilet paper (and wants a bidet for himself), so
the task is to add those items to the list — done "programmatically, using Python,"
not by manually editing the list definition.

The video introduces the concept of a **method** (a built-in Python tool/function
associated with objects/classes) via a brief clip of "Professor Bernard," then
teaches four ways to add data to a list:

1. **`append()`** — adds one item to the end of the list (e.g.
   `supplies.append("toilet paper")`). Only one item per call.
2. **`extend()`** — adds multiple items at once by passing a list
   (e.g. `supplies.extend(["toilet paper", "bidet"])`), appended to the tail.
3. **`+` (list concatenation)** — reassigns the list by adding another list to it
   (`supplies = supplies + ["toilet paper", "bidet"]`), same result as `extend`,
   using addition rather than a method.
4. **`insert(index, item)`** — adds an item at a specific position by index
   (e.g. `supplies.insert(0, "bidet")` for the front), including negative indexes
   for positions relative to the end.

The video reinforces the indexing concept from the prior list episode (lists are
ordered/sequenced, `0, 1, 2, 3…`), and clarifies a subtle difference: when
*printing/referencing*, negative index `-1` is the last item, but when *inserting*,
`insert(-1, …)` places the item **second-to-last** (one before the end).

Sponsored by IT Pro TV (the sponsor that funds the free series); Chuck mentions
learning to build a port scanner in their "Python For Security" course, plus a
30%-off-forever code "NetworkChuck." Also promotes the free in-browser Python lab
and NetworkChuck Academy for extra practice/quizzes. Next episode teased: removing
items from a list.

## Key claims (dated — concepts)

- (2022-04-29) A **method** is a built-in Python tool/function associated with
  objects/classes; for lists, methods let you change the list. Chuck: methods are a
  concept used broadly in Python, not just with lists, so learning them here gives a
  head start.
- (2022-04-29) `append()` adds a single item to the **end** of a list; it accepts
  only one piece of data per call — trying to add two items in one `append` fails.
- (2022-04-29) `extend()` adds **multiple** items at once by passing a list; the
  items are appended at the tail end.
- (2022-04-29) Adding two lists with `+` (e.g. `supplies = supplies + [...]`)
  produces the same result as `extend` — it is plain addition, not a method, the
  same concatenation idea already covered for strings and integers.
- (2022-04-29) `insert(index, item)` takes two arguments — a position (index) and
  the data — and places the item at that index; `insert(0, "bidet")` puts it at the
  beginning.
- (2022-04-29) Lists are ordered/sequenced and indexable (`0, 1, 2, 3…`); negative
  indexes count from the end.
- (2022-04-29) Distinction: when printing, index `-1` is the last item, but with
  `insert(-1, …)` the item lands **second-to-last**; `insert(-2, …)` lands
  third-from-last.
- (2022-04-29) Best practice framing: modify lists programmatically with Python
  rather than manually rewriting the list literal ("that's lazy").
- (2022-04-29) `append` on single items previews later use with **for loops**,
  teased as an upcoming topic.

## Notable verbatim quotes

> Do you know what's more fun than Python lists? Nothing. Not even "Elden Ring," maybe.

> Now I know what you're thinking. You're thinking, "Well, Chuck, can't we just go
> over here in our list and edit the list manually." ... No, that's lazy. We have to
> do it programmatically, using Python.

> This "append" thing is called a method. A method is a built-in Python tool or
> function and specifically for list. It allows us to change things up with our list.

> Using the append method, you can only add one item, one piece of data at a time,
> which honestly, yeah, is kind of annoying.

> So with our extend method, we extended our list by adding two items at the very
> tail end.

> First notice that we're not really using a method anymore. We're simply using a
> plus sign addition ... and here we're adding two lists, which is kind of crazy.

> If you're not using a bidet, what are you even doing? Okay. Off my soapbox.

> And by the way, have you hacked the YouTube algorithm today? ... You gotta hack
> YouTube today. Ethically of course.

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT). (A short scripted
clip of "Professor Bernard" defining a method appears but is cut off by Chuck; no
substantive attributed claim beyond the generic method definition, which Chuck
restates himself.)
