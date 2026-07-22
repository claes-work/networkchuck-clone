---
type: youtube-video
source_date: 2020-08-27
url: https://www.youtube.com/watch?v=oIRkXulqJA4
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [networking, certifications-career]
tags: [free-ccna, osi-model, application-layer, transport-layer, ep-5]
---

# how the OSI model works on YouTube (Application and Transport Layers) // FREE CCNA // EP 5

## Summary

Episode 5 of Chuck Keith's free CCNA course, sponsored by Boson Software. It covers the upper layers of the OSI model — application, presentation, session, and transport — by asking what actually happens on the network when Johnny (the recurring student character) opens a web browser and watches a YouTube video. Building on prior episodes that covered the lower three layers (physical, data link, network) via a story about ordering coffee from networkchuck.coffee, this episode "pops the hood" on the upper layers.

Chuck walks the application layer as the interface/gateway that a program (web browser, online game) uses to reach the network; the presentation layer, which handles data format (file types like HTML, XML, JPG) and encryption (e.g., SSL); and the session layer, which opens, maintains, and tears down the conversation between the browser and the YouTube server. He notes that in the TCP/IP model these three OSI layers collapse into a single application layer (no separate presentation/session), but the concepts still apply.

The bulk of the episode is the transport layer, "where people who love networking start to pay attention." He contrasts TCP (reliable, connection-oriented, uses the three-way handshake and waits for acknowledgements, "naggy") with UDP (fast, connectionless, doesn't care whether packets arrive). Using a real Wireshark capture, he shows that watching YouTube uses BOTH: TCP for loading the web page/HTML, then a switch to UDP for streaming the video. He explains why real-time media (video, live streams, online gaming) prefers UDP — re-sending a dropped packet is useless once the moment has passed. He then explains ports: the destination port 443 (HTTPS) identifies the service on the server, while the large source port (57095) is an ephemeral, temporary port his browser picks so returning traffic reaches the right application. He covers well-known ports (0–1023), the full range (0–65535), and lists common ones. The episode closes with two Boson-provided practice questions (matching application-layer protocols to TCP/UDP, and the port for TFTP).

## Key claims (dated — the concepts)

_All 2020-08-27, paraphrased from Chuck Keith._

- The OSI upper layers are application, presentation, session, and transport; earlier episodes covered the lower three (network, data link, physical).
- Sending data down the OSI layers is encapsulation (segment → packet → frame); reversing it at the destination is de-encapsulation (frame → packet → segment).
- The **application layer** is the portal/interface a program uses when it needs a network (e.g., web browser, online game); it is the gateway to the presentation and session layers.
- The **presentation layer** makes data presentable, chiefly via data format and encryption. Data formats are analogous to file types (PDF, HTML, XML, JPG) that everyone has agreed to use; SSL (secure socket layer) is a common encryption example done here.
- The **session layer** opens the conversation between the application and the server, ensures authentication, keeps the session logically open despite all the switching/routing happening at lower layers, and tears it down when done. It manages multiple simultaneous sessions (e.g., browser + Spotify). Example protocols: L2TP (layer 2 tunneling protocol, common with VPNs), RTCP, H.245 (video calls), and SOCKS proxies.
- In the **TCP/IP model** (the one actually used), the presentation and session layers do not exist as separate layers — application, presentation, and session collapse into a single application layer — but the underlying concepts remain.
- The **transport layer** decides how to get the data to the other end, analogous to choosing a shipping carrier; instead of a carrier you choose a protocol. The two main protocols are TCP and UDP.
- The core transport question is speed vs. reliability: UDP for fast, TCP for reliable/guaranteed delivery.
- **TCP** (Transmission Control Protocol) is reliable because it is "naggy": it waits for acknowledgement that data was received and re-sends if it doesn't get confirmation. It also establishes a connection first via the **three-way handshake** (SYN → SYN-ACK → ACK), where SYN = synchronization and ACK = acknowledgement. Emphasis on "control."
- **UDP** is fast because it "doesn't care" — connectionless, no handshake, no waiting for verification; it just keeps sending.
- Watching a YouTube video uses **both** TCP and UDP: TCP loads the web page/HTML, then it switches to UDP to stream the video, all while still talking to YouTube.
- Real-time applications (video, live streams, online gaming) prefer UDP because re-transmitting a missed packet is pointless — the moment has passed (a dropped game packet shouldn't rewind you 15 feet).
- **Ports** let one server run multiple services (web/HTTP, FTP, SSH, RDP, gaming) at one IP address; the port number tells the server which service you want.
- Port 443 is the well-known port for HTTPS; you can address a server as `IP:443`. HTTP/HTTPS is used to reach a web server.
- The large number like 57095 is an **ephemeral port** — a temporary source port the browser "pulls out of the air" so return traffic reaches the correct application when many apps are receiving data at once.
- Well-known port ranges and examples: total ports 0–65535; well-known/reserved ports are 0–1023. Named ports: FTP 21, SSH 22, Telnet 23, HTTP 80, TFTP 69 (UDP), and others (SMTP, NTP, DHCP referenced).
- Protocol/transport mappings given in the quiz: DNS uses both TCP and UDP; DHCP uses UDP; FTP uses TCP; HTTP uses TCP; SMTP uses TCP; SNMP uses UDP; TFTP uses UDP (port 69).
- **Wireshark** is the tool used to capture real network traffic to observe this behavior (source/destination IPs, protocol, three-way handshake, ports); YouTube's IP in the capture was 173.194.191.167.

## Notable verbatim quotes

> the transport layer is where people who love networking start to pay attention application layer nah that's for programmers wait did you say transport now you got my attention this is where we operate

> whereas udp it's a little crazy do you want to know why udp is fast because it just doesn't care it doesn't care if you get the message it doesn't care if you get the package it's just going to keep on sending stuff

> tcp stands for transmission control protocol with a strong emphasis on control because it wants to control every bit of that communication

> for real time applications like that watching a video watching a live stream gaming online it doesn't make sense to resend the same thing because once that thing's missed it does no good to get it later

> my web browser pulled this number out of the air it's temporary often referred to as an ephemeral port i love saying that word ephemeral ephemeral say it say it ephemeral say it out loud right now ephemeral

> those ports allow us to run multiple services on one server so one server can be a ton of things it could be rdp server ssh server ftp server web server gaming server

> now i know i say this a lot in pretty much every video but we just scratch the surface there's a lot more to know

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: FREE CCNA EP 5 — OSI application/transport layers -->
