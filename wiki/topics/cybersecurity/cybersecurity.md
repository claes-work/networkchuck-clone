---
type: hub
domain: cybersecurity
created: 2026-07-14
updated: 2026-07-23
---

# Cybersecurity — hub

Ethical hacking, pentesting, hands-on hacking demos, and security tooling — the "you just hacked X" hook that draws newcomers into security. Chuck's signature security format is a live, physical attack demo (Raspberry Pi + Kali Linux) wrapped in an explicit white-hat ethics frame: learn to hack so you can learn to defend.

## Key ideas & topics

### The hands-on hacking-demo format (Raspberry Pi + Kali Linux)
Chuck's recurring security-teaching pattern is to run a real attack on cheap, tangible hardware — a credit-card-sized Raspberry Pi running Kali Linux (a Linux distro packed with networking-attack tools), remotely accessed over SSH — so the attack feels concrete rather than abstract. He personifies the rig (the Pi is "Malcolm," "a bad dude") and ties each demo directly to certification study, framing "what one setting would have stopped this?" as a CCNA/CCNP Security study question. Wireless attacks additionally require a USB wireless adapter that supports monitor mode. See [[../../sources/2018-04-17-yt-lTlTjeCjXYM]] and [[../../sources/2019-08-27-yt-q7HkIwbj3CM]]. Related: [[../linux-terminal/linux-terminal]].

### Hack-a-Cisco-switch demo — VLAN hopping via DTP (2018-04-17)
Chuck plugs the Pi into an access port on VLAN 1, then attacks his own network remotely. Using the **Yersinia** tool he launches a **DTP (Dynamic Trunking Protocol)** attack — "switch spoofing" — that tricks the switch into converting the harmless access port into a **trunk port**, giving access to all VLANs. From there he can read broadcast traffic on every VLAN, discover IPs/VLANs, and assign himself any VLAN. He verifies port state before and after with `show interface fa1/0/14 status` / `show interface trunk`, notes the whole attack can also be run in GNS3 (where he first did it), and poses the defense as a study question: a single default practice — disabling DTP / hardcoding ports as access (`switchport mode access` / `nonegotiate`) — prevents it. [[../../sources/2018-04-17-yt-lTlTjeCjXYM]]

### Hacking public WiFi — with the ETHICS/education/legality frame (2019-08-27)
Chuck's key reframe: on free public WiFi you are not hacking the network, you are hacking the **people** on it — stealing their traffic. He runs three attacks against **consenting family members** (wife Abby, daughters):
- **Evil twin** — the Pi joins the real network for upstream internet (so victims notice nothing), stands up a rogue AP with a lookalike SSID via **hostapd**, surveys clients with **airodump-ng** (Aircrack-ng), serves a fake site, and DNS-spoofs victims with **DNSChef**.
- **Deauthorization attack** — copies the real SSID + channel with **airbase-ng**, grabs the target's MAC from airodump-ng, sends deauth frames so the device auto-roams to his stronger signal.
- **ARP spoofing / man-in-the-middle** — joins the same WiFi, scans with **nmap**, then uses **Ettercap** to forge ARP replies (tell the router "I am the victim," tell the victim "I am the router") plus simultaneous DNS spoofing.

The **ethical framing is explicit and repeated**, and should be treated as core to his security voice: "do not do this to someone without their permission," practice only on your own network/family/friends who consent, and the whole point is to become a **white-hat**: *"Learn how to hack things so you can learn how to protect things."* He also notes enterprise networks (Starbucks, McDonald's) isolate clients and are harder targets than home-style single-owner networks, and closes on defense — a **VPN encrypts the traffic and defeats all three attacks** (NordVPN is the paid sponsor). [[../../sources/2019-08-27-yt-q7HkIwbj3CM]]

### Security certifications — CCNA Cyber Ops vs CCNA Security (2019-03-12)
Comparing the two 2019-era Cisco security tracks: **CCNA Security** needed a prerequisite (CCENT / CCNA R&S / any CCIE), was **one exam** (210-260 IINS), targeted an entry-level network **security admin**, and fed into CCNP Security → CCIE Security. **CCNA Cyber Ops** had **no prerequisite**, was **two exams** (210-250 SECFND + 210-255 SECOPS), and targeted a **SOC analyst** role (correlating data, forensics, incident response, compliance frameworks). Chuck's verdict: get **CCNA Security first** — Cyber Ops is a dead-end track (no CCNP Cyber Ops exists) and Security is more marketable to recruiters; get a cert for (1) knowledge and (2) marketability. He also restates his standing rule that everyone should get CCNA Routing & Switching before any specialty track.

> ⚠️ Version note: **Both certs were later retired** in Cisco's February 2020 overhaul. CCNA Security, CCNA Cyber Ops, CCENT, and the separate CCNA tracks were consolidated into a single CCNA plus the new CyberOps Associate/Professional certs. This reflects Chuck's advice **as of 2019-03-12** and is not current cert guidance.

[[../../sources/2019-03-12-yt-PusUAu9gGiI]]. See also the certifications/career workstream and [[../homelab-selfhosting/homelab-selfhosting]] for the home-lab practice environment behind this study.

### OSINT — open-source intelligence tooling (2020–2021)
Starting 2020, Chuck built out a recurring OSINT thread: showing how much can be discovered about a target from public data alone, always framed as reconnaissance that ethical hackers and defenders need to understand (and that individuals should know about to protect their own footprint). The recurring tools/demos:
- **Google dorking (Google hacking)** — advanced search operators (`site:`, `filetype:`, `inurl:`, `intitle:`, etc.) to surface exposed files, login pages, cameras, and misconfigured servers indexed by Google (2020-06-28). [[../../sources/2020-06-28-yt-hrVa_dhD-iA]]
- **Sherlock** — hunt down a person's accounts across hundreds of social platforms by username (2021-03-06). [[../../sources/2021-03-06-yt-KdZvxxLsN3E]]
- **PhoneInfoga** — reconnaissance on a phone number (carrier, location, footprint) (2021-03-13). [[../../sources/2021-03-13-yt-6CnDdXVTxhU]]
- **Instagram OSINT** — pulling intelligence from Instagram profiles/activity (2021-03-28). [[../../sources/2021-03-28-yt-NWyqSbnsvGU]]
- **Twitter OSINT** — mining public Twitter data for intelligence (2021-04-29). [[../../sources/2021-04-29-yt-SvO_FDa8AIs]]

These run in [[../linux-terminal/linux-terminal]] (Kali/Linux) and reinforce the defensive lesson: know what you're leaking so you can lock it down.

### Ethical-hacking demo catalog (2020–2022)
As the channel's security content exploded through 2020–2022, Chuck ran a steady stream of hands-on attack demos. Two constants across all of them: (1) the attack is performed only against **his own or consenting systems** (his home network, his own VMs/labs, his own browser or infra), and (2) each closes with a **defensive lesson** — what setting, habit, or tool would have stopped it. Paraphrased catalog:
- **Nmap** — network scanning/enumeration to find open ports and vulnerabilities on your own network (2020-07-09). [[../../sources/2020-07-09-yt-4t4kBkMsDbQ]]
- **HashCat password cracking** — cracking password hashes with Kali + HashCat, and the takeaway on why long/unique passwords matter (2020-08-21). [[../../sources/2020-08-21-yt-z4_oqTZJqCo]]
- **ProxyChains / Tor anonymity** — routing tools through proxy chains for anonymity, framed as "don't make this mistake" when learning to hack (2020-08-02). [[../../sources/2020-08-02-yt-qsA8zREbt6g]]
- **Reverse shells with netcat** — establishing a callback shell to understand how attackers gain remote control (2021-07-08). [[../../sources/2021-07-08-yt-bXCeFPNWjsM]]
- **BadUSB on a Raspberry Pi Pico** — turning an $8 Pi Pico into a keystroke-injection "bad USB," and why you should never trust unknown USB devices (2021-08-20). [[../../sources/2021-08-20-yt-e_f9p-_JWZw]]
- **ARP spoofing / man-in-the-middle** — a device intercepting traffic on his own network via ARP poisoning (2021-09-24). [[../../sources/2021-09-24-yt-2rVzRoF7vQw]]
- **Dark-web DDoS against his own infrastructure** — buying a DDoS attack on the dark web and pointing it at his own server to show the threat (explicitly "don't do this") (2020-10-03). [[../../sources/2020-10-03-yt-eZYtnzODpW4]]
- **Tor hidden service on a Raspberry Pi** — standing up a dark-web (.onion) site on a Pi to demystify how hidden services work (2021-05-08). [[../../sources/2021-05-08-yt-bllS9tkCkaM]]
- **"Hack like Mr. Robot"** — recreating show-style hacking techniques for teaching (2020-12-18). [[../../sources/2020-12-18-yt-nnAQ8SYzAnE]]
- **Python malware (lab)** — writing malware in Python inside an isolated lab to understand how it works and how defenders detect it (2022-05-16). [[../../sources/2022-05-16-yt-UtMMjXOlRQc]]
- **Browser exploitation** — hacking a web browser (demoed against his own/his wife's consenting machine) to show client-side attack surface (2022-02-15). [[../../sources/2022-02-15-yt-3ogyS4KOlXc]]

Related tooling background lives in [[../linux-terminal/linux-terminal]]; the isolated environments these run in are covered in [[../homelab-selfhosting/homelab-selfhosting]].

### Build-a-hacking-lab blueprint (2021–2022)
Chuck repeatedly stresses that you should practice hacking **only** in an isolated lab you own — never on systems you don't have permission to touch. His lab guidance:
- **How to build a hacking lab** — the blueprint: a Kali attack box plus deliberately vulnerable target VMs, isolated on their own network (2021-03-05). [[../../sources/2021-03-05-yt-mvsiuLzpx2E]]
- **The $0.30 hacking lab** — a near-free cloud-based lab so cost is no excuse to practice illegally (2022-06-03). [[../../sources/2022-06-03-yt-4xJDDUt4Wq8]]
- **Kasm browser-based Kali lab** — running Kali Linux in the browser via Kasm for a disposable, containerized hacking environment (2022-01-17). [[../../sources/2022-01-17-yt-U7e-mcJdZok]]

### "How X gets hacked" awareness series (2021–2022)
A defender-facing format that walks through how real targets get compromised so viewers can protect themselves:
- **How big companies get hacked** — common enterprise attack paths (phishing, credential theft, misconfig) (2021-02-09). [[../../sources/2021-02-09-yt-bsCsuoIzyTg]]
- **How YouTubers get hacked** — session-token/OAuth theft and social engineering aimed at creators, plus how to defend the account (2022-08-30). [[../../sources/2022-08-30-yt-u2M_V5LtzpQ]]

### FREE Security+ course
Extending his "free certification course" model from the CCNA into security, Chuck published a free **CompTIA Security+** training series on the channel (episodes covering hacking fundamentals, phishing, social engineering, and web attacks — see the 2020-10 → 2020-11 Security+ source pages below). Details and links are tracked under [[../certifications-career/free-courses]] alongside his other free courses.

### The entry-level hacking certification — PenTest+ (2020-12-19)
Chuck points beginners who want to go into offensive security toward **CompTIA PenTest+** as a solid first *hacking* certification — an entry point into penetration testing that pairs well with Security+ and the hands-on lab work above (2020-12-19). [[../../sources/2020-12-19-yt-EY-Scg1z6zA]] See also [[../certifications-career/certifications-career]].

### Privacy, opsec & data sovereignty (2023–2025)
Alongside the offensive demos, Chuck runs a defender/privacy thread — hardening, hiding, and self-hosting to keep your data yours:
- **Qubes OS — security-vs-usability philosophy** — Qubes as the "reasonably secure" OS built on assume-breach / compartmentalization (isolating everything into disposable qubes so one compromise stays contained); Chuck respects the model but ultimately rejects it as a daily driver on usability grounds — the recurring security-vs-usability trade-off (2023-12-23). [[../../sources/2023-12-23-yt-i3sRSS6fN0g]]
- **Hide your files like a hacker** — five escalating concealment methods: the hidden attribute, extension renaming, NTFS Alternate Data Streams (ADS), VeraCrypt encrypted containers, and Steghide steganography (hiding data inside images) (2024-09-16). [[../../sources/2024-09-16-yt-VcqtWsbSbgU]]
- **Twingate ZTNA ("not a VPN")** — zero-trust network access for remote access: instead of a flat VPN tunnel into the whole network, per-resource authenticated access following zero-trust principles (2024-12-20). [[../../sources/2024-12-20-yt-1lZ3FQSv-wI]]
- **DeepSeek locally in an isolated Docker container** — running the DeepSeek LLM locally, sandboxed in Docker, framed as data sovereignty / opsec: keep your prompts and data off someone else's servers (2025-01-31). [[../../sources/2025-01-31-yt-7TR-FLWNVHY]] Related: [[../homelab-selfhosting/homelab-selfhosting]].

### AI + security crossover (2024-08-15)
As AI tooling matured, Chuck brought it into the security thread — using AI as a **hacking copilot**: leaning on an LLM to assist with offensive tasks (recon, tooling, code) while still under the same educational/ethics frame (2024-08-15). [[../../sources/2024-08-15-yt-3D6gaawXwfk]]

### Tor .onion hidden service — dark-web hosting (2023-11-01)
A return to the dark-web-hosting demo: standing up a **Tor hidden service** (.onion site) to demystify how hidden services work, strictly educational (2023-11-01). Echoes the earlier 2021 Pi-based version above. [[../../sources/2023-11-01-yt-CurcakgurRE]]

### AI security — prompt injection & AI red-teaming (2025–2026)
As LLMs moved into production, Chuck extended the security thread from "AI as a hacking copilot" (above) into **attacking AI systems themselves** — bringing in offensive-security expert **Jason Haddix** ([[../../entities/jason-haddix]], context guest) to cover **prompt injection**, jailbreaks, and **red-teaming** LLM/agent applications. Guest domain expertise is context, not persona voice. (2025-08-12, 2026-02-20) [[../../sources/2025-08-12-yt-2Z-9EOyb6HE]], [[../../sources/2026-02-20-yt-_yfiUQSbdPY]].

### The 2020 Twitter hack — social-engineering breakdown (2020-07-22)
A breakdown of the July 2020 Twitter compromise (high-profile accounts hijacked for a Bitcoin scam), featuring **Marcus Hutchins** — the attack traced to **social engineering** of Twitter employees / internal admin tooling rather than a technical exploit, reinforcing the recurring lesson that people are the softest attack surface. (2020-07-22) [[../../sources/2020-07-22-yt-GE5J_26Ut1Q]]

### Hacker community & industry (2025)
A later thread stepping back from individual demos to the **people and institutions** of security:
- **DEF CON 2025** — Chuck attends the hacker conference and makes the case for the value of the in-person hacker community — villages, hands-on learning, and culture (2025-11-04). [[../../sources/2025-11-04-yt-qFsj6KL8_nU]]
- **Robin — open-source dark-web OSINT tool** — an OSS tool by researcher **Apurv Singh Gautam** for surfacing intelligence from dark-web sources, extending the OSINT thread above, with a companion interview covering the researcher's career and threat-intel work (2025-11-17). [[../../sources/2025-11-17-yt-_KzObeom88Y]] + interview [[../../sources/2025-11-17-yt-KxfAW8wPDX4]].
- **Inside Bitdefender's Draco team** — a look at the threat-hunting team behind the **GandCrab / REvil** ransomware takedowns, showing the defensive/law-enforcement side of the ransomware fight (2025-11-28). [[../../sources/2025-11-28-yt-o-8amaZBi5M]].

### Self-hosted physical security — Frigate NVR (2025-12-15)
Extending the data-sovereignty thread into physical security: standing up **Frigate**, a self-hosted, open-source network video recorder (NVR) with local AI object detection, so your camera footage stays on hardware you own instead of a cloud vendor's servers (2025-12-15). [[../../sources/2025-12-15-yt-tbCKWX34_G4]] Related: [[../homelab-selfhosting/homelab-selfhosting]].

### The consistent ethics / legality frame (through-line)
Across every OSINT tool, attack demo, lab build, and awareness video from 2020 onward, Chuck applies the same explicit framing established in the earlier WiFi demos: the content is **educational**, run **only against systems you own or have explicit consent to test**, and its purpose is **defensive** — learn how the attack works so you can stop it. He repeatedly warns viewers not to use these techniques on others ("do not do this without permission"), the goal being to become a **white-hat**: *"learn how to hack things so you can learn how to protect things."* This ethics/legality frame should be treated as core to his security voice and reproduced whenever the persona discusses offensive tooling.

## Source pages

- 2018-04-17 — [[../../sources/2018-04-17-yt-lTlTjeCjXYM]] — Hack a Cisco Switch with a Raspberry Pi (VLAN hopping / DTP / Yersinia)
- 2019-03-12 — [[../../sources/2019-03-12-yt-PusUAu9gGiI]] — CCNA Cyber Ops vs CCNA Security (both since retired)
- 2019-08-27 — [[../../sources/2019-08-27-yt-q7HkIwbj3CM]] — Hacking Public WiFi with a Raspberry Pi and Kali Linux (evil twin / deauth / ARP MITM; ethics + VPN defense)
- 2020-06-28 — [[../../sources/2020-06-28-yt-hrVa_dhD-iA]] — Google HACKING (Google dorking / OSINT)
- 2020-07-09 — [[../../sources/2020-07-09-yt-4t4kBkMsDbQ]] — Nmap tutorial to find network vulnerabilities
- 2020-07-22 — [[../../sources/2020-07-22-yt-GE5J_26Ut1Q]] — the 2020 Twitter hack, explained (social engineering; ft. Marcus Hutchins)
- 2020-08-02 — [[../../sources/2020-08-02-yt-qsA8zREbt6g]] — learning hacking? DON'T make this mistake!! (ProxyChains / Tor anonymity)
- 2020-08-21 — [[../../sources/2020-08-21-yt-z4_oqTZJqCo]] — how to HACK a password (Kali + HashCat)
- 2020-10-03 — [[../../sources/2020-10-03-yt-eZYtnzODpW4]] — i bought a DDoS attack on the DARK WEB (against own infra; don't do this)
- 2020-10-19 — [[../../sources/2020-10-19-yt-vyqSdJLVQgg]] — 3 Hacking Skills EVERYONE has // FREE Security+ // EP 1
- 2020-10-28 — [[../../sources/2020-10-28-yt-u9dBGWVwMMA]] — Phishing attacks // FREE Security+ // EP 2
- 2020-11-10 — [[../../sources/2020-11-10-yt-HfPKe98UqEI]] — i hacked my grandma (social engineering) // FREE Security+ // EP 3
- 2020-11-17 — [[../../sources/2020-11-17-yt-UydNRZp_fmk]] — your favorite websites can be HACKED // FREE Security+ // EP 4
- 2020-11-20 — [[../../sources/2020-11-20-yt-Q2ErfVPomFQ]] — you're about to get hacked (7 reasons) // FREE Security+ // EP 6
- 2020-12-18 — [[../../sources/2020-12-18-yt-nnAQ8SYzAnE]] — hack like Mr. Robot
- 2020-12-19 — [[../../sources/2020-12-19-yt-EY-Scg1z6zA]] — your first Hacking certification (PenTest+)
- 2021-02-09 — [[../../sources/2021-02-09-yt-bsCsuoIzyTg]] — How Big Companies Get Hacked
- 2021-03-05 — [[../../sources/2021-03-05-yt-mvsiuLzpx2E]] — how to build a HACKING lab
- 2021-03-06 — [[../../sources/2021-03-06-yt-KdZvxxLsN3E]] — find social media accounts with Sherlock (OSINT)
- 2021-03-13 — [[../../sources/2021-03-13-yt-6CnDdXVTxhU]] — find info on phone numbers with PhoneInfoga (OSINT)
- 2021-03-28 — [[../../sources/2021-03-28-yt-NWyqSbnsvGU]] — Instagram OSINT
- 2021-04-29 — [[../../sources/2021-04-29-yt-SvO_FDa8AIs]] — Twitter OSINT (ethical hacking)
- 2021-05-08 — [[../../sources/2021-05-08-yt-bllS9tkCkaM]] — i put a DARK WEB website on a Raspberry Pi!! (Tor hidden service)
- 2021-07-08 — [[../../sources/2021-07-08-yt-bXCeFPNWjsM]] — reverse shells with netcat
- 2021-08-20 — [[../../sources/2021-08-20-yt-e_f9p-_JWZw]] — bad USBs are SCARY!! (BadUSB on a Raspberry Pi Pico)
- 2021-09-24 — [[../../sources/2021-09-24-yt-2rVzRoF7vQw]] — this device is HACKING my network!! (ARP spoofing / MITM)
- 2022-01-17 — [[../../sources/2022-01-17-yt-U7e-mcJdZok]] — create the ULTIMATE hacking lab (Kasm Kali-in-browser)
- 2022-02-15 — [[../../sources/2022-02-15-yt-3ogyS4KOlXc]] — i HACKED my wife's web browser (browser exploitation)
- 2022-03-14 — [[../../sources/2022-03-14-yt-GMOoXz20VZU]] — my kids built a HACKING computer!!
- 2022-05-16 — [[../../sources/2022-05-16-yt-UtMMjXOlRQc]] — i created malware with Python (lab)
- 2022-06-03 — [[../../sources/2022-06-03-yt-4xJDDUt4Wq8]] — the $0.30 Hacking Lab
- 2022-08-30 — [[../../sources/2022-08-30-yt-u2M_V5LtzpQ]] — How YouTubers Get Hacked
- 2023-11-01 — [[../../sources/2023-11-01-yt-CurcakgurRE]] — Tor .onion hidden service (dark-web hosting, educational)
- 2023-12-23 — [[../../sources/2023-12-23-yt-i3sRSS6fN0g]] — Qubes OS (assume-breach / compartmentalization; security-vs-usability, rejected as daily driver)
- 2024-08-15 — [[../../sources/2024-08-15-yt-3D6gaawXwfk]] — AI as a hacking copilot (AI + security crossover)
- 2024-09-16 — [[../../sources/2024-09-16-yt-VcqtWsbSbgU]] — hide your files like a hacker (hidden attr / ext-rename / NTFS ADS / VeraCrypt / Steghide)
- 2024-12-20 — [[../../sources/2024-12-20-yt-1lZ3FQSv-wI]] — Twingate ZTNA ("not a VPN") — zero-trust remote access
- 2025-01-31 — [[../../sources/2025-01-31-yt-7TR-FLWNVHY]] — running DeepSeek locally in an isolated Docker container (data sovereignty / opsec)
- 2025-08-12 — [[../../sources/2025-08-12-yt-2Z-9EOyb6HE]] — AI hacking / prompt injection / red-teaming (ft. Jason Haddix, [[../../entities/jason-haddix]])
- 2025-11-04 — [[../../sources/2025-11-04-yt-qFsj6KL8_nU]] — DEF CON 2025 (value of the in-person hacker community)
- 2025-11-17 — [[../../sources/2025-11-17-yt-_KzObeom88Y]] — Robin, an open-source dark-web OSINT tool (Apurv Singh Gautam)
- 2025-11-17 — [[../../sources/2025-11-17-yt-KxfAW8wPDX4]] — companion interview with researcher Apurv Singh Gautam (threat intel / career)
- 2025-11-28 — [[../../sources/2025-11-28-yt-o-8amaZBi5M]] — inside Bitdefender's Draco team (GandCrab / REvil ransomware takedowns)
- 2025-12-15 — [[../../sources/2025-12-15-yt-tbCKWX34_G4]] — self-hosted Frigate NVR (own-your-data physical security)
- 2026-02-20 — [[../../sources/2026-02-20-yt-_yfiUQSbdPY]] — AI hacking / prompt injection / red-teaming (ft. Jason Haddix, [[../../entities/jason-haddix]])
