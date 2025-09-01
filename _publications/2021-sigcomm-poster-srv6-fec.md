---
title: "SRv6-FEC: bringing forward erasure correction to IPv6 segment routing"
collection: publications
category: publications
permalink: /publication/2021-sigcomm-poster-srv6-fec
excerpt: 'First implementation of Forward Erasure Correction at the network layer using IPv6 Segment Routing and eBPF.'
date: 2021-08-24
venue: 'Proceedings of the SIGCOMM 21 Poster and Demo Sessions'
authors: <strong>Louis Navarre</strong>, François Michel, Olivier bonaventure
slidesurl:
paperurl: 'http://louisna.github.io/files/2021-sigcomm-poster-srv6-fec.pdf'
bibtexurl: 'http://louisna.github.io/files/2021-sigcomm-poster-srv6-fec.bib'
citation: 'Navarre, L., Michel, F., & Bonaventure, O. (2021). SRv6-FEC: bringing forward erasure correction to IPv6 segment routing. In Proceedings of the SIGCOMM 21 Poster and Demo Sessions (pp. 45-47).'
---
IPv6 Segment Routing (SRv6) is a recent implementation of the source routing paradigm
in IPv6 network. A programmability framework has recently been added to SRv6 and enables it to support diverse
use-cases. We leverage this support to design, implement and assess a Forward Erasure Correction (FEC) technique
that transparently protects IPv6 packets. We implement our encoders and decoders using eBPF on the Linux kernel
and evaluate the benefits that they bring with IoT devices.