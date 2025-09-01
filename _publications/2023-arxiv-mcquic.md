---
title: "MCQUIC: Multicast and Unicast in a Single Transport Protocol"
collection: publications
category: publications
permalink: /publication/2024-arxiv-mcquic
excerpt: 'First design and implementation of Multicast extensions in QUIC'
date: 2024-06-01
venue: 'Arxiv (unpublished)'
authors: <strong>Louis Navarre</strong>, Olivier Pereira, Olivier Bonaventure
slidesurl:
paperurl: 'http://louisna.github.io/files/2023-arxiv-mcquic.pdf'
bibtexurl: 'http://louisna.github.io/files/2023-arxiv-mcquic.bib'
citation: 'Navarre, L., Pereira, O., & Bonaventure, O. (2023). MCQUIC: Multicast and unicast in a single transport protocol. arXiv preprint arXiv:2309.06633.'
---
Multicast enables efficient one-to-many communications. Several applications benefit
from its scalability properties, e.g., live-streaming and large-scale software updates. Historically, multicast
applications have used specialized transport protocols. The flexibility of the recently standardized QUIC protocol
opens the possibility of providing both unicast and multicast services to applications with a single transport
protocol. We present MCQUIC, an extended version of the QUIC protocol that supports multicast communications. We
show how QUIC features and built-in security can be leveraged for multicast transport. We present the design of
MCQUIC and implement it in Cloudflare quiche. We assess its performance through benchmarks and in emulated
networks under realistic scenarios. We also demonstrate MCQUIC in a campus network. By coupling QUIC with our
multicast extension, applications can rely on multicast for efficiency with the possibility to fall back on
unicast in case of incompatible network conditions.