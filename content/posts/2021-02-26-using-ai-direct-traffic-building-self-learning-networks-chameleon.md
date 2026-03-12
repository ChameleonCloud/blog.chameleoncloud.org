---
abstract: "<p>Dr. Mariam Kiran is a research scientist in the Scientific Networking\
  \ Division, as a member of\_the Prototypes and Testbed group at ESnet, LBNL, and\
  \ is leading research efforts in AI solutions for operational network research and\
  \ engineering problems. In this blog, she discusses her research project<b id=\"\
  docs-internal-guid-c2d515f6-7fff-2560-66e6-8f226b7526ac\">\_</b>DAPHNE (Deep and\
  \ Autonomous High-speed Networks), her use of Chameleon, and her research background.</p>"
authors:
- Mariam Kiran
categories:
- User Experiments
date: '2021-02-26 16:26:31+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/e3/6c/e36c5714-49f4-4769-95ee-260084b005be/new-mk.jpeg
related_posts: []
slug: using-ai-direct-traffic-building-self-learning-networks-chameleon
subtitle: ''
title: 'Using AI to Direct Traffic: Building Self Learning Networks on Chameleon'
---

<p>Dr. Mariam Kiran is a research scientist in the Scientific Networking Division, as a member of the Prototypes and Testbed group at ESnet, LBNL, and is leading research efforts in AI solutions for operational network research and engineering problems. She has a Ph.D. in Computer Science and is exploring learning and decentralized optimization of distributed computing system architectures, wide area networks, wireless, and Cloud infrastructures. She is also one of the developers of <a href="http://www.flame.ac.uk/">FLAME</a>, an open-source agent-based framework being used world-wide for multi-disciplinary research.</p>

<p dir="ltr">Before joining the lab in 2016, Dr. Kiran worked at Universities of Sheffield, Leeds, and University College London, with collaborations with European industries such as SAP, ATOS, and BT. She was selected as the Royal Society's Scientists in Westminster in 2015 and is the recipient of the 2017 U.S. DOE Early Career Award. She is the PI and co-PI on multiple deep learning and artificial intelligence and control for infrastructure projects such as smart networks, buildings, and accelerators technologies. She is a member of ACM and a Senior IEEE member. Her hobbies include hiking, pottery, restoring old furniture and painting. </p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-b6117d07-7fff-70cc-a5fb-5c13f8ffb30a">On her current research:</b></p>

<p dir="ltr">The new advances in supercomputing and high-speed detector capabilities, including for DOE science applications, means data will be produced at exponential rates, going into Exa and Petascales. Consequently, our networking infrastructures need to cope with these demands while also providing flexible and reliable  global connectivity. One approach is to buy very expensive hardware, upgrade network links, and install data hubs everywhere to make it easy to move data around at optimal speeds, but this is not sustainable. My vision is to get the most utilization of what we have and only upgrade if necessary. I'm working on strategies to optimize current infrastructures, so that they can operate with higher flow throughput with less packet loss, and provide seamless end-to-end connectivity for science applications.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-b6117d07-7fff-70cc-a5fb-5c13f8ffb30a">On approaching the research challenge: </b></p>

<p dir="ltr">In my DOE Early Career project, DAPHNE (Deep and Autonomous High-speed Networks), I'm exploring the use of AI (particularly deep learning) to allow the network to self-learn and improve data transfers, provide guaranteed transfers, and improve traffic engineering. For this, I have been developing a number of tools. These include  advanced network monitoring like NetGraf, and an automation and intelligent traffic controller known as 'DeepRoute Controller', which essentially uses deep reinforcement learning algorithms to learn network bandwidth and packet loss patterns, and uses these 'learned patterns' to route incoming flows onto paths where there is less loss and maximum throughput in order to achieve best flow completion times. With a DOE ASCR Early Career grant, my goal is to test this out and try to deploy an AI Controller for DOE networks, aka ESnet.</p>

<p> </p>

<p dir="ltr">The block diagram in the figure shows the various building blocks of an intelligent network being built in DAPHNE.</p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-b6117d07-7fff-70cc-a5fb-5c13f8ffb30a"><img height="482" src="https://lh4.googleusercontent.com/_g7wnJyCsf0o5-uDmT3Em24WBlZwvy--N6pCJogw2Q222gNqzGg7lITVGfadlLcByq0jYutGjqGZzCeV0rS-TSJKsb6jr5INn8bl2DNTPZcflNo0tyk2ZY9wwSfeXefx867oZVBs" width="586"></b></p>

<p dir="ltr" style="text-align: center;">Figure 1: Network Intelligence tools being implemented as part of DAPHNE</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-b6117d07-7fff-70cc-a5fb-5c13f8ffb30a">On testbed needs:</b></p>

<p dir="ltr">Chameleon has been instrumental in providing the resources for the ideas being developed in the DAPHNE project. Because Chameleon is based on OpenStack and a number of open source tools, it offers many services to researchers and users to develop their own bespoke services. With my focus on networks, Chameleon offers me many advantages compared to other testbed tools, such as:</p>

<ul>
	<li dir="ltr">
	<p dir="ltr">The 'bring your own controller' capability where I can develop my own virtual network controller on top of Ryu code, such as DeepRoute interacting with Openflow commands.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">I can set up complex networks with multiple paths and hops, sometimes through stitching with Exogeni for dedicated bandwidth. We have been building various topologies exploiting both the Texas and Chicago sites to either host our VMs or routers.  </p>
	</li>
	<li dir="ltr">
	<p dir="ltr">In my past, I have experimented with OpenStack and also built services using AWS and Google Cloud for complex big data processing. All of this experience helps me understand and build things using Chameleon and to use its modular architecture effectively. </p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Because Chameleon is all virtual, I'm not held back by the capability of the hardware. I have recently started working with ESnet's SDN testbed. The hardware available there is different, such as Corsa switches, here I am still learning how to communicate the openflow-like commands to reroute flows. It's a learning curve, but it was great to quickly build and test the experiment on Chameleon before transitioning to other complex hardware.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">In NetGraf, we have been developing this idea of a “one dashboard for all” approach (installing various open-source network monitoring tools on Chameleon nodes) and then filtering the data into one Grafana location. We experimented with netflow, snmp and loss statistics, now we are working with Chameleon engineers to see how we can replace the monitoring tools with sflow monitoring data. This is mainly because the open-source tools introduce a lot of noise on the monitoring data collected. We believe sflow will provide more detailed accuracy as flows change direction in the network.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">And importantly, none of this would be possible without the support Chameleon provides for its users. The Chameleon blogs provide examples I make great use of, and there is easy to use documentation in the form of jupyter notebooks but also terminal commands. Chameleon’s support community is also very quick to respond to questions and tickets, helping us through challenges when we face them.</p>
	</li>
</ul>

<p dir="ltr">Chameleon has been a concrete part of my research and I think is essential for network researchers. The flexibility it offers due to the virtualization capability and the various features, allows us to build crazy thought experiments, which in some cases (1) cannot be built or tested on available hardware unless you have large amounts of money and (2) allow us to test our theories before we deploy any controllers to network operations, especially where one wants to develop experiments that go beyond the realm of ‘simulations’. You can do real traffic tests, collect real TCP traces and build complexity to test theories. If I were to name things to be added, having more Chameleon sites would be great, so we can easily build complex topologies of various nodes spanning across the various cities or adding more capability to go above 10GB in the network links to test massive data transfers.</p>

<p style="text-align: center;"><b id="docs-internal-guid-b6117d07-7fff-70cc-a5fb-5c13f8ffb30a"><img height="400" src="https://lh5.googleusercontent.com/pV2ZHGmLM6EclVfJbob8njnDBg0VEiGtlVEzCQqa0VmzMTMBcsJZZoUKIGe0jMLaAKICxM-suhd30fezoJEGfSm6PcQsBeFnDVCczS4grvAHYdnY0XMDqvNlkhwM72vJnYmF5IZu" width="267"></b></p>

<p dir="ltr" style="text-align: center;">Image courtesy of Dr. Kiran</p>

<p dir="ltr"><b id="docs-internal-guid-b6117d07-7fff-70cc-a5fb-5c13f8ffb30a">On staying motivated through a long research project: </b></p>

<p dir="ltr">I have an excellent team of postdocs and students who work with me. They constantly are engaged and bring interesting ideas and challenges that keep things interesting.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-b6117d07-7fff-70cc-a5fb-5c13f8ffb30a">On researchers she admires: </b></p>

<p dir="ltr">Too many to name. I am lucky to have great colleagues at ESnet, LBNL, and even other DOE labs and projects I am working with. With a lot of them, such as in the Panorama team, we have collectively done a number of experiments on Chameleon and published papers. </p>

<p><br>
 </p>

<p dir="ltr"><b id="docs-internal-guid-b6117d07-7fff-70cc-a5fb-5c13f8ffb30a">On choosing her research direction: </b></p>

<p dir="ltr">Initially, I was inspired by Google’s AlphaGo experiment, and basically asked whether we could do the same for networks. But over the past 3 years I discovered there are so many more questions to explore in this area of AI-controlled infrastructure that are fascinating challenges that can lead us to building self-driving labs. </p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-b6117d07-7fff-70cc-a5fb-5c13f8ffb30a">On obstacles that can stand in the way of experimentation: </b></p>

<p dir="ltr">Usually it is the cost of expensive hardware, or learning the limitations of certain tools that stand in the way. But I learn from these experiences, because as researchers, this can be when you work with cheaper machines and also develop new tools which expand the capabilities to what we need.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-b6117d07-7fff-70cc-a5fb-5c13f8ffb30a">On her most powerful piece of advice for people beginning research: </b></p>

<p dir="ltr">I was once given advice to ENJOY the work you do, and that really changed my productivity. I went from being stressed to just enjoying the work, and that shows through in my progress.</p>

<p> </p>

<p dir="ltr"><strong>Interested readers can learn more about Dr. Kiran’s current experiments and see related open source code at the <a href="https://sites.google.com/lbl.gov/daphne/home">DAPHNE project’s website</a>. </strong></p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-b6117d07-7fff-70cc-a5fb-5c13f8ffb30a">A sample of papers published using Chameleon as a testbed:</b></p>

<ul>
	<li dir="ltr">
	<p dir="ltr">D Kaur, B Mohammad, M Kiran, NetGraf: A Collaborative Network Monitoring Stack for Network Experimental Testbeds, Poster Accepted, SC '20: ACM/IEEE Supercomputing Conference, November 17–19, 2020</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">M Kiran, B Mohammed, N Krishnaswamy, DeepRoute: Herding Elephant and Mice Flows with Reinforcement Learning, 2nd IFIP International Conference on Machine Learning for Networking (MLN'2019)</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">B Mohammed, M Kiran, N Krishnaswamy, DeepRoute on Chameleon: Experimenting with Large-scale Reinforcement Learning and SDN on Chameleon Testbed, 2019 IEEE 27th International Conference on Network Protocols (ICNP), 1-2</p>
	</li>
</ul>

<p><br>
 </p>