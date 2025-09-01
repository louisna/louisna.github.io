---
title: "On Integrating eBPF into Pluginized Protocols"
collection: publications
category: publications
permalink: /publication/2024-ccr-ebpf
excerpt: 'Overview of pluginized protocols using eBPF.'
date: 2024-08-01
venue: 'ACM SIGCOMM Computer Communication Review, Volume 53, Issue 3'
authors: Quentin De Coninck, <strong>Louis Navarre</strong>, Nicolas Rybowski
slidesurl:
paperurl: 'http://louisna.github.io/files/2024-ccr-ebpf.pdf'
bibtexurl: 'http://louisna.github.io/files/2024-ccr-ebpf.bib'
citation: 'De Coninck, Q., Navarre, L., & Rybowski, N. (2024). On integrating ebpf into pluginized protocols. ACM SIGCOMM Computer Communication Review, 53(3), 2-8.'
---
eBPF is a popular technology originating from the Linux kernel that enables safely
running user-provided programs in a kernel-context. This technology opened the door for efficient programming in
the operating system, especially in its network stack. However, its applicability is not limited to the Linux
kernel. Various efforts leveraged the eBPF Instruction Set Architecture (ISA) as the basis of other networking
related use cases outside of the Linux kernel. This paper focuses on the pluginized protocols' use case such as
PQUIC and xBGP where the eBPF ISA serves as the basis to execute plugins providing per-session protocol behavior.
It first quickly describes how the Linux kernel builds around this eBPF ISA to provide enhanced in-kernel network
programmability. Then, the paper considers the case of pluginized protocols. Leveraging eBPF outside of the Linux
kernel environment requires complementing the eBPF ISA to meet the pluginized protocols' requirements. This paper
details these integration efforts. Based on the lessons learned from these, it finally concludes by an
applicability discussion of the eBPF ISA to other use cases.