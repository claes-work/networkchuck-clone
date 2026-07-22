---
type: youtube-video
source_date: 2014-12-01
url: https://www.youtube.com/watch?v=yn_qCnOh9xk
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [networking, cybersecurity]
tags: [cisco-asa, firewall, license, security-plus, early-era]
---

# How to Upgrade/Activate a License on a Cisco ASA (Adaptive Security Appliance)

## Summary

An early NetworkChuck tutorial walking through how to activate a higher license
level on a Cisco ASA (Adaptive Security Appliance) firewall. In this specific case
Chuck enables a **Security Plus** license to unlock **dual ISP** support via
failover. He covers the full workflow: obtaining the license from Cisco's product
license registration portal using a PAK, tying it to the device serial number,
applying the activation key on the ASA via the `activate-key` command, saving config,
and reloading so the new license takes effect. He verifies the result with `show
version`, showing failover moving from disabled to enabled (active/standby) and the
VLAN count jumping from 3 to 20. This is representative of Chuck's early
Cisco-network-engineer-era content: short, hands-on, terminal-driven CLI tutorials.

## Key claims (dated — the steps) [2014-12-01, paraphrase]

1. To increase your ASA license level, first go to cisco.com and continue to
   **product license registration** to download your license.
2. Enter your **PAK** (Product Activation Key / license) — the code you should have
   received when you bought the license from your vendor or Cisco reseller.
3. Fulfill the PAK to download the license; Cisco registers the license against your
   device's **serial number**, so the license is tied to (and must be used on) that
   specific ASA.
4. Chuck notes he has never had to un-license an ASA; he says he'd make a video if he
   ever does — just make sure you license the correct device.
5. Cisco emails the license (containing the activation key) to your address.
6. On the ASA, enter **global configuration mode** (`configure terminal`).
7. Apply the key with the **`activate-key`** command, pasting the key from the email.
8. The ASA updates its flash with the activation key; the new key becomes active only
   after you **reload** the ASA.
9. Save the running config to the startup config with `copy running-config
   startup-config` (`copy run start` / `copy rs` for short).
10. Run **`show version`** to verify status: before reload, failover is disabled
    (Security Plus not yet active).
11. Reload the ASA.
12. After reload, `show version` confirms the license is active — failover now shows
    **active/standby**, and VLANs have increased from **3 to 20**.
13. The Security Plus license enables **failover** for the ASA, which supports using
    **dual ISP connections**.

## Notable verbatim quotes

> "today I'll be showing you how to install an ASA license to increase whatever
> license level you're at currently on your Cisco ASA — in this specific environment
> I will be enabling a Security Plus license on my ASA to enable dual ISPs"

> "on the Cisco ASA to fulfill the license, Cisco will register your license with the
> serial of your device ... now that ASA is tied to your license so you must use that
> license on your ASA"

> "I've never had to unlicense an ASA, so if I ever do come to that I will make a
> video about it — just make sure you license the correct device"

> "your new key will become active when you reload your ASA"

> "you can see that my failover is enabled with active standby ... you also notice
> that my VLANs have gone from three VLANs to 20 VLANs"

> "if you have any video ideas or questions ... just hit me up in the comments below,
> I'll be happy to answer any question you have"

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: early Cisco ASA/firewall tutorial (network-engineer origin era) -->
