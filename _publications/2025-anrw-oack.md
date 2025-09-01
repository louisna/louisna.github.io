---
title: "MAY is not enough! QUIC servers should skip packet numbers"
collection: publications
category: publications
permalink: /publication/2025-anrw-oack
excerpt: 'Analyzing the optimistic acknowledgment attack in the QUIC protocol and how well the countermeasures are implemented in existing implementations.'
date: 2025-07-10
venue: 'ANRW 25: Proceedings of the 2025 Applied Networking Research Workshop'
authors: <strong>Louis Navarre</strong>, Olivier Bonaventure
slidesurl:
paperurl: 'http://louisna.github.io/files/2025-anrw-oack.pdf'
bibtexurl: 'http://louisna.github.io/files/2025-anrw-oack.bib'
citation: 'Navarre, L., & Bonaventure, O. (2025, July). MAY is not enough! QUIC servers SHOULD skip packet numbers. In Proceedings of the 2025 Applied Networking Research Workshop (pp. 136-142).'
---
The QUIC protocol increasingly replaces TCP as the dominant transport protocol on the
Internet. Its design closely integrates TLS 1.3 with modern transport features such as faster connection
establishment and stream multiplexing. QUIC uses unique and monotonically increasing packet numbers compared to
the wrapping TCP sequence number.

In this paper, we analyze the behavior of QUIC stacks against the optimistic acknowledgment (OACK) attack, i.e.,
whenever a peer falsely acknowledges non-received packets to increase the transmission rate to saturate the
emitter's network. Although QUIC implementations may skip packet numbers to prevent such an attack, we find that
of the 16 existing server implementations from the QUIC Interop Runner, 11 use contiguous packet numbers and are
vulnerable to the OACK attack. In a controlled environment, we design a simple OACK client and show that we can
increase the server's bit rate up to >200x depending on the stack. We confirm the results by carefully reproducing
the OACK attack on a large Content Delivery Network server and suggest an example of a patch to protect
implementations.