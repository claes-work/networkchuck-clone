---
type: youtube-video
source_date: 2019-10-27
url: https://www.youtube.com/watch?v=B_krqlk_cXo
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [homelab-selfhosting, cloud-devops]
tags: [raspberry-pi, ifttt, alexa, rest-api, automation, maker, halloween]
---

# Raspberry Pi Halloween Automation - IFTTT, Alexa, REST API, Network Automation

## Summary

A hands-on maker/automation build in which Chuck automates Halloween props with a Raspberry Pi, an 8-channel relay, and a Python/Flask REST API. Each prop is a store-bought animatronic with a "try me" button; Chuck strips the button and wires the trigger's two "try me" wires into a relay channel, so closing the relay activates the prop just as pressing the button would. A Flask app (`Halloween.py`) declares GPIO pins per monster, serves a simple web interface (an iPad/phone-friendly page of "activate" buttons), and exposes a REST API where a URL path names the monster to fire (e.g. `/pumpkin`, `/MonsterMash` to fire everything at once).

Because the API is just HTTP GET requests, Chuck chains it to broader automation: **IFTTT** webhooks trigger the props on external events (a new YouTube upload from a subscription, an Alexa spoken phrase, or a tweeted hashtag), and **SolarWinds Engineer's Toolset** network monitoring fires the props on a network alert (e.g. loss of ping to 8.8.8.8 or an interface going down). The whole build is framed as under ~$60 and as a way to practice Linux, Python, network automation, and REST APIs on a fun project. Chuck credits an article by "Marcello Ravi" (name uncertain from captions) as the basis for the code. Explicitly cross-domain: the payoff use case is a scary network-outage alert for the IT department / cubicle.

## Key claims (dated — build steps + concepts)

- **[2019-10-27]** Bill of materials, ~$60 total: a Raspberry Pi 3 B+ (earlier/Pi 4 fine, but pinout differs below Pi 3); an 8-channel relay (~$12, controls up to 8 devices); a Halloween prop with a "try me" button (or a step-pad trigger for larger props); and female-to-female DuPont jumper wires. (paraphrase)
- **[2019-10-27]** Prereqs not covered in the video (links provided): flash Raspbian to a microSD, assign a static IP, and enable SSH remote access before starting. (paraphrase)
- **[2019-10-27]** Wiring the relay to the Pi (Pi 3 pinout; a diagram is on Chuck's GitHub): power from Pi **pin 2 (5V)** to the relay **VCC**; **pin 6** as ground to the relay ground; a second (paranoid, admittedly unnecessary) ground from **pin 34** to the relay's other ground; and four control lines from the relay's IN pins to Pi GPIO **pins 40, 38, 36, 32**. Power the relay off while wiring to avoid frying anything. (paraphrase)
- **[2019-10-27]** How a prop's trigger works: the "try me" button simply closes two wires; making those two wires touch activates the prop. Chuck strips out the button and screws the two trigger wires into a relay channel's A and B screw terminals (topmost two), so "activating" the relay connects the wires and fires the prop. (paraphrase)
- **[2019-10-27]** Software: install Flask with `sudo apt install python3-flask` (Chuck's full-image Raspbian already had it). Flask is described as a "micro framework" that stands up an API and web server without the bloat of larger frameworks. (paraphrase)
- **[2019-10-27]** Project layout (must match exactly for the script): a `Halloween` directory containing `templates/` (holds `index.html`) and `static/` (holds `style.css`), plus `Halloween.py`; all three files are copied from Chuck's GitHub. The web page uses Jinja templates. (paraphrase)
- **[2019-10-27]** GPIO test from the Python 3 REPL (run as `sudo python3`): `import RPi.GPIO as GPIO`; `GPIO.setmode(GPIO.BOARD)`; `GPIO.setup(32, GPIO.OUT)`; then `GPIO.output(32, GPIO.HIGH)` turns the relay/prop **off** and `GPIO.output(32, GPIO.LOW)` turns it **on** (i.e. LOW closes the circuit — active-low relay). (paraphrase)
- **[2019-10-27]** Run the app with `sudo python Halloween.py`. On launch all pins go on; the result is both a website (open the Pi's IP in a browser, click "activate" per monster) and a REST API (append the monster name to the URL, e.g. `http://<pi-ip>/pumpkin`). `/MonsterMash` activates every prop at once. (paraphrase)
- **[2019-10-27]** In Chuck's script the props map to relays: zombie = relay 1 (pin 40), stone wolf = relay 2 (pin 38), werewolf = relay 3 (pin 36), pumpkin = relay 4 (pin 32). (paraphrase)
- **[2019-10-27]** Editing the script to add a monster (e.g. "vampire"): declare `vampire = 35` at the top with the other pin variables, add it to the `MonsterMash` Python list, and add an `if` branch in the Flask `@app.route` handler that sets `relay = vampire` when the device name is `vampire`; the handler then drives the pin LOW to turn on, sleeps ~5 seconds, then HIGH to turn off. To add it to the website, copy one of the `<h1>` button entries in `index.html` and change its API call to `vampire`. (paraphrase)
- **[2019-10-27]** IFTTT integration: build an applet from scratch — trigger (e.g. YouTube "new public video from subscriptions", an Alexa "say a specific phrase", or a tweeted hashtag) → action = **Webhooks → Make a web request** (method GET, URL is the Pi with the monster path). (paraphrase)
- **[2019-10-27]** Networking caveat for IFTTT: IFTTT lives on the public internet and cannot reach the Pi's private IP, so you must configure **port forwarding on port 80** on your router to the Pi's private IP, then use your **public IP** (found via whatismyip.com / "what is my IP") in the webhook URL. Port forwarding is called out as its own whole topic/video. (paraphrase)
- **[2019-10-27]** Alexa integration is done through IFTTT (Alexa "say a specific phrase" trigger → webhook), e.g. saying "trigger Monster Mash." The Flask command line shows a live log of requested monsters. (paraphrase)
- **[2019-10-27]** Network-monitoring integration: SolarWinds Engineer's Toolset (free "standard toolset" and a paid premium with free trial) — use the Network Performance Monitor to watch a Cisco router via SNMP and a ping to 8.8.8.8; configure a new alert (property = node status, trigger = down, reset = up) whose action is a GET to the Pi's `/MonsterMash` URL, so a network outage physically fires the Halloween props. Chuck demos it by shutting his LAN port. (paraphrase)
- **[2019-10-27]** Framing / positioning: a Raspberry Pi driving a relay is pitched as more technologically sophisticated than ~99% of commercial haunted houses; the same rig is reusable for Christmas and other holidays, and as a permanent cubicle network-outage alerter. (paraphrase)
- **[2019-10-27]** Growth hack: Chuck left a live IFTTT applet running so that tweeting `#NetworkChuckHalloweenSpecial` (and `#scareNetworkChuck`) fires his real props at home — audience-driven physical automation. (paraphrase)

## Notable verbatim quotes

> "today we're talking about raspberry pi automation we're gonna automate our Halloween props and not just that we're doing it with the REST API so we connect it to everything"

> "all you need to do is make sure these two wires touch and it activates the prop and that's all this relay is doing is connecting those two wires and using Raspberry Pi and Python and flask will make that happen"

> "I'm not an expert electrician or maker in any of that I just try to make stuff work"

> "I'm not an expert at any programming or any of this electronic stuff I just stand on the shoulders of giants who do this before me and I learned so much and I'm trying to share what I've learned with you"

> "it's a micro framework that doesn't require all the bloat that you would need to set up an API and a webserver and all this that we're doing you just do it so quickly and awesomely"

> "so you can literally call it from anywhere especially if you know how to like program right like if you know network automation or some Python you can integrate that into whatever you want"

> "I'll be the first one to admit I don't know what's happening in this app dot route stuff it's flask stuff but I do know that down here we can add some more if statements to include your monster"

> "I set out with this video my goal was to be able to integrate what I work with everyday as your network monitoring learning Python learning Linux I wanted to integrate that into something I loved also which is Halloween"

> "a Raspberry Pi running a relay is more advanced than probably 99% of the haunted houses you see out there so you can run a more technologically sophisticated haunted house on your front porch this year"

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: Raspberry-Pi maker/automation project format -->
