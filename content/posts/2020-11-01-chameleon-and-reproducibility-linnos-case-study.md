---
abstract: "<p dir=\"ltr\">This summer, a team of students worked on an experiment\
  \ that ultimately became part of the LinnOS paper that infers the SSD performance\
  \ with the help of its built in light neural network architecture. The LinnOS paper,\
  \ which utilizes Chameleon testbed to provide a public executable workflow, will\
  \ be presented in OSDI \u201920 and is available <a href=\"https://www.usenix.org/conference/osdi20/presentation/hao\"\
  >here</a>.\_</p>\n\n<p dir=\"ltr\"><br>\nTwo of the students, Levent Toksoz and\
  \ Mingzhe Hao, write about their experience in this Chameleon User Stories series.\
  \ Toksoz is a recent graduate of the University of Chicago computer science masters\
  \ program. He studied physics and math as an undergrad at the University of Michigan\
  \ and is planning to apply to PhD programs in computer science. Hao is a Ph.D candidate\
  \ of the UCARE group in the Department of Computer Science at the University of\
  \ Chicago. His research interests include operating systems, storage systems, and\
  \ distributed systems.</p>"
authors:
- Levent Toksoz
categories:
- User Experiments
date: '2020-11-01 04:03:00+00:00'
featured: false
hide_image: true
image: ''
related_posts: []
slug: chameleon-and-reproducibility-linnos-case-study
subtitle: ''
title: 'Chameleon and Reproducibility: LinnOS Case Study'
---

<p dir="ltr">Authors: Levent Toksoz and Mingzhe Hao</p>

<p dir="ltr">LinnOS is one of the first that utilizes machine learning inside the OS to infer I/O speed for flash storage at per-I/O granularity in real-time and helps parallel storage applications achieve performance predictability. It supports black-box SSD devices and real production traces without requiring any extra input from users. In addition, it outperforms industrial mechanisms and other approaches. More specifically compared to hedging and heuristic based methods, it improves the average I/O latencies around 9.6% to 79.6% with a reasonable per I/O overhead of 4-6?s. </p>

<p dir="ltr">We used Chameleon’s Jupyter interface to implement our experiments since it offers cell level execution with strong support for documentation to create easy to understand and execute “presentation” projects. Chameleon’s Jupyter interface also allows users to book bare metal instances with various complex hardware configurations. This support was very beneficial to our experiment as it requires a storage hierarchy instance with 3 SSDs to successfully execute failover behaviour. Finally, LinnOS utilizes Chameleon’s easy to use publishing system, where users can publish their experiment to Zenodo or Trovi, to be publicly accessible and executable.</p>

<p dir="ltr">We chose to reproduce LinnOS paper, because it provides a wide range of interactions with the Chameleon testbed that covers the entire stack ranging from application-level software to operating system, and hardware (SSD) (such as installing a new Kernel using the Jupyter-Chameleon interface, running Python and Bash scripts on that kernel via the Jupyter-Chameleon interface, etc.). </p>

<p dir="ltr"><b id="docs-internal-guid-3c4309e6-7fff-f742-4c39-4a0d11c17034">LinnOS experiment works as follows:</b></p>

<p dir="ltr">First, we populate the SSD drives with I/O trace sets. Then using those I/O trace sets LinnOS`s lightweight machine learning model is trained and learned weights are saved to the LinnOS Kernel code. Finally the LinnOS Kernel is installed to make real time I/O speed predictions. </p>

<p dir="ltr">We made our packaged experiment available <a href="https://www.chameleoncloud.org/experiment/share/15?s=409ab137f20e4cd38ae3dd4e0d4bfa7chttps://www.chameleoncloud.org/experiment/share/15?s=409ab137f20e4cd38ae3dd4e0d4bfa7c">here</a>. The current version of the package only includes comparison between baseline and LinnOS models. Ultimately, we are planning to reproduce most of the experiments shown in the LinnOS paper.</p>

<p dir="ltr"><b id="docs-internal-guid-3c4309e6-7fff-f742-4c39-4a0d11c17034"><img height="288" src="https://lh3.googleusercontent.com/j6oYwOsrx_MXQbfqZ4k6fRhpD_6l5EerN1XQ-rA-C44dUMSKNzE5utSL8nzJq2ro2Hgqp__dotRPpxHXGUbBzdxEZ8Q7Me4E6K2mbNkwIpLESLi6oTAy-cMNdsGC-mbyWhXxNrII" width="432"></b></p>

<p dir="ltr"><b id="docs-internal-guid-3c4309e6-7fff-f742-4c39-4a0d11c17034">Example graph. Note that when you run the code you don't always get this exact graph.</b></p>

<p dir="ltr">Developing and packaging our LinnOS experiment so that it is easily repeatable for us and for others provided us with various insights on how experiments should be packaged. For example, for the experiments that are as long and comprehensive as LinnOS, stability and making cells idempotent is quite important. If an error occurs at an intermediate stage, the user might be forced to restart. All of the insights we accumulated over the duration of the project will be shared in a separate blog post.</p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-3c4309e6-7fff-f742-4c39-4a0d11c17034">LinnOS Packaged Experiment Link: <a href="https://www.chameleoncloud.org/experiment/share/15?s=409ab137f20e4cd38ae3dd4e0d4bfa7c">https://www.chameleoncloud.org/experiment/share/15?s=409ab137f20e4cd38ae3dd4e0d4bfa7c</a></b><br>
<b id="docs-internal-guid-3c4309e6-7fff-f742-4c39-4a0d11c17034">OSDI Paper and Presentation Link: <a href="https://www.usenix.org/conference/osdi20/presentation/hao">https://www.usenix.org/conference/osdi20/presentation/hao</a></b></p>

<p dir="ltr"> </p>

<p dir="ltr"><b>Authors' Background: </b></p>

<p dir="ltr">This summer, a team of students worked on an experiment that ultimately became part of the LinnOS paper that infers the SSD performance with the help of its built in light neural network architecture. The LinnOS paper, which utilizes Chameleon testbed to provide a public executable workflow, will be presented in OSDI ’20 and is available <a href="https://www.usenix.org/conference/osdi20/presentation/hao">here</a>. </p>

<p dir="ltr"><br>
Two of the students, Levent Toksoz and Mingzhe Hao, write about their experience in this Chameleon User Stories series. Toksoz is a recent graduate of the University of Chicago computer science masters program. He studied physics and math as an undergrad at the University of Michigan and is planning to apply to PhD programs in computer science. Hao is a Ph.D candidate of the UCARE group in the Department of Computer Science at the University of Chicago. His research interests include operating systems, storage systems, and distributed systems.</p>

<p dir="ltr"><b id="docs-internal-guid-4e5f0b40-7fff-4efd-0f3d-f2910138c204"><img height="164" src="https://lh6.googleusercontent.com/xy68dzUNpxQ_g-dwp5Qqw6fJ3xAltf5aFwnKjhejOJx0KpMU_cVUDyo1L_hyLA1WbpKp3FAUXoGkqgHLUGs-wO6YG9Epw7Dseq4Rmg-MmSovZFykpyZMCT5wWUQxeps1N8fkCy07" width="221">   </b><b id="docs-internal-guid-9061285a-7fff-7fda-4d81-ece034929653"><img height="247" src="https://lh3.googleusercontent.com/gqq7gePfjWGnDfVmun-D3IGuZC18yUGRPfRvD21HMuaX4WlOUFS003-pJD20SwI6wdCSNZcxLPI9oEA9yXUGlF-skS9CjWALwdNUKrls78tX7h4crn0qNuWSrB-qegGFOnyh-oRl" width="189"></b></p>

<p dir="ltr">Pictured: Mingzhe Hao, Left, and Levent Toksoz, Right. </p>