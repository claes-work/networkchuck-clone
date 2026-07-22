---
type: youtube-video
source_date: 2018-07-16
url: https://www.youtube.com/watch?v=G5HucqXioBY
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [networking, homelab-selfhosting]
tags: [dmvpn, home-network, data-center, homelab, cisco, ccnp]
---

# Moving my HOME NETWORK to a DATA CENTER w/ DMVPN

## Summary
Chuck explains how he solved the problem of keeping a full Cisco lab while going fully remote and traveling the world with his family. After leaving his job at CBT Nuggets to travel (filmed from an Airbnb in Paris), he sold nearly everything he owned and colocated his entire home network and lab — two large Dell servers, routers, and switches — into a data center in Dallas, Texas. He then uses DMVPN so that wherever he travels, a small branch router builds a VPN tunnel back to the Dallas hub, giving him always-on access to his servers, Cisco phones, and Wi-Fi as if he never left home.

## Key claims
- (2018-07-16) Chuck left his job at CBT Nuggets to become fully remote and travel; he and his family sold almost everything (cars, furniture, most clothes) and travel with suitcases, backpacks, and his tech gear. Video is filmed in Paris, France.
- (2018-07-16) To keep his lab while traveling, he moved his entire home network and lab into a data center in Dallas, Texas, rather than downsizing to a compact lab or going full cloud. His gear includes two large Dell servers plus routers and switches; his dad and brother Cameron helped him rack, stack, and wire it in.
- (2018-07-16) He wanted more than plain remote-access VPN because he travels with Cisco IP phones; he needed a persistent site-to-site connection wherever he goes, so he runs DMVPN with a traveling "remote site."
- (2018-07-16) DMVPN is described as a remote-access technology for branches/sites: many branch sites with Cisco routers connect back to a central home/hub. It's lightly touched in CCNA, partially configured at CCNP, and covered in depth at CCIE.
- (2018-07-16) His traveling kit: a Cisco 881 branch router that builds the DMVPN tunnel back to Dallas; a small-business switch with 4 PoE ports to power his Cisco phones; and UniFi access points (AP AC Lite, ~$70) broadcasting his own SSID "let's just go da family," managed by a UniFi controller running on his server back in Dallas.
- (2018-07-16) His Cisco phones register back to his Call Manager on the server in Dallas over the DMVPN tunnel; his brother Cameron also has a Cisco router at his house connected via DMVPN to the Dallas data center, so they share an internet connection and routes.
- (2018-07-16) For sites without Ethernet, he uses a UniFi AirGateway (~$30–40) as a repeater/station that connects to any Wi-Fi and hands it to his router as Ethernet (or acts as a standalone router); he used it successfully in a hotel at Cisco Live.
- (2018-07-16) He monitors the home network from the data center with PRTG (free up to 100 sensors), running it low-resource on his domain controller, with a map showing his DMVPN tunnels and traffic metrics plus app notifications.
- (2018-07-16) His network runs EIGRP and OSPF. He plans to add firewalls when time permits and intends to experiment with pfSense on a Raspberry Pi as a travel firewall. He also still uses remote-access VPN via L2TP on his router for casual access back to his gear.
- (2018-07-16) He identifies as "a collaboration guy" (Cisco voice/phones); he actually travels with three Cisco phones.

## Notable verbatim quotes
> "pretty much my entire home networks and my lab inside a data center"

> "I have a from my Airbnb in Paris I have a VPN connection back to my data center in Dallas Texas that's nuts"

> "what is dmvpn it's for remote access for your branches you can have a lot of branch a lot of sites that connect with Cisco routers back to your home your hub"

> "no matter where I am in the world we have we share an internet connection we share routes"

> "for you nerds out there which should be all of you I'm running EIGRP and OSPF of my network"

> "these phones are communicating back to my data center in Dallas that means they are registered with my call manager on my server in Dallas"

## Guest attribution
Solo — all statements attributable to Chuck Keith (the SUBJECT). Family members are mentioned but do not speak: his wife runs a family travel vlog ("let's just go da family"); his brother Cameron (aspiring network engineer) and his dad (also named Chuck, a VMware/Microsoft systems guy with a VCP) helped move the gear into the data center.

<!-- ★ L3-candidate: early homelab / personal data-center infrastructure -->
