---
type: youtube-short
channel: "@NetworkChuck"
source_date: 2024-08-13
url: https://www.youtube.com/watch?v=LI7he7KYSLY
ingested: 2026-07-22
tier: L2
domains: [networking, ai-tools, cloud-devops]
---

# over 24,000 GPUs!!! (Short)

## Summary

A short on how Meta built the network to train its Llama 3.1 405B-parameter model, and why large-scale AI training is a distinct networking discipline. Ends with a sponsor pointer to Juniper's "AI moment" resources. (Transcript says "45 billion" but the model is the 405B-parameter Llama 3.1 — likely a caption/verbal slip.)

## Key points

- 2024-08-13 — Meta trained Llama 3.1 using RDMA over Converged Ethernet (RoCE) with 400 GB/s interconnects between GPUs.
- 2024-08-13 — A three-layer CLOS network connected 24,000 GPUs, optimizing bandwidth and reducing oversubscription.
- 2024-08-13 — Enhanced ECMP was used to balance traffic; poor load balancing raises tail latency, which slows the next training iteration.
- 2024-08-13 — Thesis: AI networking requires a different strategy — fast failure detection/isolation and fast job startup matter. <!-- ★ L3-candidate: recurring NetworkChuck stance that "AI networking is different" — candidate for a networking/AI topic page and beliefs -->
- 2024-08-13 — Sponsor: directs viewers to juniper.net "the AI moment" to see how production network engineers at Meta handle AI networking.

## Notable verbatim quotes

- "I'm telling you AI networking is different it requires a different strategy"
- "if you cannot load balance all the traffic your tail latency increases your next training iteration is running slower"

## Guest attribution

No guest. Single speaker (Chuck Keith). References (does not quote) an unnamed production network engineer at Meta.
