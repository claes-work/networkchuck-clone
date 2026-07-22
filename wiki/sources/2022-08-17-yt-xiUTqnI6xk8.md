---
type: youtube-video
source_date: 2022-08-17
url: https://www.youtube.com/watch?v=xiUTqnI6xk8
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cloud-devops, certifications-career]
tags: [sql, databases, learn-x-now, tutorial, beginners]
---

# you need to learn SQL RIGHT NOW!! (SQL Tutorial for Beginners)

## Summary

A landmark entry in Chuck Keith's signature "you need to learn X RIGHT NOW" tutorial
format, this time teaching SQL from zero for beginners. Chuck frames SQL as an
essential, near-universal IT skill ("pretty much any job in IT") and deliberately
targets a "Goldilocks amount" of SQL — "just enough to make you dangerous, but not too
dangerous." Guest cameo: Cameron confirms he used SQL constantly as an AWS cloud
engineer.

The hands-on demo builds a MySQL database from scratch on Ubuntu desktop running in a
VirtualBox VM. Chuck installs MySQL server via `apt`, verifies the service, connects to
the local MySQL prompt, and walks through the core relational-database workflow using a
themed "NetworkChuck Coffee" example (a `coffee_table` of coffees and an `Avengers`
table of Marvel-character customers). He covers the conceptual foundations (what a
database is, tables/columns/rows, DBMS, relational vs. non-relational, CRUD, schema)
and the practical SQL commands: `CREATE DATABASE`, `USE`, `SHOW DATABASES`,
`SHOW TABLES`, `CREATE TABLE`, `DESCRIBE`, `INSERT INTO ... VALUES`, `SELECT`,
`WHERE`/`AND`/`OR`/`NOT`, `DELETE`, `UPDATE ... SET`, `ORDER BY ... ASC/DESC`, and
`ALTER TABLE ... ADD`. He closes by pointing beyond the video to the topics he
deliberately skipped — the orders table, primary keys, foreign keys, joins, and views —
to leave viewers "hungry" to learn more. Sponsored by Dashlane (password manager). Solo
Chuck throughout (aside from the Cameron cameo line).

## Key claims (dated — SQL concepts)

All paraphrase unless quoted. Dated 2022-08-17.

- SQL stands for Structured Query Language; it is a language (like a programming
  language, similar to Python) whose primary use is to talk to databases.
- SQL is a near-universal IT skill — useful for hackers doing SQL injection, cloud
  engineers querying data, and "pretty much any job in IT."
- You do not need to become a SQL expert (unless you want to be a DBA); knowing the
  basics goes a long way across IT.
- A database is conceptually like a big Excel spreadsheet: it has columns (also called
  fields) and rows (also called records), and the rows hold the data. Databases are for
  storing large amounts of data beyond what a spreadsheet handles.
- A DBMS (database management system) manages databases; examples named: Microsoft SQL
  Server, MySQL, PostgreSQL, Oracle. Different DBMSs have nuances but all use SQL.
- SQL is an ISO-ratified standard, so learning it lets you approach most databases with
  relative ease; DBMS-specific differences are minor and Googleable.
- CRUD = Create, Read, Update, Delete — the four things you do to data.
- Two database types: relational (RDBMS, most popular) and non-relational (NoSQL,
  unstructured data). The tutorial focuses on relational.
- Relational databases relate tables to each other — e.g. an orders table referencing a
  coffee ID and a customer ID that point back to the coffee and customer tables.
- Demo environment: MySQL installed on Ubuntu desktop inside a VirtualBox VM; MySQL is
  free and installable anywhere, including Windows.
- Install/verify commands: `sudo apt update`, `sudo apt install mysql-server -y`,
  `sudo systemctl status mysql` (look for active/running), connect with `sudo mysql`.
- Connecting with `mysql` and no parameters works because it connects to localhost and
  no password is set (fine for local practice); production connections specify username,
  remote server, port, and `-p` for password.
- Every MySQL statement must end with a semicolon, or the prompt waits for more input.
- Core commands demonstrated: `SHOW DATABASES;`, `CREATE DATABASE nc_coffee;`,
  `USE nc_coffee;`, `SHOW TABLES;`.
- `CREATE TABLE` defines columns, each with a name and a data type — `INT` (integer),
  `VARCHAR(255)` (variable-length string, e.g. up to 255 characters), `BOOLEAN`
  (true/false). Commas separate column definitions; the last column gets no trailing
  comma; the statement is wrapped in parentheses and ended with a semicolon.
- `DESCRIBE coffee_table;` shows a table's fields and types; defining columns/types is
  defining the schema (how the database is arranged/organized).
- `INSERT INTO <table> VALUES (...)` adds a row; values must be given in column order;
  MySQL reports "1 row affected."
- `SELECT * FROM <table>;` pulls all columns from a table; `*` means everything. You can
  select specific columns instead, e.g. `SELECT name FROM coffee_table;`.
- `WHERE` filters rows, e.g. `WHERE origin = 'earth'`; combine conditions with `OR`
  (`WHERE origin = 'earth' OR origin = 'asgard'`), use comparisons like `WHERE age < 30`,
  and negate with `NOT` (`WHERE NOT origin = 'earth'`).
- Queries can be run in a terminal, via a GUI application, or programmatically (e.g. from
  Python).
- `DELETE FROM <table> WHERE ...` removes records (careful — it can delete many at once);
  example `DELETE FROM Avengers WHERE first_name = 'Jeff';`.
- `UPDATE <table> SET <column> = <value> WHERE ...` edits existing records; you can set a
  value to `NULL` (nothing); scope the change with `WHERE`.
- `ORDER BY <column> ASC` sorts results ascending (youngest to oldest by age); `DESC`
  sorts descending.
- `ALTER TABLE <table> ADD <column> <type>;` adds a new column to an already-created
  table (demo: adding a `beard` BOOLEAN column). Boolean shows as 1 (true) / 0 (false).
- Deliberately not covered (left as next steps to pursue): building the orders table,
  defining primary keys and foreign keys, joins, and views — which unlock "the full power
  of relational databases."

## Notable verbatim quotes (signature hook)

> "You need to learn SQL probably right now, especially if you want this job or this
> job, or this job — pretty much any job in IT."

> "So in this video, I'm going to teach you SQL, not too much like a Goldilocks amount of
> SQL, just enough to make you dangerous, but not too dangerous. I don't want you
> dropping elbows on some poor unsuspecting tables."

> "It's the love language of our databases. You know, the massive Excel spreadsheets that
> run the world."

> "So get your coffee ready. Mine is right here — and let's learn some SQL."

> "Create things, read things, update things, delete things. CRUD. You've heard of CRUD,
> right? Well, you just did."

> "If you just did this — clap, pat yourself on the back — that's a big deal. You created
> a database, you created a table inside the database, and you added some data to it.
> Simple, but killer."

> "I hope in this video I gave you enough to make you feel semi-confident, like 'I know
> what a database is, I created one, I can select things,' but also I want to give you
> that hunger, that drive to learn just a bit more."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT). (One brief cameo line
from Cameron confirming he used SQL as an AWS cloud engineer; not persona training
material.)

<!-- ★ L3-candidate: 'you need to learn X RIGHT NOW' format (SQL) -->
