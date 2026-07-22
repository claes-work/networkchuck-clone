---
type: youtube-video
source_date: 2022-02-09
url: https://www.youtube.com/watch?v=HSRghjwTTOQ
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [linux-terminal, cybersecurity]
tags: [linux-for-hackers, curl, wget, web, cli, ep-8]
---

# 2 cool (web) things to do in Linux // Linux for Hackers // EP 8

## Summary

Episode 8 of NetworkChuck's free "Linux for Hackers" series covers two web-oriented
skills from the Linux command line. First, spinning up a web server / website with a
single command using several different tools (Python, PHP, Node/npx, Apache), and
understanding why that is useful (a quick, ad-hoc way to transfer files off a Linux box
when the usual methods — SSH, FTP, Netcat — aren't available). Second, "talking to"
websites entirely from the CLI instead of a browser, using `curl` and `wget` to fetch
pages, download files, save output, and inspect HTTP request and response headers.

The lesson is framed for aspiring hackers and IT people: web servers are an essential
part of technical life, and the command line is "our love language" for interacting with
them. Chuck teaches the concept of HTTP headers by analogy to a physical letter
(envelope = headers, contents = the body/message) and introduces request methods (GET
vs POST/PUT/UPDATE), the loopback address, and common status codes (200 OK, 404 Not
Found). The video is sponsored by Hack The Box Academy, whose free Linux Fundamentals
lab provides the in-browser Linux environment used throughout.

## Key claims (dated — the tools/commands)

All from 2022-02-09:

- `python -m http.server` spins up a web server in the current directory with one
  command; it defaults to port 8000 (a non-standard port, versus HTTP's standard port 80
  or HTTPS/SSL's 443). Access it in a browser at `localhost:8000`.
- To use a different port, append it: e.g. `python -m http.server 7600` serves on port
  7600.
- The Python server serves whatever directory you launch it from. With no `index.html`
  present, it shows a browsable directory listing of files; with an `index.html`, it
  serves that page instead.
- Serving a directory this way is another means of transferring files off a Linux box —
  useful when SSH, FTP, or Netcat aren't available; you browse the files like a website.
- Create a test page: `mkdir website`, `cd website`, `nano index.html`, write HTML, save
  in nano with `Ctrl+X` → `Y` → `Enter`.
- PHP can serve a site too: `php -S 127.0.0.1:8085` (`-S` for the built-in server).
- `127.0.0.1` is the loopback address — a special IP that always refers back to your own
  machine's network interface card (NIC); `localhost` is effectively the DNS name for
  `127.0.0.1` ("there's no place like 127.0.0.1").
- Node's package tooling can serve a site: `npx http-server -p 8086` (`-p` sets the
  port).
- Apache is a very popular, widely deployed web server and is often already installed
  (including on the Hack The Box free lab). Start it with `sudo systemctl start apache2`.
- Apache defaults to port 80; if port 80 is already in use (as it was in the lab), edit
  `/etc/apache2/ports.conf`, change the `Listen 80` line to `Listen 8080`, save, and
  restart with `systemctl start apache2`. It then serves the Apache default page at
  `localhost:8080`.
- A web server "listens" on its configured port only — a request on the wrong port won't
  be heard.
- `curl` (client URL) is used constantly in IT/hacking, comes pre-installed almost
  everywhere, and supports many protocols (HTTP, HTTPS, FTP, FTPS, SFTP). `curl
  localhost:7600` fetches and prints the page's source (HTML) to the terminal.
- `curl -o cool-website localhost:8080` saves the fetched output to a file (`-o` =
  output filename); view it with `cat cool-website`.
- `curl -I localhost:8080` (capital I) prints just the response header — server info,
  content type, content length, status code, etc.
- `curl -v localhost:8080` (verbose) shows the full conversation including the request
  header at the top; in curl's output, one arrow direction marks request headers and the
  other marks response headers.
- HTTP headers are like a letter's envelope: metadata about who is sending and what kind
  of data, separate from the body/contents.
- Default browser/client requests are GET requests ("get me that webpage"); other
  methods include POST (send/add data), PUT, and UPDATE — useful to know for hacking.
- Status codes: `200 OK` is the healthy response you want; `404 Not Found` means the
  requested resource doesn't exist on that server.
- `wget localhost:7600` does essentially the same download function as curl for one use
  case — it downloaded `index.html` and reported the HTTP headers (request sent, awaiting
  response, `200 OK`).

## Notable verbatim quotes

> "First, we're gonna spin up a website in [Linux] with one command. We're gonna hit
> enter — website, web server running right here on your [Linux] box."

> "Instead of using a browser, we use our command line to browse that website."

> "curl stands for client URL. And you really can't put this command in a box because
> it's used for so many stinking things."

> "You're essentially downloading the code, the source code of that website when you run
> curl."

> "Think about it like a letter. ... Inside [the] letter, you have the contents, the
> actual message you wanna give somebody, and on the outside, on the envelope, you have
> the mailing details ... that stuff on the outside is what we're talking about when we
> talk about the headers."

> "200, OK is the best message in the world when you're dealing with websites. That
> means, yes, it's good. It's here. Here you go, friend."

> "What's the code that we never want to see? ... 4-0-4, not found. So if you're
> requesting a website or a web address that doesn't exist on that server, it's gonna go,
> dude, are you lost? It ain't here."

> "We're gonna use our favorite place in the world to talk to our websites. We're gonna
> use our command line."

> "It's always just one Google search away."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: Linux for Hackers EP8 — web from the CLI (curl/wget) -->
