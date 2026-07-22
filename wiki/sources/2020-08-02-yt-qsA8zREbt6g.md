---
type: youtube-video
source_date: 2020-08-02
url: https://www.youtube.com/watch?v=qsA8zREbt6g
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cybersecurity, linux-terminal]
tags: [proxychains, tor, kali-linux, anonymity, ethical-hacking, opsec]
---

# learning hacking? DON'T make this mistake!! (hide yourself with Kali Linux and ProxyChains)

## Summary

An ethical-hacking tutorial on operational anonymity: how to hide your source IP address when running hacking tools from Kali Linux, using proxies, proxy chaining, and ProxyChains. Chuck opens with the mistake the title warns about — firing up Kali and scanning a target (using a demo target named "David Bombal") without hiding yourself. Every scan carries a "from" address (your public IP), so the target's firewall not only blocks the scan but tells the target exactly who did it, and they can report you to the police and you go to jail. Before showing the technique, Chuck frames it strictly as ethical hacking done with explicit permission (a signed business agreement) — anything else, "don't do it."

The core technique: instead of sending attacks directly, route them through a proxy server (a middleman) so the target sees the proxy's IP, not yours. But a single proxy keeps logs that can trace back to you, so the answer is proxy chaining — hopping traffic through multiple proxy servers so untangling the chain of logs becomes "crazy difficult" (though not foolproof; no solution is). He then demos configuring ProxyChains in Kali: locating the config with `locate proxychains`, editing `/etc/proxychains.conf` with vim, choosing a chaining mode (dynamic vs. random vs. strict — he uses dynamic, disables strict), keeping `proxy_dns` enabled so DNS requests are also proxied, and adding proxy entries in `type ip port` format (socks4/socks5/http/https). He verifies it works by running `proxychains firefox google.com`, checking "what's my IP" (shows a proxy in Thailand), then runs `proxychains nmap -sT -p 80,443 <target>` through the chain. He notes the default config points at Tor (the loopback 127.0.0.1 entry) as a gateway to the dark web but skips it for this video. He sources free proxies by Googling "free proxy server list" (e.g., spys.one), warning not all proxies work. The video closes with a sponsored challenge: use three chained proxies plus nmap (with `-Pn` to skip host-discovery pings and `-sT` for a TCP connect scan) to reach a private-IP web server on port 80 in the 172.31/172.32.29 range and follow further instructions there — first five winners get an IT Pro TV membership and NetworkChuck coffee. Sponsored by IT Pro TV.

## Key claims (dated 2020-08-02)

Technique:
- If you use hacking tools like Kali Linux without hiding yourself, every scan you send carries your public IP as a "from" address, so the target's firewall flags it, blocks it, and can identify you. (paraphrase)
- A proxy server acts as a middleman: route your attacks through it so the target sees the proxy's IP instead of yours. (paraphrase)
- A single proxy is not enough because proxy servers keep logs that can trace an attack back to you; proxy chaining routes traffic through multiple proxies so untangling the logs is very difficult (not impossible / not foolproof). (paraphrase)
- ProxyChains comes pre-installed on Kali; you configure it by editing the config file, found via `locate proxychains` (typically `/etc/proxychains.conf`). (paraphrase)
- ProxyChains has three modes — dynamic, strict, and random; Chuck recommends dynamic (uses all proxies in listed order, skipping any that are down) and comments out strict. Random picks one proxy at random, which keeps targets guessing. (paraphrase)
- Keep `proxy_dns` enabled so DNS lookups are also proxied; otherwise your DNS requests leak your real IP. (paraphrase)
- Proxy list format is `type ip port` (plus optional username/password); types include socks4, socks5, http, https — socks5 is better than socks4, and https/socks5 are more secure. (paraphrase)
- The default config's loopback entry (127.0.0.1) points at Tor / the onion router as a gateway to the dark web; it requires the Tor service enabled and is skipped here. (paraphrase)
- Usage: prefix any command with `proxychains` (e.g., `proxychains firefox`, `proxychains nmap -sT -p 80,443 <ip>`) to route it through the chain; verify with a "what's my IP" check. (paraphrase)
- Free proxies can be found by Googling "free proxy server list" (e.g., spys.one), but not all proxies work, so you may have to test several. (paraphrase)
- For scanning hosts that don't respond to ping, use nmap's `-Pn` switch to skip the initial host-discovery ping, combined with `-sT` for a TCP connect scan. (paraphrase)

Ethics / legality:
- Using hacking tools without hiding yourself is dangerous — you can get into legal trouble and go to jail because scans identify you by IP. (paraphrase)
- The technique is presented strictly in the context of ethical hacking, which requires explicit permission — a business agreement authorizing the activity. (paraphrase)
- Doing this against anyone without that explicit permission: "don't do it." (paraphrase)

## Notable verbatim quotes

> "If you're using hacking tools like Kali Linux and you're not doing anything to hide yourself, it's kind of dangerous. Like, you could get into trouble."

> "Every scan you send has a from address, a nice little note that says, hey, it was me, I'm doing it, I'm hacking. That's your IP address."

> "But Chuck, I had a mask on. Doesn't matter if you don't do something to hide the fact that all of these messages, all these attacks, are coming from you."

> "Before I show you how to hide yourself, let me tell you this: I'm speaking strictly in the context of ethical hacking, having a business [agreement], explicit permission to do this. Anything else, don't do it."

> "This is what's called proxy chaining. We're chaining together multiple proxy servers to hide ourselves."

> "This is not a foolproof situation where you'll never be discovered. No solution is. But it does make it crazy difficult."

> "Best case is you want to proxy everything, even your DNS request, through your proxy. That way no one can find you."

> "I am in Thailand. So good luck finding me."

> "Just know it's your gateway to the dark web."

> "Proxy chains — got to keep yourself safe. I'll catch you guys later."

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).

<!-- ★ L3-candidate: anonymity/opsec tutorial + ethics framing -->
