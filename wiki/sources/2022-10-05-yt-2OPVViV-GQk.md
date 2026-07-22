---
type: youtube-video
source_date: 2022-10-05
url: https://www.youtube.com/watch?v=2OPVViV-GQk
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, cloud-devops]
tags: [sql-injection, web-security, ethical-hacking, owasp, defense, lab]
---

# SQL Injections are scary!! (hacking tutorial for beginners)

## Summary

A beginner-oriented ethical-hacking walkthrough of SQL injection (SQLi), demonstrated
against a deliberately vulnerable lab banking app ("Al Toro Mutual") whose link Chuck
provides as homework. The whole exercise is framed as education on a purpose-built
practice target — no real system is attacked.

Chuck explains the concept conceptually rather than as an attack recipe: a login form
builds a SQL query by dropping the user's typed username/password into the query as
string values between quotes. If user input is inserted directly, an attacker can break
out of the string and inject extra SQL logic. He shows two classic ideas at a high level:
an "OR"-style payload that forces the query's WHERE condition to always evaluate true
(exploiting SQL's operator precedence, where AND is evaluated before OR), and a
comment-based trick that uses SQL's comment syntax to make the database ignore the rest
of the query (e.g. the password check). He also notes the diagnostic tell — a single
unbalanced quote produces a syntax error, which reveals that an app is vulnerable.

The stakes: attackers can dump databases of usernames and passwords and sell them on the
dark web without the victim ever knowing. He stresses SQLi is an old technique that still
ranks around #3 on the top vulnerability list because companies (or lazy coders) fail to
guard against it — even though it's relatively easy to prevent. The defensive close is
the core lesson: use prepared statements / parameterized queries, allow-list input
validation, escape user input before it enters a query, and use stored procedures. He
also mentions there are more advanced variants (union-based, blind SQLi) beyond the basic
in-band error-based case shown, and points to PayloadsAllTheThings as a resource. Sponsor
segment: Dashlane (password manager, dark-web monitoring).

## Key claims (dated — concept + defense)

- [2022-10-05] SQL injection works because a login form builds a SQL query by inserting
  the user's typed input as string values between quotes; if input isn't handled safely,
  an attacker can break out of the string and add their own SQL. (concept)
- [2022-10-05] A quick vulnerability test: submit a single stray quote — if the app
  returns a SQL syntax error, its input is being concatenated unsafely into the query and
  it's likely vulnerable to SQLi. (concept)
- [2022-10-05] SQL evaluates AND before OR (operator precedence), which is what lets an
  "OR 1=1"-style condition force the overall WHERE clause to always evaluate true. (concept)
- [2022-10-05] A SQL comment sequence can be injected so the database ignores the rest of
  the query — e.g. skipping the password check so only the username is required. (concept)
- [2022-10-05] The real danger is data theft: attackers can dump databases of usernames
  and passwords and sell them on the dark web, often without the victim knowing. (concept)
- [2022-10-05] SQLi is an old technique but still ranks around #3 on the top vulnerability
  list, because organizations and developers stay lazy or unaware of it. (concept)
- [2022-10-05] The basic case shown is in-band, error-based SQLi — the easiest and most
  common; more advanced variants include union-based and blind SQL injection. (concept)
- [2022-10-05] SQLi is relatively easy to prevent: use prepared statements with
  parameterized queries, allow-list input validation, escape user input before putting it
  in a query, and use stored procedures. (defense)
- [2022-10-05] Developers who think they're safe often aren't and should double-check
  their code for SQLi exposure. (defense)
- [2022-10-05] The demo is a lab exercise: the target is a deliberately vulnerable practice
  site provided as homework, framed as learning, not an attack on real infrastructure.
  (ethics / lab)

## Notable verbatim quotes

> "Here is our Target Al Toro Mutual and online banking site that is totally real."
(said sarcastically — it is a deliberately vulnerable practice lab)

> "One of the scariest uses of SQL injection is that bad actors can use a simple login
> form like this to dump a database of user names and passwords and then put them on the
> dark web with a for sale sign and you'll never know about it."

> "And this will tell you if a website is vulnerable to SQL injection... pay close
> attention to the [error]. We have a syntax error because if you look at our query...
> we have another quotation mark right here, a floating quote."

> "So what do you say? We use this good thing for a bad thing. We're gonna turn a comment
> into a hack."

> "While it is an old hacking technique, it's been around for a long time, it still ranks
> number three in the top list. It's still crazy dangerous. And the reason is because
> companies are lazy or the company has coders that are lazy."

> "Some things you can do are, hey, use prepared statements with parameter... parameterized
> queries, use an allow list for input validation, escape user input before putting it into
> a query... and use stored procedures."

> "You should probably just double check that real quick just to make sure. If you think
> you're safe, you're not."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
