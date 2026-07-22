---
type: youtube-video
source_date: 2018-04-17
url: https://www.youtube.com/watch?v=lTlTjeCjXYM
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, networking]
tags: [raspberry-pi, cisco, switch, hacking, security, ccna-security, demo]
---

# Hack a Cisco Switch with a Raspberry Pi

## Summary
Chuck demonstrates a VLAN hopping attack against a Cisco switch using a Raspberry Pi (nicknamed "Malcolm") running Kali Linux. He plugs the Pi into an access port on VLAN 1, then walks to a public area to attack his own network remotely over VPN/SSH. Using the Yersinia tool he launches a DTP (Dynamic Trunking Protocol) attack that tricks the switch into converting the harmless access port into a trunk port, giving him access to all VLANs — from which he can read broadcast traffic, discover IP addresses/VLANs, and assign himself any VLAN. It is an early NetworkChuck hands-on hacking/Raspberry Pi demo tying practical attacks to CCNA/CCNP Security study.

## Key claims
- (2018-04-17) A VLAN partitions a switch into virtual switches, separating broadcast domains; a host on VLAN 1 cannot reach a host on VLAN 2 at layer 2 without going through a router or layer-3 device, so VLANs act as an extra layer of security. [paraphrase]
- (2018-04-17) Switch ports are either access ports (one VLAN, typically for computers/printers) or trunk ports (carry multiple VLANs, typically between switches, tagging frames with 802.1Q). [paraphrase]
- (2018-04-17) The demonstrated VLAN hopping method is "switch spoofing" — the attacker impersonates a switch to turn an access port into a trunk. [paraphrase]
- (2018-04-17) The attack rig is a Raspberry Pi ("Malcolm") running Kali Linux, accessed remotely via SSH with auto-login, plugged into switch port 14 (interface Fa1/0/14) which was in access mode on VLAN 1. [paraphrase]
- (2018-04-17) Verify port state before attacking with `show interface fa1/0/14 status`; a trunk port shows as trunk under status and can be inspected with `show interface trunk`. [paraphrase]
- (2018-04-17) The attack is run with the Yersinia tool, selecting the DTP (Dynamic Trunking Protocol) module, then choosing attack type 1 "enable trunking" — switches use DTP to negotiate whether a port becomes a trunk or access port, and the Pi impersonates a switch in that negotiation. [paraphrase]
- (2018-04-17) After the attack, `show interface fa1/0/14 status` shows the port is now a trunk and `show interface trunk` confirms it has access to all VLANs, within a few seconds. [paraphrase]
- (2018-04-17) Yersinia/Malcolm can then be set to 802.1Q mode to listen to broadcasts on all VLANs, revealing IP addresses and VLANs; the attacker could assign themselves an IP and VLAN of choice to access any network. [paraphrase]
- (2018-04-17) A single default security practice prevents this attack (Chuck poses it as a study question for CCNA/CCNA Security/CCNP Security students) — implicitly disabling DTP / hardcoding ports as access (switchport mode access / nonegotiate). [paraphrase]
- (2018-04-17) The entire attack can also be run in GNS3, and Chuck first performed it in GNS3 rather than on the Raspberry Pi. [paraphrase]

## Notable verbatim quotes
> "this is my good buddy Malcolm he is my Raspberry Pi now Malcolm he's kind of a bad guy he's a bad dude he's running Kali Linux and that's a flavor of Linux that has a bunch of tools for networking attacks"

> "using malcolm our Raspberry Pi with Kali Linux we will try to turn this room harmless access port that only gives people access to one VLAN into a trunk port giving us access to all of the VLANs opening up the door for a number of amazing attacks"

> "we're gonna do a DTP attack the dynamic trunking protocol which is what switches will use to negotiate if the report is going to be a trunk or an access port"

> "this is kind of cool it's really stinking easy this is all I'm doing I'm selecting one for enabled trunking and that was it"

> "before not moments ago it was just in an access port VLAN 1 now it's a stinkin trunk port show interface trunk there he is right there you know what he has access to all VLANs that's crazy"

> "so if I were a malicious hacker trying to do this pretty easy right"

> "the first time I actually did this attack was not with the Raspberry Pi it was actually in gns3 you can run the entire attack in gns3 not even kidding"

## Guest attribution
Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: early hacking + Raspberry Pi demo format -->
