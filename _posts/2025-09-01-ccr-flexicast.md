---
title: 'Flexicast QUIC in ACM SIGCOMM CCR: flexible multicast in QUIC!'
date: 2025-09-01
permalink: /posts/2025/09/flexicast-quic
tags:
  - Flexicast
  - QUIC
  - Multicast
  - Multipath
---

# Flexicast QUIC: Rethinking Multicast for the QUIC Era

When distributing live video, software updates, or cloud gaming streams, today’s Internet almost exclusively relies on **unicast**: each receiver gets its own copy of the data. This is simple and robust but highly inefficient, especially when thousands of receivers consume the same content. The cost is felt both at the sender — which must generate and encrypt per-receiver packets — and in the network, which carries redundant traffic.

**Multicast** was designed decades ago to solve exactly this problem: a source transmits once, and routers replicate packets along a multicast tree. But despite its promise, multicast never became mainstream on the global Internet. It is difficult to deploy across ISPs, hard to monetize, and fragile — applications always need to fall back to unicast anyway. Most content providers gave up and built massive unicast infrastructures instead.

With the wide deployment of **QUIC**, a modern transport protocol running above UDP, there is a chance to revisit multicast — not at the IP layer, but directly at the transport layer. This is where **Flexicast QUIC** comes in.

## The Idea of Flexicast QUIC

Flexicast QUIC, presented in our *SIGCOMM CCR 2025* paper, extends **Multipath QUIC** to combine the efficiency of multicast with the reliability of unicast. The idea is to make multicast *flexible*:

* Each receiver gets a **unicast QUIC path** for control and fallback.
* The sender also establishes a **flexicast flow**: a shared, unidirectional path encrypted with a common key and intended for all receivers.
* If multicast routing is available, this flow is carried efficiently through the network. If not, the sender can still replicate the packets itself and deliver them over unicast.

Receivers can join or leave the flexicast flow at any time. If multicast fails for one receiver, it automatically falls back to unicast — without affecting others. All this happens within the same QUIC connection, so applications don’t need to juggle two protocols.

![](/images/fcquic-design.pdf)

## Key Design Points

Flexicast QUIC builds on QUIC’s extensible design:

* **Per-path keys**: unlike regular Multipath QUIC, each unicast path and the flexicast flow use distinct encryption keys.
* **Reliability**: acknowledgments are sent over unicast paths, aggregated at the sender to avoid the classic *ack implosion* problem.
* **Congestion control**: the sender maintains per-receiver congestion states. If one receiver drags the group down, it can be removed from the flexicast flow and served over unicast.

## Implementation and Results

We implemented Flexicast QUIC in **Cloudflare’s quiche** library (Rust), adding \~10,000 lines of code and 5,000 lines of tests. The evaluation was run on CloudLab and emulated networks.

![](/images/fcquic-mt.pdf)

### Scalability

* **Unicast QUIC**: saturates at \~200 receivers (\~20 Gbps). CPU is the bottleneck, as every packet must be encrypted per receiver.
* **Flexicast QUIC**: supports **1000 receivers** and delivers **>80 Gbps**, over 4× higher throughput than unicast QUIC, with acceptable CPU usage.
* With a small acknowledgment delay (5 ms), Flexicast QUIC perfectly matches the ideal UDP baseline.

Even without multicast in the network, Flexicast QUIC still helps: the sender can replicate encrypted packets using `sendmmsg`, which is far cheaper than generating per-receiver packets.

![](/images/fcquic-proxy.pdf)

### Robustness

We tested Flexicast QUIC with a 5 Mbps live video stream under failing multicast trees. Some receivers randomly lost multicast connectivity, forcing fallback to unicast. Results:

* Other receivers were unaffected.
* Video quality stayed excellent (SSIM > 0.99 for 99.4% of frames).
* Latency remained low, with only small tail increases during recovery.

This shows Flexicast QUIC provides seamless continuity even when multicast is unreliable.

## Why It Matters

Flexicast QUIC makes multicast practical again:

* **Efficient**: one packet can serve thousands of receivers.
* **Robust**: unicast fallback is built-in, so failures don’t break the stream.
* **Practical**: works today, even without multicast routers.
* **Deployable**: it’s just QUIC — already used by major Internet services.

This makes it promising for content delivery networks, software updates, and live streaming at scale.

## What’s Next?

Our future work will explore:

* **Forward Erasure Correction** to improve reliability.
* **Smarter flow control** for heterogeneous receivers.
* **Source authentication** to defend against spoofed multicast traffic.
* **Multiple flexicast flows** (e.g., different video bitrates).
* **Dynamic key rotation** for large, changing groups.
* **Inter-domain deployment** using AMT and TreeDN.
* **New use cases** like software updates or gaming.

The source code and experiment scripts are open-source: [Flexicast QUIC on GitHub](https://github.com/IPNetworkingLab/flexicast-quic).

---

**In short:** Flexicast QUIC brings multicast back to the Internet by blending it with unicast, all within QUIC. It offers scalability where multicast works, and robustness where it doesn’t — making it a practical transport for the next generation of large-scale applications.
