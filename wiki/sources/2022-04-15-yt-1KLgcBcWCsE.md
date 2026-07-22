---
type: youtube-video
source_date: 2022-04-15
url: https://www.youtube.com/watch?v=1KLgcBcWCsE
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cloud-devops, certifications-career]
tags: [python, lists, data-structures, free-course]
---

# what is a List in Python?

## Summary

An entry in NetworkChuck's free Python course covering the Python **list** data
structure. Chuck frames the lesson with a running "camping trip" story: first he shows
the *wrong* way — cramming all the camping supplies into one giant string variable
(`camp_stuff`) — then contrasts it with a proper list (`camping_list`) built with square
brackets. He proves the data type using `print(type(...))`, which returns `list`.

Chuck teaches the core properties of lists: they are ordered/sequenced/indexed and
changeable, and (unlike an array) can hold a *mixture* of data types. He demonstrates a
mixed list `camp_site = ["Crystal Lake", 404, 89.3, True]` containing a string, an
integer, a float, and a boolean. He then teaches **indexing**: pulling out a single item
by its position in brackets (`camping_list[4]`), stressing that indexing starts at 0
(so a 10-item list's last index is 9). Finally he covers **negative indexing**:
`[-1]` returns the last item, `[-2]` the second-to-last — a handy way to grab the end of
a list whose length you may not know. He closes by printing the whole list, noting Python
renders it with single quotes.

The video is sponsored by ITProTV (code NETWORKCHUCK for 30% off), points viewers to a
free Python lab (Replit-based) linked in the description, and promotes NetworkChuck
Academy for extra labs, quizzes, and early access to the series. Recurring "coffee break"
running gag throughout.

## Key claims (dated — concepts)

- (2022-04-15) A Python list is created with square brackets `[ ]`; the brackets are
  what define it as a list, and items inside are separated by commas.
- (2022-04-15) Storing many pieces of data as one big string is bad practice — bloated,
  hard to use; a list stores each item as a separate individual piece of data.
- (2022-04-15) Per the "nerdy definition" (voiced by Bernard): a Python list is an ordered
  and changeable collection of data objects; unlike an array (single type only), a list can
  contain a mixture of object types.
- (2022-04-15) `print(type(variable))` returns the data type; for a list variable it prints
  `list`, proving it is a `list` data structure.
- (2022-04-15) A single list can hold multiple different data types at once — string,
  integer, float, and boolean — demonstrated with `["Crystal Lake", 404, 89.3, True]`.
- (2022-04-15) Lists are ordered/sequenced: the order you put items in is preserved unless
  you change it, which lets you reference individual items by position.
- (2022-04-15) You index (reference) a single item with brackets after the variable, e.g.
  `camping_list[4]`.
- (2022-04-15) Indexing starts at 0, because computers start counting at zero; so in a
  10-item list the last item's index is 9, not 10.
- (2022-04-15) "Indexed" is just another word for ordered/sequenced — each item is assigned
  a number based on its position, and referencing calls out that index.
- (2022-04-15) Negative indexing counts in reverse: `[-1]` is the last item, `[-2]` the
  second-to-last. There is no negative zero.
- (2022-04-15) Negative indexing is useful when you don't know how big a list is or
  specifically need the last item.
- (2022-04-15) A space after each comma is optional but best practice for readability.
- (2022-04-15) When you print a whole list, Python displays it with single quotes rather
  than double quotes.

## Notable verbatim quotes

> This is a Python list, and they are ridiculously powerful and pretty fun to play with.

> Because right now this is one big fat gargantuous string. It's bloated. It's ugly. I hate it.

> Now you can recognize a list because it'll always have opening and closing brackets. Bam, and bam. It has to have those. That's what a list needs.

> [Bernard] A Python list is an ordered and changeable collection of data objects. Unlike an array, which can contain objects of a single type, a list can contain a mixture of objects.

> Here in this list we have four different types of data, right? We got a string, we have an integer, a float, and a boolean.

> No, we're dealin' with computers and computers have to be difficult sometimes. You might realize and remember and know that computers always start counting with zero.

> So in a list with 10 items, your last number will always end up being 9. Just keep that in mind. That always messes me up whenever I'm dealing with list.

> Ordered, sequenced, indexed. And when I say indexed, it just means that each item in our list is assigned a number.

> So the very last item in our list would be negative one. And you're probably thinkin', well, Chuck, nuh uh, should be negative zero. It's not. Just isn't. You can't have negative zero. It's impossible.

> Have you hacked the YouTube algorithm today? ... You gotta hack YouTube today. Ethically, of course.

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT). (The "nerdy definition"
is voiced by "Bernard," a text-to-speech/character device used as a scripted teaching
aid within Chuck's own video, not an independent guest.)
