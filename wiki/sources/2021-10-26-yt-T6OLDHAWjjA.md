---
type: youtube-video
source_date: 2021-10-26
url: https://www.youtube.com/watch?v=T6OLDHAWjjA
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cloud-devops, certifications-career]
tags: [python, math, encouragement, free-course, ep-3]
---

# do you need to be good at MATH to learn Python? // Python RIGHT NOW!! // EP 3

Episode 3 of Chuck Keith's free Python series ("everything you need to know to become
dangerous in Python"). The video opens by defusing the fear that Python requires math
skill, then teaches Python numbers (integers, floats), type checking, arithmetic
operators, order of operations, and type conversion — all applied to the running
"robot barista" coffee-shop project.

## Summary

Chuck frames the episode around a worry many beginners share: that Python's use of
numbers and math means you have to be good at math. He answers directly — you do not,
the math involved is "stupid, simple." He then teaches, hands-on in his free browser
lab, the core numeric concepts:

- **Integers** — whole numbers; assigns `age = 7`, then `age = 31`.
- **The `type()` function** — inspects a value's data type; wrapping a number in quotes
  turns it into a string even though it looks like a number.
- **Floats** — decimals; adding a decimal point (`actual_age = 31.96`) makes it a
  floating-point number rather than an integer.
- **Arithmetic operators** — `+`, `-`, `/` (forward slash), `*` (asterisk), and `**`
  (double asterisk / exponent); Python obeys the order of operations, and division
  always converts to and returns a float.
- **Type conversion** — `int()` to turn a string into an integer, `str()` to turn an
  integer into a string.

The concepts are motivated by adding pricing to the robot barista. Setting a price and
multiplying by quantity fails at first because `input()` returns a string, so
`price * quantity` produces repeated text ("eight tens") instead of a product — fixed
by wrapping the quantity in `int()`. Concatenating the total into a print string then
throws a `TypeError` (can only concatenate string to string), fixed by wrapping the
total in `str()`. Chuck emphasizes that hitting these errors is normal and to "get used
to it." The episode is sponsored by ITProTV (code NETWORKCHUCK, 30% off).

## Key claims (paraphrase unless quoted)

- (2021-10-26) You do not have to be good at math to learn Python; the math involved is
  extremely simple (addition-level). Math not being fun in school does not disqualify you.
- (2021-10-26) It is precisely this simple math that makes Python powerful.
- (2021-10-26) A whole number in Python is called an **integer**; `7` is an integer.
- (2021-10-26) Numbers, like strings, can be assigned to variables (e.g. `age = 7`).
- (2021-10-26) `type()` reports a value's data type — `str` for strings, `int` for
  integers, `float` for floats.
- (2021-10-26) Any value between quotes is a string, even a number — Python then treats
  it as regular text, not a number.
- (2021-10-26) Adding a decimal point makes a number a **floating-point number** ("float"),
  no longer an integer.
- (2021-10-26) Python's arithmetic operators: `+` add, `-` subtract, `/` divide (forward
  slash), `*` multiply (asterisk), `**` exponent (double asterisk). Negative numbers can
  be integers.
- (2021-10-26) Python follows the standard order of operations.
- (2021-10-26) Whenever Python divides, it converts the numbers to floats first, so a
  division result is a float.
- (2021-10-26) `input()` always returns a **string**, so numeric input must be converted
  before doing math on it (e.g. `int(quantity)`) — otherwise `8 * "10"` yields the string
  repeated, not `80`.
- (2021-10-26) Converting types: `int()` turns a value into an integer; `str()` turns a
  value into a string. Concatenating a string with an integer raises a `TypeError`, fixed
  by wrapping the integer in `str()`.
- (2021-10-26) Errors (like `TypeError`) are a normal part of programming — expect to hit
  them often.
- (2021-10-26) Learning is best done hands-on; the free browser-based Python lab lets you
  start coding immediately, even from a phone.

## Notable verbatim quotes

> You don't have to be good at math to learn Python. And the math I'm talking about is
> like stupid, simple, like one plus two equals four simple.

> Maybe math wasn't fun for you in school, but it's about to get lit with Python.

> This is episode three of my free Python series, where I'm going to teach you everything
> you need to know to become dangerous in Python.

> Anything between quotes is a string. Even if you put a number there, that number is now
> seen by Python as just regular text, a string.

> When you use the input function, whatever data it asks you for, that data is not going
> to be a number. It's not going to be an integer... it's going to be a string.

> This int function... turns whatever's inside into an integer.

> We convert a string to an integer and then an integer into a string. That's programming,
> man. That's programming.

> Whoa, error. Ooh. Get used to it. This can happen to you a lot.

> Normally math sucks... but math and Python, much better.

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: Python EP3 — "you don't need math" encouragement (accessibility ethos) -->
