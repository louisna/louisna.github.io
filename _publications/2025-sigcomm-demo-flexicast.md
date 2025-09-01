---
title: "Towards an Internet Deployment of Flexible Multicast QUIC"
collection: publications
category: publications
permalink: /publication/2025-sigcomm-demo-flexicast
excerpt: 'First Internet deployment of Flexicast QUIC with Automatic Multicast Tunneling.'
date: 2025-09-09
venue: 'SIGCOMM 25: Proceedings of the SIGCOMM 25 Poster and Demo Sessions'
authors: <strong>Louis Navarre</strong>, Olivier Bonaventure
slidesurl:
paperurl: 'http://louisna.github.io/files/2025-sigcomm-demo-flexicast.pdf'
bibtexurl: 'http://louisna.github.io/files/2025-sigcomm-demo-flexicast.bib'
citation: 'Navarre, L., & Bonaventure, O. (2025). Towards an Internet Deployment of Flexible Multicast QUIC. " SIGCOMM 25: Proceedings of the SIGCOMM 25 Poster and Demo Sessions".'
---
Despite their scalability benefits, multicast protocols are not widely deployed and
are confined to intra-domain use cases such as IPTV. Several factors contribute to this reluctance to deploy
multicast on the Internet. Among them, the chicken-and-egg and all-or-nothing problems hindered the emergence of
inter-domain multicast. Recent advancements within the IETF suggest solutions to these issues, such as Automatic
Multicast Tunneling (AMT) and flexible multicast extensions to the QUIC transport protocol (FCQUIC). This demo
leverages AMT and Flexicast QUIC to enable researchers to conduct large-scale inter-domain multicast measurement
campaigns. We provide Docker images of FCQUIC receivers that can be connected to our FCQUIC source, which any
Internet host can reach using AMT. We will also publish our setup code to motivate researchers to instantiate
their own FCQUIC source application with AMT.