---
abstract: "<p>Learn about University of Chicago PhD student Chengcheng Wan's research\
  \ on designing a solution to integrate machine learning components into traditional\
  \ software systems to maximize energy\_efficiency, latency, and accuracy constraints\
  \ at machine learning, system and application levels, with related research published\
  \ at USENIX ATC, ICML, and ICSE.</p>"
authors:
- Chengcheng Wan
categories:
- User Experiments
date: '2021-10-18 17:05:35+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/5f/36/5f36126d-a47d-42b8-8113-490c3cd2f0d3/screen_shot_2021-10-18_at_65547_pm.png
related_posts: []
slug: alert-accurate-anytime-learning-for-energy-and-timeliness-in-software-systems
subtitle: ''
title: 'ALERT: Accurate Anytime Learning for energy and timeliness in software systems'
---

<p dir="ltr"><b id="docs-internal-guid-4e1d5bbb-7fff-113d-dd1b-ebfb937088c7">On the current research:</b></p>

<p dir="ltr">An increasing number of software applications incorporate Deep Neural Networks (DNNs) to process sensor data and return inference results to humans. Effective deployment of DNNs in these interactive scenarios requires meeting latency and accuracy constraints while minimizing energy.  However, there exist many challenges in integrating ML components into traditional software systems.</p>

<p dir="ltr">At the machine learning level, traditional neural networks are not flexible enough for the dynamic software-deployment environment. Applications often have different accuracy, performance, and energy consumption requirements at different stages of the execution or under different interaction contexts.The software and hardware resource provisioning also changes in an unpredictable way at run time. However, a traditional neural network cannot easily adapt itself, having to complete all the predefined computations to produce one inference result.</p>

<p dir="ltr">At the system level, for a machine learning integrated software, dynamically managing its resources faces unique challenges: (1) machine-learning components offer unique accuracy-performance-energy tradeoffs; (2) the combined neural network and software system configuration space is huge; (3) the resource-management and system-configuration decision making needs to be very fast, to not delay the neural-network inference.</p>

<p dir="ltr">At the application level, developing, testing, and fixing machine learning software systems requires cross-domain efforts. For non-experts, using a third-party machine-learning API is much easier than building a neural network from scratch. However, challenges still exist: unlike traditional APIs that are coded to perform well-defined algorithms, ML APIs are trained to perform cognitive tasks whose input are digitized real-world visual, audio and text content, and whose semantics cannot be reduced to concise mathematical or logical specifications. As a result, it is challenging for developers to use these APIs correctly and efficiently.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-4e1d5bbb-7fff-113d-dd1b-ebfb937088c7">On approaching the research challenge:</b></p>

<p dir="ltr">To tackle these problems, our project offers support at three layers: </p>

<p dir="ltr">At the machine learning level, I have proposed a novel neural network architecture and a customized optimizer that supports anytime prediction—one neural network is able to generate a series of increasingly accurate outputs over time without sacrificing accuracy for flexibility. Our experiments demonstrate synergy between our architecture and optimizer: our anytime neural networks perform almost as well as independent non-anytime neural networks of the same size. <a href="https://arxiv.org/abs/2008.06635">(ICML’20)</a></p>

<p dir="ltr">At the system level, I have designed a runtime scheduler ALERT, which holistically configures neural networks and system resources together to meet application-specific accuracy, performance, and energy-consumption constraints. As shown in Figure 1, ALERT is a feedback-based run-time. It measures inference accuracy, latency, and energy consumption; it checks whether the requirements on these goals are met; and, it then outputs both system and application-level configurations adjusted to the current requirements and operating conditions.  <a href="https://arxiv.org/abs/1911.00119">(ATC’20)</a></p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-4e1d5bbb-7fff-113d-dd1b-ebfb937088c7"><img height="254" src="https://lh5.googleusercontent.com/XSAqF9oEb_WQKf9RXzugAxhQZABEl2ZDgao1AJQ3dO67JzKFqpgyn_lU-IJkaw_6BGnAapx8wuH4n3nVg2DawRU5OO9H-129C2ExPgXPnM8cXHWoowJy1KwRcn3fu8TnA5zAMaQj=s0" width="418"></b></p>

<p dir="ltr">At the application level, I conducted the first comprehensive study about how real-world applications are using machine learning APIs. I found that misuse or improper calling of ML APIs is widespread and severe: 69% of applications contain instances of misuse in their latest version, more than half of them multiple times. The root cause is the nature of machine learning tasks: unique semantics, complicated data requirements, and accuracy-performance tradeoffs. This misuse leads to various types of problems, including reduced functionality, degraded performance, and increased cost. My study identified close to 1,000 instances of machine learning API misuse in the latest versions of open-source applications, with over half of the studied applications containing at least one. <a href="http://people.cs.uchicago.edu/~cwan/paper/ml_api.pdf">(ICSE21)</a></p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-4e1d5bbb-7fff-113d-dd1b-ebfb937088c7">On testbed needs:</b></p>

<p dir="ltr">We greatly benefit from Chameleon in two ways.  First, the access to powerful  GPU resources allows us to conduct a large amount of training experiments for our anytime network project. Second, the access to model-specific registers (MSR) under Chameleon’s bare-metal configuration allows us to conduct experiments related to dynamic voltage and frequency scaling (DVFS) for our ALERT project. Chameleon’s bare-metal reconfiguration feature also greatly helps us to set up the experimental environment.</p>

<p dir="ltr">If Chameleon was not available, it may take us years instead of a couple of months to finish our DNN training experiments and hence our anytime neural network design. It would also cause us to miss some important testing platforms in our ALERT DVFS experiments. </p>

<p style="text-align: center;"><b id="docs-internal-guid-4e1d5bbb-7fff-113d-dd1b-ebfb937088c7"><img height="572" src="https://lh4.googleusercontent.com/a5eUShDxwxFFh9bE608KIRtSvghza8GnA51lz2HL2zsv6Jg5KEogOjjGBLPVaCa29uAo3Gjo1ypfFF3YjyQsmwYBAt412L0P_3Q63B_cvPudvYS-5bjJkoMcCuWTf2z7CkCahcy_=s0" width="424"></b></p>

<p style="text-align: center;"><b>Chengcheng Wan</b></p>

<p dir="ltr"><b id="docs-internal-guid-4e1d5bbb-7fff-113d-dd1b-ebfb937088c7">On the author:</b> </p>

<p dir="ltr">Chengcheng Wan is a fifth-year Ph.D. student in the Department of Computer Science at the University of Chicago, advised by Professor Shan Lu. Her research focuses on creating robust methods to incorporate neural networks into software systems to satisfy accuracy, performance, and energy-efficiency requirements across a variety of platforms and applications. Her research has led to first author papers published at top conferences (USENIX ATC, ICML, ICSE). She has been awarded Siebel Scholar, Microsoft Dissertation Grant in 2021, invited to the EECS Rising Stars workshop in 2020, and the SIGSOFT Distinguished Paper Award in 2019. Wan has served as a mentor in the UChicago undergrad summer research program and an instructor for middle-school girls in the compileHer program.</p>

<p dir="ltr">Wan‘s career plan is to get a faculty job after graduation. Her research goal is to create systemic approaches for building correct and efficient AI systems that solve real-world problems. She is also interested in encouraging and guiding young students to participate in research work.</p>

<p dir="ltr">Besides research life, Wan likes playing 4X video games, especially Stellaris, Crusader Kings, and Sid Meier's Civilization. She enjoys exploring the infinite world in the game and making strategic decisions to affect it. These games allow her to experience the rise and fall of dynasties and the joys and sorrows of characters within a few hours. As a CS person, she also “hacks” these stand-alone games to have more fun from a more diversified game process.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-4e1d5bbb-7fff-113d-dd1b-ebfb937088c7">On staying motivated during a long research project:</b></p>

<p dir="ltr">The key is to break it into several small tasks and set up milestones for them. While a long research project is exhausting, a timely positive feedback refreshes the researchers. It could be a publication, a talk, a poster, or other forms of wrap up. I use them as milestones and get feedback from other researchers to confirm that I am going in the right direction, which builds the sense of accomplishment. In addition, separating a long research project into several phases also helps to capture the big picture ---- where I am and what’s remaining to be done. This sense of control further strengthens motivation.</p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-4e1d5bbb-7fff-113d-dd1b-ebfb937088c7">On her most powerful piece of advice for new researchers and students:</b></p>

<ol>
	<li dir="ltr">
	<p dir="ltr">Keep updated with publications and research events in your domain.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Get feedback from colleagues and other researchers. People from other domains may have a different perspective.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Keep connected with industry. Many research problems are inspired by the real-world problems that are formulated by industry.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Make plans and keep deadlines. A good time schedule greatly improves efficiency.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Stay positive and be inspired. </p>
	</li>
</ol>

<p> </p>

<p dir="ltr"><strong>Interested readers can explore the following resources for more information:</strong></p>

<p dir="ltr">We published three papers with the help of Chameleon resource, under the funding support of NSF (CNS-1764039, CNS-1956180):</p>

<ol>
	<li dir="ltr">
	<p dir="ltr">[USENIX ATC 2020] Chengcheng Wan, Muhammad Santriaji, Eri Rogers, Henry Hoffmann, Michael Maire, Shan Lu. “ALERT: Accurate Learning for Energy and Timeliness” </p>

	<ol>
		<li dir="ltr">
		<p dir="ltr"><a href="https://arxiv.org/abs/1911.00119">https://arxiv.org/abs/1911.00119</a></p>
		</li>
	</ol>
	</li>
	<li dir="ltr">
	<p dir="ltr">[ICML 2020] Chengcheng Wan, Henry Hoffmann, Shan Lu, Michael Maire. “Orthogonalized SGD and Nested Architectures for Anytime Neural Networks”</p>

	<ol>
		<li dir="ltr">
		<p dir="ltr"><a href="https://arxiv.org/abs/2008.06635">https://arxiv.org/abs/2008.06635</a></p>
		</li>
	</ol>
	</li>
	<li dir="ltr">
	<p dir="ltr">[ICSE 2021] Chengcheng Wan, Shicheng Liu, Henry Hoffmann, Michael Maire, Shan Lu. “Are Machine Learning Cloud APIs Used Correctly?”</p>

	<ol>
		<li dir="ltr">
		<p dir="ltr"><a href="http://people.cs.uchicago.edu/~cwan/paper/ml_api.pdf">http://people.cs.uchicago.edu/~cwan/paper/ml_api.pdf</a></p>
		</li>
		<li dir="ltr">
		<p dir="ltr"><a href="https://github.com/mlapistudy/ICSE2021_421">https://github.com/mlapistudy/ICSE2021_421</a></p>
		</li>
	</ol>
	</li>
</ol>

<p>We have a project webpage at <a href="https://alert.cs.uchicago.edu/">https://alert.cs.uchicago.edu</a>.</p>