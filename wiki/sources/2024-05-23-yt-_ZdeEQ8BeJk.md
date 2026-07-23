---
type: youtube-short
channel: "@NetworkChuck"
source_date: 2024-05-23
url: https://www.youtube.com/watch?v=_ZdeEQ8BeJk
ingested: 2026-07-22
tier: L2
domains: [networking]
---

# What is SNMP?

## Summary

A quick primer on SNMP (Simple Network Management Protocol), framed as a "secret
protocol" that lets you see and monitor everything about a device — CPU and memory
utilization, hard drive space, and so on. Chuck notes it typically runs on UDP port 161
and that many devices (network storage, printers) ship with SNMP enabled by default.
He demos a Linux setup: update repos, install `snmpd` and `snmp`, then use `snmpwalk`
to pull OIDs such as system uptime and the number of running processes. He closes by
noting the real power comes when IT monitoring systems poll devices remotely to verify
health and alert on issues, teasing a full home-network video.

## Key points

- (2024-05-23) SNMP = Simple Network Management Protocol; typically operates on UDP
  port 161.
- (2024-05-23) You poll a device to read its metrics (CPU, memory, disk, uptime,
  process count, etc.).
- (2024-05-23) Many devices have SNMP enabled by default, including network storage
  devices and printers.
- (2024-05-23) Linux setup: update repos, `sudo apt install snmpd snmp`.
- (2024-05-23) Use the `snmpwalk` command to pull an OID (demoed for system uptime and
  running processes).
- (2024-05-23) SNMP becomes most powerful when IT monitoring systems poll remotely to
  confirm health and alert on issues.

## Notable verbatim quotes

> "It's called SNMP or the Simple Network Management Protocol. It typically operates on
> UDP port 161. And all you have to do is pull a device and you can see all its goodies."

> "what's crazy is many devices already have SNMP set up by default. Things like network
> storage devices and even printers."

## Guest attribution

Solo Chuck.
