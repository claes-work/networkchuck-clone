---
type: youtube-video
source_date: 2023-11-01
url: https://www.youtube.com/watch?v=CurcakgurRE
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, homelab-selfhosting]
tags: [tor, onion-service, dark-web, self-hosting, privacy]
---

# Put your website on the Dark Web

## Summary

A hands-on tutorial for hosting your own website as a Tor `.onion` hidden service.
Chuck frames it as fun, educational, and slightly rebellious, and splits it into two
levels. **"Dark Web Light"** uses [OnionShare](https://onionshare.org) (GUI or CLI) so
that *anyone* on Windows, macOS, or Linux can, in a few clicks, host an ephemeral
website, run an anonymous chat session, and send/receive files over Tor — with no port
forwarding and no public IP. **"Dark Web Supreme"** is the advanced path: on a Linux
box (he recommends Ubuntu, cloud or local), stand up an [[../entities/nginx]] web
server serving a portfolio/resume site, install Tor from the Tor Project's Debian repo,
uncomment the hidden-service lines in `torrc`, and expose the site on the dark web. He
then generates a **vanity `.onion` (v3) address** — prepending a custom keyword like
"chuck" — by building the `mkp224o` tool from source and brute-forcing addresses with
CPU threads.

Throughout, Chuck explains *how Tor protects you*: every connection to a hidden service
is routed through six onion relays that meet at a rendezvous point, each adding a layer
of encryption and hiding the IP of the visitor, the host, and the site. He uses a
Facebook-Marketplace analogy (meet at a neutral spot, nobody learns where the other
lives — except through "six Walmart parking lots"). The ethics framing is explicit: he
stresses they are only *hosting* benign content, not accessing anything nefarious, and
he highlights the legitimate value for people in censored or surveilled countries who
need to communicate safely. The video is sponsored by Bitdefender (a phishing-website
quiz segment).

## Key claims (dated 2023-11-01)

### Concept — how Tor hidden services work
- Every connection to a dark-web (hidden-service) site is routed through six onion
  relays that meet in the middle at a "rendezvous point." (paraphrase)
- Each relay/onion adds a layer of encryption and hides the IP address of the visitor,
  the host, and the website itself. (paraphrase)
- Hosting on the dark web does not require a public IP, opening router ports, or port
  forwarding — it "just works" because Tor handles reachability. (paraphrase)
- The dark web feels slower, which Chuck frames as reassuring — it signals traffic is
  passing through multiple secure relays that obscure identity and encrypt data.
  (paraphrase)
- OnionShare sites are ephemeral by default: the site exists only while the sharing
  window/process is running and disappears when you stop it. (paraphrase)
- A non-public share generates both a `.onion` address *and* a secret key required to
  open it; making it public drops the key and leaves an address open to anyone.
  (paraphrase)

### Setup — Dark Web Light (OnionShare)
- OnionShare runs on Windows, macOS, Linux, iOS, and Android, and offers both a GUI and
  a CLI; the CLI feels more natural for this kind of work. (paraphrase)
- On Windows it installs like any other app; on Ubuntu, install via Snap:
  `sudo apt install snapd` then `sudo snap install onionshare`. (paraphrase)
- One OnionShare tool can host a website, run an anonymous chat, and send/receive files.
  (paraphrase)
- CLI example for an anonymous public chat room: `onionshare-cli chat --public`.
  (paraphrase)

### Setup — Dark Web Supreme (Nginx + Tor hidden service)
- Requires only a Linux machine of any kind (cloud, VM, Raspberry Pi, local); Ubuntu
  recommended, any size works. (paraphrase)
- Install and use Nginx as the web server: `apt update` then `apt install nginx`;
  verify by browsing to the host IP or `localhost` on port 80. (paraphrase)
- Deploy the site by copying the portfolio folder into the web root:
  `cp -r portfolio /var/www/`, then edit the default Nginx site config to point `root`
  at the portfolio folder and `systemctl restart nginx`. (paraphrase)
- Install Tor from the Tor Project repo: find your Debian version with
  `cat /etc/debian_version` (his is "bookworm"), add the Tor repo lines to
  `/etc/apt/sources.list.d/tor.list` (replacing the distribution placeholder with your
  version), add the GPG key via `wget`, `apt update`, then
  `apt install tor deb.torproject.org-keyring`. (paraphrase)
- Tor does nothing until configured — unlike Nginx it does not auto-start a service; you
  activate a hidden service by uncommenting the HiddenServiceDir/HiddenServicePort lines
  in `/etc/tor/torrc` (default port 80, match your web server's port) and restarting
  Tor. (paraphrase)
- After restarting Tor, the generated `.onion` hostname and public/private keys appear
  under `/var/lib/tor/hidden_service/`; read it with `cat hostname`. (paraphrase)

### Setup — vanity .onion (v3) address
- A custom "vanity" v3 onion address is generated with the tool `mkp224o`, built from
  source: clone the repo, then `./autogen.sh`, `./configure`, `make`. (paraphrase)
- The tool rapidly generates random onion addresses over and over, using CPU threads, to
  find one that starts with your chosen keyword. (paraphrase)
- The more characters you prepend, the exponentially longer it takes — "chuck" is quick,
  but "networkchuck" he had not yet managed to generate. (paraphrase)
- Example invocation: `./mkp224o chuck -d -n 1 -d ~/supreme-onion-key -t 4` (keyword,
  verbose, one result, output folder, four threads). (paraphrase)
- To apply the vanity address, copy the generated hostname/keys into
  `/var/lib/tor/hidden_service/` (overwriting the existing ones) and restart Tor.
  (paraphrase)

### Ethics / framing
- This is legal, benign, and safe — they are only hosting content, not accessing
  anything nefarious, and hosting is "relatively safe." (paraphrase)
- Chuck presents a legitimate use case: people in censored or surveilled countries who
  need to communicate securely without being spied on or getting in trouble.
  (paraphrase)
- He pitches hosting a resume/portfolio on the dark web as a resume-booster — it signals
  curiosity and knowledge of web hosting and the Tor network to prospective employers.
  (paraphrase)

## Notable verbatim quotes

> "In five minutes, you're going to have your very own dark web website."

> "Every single time someone connects to your dark web website, this communication is
> going through six onion relays and they meet in the middle at the Rendezvous point."

> "Each of these onions is adding a layer of encryption and hiding the IP address of
> you, your website and the person visiting your website."

> "It's kind of like when you buy something off Facebook marketplace, you don't tell 'em
> to come to your house, you meet them somewhere neutral... except there's like six
> different Walmart parking lots you have to go through."

> "But also thinking about people who are in countries that are being censored or
> they're being watched and they want to communicate securely and safely with someone...
> This kind of stuff protects people like that. It's so cool."

> "I honestly like that about Tor. You install it, but it's not going to do anything...
> it's dead until you make it alive."

> "Nano is the best editor ever in Linux. Fight me. It just is."

> "That's going to look cool on your resume. I'll catch you next time."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
