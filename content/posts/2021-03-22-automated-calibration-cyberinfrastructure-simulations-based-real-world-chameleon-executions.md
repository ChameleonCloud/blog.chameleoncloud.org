---
abstract: "<p>Learn about using Chameleon to develop\_automated\_calibration for cyberinfrastructure\
  \ research\_as part of\_WRENCH research team member's\_William Koch's Master's thesis.\_\
  A\_M.S. student at\_the University of Hawai`i at Manoa (UHM), Koch explores cyberinfrastructure\_\
  research, this research project's approach,\_and his research\_background in this\_\
  blog post.</p>"
authors:
- William Koch
categories:
- User Experiments
date: '2021-03-22 23:35:43+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/7a/db/7adb8a6e-df8d-4c70-8733-62d0f8d71648/image2.png
related_posts: []
slug: automated-calibration-cyberinfrastructure-simulations-based-real-world-chameleon-executions
subtitle: ''
title: Automated Calibration of CyberInfrastructure Simulations Based on Real-World
  Chameleon Executions
---

<p dir="ltr"><b id="docs-internal-guid-add448e5-7fff-26c8-41ee-25ce8319744f"><img height="384.8984771573604" src="https://lh5.googleusercontent.com/jzoQIlZJcT_zActIxqe-5BqOLuLNXrm-Tu37jzDkvFc_kitGnrviZPPS3PiRvknwaWxD4rJWo5QgJN_6h1-7uHDnjAP0WyVx8q_YJKybhwd2JxGzdGo0mEAM-hmtG8GStOTYXQoC" width="355"></b><b><img height="267" src="https://lh6.googleusercontent.com/iK114574yIrAjQBqaXsGFdW9oqJz0MBezVMhQEW9LOSTyiJXhm3lEEgeKEmjlRA7zUQG0Ci8KVgvc2THJ5t7hbbdRpmMEfHhQNZHOD3gLl6K5wNCj3G5VvehV-H_ykHklJ5beeKk" width="267"></b></p>

<p> </p>

<p dir="ltr">This work is part of the <a href="http://wrench-project.org/">WRENCH project</a>, a collaboration between the Information and Computer Sciences Dept. at the University of Hawai`i at Manoa (UHM) and the Information Science Institute (ISI) at the University of Southern California. The WRENCH team is large, comprising senior researchers as well as graduate and undergraduate students. William Koch, a current M.S. student at UHM is the main researcher working on this particular project. He’s planning to graduate later this year and is looking for employment in industry following graduation. </p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-add448e5-7fff-26c8-41ee-25ce8319744f">On his current research: </b></p>

<p dir="ltr">Much of CyberInfrastructure (CI) research relies on experimental results obtained for scenarios in which application workloads of interest are executed on CI platforms. For instance, workload traces (e.g., <a href="https://www.cs.huji.ac.il/labs/parallel/workload/">Parallel Workload Archive</a>) are commonly used for extracting system and application parameters (e.g., CPU, memory, and disk usage, I/O wait, etc.) that are used for developing models of the system behavior. Many published works include results obtained in simulation. Simulation is attractive because it makes it possible to explore scenarios that go beyond application and platform configurations available at hand. Additionally, simulated executions are 100% reproducible and observable and take significantly less time, labor, and/or funds than their real-world counterparts. A key concern, however, is simulation accuracy. </p>

<p dir="ltr">Simulators of CI systems are built based on simulation models, either custom-developed or provided by established CI simulation frameworks. These models come with configuration parameters that define their behaviors, and different choices for these parameter values lead to different simulated execution.  An important question is then: How should one pick simulation model parameter values so as to maximize simulation accuracy with respect to real-world executions?  We term the process of picking parameter values based on real-world executions simulation calibration. Simulation calibration can be performed for one or more feasible real-world scenarios, and the calibrated simulator can then be used to simulate other scenarios, including scenarios that are not necessarily feasible on available real-world CI configurations.  Simulation calibration is challenging due to the potentially large number of simulation model parameters and the large range of values that some of these parameters can take.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-add448e5-7fff-26c8-41ee-25ce8319744f">On approaching the research challenge: </b></p>

<p dir="ltr">We propose to develop an automated simulation calibration approach, as depicted in the diagram below:</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-add448e5-7fff-26c8-41ee-25ce8319744f"><img height="125" src="https://lh3.googleusercontent.com/uGWTiXOxcT112gYW0unxN9vfEBio_Gd4bwhnBChErmiaS2ehYm1RBaCo7rL7UMjVuVD5trmP1DkAJ6XN6ad4Rgk5xy5v8Xt5kOf12WKO4m7FCtOZnekvtEky9M3ITHmxJDP8x9k3" width="624"></b></p>

<p dir="ltr">Our simulation calibration approach, depicted in the center of the diagram, takes as input traces obtained from the real-world execution of a CI system of interest (left-hand side of the diagram). Using an efficient calibration algorithm our approach searches for simulation model parameter values that maximize the simulation accuracy metric. This is done by repeatedly invoking a simulator of the CI system with different parameter values. Once parameter values have been instantiated so as to maximize simulation accuracy, they are output by our approach. These parameter values can then be used to configure the simulator so that its output has high accuracy (right-hand side of the diagram).</p>

<p>To evaluate the feasibility and effectiveness of our proposed approach, we are using Chameleon as our real-world system. Specifically, on our Chameleon allocation we have installed the <a href="http://pegasus.isi.edu/">Pegasus</a> workflow management system, the <a href="http://htcondor.org/">HTCondor</a> workload management system, and the <a href="https://slurm.schedmd.com/">Slurm</a> batch scheduler. This installation serves as an exemplar of a multi-component, production CI system. We use this system to execute workflow applications, both synthetically generated and from production scientific applications.  These executions provide us with a relevant case-study for driving and evaluating our proposed approach. We plan to make our appliance available in Chameleon's Appliance Catalog, thus other researchers can also use this installation to evaluate their Pegasus workflows in small and large scale scenarios under a controlled environment.</p>

<p><br>
 </p>

<p dir="ltr"><b id="docs-internal-guid-add448e5-7fff-26c8-41ee-25ce8319744f">On testbed needs: </b></p>

<p dir="ltr">Chameleon provides an easily configurable cloud testbed for conducting our experiments under a controlled environment. While it is possible to conduct our research on most cloud platforms, Chameleon has facilitated the calibration work as it is able to provide a consistent (both hardware and software stacks) baseline for our executions. The high-connectivity between Chameleon nodes also significantly reduces noise in communication overheads, which would harm our proposed calibration procedure due to inconsistencies in measurements.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-add448e5-7fff-26c8-41ee-25ce8319744f">On staying motivated through a long research project: </b></p>

<p dir="ltr">Having weekly and monthly goals really helps to progress the work for the project as a whole. It is much easier for me to be motivated when I can see tangible progress, even if the objectives I am checking off are only minor things. </p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-add448e5-7fff-26c8-41ee-25ce8319744f">On choosing his research direction: </b></p>

<p dir="ltr">This project came out of a brainstorming session with several other researchers on the WRENCH team. It is particularly interesting because of the nature of the rest of our work, calibration is such a necessary part of any project involving simulation. A good result here can have long-reaching implications for much else that we are doing. </p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-add448e5-7fff-26c8-41ee-25ce8319744f">On encountering obstacles that can stand in the way of experimentation: </b></p>

<p dir="ltr">This has happened many times in the course of this project alone. It usually comes down to the time needed to set up the experiment versus the potential importance of the results. I would like to try many different things, but often it comes down to how many hours are in the day and having to prioritize only the ones with the most favorable odds of producing something interesting. </p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-add448e5-7fff-26c8-41ee-25ce8319744f">On his most powerful piece of advice:</b> </p>

<p dir="ltr">I would recommend that you find an area that you are interested in, but also one that you do not know so well; that way you can explore during your research and learn in more ways than one. For finding a new research project: keep yourself open to opportunities that present themselves, even in unexpected directions. </p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-add448e5-7fff-26c8-41ee-25ce8319744f">On related artifacts that will be available for interested users to interact with:</b> </p>

<p dir="ltr">At this time, I am writing my M.S. thesis that describes our proposed approach, explains how Chameleon was used for providing input to our simulation calibration approach, and discusses obtained experimental results. A research article is also being written. We expect both of these publications to be completed within the next few months, at which point they will be available on the WRENCH project’s web site (<a href="https://wrench-project.org/">https://wrench-project.org</a>).  We used the WRENCH simulation framework for building the simulator of our target system, and this simulator will be released under an open-source license in the upcoming months as well.  </p>

<p> </p>