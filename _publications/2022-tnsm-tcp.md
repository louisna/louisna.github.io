---
title: "Leveraging eBPF to make TCP path-aware"
collection: publications
category: publications
permalink: /publication/2022-tnsm-tcp
excerpt: 'Leveraging IPv6 Segment Routing and eBPF to dynamically change the TCP path to optimize the connection.'
date: 2022-05-01
venue: 'IEEE Transactions on Network and Service Management, Volume 19, Issue 3'
authors: Mathieu Jadin, Quentin De Coninck, <strong>Louis Navarre</strong>, Michael Schapira, Olivier Bonaventure
slidesurl:
paperurl: 'http://louisna.github.io/files/2022-tnsm-tcp.pdf'
bibtexurl: 'http://louisna.github.io/files/2022-tnsm-tcp.bib'
citation: 'Jadin, M., De Coninck, Q., Navarre, L., Schapira, M., & Bonaventure, O. (2022). Leveraging eBPF to make TCP path-aware. IEEE Transactions on Network and Service Management, 19(3), 2827-2838.'
---
The Transmission Control Protocol (TCP) is one of the key Internet protocols. It is
used by a broad range of applications. TCP was designed when there was typically a single path between a client
and a server. Today’s networks provide higher path diversity, yet TCP still only uses the single path selected by
the network layer. This limits the ability of TCP to react to events such as interdomain failures or highly
congested peering links. We propose the TCP Path Changer (TPC), a set of eBPF programs that are incorporated into
the Linux TCP/IP stack to make it more agile. To illustrate the benefits of our approach, we first demonstrate
that TPC can quickly reroute an ongoing TCP connection around a failure. We then show that TPC can also monitor
the round-trip-time of active TCP connections and automatically reroute them if it becomes too high. Our
evaluation of TPC in emulated networks evidences the significant performance benefits of a path-aware transport
protocol.