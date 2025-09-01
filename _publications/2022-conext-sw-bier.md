---
title: "Experimenting with bit index explicit replication"
collection: publications
category: publications
permalink: /publication/2022-conext-sw-bier
excerpt: 'Open-source implementation of the Bit Index Explicit Replication protocol'
date: 2021-09-30
venue: 'Proceedings of the 3rd International CoNEXT Student Workshop'
authors: <strong>Louis Navarre</strong>, Nicolas Rybowski, Olivier Bonaventure
slidesurl:
paperurl: 'http://louisna.github.io/files/2022-conext-sw-bier.pdf'
bibtexurl: 'http://louisna.github.io/files/2022-conext-sw-bier.bib'
citation: 'Navarre, L., Rybowski, N., & Bonaventure, O. (2022, December). Experimenting with bit index explicit replication. In Proceedings of the 3rd International CoNEXT Student Workshop (pp. 17-19).'
---
Bit Index Explicit Replication (BIER) is a recent multicast architecture that solves
several problems with deployed IP multicast protocols. BIER embeds an implicit multicast tree representation
inside each transmitted packet. With this new mechanism, it becomes possible to reconsider multicast applications.
However, no open-source implementation of BIER can be found. This paper presents our open-source implementation of
the BIER forwarding mechanism and a companion socket-like API. Additionally, we show simulations of the
implementation with ns-3 DCE.