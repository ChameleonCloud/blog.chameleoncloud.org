---
abstract: "<p dir=\"ltr\">November\u2019s Chameleon User Experiments blog features\
  \ Nanqinqin Li, a first-year PhD student at Princeton University. Learn more about\
  \ Li, his summer research on reproducibility and Solid-State Drive Simulators, and\
  \ learn where to <a href=\"https://www.chameleoncloud.org/experiment/share/4\">replicate\
  \ his experiment</a> on <a href=\"https://www.chameleoncloud.org/experiment/share/\"\
  >Trovi</a>!</p>"
authors:
- Nanqinqin Li
categories:
- User Experiments
date: '2020-11-23 23:54:43+00:00'
featured: false
hide_image: true
image: ''
related_posts: []
slug: reproducing-solid-state-drive-simulator-research-results-chameleon
subtitle: ''
title: Reproducing Solid State Drive Simulator Research Results on Chameleon
---

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-0090a3e3-7fff-02b7-c41a-b2d71c180b00"><img height="263px;" src="https://lh6.googleusercontent.com/qkOFv7tiqcqF2tyaTOlgDI5RXow0b4ZDQlEcIhsivreHDbK1YIgR08bbUGFxfACRKQ9g8dzzFheXMXD-57jktxFvPKaa1DwplMVMvh95ZsApL1QSW8-ZGIv6yNNcFvcA-W8B_Pgr3i4" width="192px;"></b></p>

<p dir="ltr" style="text-align: center;">Image courtesy of Nanqinqin Li</p>

<p dir="ltr">November’s Chameleon User Experiments blog features Nanqinqin Li, a first-year PhD student at Princeton University. Learn more about Li, his summer research on reproducibility and Solid-State Drive Simulators, and learn where to <a href="https://www.chameleoncloud.org/experiment/share/4">replicate his experiment</a> on <a href="https://www.chameleoncloud.org/experiment/share/">Trovi</a>!</p>

<p dir="ltr"><b id="docs-internal-guid-c47ea7f2-7fff-eabc-ca47-faf0a2ba1c96">On his background:</b> My name is <a href="https://linanqinqin.github.io/">Nanqinqin Li</a>. I am a first-year PhD student at Princeton University. I received my master’s degree at the University of Chicago working with Prof. Haryadi Gunawi. My major research interest is storage/file systems. I am always trying to train myself as an individual researcher and to leave a footprint of my own in the evolution of computer science. In my spare time, I like doing a little sports (soccer, swimming, hiking, etc.) and a lot of video gaming with my friends. </p>

<p dir="ltr"><b id="docs-internal-guid-c47ea7f2-7fff-eabc-ca47-faf0a2ba1c96">On his summer research: </b>This summer, I worked on a reproducibility project with Prof. Gunawi and several other students. The purpose of this work is to get a picture of research reproducibility in the current literature and to reveal interesting findings and potential underlying reasoning. My role was to do a thorough survey on the topic of SSD (solid-state drives) simulators to find papers that published their experiments and then try to reproduce the results on the Chameleon testbed. We chose SSD simulators mainly because they are general software tools for facilitating research on hardware, and reproducibility is the core to such software. The major challenge was mostly the literature review part where we manually searched for papers which covered relevant topics and also published their experiments. After that, the second challenge was to actually reproduce those experiments using Chameleon. </p>

<p><b id="docs-internal-guid-70ca2cc3-7fff-759e-2eb4-3b499cb1d1ea">On approaching the research challenge: </b>The approach is simple. We first located the paper that presented the simulator, then traced back to all the papers that cited it. We looked into two popular SSD simulators, SSDsim and FlashSim, and this approach narrowed down the paper pool to 600 papers that actually used/extended the simulators. From this survey, we were able to find 8 papers (about 1%!) that published their experiments (mostly on GitHub), but only one that we were able to reproduce on Chameleon. The major reason for the other failed 7 papers is the poor maintenance of their published code repo (e.g., compilation problem, incompatible with newer kernel version, and runtime errors). These percentages match up to <a href="http://reproducibility.cs.arizona.edu/tr.pdf">a paper</a> investigating reproducibility that was published a long time ago, which means that most of the time, researchers do not focus much on reproducibility.</p>

<p><b id="docs-internal-guid-439c806a-7fff-a5fa-63ec-ead36b243501">On testbed needs:</b> The need here mostly depends on the experiments in the papers. For simulator related research, I don’t think there are special feature needs for the platform as long as it provides basic computing nodes, given that the goal of simulators is to empower research in absence of adequate hardware. Thus, the features unique to Chameleon that I mostly used were the Jupyter integration for experiment orchestration and experiment packaging for publishing. The Jupyter integration provides a great interface for orchestrating the experiment flow, making complicated research results easy to be reproduced in the form of Jupyter notebooks.</p>

<p dir="ltr"><b id="docs-internal-guid-322bf424-7fff-004f-ba93-b5e587fa1826">On the role of reproducibility in science:</b><b id="docs-internal-guid-c47ea7f2-7fff-eabc-ca47-faf0a2ba1c96"> </b>I think the role is to greatly inspire new ideas. Aside from well-written papers, repeatable experiments is another (arguably the best) way to precisely convey ideas/designs/arguments in published research, thus making it much easier for new ideas to wander around.</p>

<p dir="ltr"><b id="docs-internal-guid-ee7aa54f-7fff-3147-9cb2-d72c3ccf20be">On the greatest obstacles for repeatable research: </b>Based on my experience with those 600 papers I surveyed, I would say the greatest obstacles are 1.) most papers do not publish their experiments along with the paper; and 2.) poor maintenance to their github repo which makes their experiments obsolete rather quickly.</p>

<p dir="ltr"><b id="docs-internal-guid-1095f5f4-7fff-65f9-58f2-1e579c927591">On obstacles that stand in the way of systems experimentation:</b> Given that my research interacts closely with various storage devices, the kind of situation happens when we don’t have a specific type of device we need (such as Intel Optane, open-channel SSDs, etc.). Also, COVID makes it hard for us to sometimes access the devices physically when there is a need, and I think this is where Chameleon could help. For example, one of my previous projects requires constant physical access to the machine because we need to swap on/off SSD devices due to limitations on our hardware supply. On Chameleon, we could actually just configure a few nodes differently to meet our various needs, instantly and pain free.</p>

<p><b id="docs-internal-guid-e5348554-7fff-d3c7-ba18-13bf163edd28">On his most powerful piece of advice for students beginning research: </b>Failures could destroy your will, while success may also blind your eyes. Keep up your equanimity!</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-3a15fa28-7fff-fdad-7ff7-734681b7c80e">Where to find artifacts related to his experiment:</b></p>

<p dir="ltr">The tinyTailFlash package has been published to Chameleon (it’s a self-explained Jupyter notebook): <a href="https://www.chameleoncloud.org/experiment/share/4">https://www.chameleoncloud.org/experiment/share/4</a></p>

<p dir="ltr">It is expected to take 30 minutes to reproduce the results.</p>

<p dir="ltr">The original paper corresponding to the package is here: <a href="https://www.usenix.org/system/files/conference/fast17/fast17-yan.pdf">https://www.usenix.org/system/files/conference/fast17/fast17-yan.pdf</a></p>