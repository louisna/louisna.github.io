---
title: "Taking the Best of Multicast and Unicast with Flexicast QUIC"
collection: publications
category: publications
permalink: /publication/2025-ccr-flexicast
excerpt: 'Flexible Multicast extensions for the QUIC protocol.'
date: 2025-04-01
venue: 'ACM SIGCOMM Computer Communication Review, Volume 55, Issue 2'
authors: <strong>Louis Navarre</strong>, Quentin de Coninck, Tom Barbette, Olivier Bonaventure
slidesurl:
paperurl: 'http://louisna.github.io/files/2025-ccr-flexicast.pdf'
bibtexurl: 'http://louisna.github.io/files/2025-ccr-flexicast.bib'
citation: 'Navarre, L., De Coninck, Q., Barbette, T., & Bonaventure, O. (2025). Taking the Best of Multicast and Unicast with Flexicast QUIC. ACM SIGCOMM Computer Communication Review, 55(2), 2-12.'
---
With IP Multicast, a source can efficiently send the same information to a set of
receivers attached to a multicast tree. Unfortunately, when distributing live video or large files, some receivers
might be unable to join the multicast tree. Applications willing to use multicast for efficiency must also support
unicast to reach all their receivers. Given the complexity of mixing unicast and multicast, most popular
applications only use unicast protocols.

The large deployment of QUIC, a secure and flexible transport protocol that runs above UDP, allows for
reconsidering multicast at the transport layer. We design and implement Flexicast QUIC, an extension of Multipath
QUIC that enables applications to use multicast where and when it works efficiently and seamlessly fall back on
unicast otherwise. Our in-lab performance evaluation shows that a Flexicast QUIC source can sustain up to 1000
receivers for an aggregated traffic of more than 80 Gbps, more than 4 times what we achieve with (unicast) QUIC in
the same setup. We also show that Flexicast QUIC can easily distribute a video stream and recover from transient
failures on the underlying multicast tree while maintaining excellent quality of experience.