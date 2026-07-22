---
type: youtube-video
source_date: 2023-09-14
url: https://www.youtube.com/watch?v=qHe4mlhuNt4
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, cloud-devops]
tags: [mysql, database-security, sql-injection, ethical-hacking, defense, lab]
---

# Hacking the world's most popular database

## Summary

A two-part tutorial that first walks the viewer through building a personal Oracle
Database 23c Free instance, then demonstrates how an ethical hacker would attack it in
a safe lab. (Despite the title/task framing around "MySQL," the actual subject of this
video is **Oracle SQL** / Oracle Database 23c — the sponsored successor to Chuck's
earlier MySQL "first databases" video.) Chuck opens with two explicit ethics
disclaimers: hack only with permission, and the database is only hackable because he
deliberately configured it insecurely — Oracle itself is not inherently insecure.

The build half deploys Oracle Database 23c Free as a **Docker container** (image pulled
from the Oracle Container Registry, listener on port 1521, SYS password set via `-e` to
the deliberately weak `password`). Chuck then teaches Oracle's multi-tenant
architecture — the root **CDB** (container database) versus **PDBs** (pluggable
databases) that behave like VMs with their own users, schemas, table spaces and data
files — by creating a PDB called "the matrix," a user "Neo," a table `Red Pill DB`, and
granting Neo `create session`, `create table` and `unlimited tablespace`. He also shows
the new 23c **JSON Relational Duality** feature, where a duality view lets the same data
be read/written as both relational rows and pure JSON documents, with changes syncing
back to the underlying tables.

The hacking half uses **ODAT (Oracle Database Attacking Tool)**, also run as a Docker
container, to enumerate and break into the database over the Docker bridge network:
confirm the TNS listener is alive (`tnscmd --ping`), brute-force the **SID** with the
`sidguesser` module, then brute-force credentials with the `passwordguesser` module.
Chuck stresses that he "cheated" — he seeded the wordlists with the known SID (`free`)
and the known SYS credentials — because with 23c's hardening those values would
otherwise be hard to find, and privilege-escalation modules likely fail against 23c.
Finding a **SYS / system-admin** login is framed as the jackpot for the attacker and
the worst case for the company. The implicit defensive lesson: strong/non-default
credentials, non-default SIDs, and keeping to a current, hardened version (23c) are what
make these attacks fail.

## Key claims (paraphrase unless quoted)

**Concept / architecture**
- Oracle SQL is used by large enterprises (he names Netflix, LinkedIn, Cisco, Intel) and is worth learning whether you want to work for or hack those companies. (2023-09-14)
- Oracle Database 23c ("23c Free") was released free for developers/anybody and can be run trivially as a Docker container; the image is ~9 GB and pulled from the Oracle Container Registry. (2023-09-14)
- Oracle uses a multi-tenant model: a root container database (CDB) hosts pluggable databases (PDBs) that act like virtual machines with their own users, schemas, table spaces and data files, and can be unplugged and moved to another root container. (2023-09-14)
- In Oracle, databases are exposed as **schemas tied to a user** — creating a user automatically creates a same-named schema that owns that user's tables/views/procedures — which differs from MySQL's `show databases`/`show tables`. (2023-09-14)
- 23c's **JSON Relational Duality** lets the same data be treated interchangeably as relational rows and as JSON documents; a duality view auto-reflects underlying table changes, and inserting a JSON document into the view updates the underlying tables — blurring the line between SQL and NoSQL. (2023-09-14)
- SQL*Plus is Oracle's command-line client; connecting requires username/password, host, port (default **1521**), and for admin access the `as sysdba` role. (2023-09-14)

**Attack (ethical-hacking, lab)**
- To attack a suspected Oracle target, first locate a server with a **TNS listener** (usually port 1521), then find its **SID** (session identifier), which a PDB shares with its root container. (2023-09-14)
- **ODAT** enumerates and attacks Oracle databases; its `tnscmd`, `sidguesser` and `passwordguesser` modules respectively confirm the listener, brute-force the SID, and brute-force credentials (analogous to Hydra / John the Ripper). (2023-09-14)
- Finding a SYS / system-admin credential is effectively game over — the attacker can log in via SQL*Plus and do anything; privilege-escalation modules exist for weaker accounts but likely won't work against a hardened 23c. (2023-09-14)

**Defense**
- The database was only hackable because it was intentionally misconfigured; a current, hardened version (23c) is "super secure" and resists the escalation attacks. (2023-09-14)
- The attack only succeeded because the default/weak SYS password (`password`) and the SID (`free`) were essentially handed to the tool — implying strong non-default credentials and non-default SIDs are the defense. (2023-09-14)

**Ethics / lab framing**
- Never hack anyone without explicit permission; everything shown is done in a lab the presenter deliberately made vulnerable. (2023-09-14)
- Docker makes it trivial to stand up a self-contained hacking lab (target container + attacker container on the same bridge network) for safe practice. (2023-09-14)

## Notable verbatim quotes

> "I'm showing you real stuff, real hacking things. Don't hack anyone without permission, explicit permission."

> "The Oracle database will only be hackable because we're making it hackable. ... The database itself is not inherently insecure."

> "We just created a little hacking environment, right? That's so neat."

> "You see that it found valid credentials, sis and password. ... We know that is a system admin. That's the best thing you can find as a hacker. It's the worst thing for you as a company."

> "The only reason we were able to hack this is because we basically told the hacker the password and the ssid. Otherwise they would be kind of hard to find."

> "Have you hacked the YouTube algorithm today? ... You got to hack YouTube today ethically, of course."

> "I hope you have your coffee ready because Oracle sql, it's different compared to MySQL."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
