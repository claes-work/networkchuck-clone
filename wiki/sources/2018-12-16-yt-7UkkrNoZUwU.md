---
type: youtube-video
source_date: 2018-12-16
url: https://www.youtube.com/watch?v=7UkkrNoZUwU
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cloud-devops, networking]
tags: [arduino, raspberry-pi, python, devnet, automation, cisco, api]
---

# Using Arduino, Raspberry Pi and Python to Monitor Cisco Router - #DEVNET CCNA

## Summary

Chuck documents a hands-on maker build that bridges the electronics/maker community
with network engineering. Motivated by an Elegoo Arduino starter kit (sent to him,
with two more given away to viewers), he sets out to integrate the Arduino with his
network. The result: a Python script running on his Raspberry Pi ("Malcolm") pulls
live interface statistics from a Cisco CSR 1000V cloud services router via its REST
API and displays them on an LCD screen wired to the Arduino over a serial connection.
He also connects to the Google API to pull and display his YouTube subscriber count
(and a rival's, Eli the Computer Guy). The build took hours ("five hours later… I
nearly lost my mind"), but Chuck frames it as proof that networking can be made fun
again through programmability and physical computing. He closes by previewing future
maker projects (RFID entry system, servo-motor lock, temperature/humidity-triggered
cooling fan for his lab) and encouraging network engineers to explore Python and
network programmability.

## Key claims (dated — the build steps / concept)

- [2018-12-16] Chuck uses a Cisco CSR 1000V (Cloud Services Router) in his lab — a
  router that deploys as a VM, including into AWS; he also runs it as a voice gateway.
  (paraphrase)
- [2018-12-16] The CSR 1000V is free with no licensing required, but has a bandwidth
  cap of roughly 1.5 Mbps — fine for lab use. (paraphrase)
- [2018-12-16] He enables the REST APIs on the CSR 1000V router. (paraphrase)
- [2018-12-16] He writes a Python script that queries the router and grabs interface
  statistics (in/out internet traffic) from the GigabitEthernet 1 interface.
  (paraphrase)
- [2018-12-16] The Python script runs on his Raspberry Pi (nicknamed "Malcolm"), which
  collects the router stats. (paraphrase)
- [2018-12-16] The Raspberry Pi connects to the Arduino via a serial connection; the
  Arduino drives an LCD screen that displays the router's bits-per-second stats.
  (paraphrase)
- [2018-12-16] The build combines the REST API, Python, Arduino, and Raspberry Pi to
  show live router stats on the LCD. (paraphrase)
- [2018-12-16] Arduino programs are written/uploaded using the Arduino interface; the
  board is powered over USB from the computer. (paraphrase)
- [2018-12-16] The Elegoo starter kit includes a walkthrough PDF and components (motor,
  fan, LCD, keypad, RGB LED, sensors, buzzer, RFID sensor/fob, servo motors,
  temperature/humidity sensor); he began with basic LED/RGB blink exercises.
  (paraphrase)
- [2018-12-16] He demonstrates throwing heavy traffic at the router (simulated phone
  calls) so the LCD's bits-per-second reading spikes; the router temporarily stops
  responding because of its bandwidth cap, then resumes. (paraphrase)
- [2018-12-16] He extends the script to connect to the Google API and pull his YouTube
  subscriber count (~54k at the time) for display alongside the router stats.
  (paraphrase)
- [2018-12-16] Planned follow-up maker projects: an RFID/fob key-entry system, a
  servo-motor lock, and a temperature/humidity-sensor-triggered fan to cool his lab
  gear automatically; he also intends to have his kids use the kit to learn
  programming and electronics. (paraphrase)
- [2018-12-16] Future idea: have the setup sound an alarm when a router crosses a
  utilization threshold. (paraphrase)

## Notable verbatim quotes

> whoo wow it took me a bit but using Python Linux my Raspberry Pi and Arduino I
> connected all these things to monitor my router and it was really fun

> I love my Raspberry Pi and… you'll know I affectionately call him Malcolm because it
> used to mean a man-in-the-middle attack and Malcolm in the Middle

> the beautiful thing about that is you can enable the REST APIs on that router which I
> did and then I wrote a Python script that will go out to my router and grab these
> statistics from my gigabit one interface

> using the REST APIs in Python and Arduino and Raspberry Pi I have my stats displayed
> on my LCD screen

> why did I do this to myself… it took me forever and I nearly lost my mind

> if you're getting kind of like tired of learning networking or maybe it's getting a
> little stale for you hey you can make it fresh man you can do stuff like this where it
> just becomes more interesting

> the next thing I want to do is have it like sound an alarm when I reach a threshold
> when one of my routers being overwhelmed

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: early DevNet/network-automation maker build -->
