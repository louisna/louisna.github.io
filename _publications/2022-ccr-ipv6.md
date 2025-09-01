---
title: "The multiple roles that IPv6 addresses can play in today's internet"
collection: publications
category: publications
permalink: /publication/2022-ccr-ipv6
excerpt: 'Ideas on how we can leverage IPv6 if we think of it differently than just a longer IPv4 address.'
date: 2022-10-02
venue: 'ACM SIGCOMM Computer Communication Review, Volume 52, Issue 3'
authors: Maxime Piraux, Tom Barbette, Nicolas Rybowski, <strong>Louis Navarre</strong>, Thomas Alfroy, Cristel Pelsser, François Michel, Olivier Bonaventure
slidesurl:
paperurl: 'http://louisna.github.io/files/2022-ccr-ipv6.pdf'
bibtexurl: 'http://louisna.github.io/files/2022-ccr-ipv6.bib'
citation: 'Piraux, M., Barbette, T., Rybowski, N., Navarre, L., Alfroy, T., Pelsser, C., ... & Bonaventure, O. (2022). The multiple roles that IPv6 addresses can play in today s internet. ACM SIGCOMM Computer Communication Review, 52(3), 10-18.'
---
The Internet use IP addresses to identify and locate network interfaces of connected
devices. IPv4 was introduced more than 40 years ago and specifies 32-bit addresses. As the Internet grew,
available IPv4 addresses eventually became exhausted more than ten years ago. The IETF designed IPv6 with a much
larger addressing space consisting of 128-bit addresses, pushing back the exhaustion problem much further in the
future.
In this paper, we argue that this large addressing space allows reconsidering how IP addresses are used and
enables improving, simplifying and scaling the Internet. By revisiting the IPv6 addressing paradigm, we
demonstrate that it opens up several research opportunities that can be investigated today. Hosts can benefit from
several IPv6 addresses to improve their privacy, defeat network scanning, improve the use of several mobile access
network and their mobility as well as to increase the performance of multicore servers. Network operators can
solve the multihoming problem more efficiently and without putting a burden on the BGP RIB, implement Function
Chaining with Segment Routing, differentiate routing inside and outside a domain given particular network metrics
and offer more fine-grained multicast services.