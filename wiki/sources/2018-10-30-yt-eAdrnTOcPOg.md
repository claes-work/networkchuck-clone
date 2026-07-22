---
type: youtube-video
source_date: 2018-10-30
url: https://www.youtube.com/watch?v=eAdrnTOcPOg
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cloud-devops, certifications-career]
tags: [coding, python, network-automation, intent-based-networking, devnet]
---

# HOW to Start Coding (RIGHT NOW!) as a Network Engineer - ICND1 | CCNA CCNP & Intent-Based Networking

## Summary

Chuck argues that network automation is exciting precisely because it erases the "sucky parts" of being a network engineer — the 3 a.m. outage calls, the lone-engineer overload, the endless projects-plus-firefighting grind. He walks through a progression of concepts: SDN (software-defined networking), where an SDN controller pushes scripted config out to many devices at once, and then intent-based networking (IBN), where instead of deciding what config goes on each box you simply tell a controller (his example: Cisco DNA Center) your business *intent* — e.g. "let these developers talk to these developer servers" — and it translates that intent to policy and activates it across all devices. He highlights DNA Center's "assurance" piece: it continuously verifies the network is behaving as intended and can fix or flag issues before they become outages.

The back half is an interview at Cisco Live with Hank Preston, a Cisco developer/NetDevOps evangelist and CCIE. Preston lays out a phased roadmap for network engineers getting into automation: set networking aside briefly and learn basic Python syntax (read others' code, experiment), sign up for GitHub and browse examples, learn data formats, and explore REST APIs (his teaching favorite is the Internet Chuck Norris Database API). Then layer on Linux fundamentals and Docker containers/images, and explore Linux and Docker networking. Preston stresses that networking fundamentals (CCNA/CCNP, maybe CCIE) remain essential — cloud and container networks are often built by people lacking those fundamentals, so the valuable "unicorn" has both networking depth and programming breadth. He recommends diversifying: go deep on a topic, step back, learn some programming, then oscillate. Chuck closes with a challenge to himself and viewers: take Hank Preston's free Network Programmability Basics course on Cisco DevNet (developer.cisco.com).

This is sponsored content for Cisco.

## Key claims (dated)

All dated 2018-10-30 (paraphrase):

- Being a network engineer is not always great — the "dark parts" include 3 a.m. outage calls and being one of very few engineers responsible for a large network while juggling projects and firefighting.
- Network automation is exciting because it starts to erase the worst parts of the job.
- SDN (software-defined networking) lets you script a config once and push it out to many devices (e.g. deploying access lists to 20 routers) at once, saving time.
- Intent-based networking (IBN) goes a step further than SDN: rather than deciding the config for each device, you tell a controller your *intent*, and it translates that business intent to policy and activates it across all devices.
- Chuck's IBN controller example is Cisco DNA Center.
- DNA Center's "assurance" piece continuously verifies the network is working as intended and can fix issues itself or alert you before they become outages.
- Automation freeing up time lets engineers experiment, lab, learn programming, or play with APIs — Chuck floats making the network voice-controlled via Alexa as one idea.
- Hank Preston is a Cisco developer/NetDevOps evangelist and a CCIE who came from networking.
- NetDevOps means taking best practices, culture, and ideas from the software DevOps transition and applying them to network engineering.
- Preston's recommended first step: set networking aside briefly and learn basic Python syntax — not to become a full programmer, but to read code and experiment.
- Next steps after Python basics: sign up for GitHub and browse examples, learn data formats, and explore REST APIs.
- Preston uses the Internet Chuck Norris Database (icndb.com) REST API as a teaching example for API classes.
- After the fundamentals, add Linux fundamentals, Docker containers/images, then explore Linux networking and Docker networking.
- Networking fundamentals still matter: many cloud and container networks were built by people without networking fundamentals, so they lack good segmentation, scale, and operability.
- The valuable "unicorn" has both core networking skills (CCNA/CCNP, possibly CCIE) and the ability to build networks in the cloud and with containers.
- Recommended learning strategy: diversify — go deep on something, step back, do some programming, then alternate back and forth rather than over-specializing.
- Preston recommends Cisco DevNet (developer.cisco.com) learning labs: coding basics, NETCONF and YANG fundamentals, and open-source labs like OpenDaylight controllers and TRex traffic generation.
- Chuck's challenge to himself and viewers: create a DevNet account and take Hank Preston's free Network Programmability Basics course (about nine and a half hours).

## Notable verbatim quotes

> the awesome unicorn I would call you that can bridge the gap between networking and programming and just be awesome

> intent based networking that's where it comes from so we don't worry about access list and then VLANs and all that and adding that configuration no we should tell DNA Center hey we want these guys the developers to talk to our developer servers and he just does it across all of our devices he translates our business intent like I want that to happen to policy and then he activates it and makes it happen

> it's called the assurance piece it's always assuring that your network is working the way you wanted to or the way you intended to

> go learn basic [Python] you're not gonna be a programmer developer but go learn basic syntax learn how to read other people's code experiment with what's out there

> learn some Python go sign up for github troll through all the examples learn what data formats are Explorer REST API is my favorite API when I teach REST API classes is the Chuck Norris database API

> you will be appalled by the types of networks that are running these critical applications in the cloud and in containers today because they were built by people that didn't have the fundamental understanding of how to build a good network

> what we really need are people that have both sides of it we need core fundamental networking skills but we also need to understand what does it mean to build a network in the cloud what does it mean to build a network with containers

> I always recommend people go in deep and then step back and find something else to go check out

> let's take this challenge let's actually start learning network programmability let's just dip our toe into it and see what it's like

## Guest attribution

Interview — this video contains a guest, Hank Preston (Cisco developer/NetDevOps evangelist, CCIE). Statements above are attributed per speaker: the SDN/IBN/DNA Center framing and the closing challenge are Chuck Keith's (the SUBJECT); the phased learning roadmap (Python → GitHub → REST APIs → Linux/Docker), the "unicorn needs both sides" argument, the diversify strategy, and the DevNet lab recommendations are Hank Preston's. Only Chuck-attributed material trains the persona; Preston's statements are context, not persona voice data.

<!-- ★ L3-candidate: contains Chuck's canonical "start coding as a network engineer" learning-path framework and his SDN vs. intent-based-networking (DNA Center + assurance) explanation — foundational for cloud-devops and certifications-career topics -->
