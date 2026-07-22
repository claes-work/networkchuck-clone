---
type: youtube-video
source_date: 2022-08-29
url: https://www.youtube.com/watch?v=5aYpkLfkgRE
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cloud-devops, certifications-career]
tags: [python, flask, web-dev, tutorial, beginners]
---

# build a meme Python website (Flask Tutorial for Beginners)

## Summary

A beginner-friendly tutorial in which Chuck Keith teaches Flask, the Python web
application framework, by building a "meme website" that pulls a fresh random meme
from Reddit every 30 seconds. He positions Flask as an accessible bridge from Python
scripting into web development: because Flask is written in Python and "feels like"
Python, someone who already knows a little Python can produce a working website with
very little new to learn. He explicitly frames the tutorial as beginner-inclusive —
even people brand new to Python can keep up.

The build walks through the environment setup (a Linux machine, ideally a cheap Linode
cloud VM — the video's sponsor), installing `pip3`, Flask, and the `requests` library,
then writing a minimal `flask_test.py` to demonstrate the core concepts (import Flask,
create the `app` object, decorate a route, define a view function, run the app). He
then extends this into the actual meme site by adding an external API call (via
`requests`) and HTML templating (via `render_template`). Chuck goes "high level on
purpose," providing copy-paste scripts rather than teaching HTML, and frames the real
takeaway as: take a Python project and quickly turn it into a webpage. He cites his own
real-world use — a dashboard tracking his daughters' allowance cryptocurrency ("key")
balances via the Solscan API — as the motivating example.

## Key claims (dated — the Flask concepts)

All dated 2022-08-29 (paraphrase unless quoted):

- Flask is a web application framework — "basically just a tool we use to build a
  website." It is written in Python and, as a result, feels like Python.
- Flask is called a **micro framework** because it is lightweight and designed to keep
  things simple; you use Python itself to populate data in Flask.
- The same foundational Flask skills used in this "dumb" meme site are used at Fortune
  500 companies (he notes Netflix uses Flask, though not configured the simple way shown
  here).
- **Setup / prerequisites:** a Linux computer or server (he uses a Linode Ubuntu cloud
  VM), accessed over SSH.
- **Installing the tooling:** `sudo apt update`, then `apt install python3-pip -y` to
  get pip; `pip3 install flask` to install Flask; `pip3 install requests` to install the
  `requests` library, which is used to interact with APIs (this is how the memes are
  pulled from Reddit).
- **Minimal app structure** (`flask_test.py`): import with `from flask import Flask`
  (case matters); create the app object with `app = Flask(__name__)`. The special
  `__name__` variable tells Flask everything it needs is in the current directory.
- **Routes / decorators:** `@app.route("/")` is a Python decorator that adds
  functionality to the function defined right below it. A "route" is the location/place
  to go; `"/"` (the root) means the request path with nothing after the base URL.
  (Note: the caption garbles the forward slash as "back slash" — the route argument is
  `"/"`.)
- **View function:** below the decorator, define a function (e.g. `def index():`) whose
  return value is what the site serves at that route. A function is "just a collection
  of a few lines of code that we can call and use later." Indentation (four spaces) is
  important in Python.
- **Running the app:** `app.run(host="0.0.0.0", port=80)`. Host `0.0.0.0` makes it run
  on all IP addresses; port 80 works most of the time, with `5001` as a fallback if
  there is a conflict.
- Running the dev server produces a warning that it is for development only — that is
  fine for a hobby/meme site; production setups differ ("a video for another time").
- **Templating:** import `render_template` to reference and use an external HTML file;
  the meme site's script also imports `requests` and `json`. Flask is finicky about
  where it looks for HTML — it expects templates inside a folder named `templates`, which
  you must create (`mkdir templates`).
- **Passing data to the template:** the view function returns `render_template(...)`
  passing variables to the HTML file; variables are referenced in the HTML using double
  curly braces `{{ }}` — that is the relationship between the Python/Flask script and its
  HTML.
- **Live troubleshooting lesson:** he hit a `NameError: name 'app' is not defined`
  because he forgot to define `app = Flask(__name__)` at the top of the meme script — a
  reminder that the app object must be defined before it is decorated.
- Real-world application: he uses Python + the Solscan API + Flask to build a dashboard
  tracking his daughters' "key" cryptocurrency allowance balances without manually
  checking wallets.
- Persistence (making the site survive a reboot) is not covered in the video but is in
  the written lab walkthrough/write-up linked below the video.

## Notable verbatim quotes

> "Flask is a web application framework, basically just a tool we use to build a
> website, but what's cool about flask is that it's actually written in Python. And as a
> result, it feels like Python, which we know feels awesome."

> "It's referred to as a micro framework because it's designed to keep things simple.
> And I love simple."

> "Just know the foundational skills you're learning to do that are used in fortune 500
> companies."

> "And when you hear the word route, I want you to think, okay, the place to go, where to
> go the location."

> "I love flask because I can quickly take a project I'm working on in Python and make a
> webpage out of it."

> "I went high level on purpose because it would take forever to make this video... but I
> hope I gave you enough code and just enough to like bread crumbs, to follow along that
> you could build on the knowledge you already have."

> "Python's so fun and I love to make it like available to people through a website."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
