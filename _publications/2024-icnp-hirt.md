---
title: "A High-Speed Robust Tunnel Using Forward Erasure Correction in Segment Routing"
collection: publications
category: publications
permalink: /publication/2024-icnp-hirt
excerpt: 'FastClick-based high-speed design and implementation of Forward Erasure Correction in IPv6 Segment Routing to recover losses at the network layer.'
date: 2024-10-04
venue: '2024 IEEE 32nd International Conference on Network Protocols (ICNP)'
authors: <strong>Louis Navarre</strong>, François Michel, Tom Barbette
slidesurl:
paperurl: 'http://louisna.github.io/files/2024-icnp-hirt.pdf'
bibtexurl: 'http://louisna.github.io/files/2024-icnp-hirt.bib'
citation: 'Navarre, L., Michel, F., & Barbette, T. (2024, October). A High-Speed Robust Tunnel Using Forward Erasure Correction in Segment Routing. In 2024 IEEE 32nd International Conference on Network Protocols (ICNP) (pp. 1-12). IEEE.'
---
Low-latency applications drive an increasing number of modern applications. Latency
depends on factors such as link layer technologies and how higher-layer protocols cope with transmission errors
and packet losses. Most transport protocols rely exclusively on retransmissions to cope with losses with minimal
overhead but potentially large tail latency. This paper leverages network coding to propose the high-speed robust
tunnel (HIRT), providing timely packet delivery to any application independently of the transport protocol. A
network code recovers lost data without requiring time-consuming retransmissions by adding redundancy packets,
thereby slightly increasing the bandwidth usage to reduce the tail latency. Our algorithm dynamically adapts the
rate of redundancy packets by measuring the network loss patterns. We implement HIRT using IPv6 Segment Routing
(SRv6). We suggest an efficient software implementation and demonstrate on CloudLab that our solution can protect
traffic at high speeds (> 50Gbps) on standard servers even when facing severe packet losses in the network. We evaluate
HIRT with HTTP over TCP/QUIC, and file system benchmarks over a real network with losses, Starlink. HIRT reduces
the tail latency of short HTTP requests by 2x and the mean request completion time of longer requests by up to 20%. HIRT
also decreases the tail latency of NFS requests by up to 20%.