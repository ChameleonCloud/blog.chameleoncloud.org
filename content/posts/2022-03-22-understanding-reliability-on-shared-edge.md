---
abstract: "<p>Learn about how researchers at the University of Chicago are using Chameleon\u2019\
  s new edge computing testbed, CHI@Edge to investigate how resource management can\
  \ be applied to the concept of shared edge to optimize AI applications.</p>"
authors:
- Junchen Jiang
categories:
- User Experiments
date: '2022-03-22 00:38:26+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/63/c8/63c82313-069d-4ebe-ade2-65bd8e7a8dfb/screen_shot_2022-03-22_at_123406_am.png
related_posts: []
slug: understanding-reliability-on-shared-edge
subtitle: ''
title: Understanding Reliability on Shared Edge
---

<p dir="ltr"><b id="docs-internal-guid-f560b925-7fff-694c-5349-d64d387b1211">Authors: </b>Junchen Jiang, Haryadi Gunawi, Yuyang Huang</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-f560b925-7fff-694c-5349-d64d387b1211">What is the central challenge/hypothesis your experiment investigates? </b></p>

<p dir="ltr">As a new breed of AI applications are widely used in our daily lives, the concept of "shared edge" has grown in popularity as a way for multiple AI applications (each running in a container and on a different data stream) to share network bandwidth and compute resources at the edge services. While shared edge offers new opportunities to run more AI applications together, ensuring that these AI applications return highly accurate inference/prediction results has posed a significant challenge to the conventional paradigm of resource management. This is because today's resource allocation systems, designed to optimize traditional notions of throughput and delay, are unable to directly measure AI application's accuracy. What's exciting about this direction is that new frameworks for resource sharing and management are needed. </p>

<p dir="ltr">In this project, we specifically study video-analytics applications, whose emergence has created challenges for resource management in edge environments, because (1) traditionally resource managers don't directly observe accuracy, and (2) modern video analytics applications are highly adaptive, so observing throughput and latency doesn't always reveal changes of accuracy.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-f560b925-7fff-694c-5349-d64d387b1211">How is your research addressing this challenge? </b></p>

<p style="text-align: center;"><br>
<b id="docs-internal-guid-f560b925-7fff-694c-5349-d64d387b1211"><img height="141" src="https://lh6.googleusercontent.com/gsJxe_jDd9KmM838BeK0jmeEd2wP-3Tw4J0oU4qSQkdfqFEvVV0buA3Tc2tG5U2CbYjIVBMGY3iwgSqC5frNeruRbAOP_S44lhmjsU8eTSaPfir9hX-OWt_9OIxgfzvEAGv52owx" width="353"></b></p>

<p dir="ltr">Our project proposes a new resource-management primitive of dynamically monitoring how much each application's accuracy might change with more or less resources. This primitive enables the resource manager to allocate compute/network resources to applications that are most in need of them. To do so, we create a simple-yet-efficient interaction between the resource manager and the video-analytics applications. As illustrated in this figure, each video analytics application (VAP) shares the gradient with respect to the amount of allocated resource changes of its output between two different resource allocations, and then the edge resource manager (left) uses the information to allocate resources among the applications in a way that maximizes the overall improvement of inference. </p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-f560b925-7fff-694c-5349-d64d387b1211">How do you structure your experiment on Chameleon? </b></p>

<p dir="ltr">A typical setup of our experiment consists of one GPU server from the CHI@UC site and one or multiple containers running on CHI@Edge’s Raspberry PI 4 devices, where they are communicating using the Chameleon’s Floating IP. To run the experiment, we first reserve and configure the environments (OS, container, Floating IP, etc.) for the GPU server or edge devices through Chameleon’s GUI. We then modify or start the experiments by SSH-ing onto the corresponding server or containers. In addition, we often use the system snapshot capability (i.e. cc-snapshot) as it can save so much time on configuring the environments (dataset, CUDA, python, etc.) when we need to resume the experiment on a new server. </p>

<p dir="ltr">When we first started using Chameleon, we found the documentation to be particularly detailed and helpful in guiding us through the process like reserving bare-metal servers, starting the servers, or exposing the server with Chameleon’s Float IP. Thus, we recommend anyone who wishes to start experimenting on the Chameleon to follow the documentation and the examples in it because this could help them understand the structure and logistic of the Chameleon testbed. We also found that the Chameleon team has been very helpful and responsive to our questions. <br>
 </p>

<p dir="ltr"><b id="docs-internal-guid-f560b925-7fff-694c-5349-d64d387b1211">What features of the testbed do you need in order to implement your experiment?</b></p>

<p dir="ltr">Since the project is still in its early stage, we have kept the experiment setting as simple and straightforward as possible and have not explored some of Chameleon’s advanced features, such as custom kernel boot or network stitching. However, one feature did play a critical role in our current experiment setting: the bare-metal access to GPU machines with configurable network connections with edge devices. If Chameleon was not available, implementing our experiment would require purchasing a standalone GPU server shared by several projects, and our experiment and the results would be affected by the resource availability of such a server. The bare-metal access to a powerful GPU server on Chameleon significantly reduces the cost of equipment purchasement and hardware maintenance for our experiment.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-f560b925-7fff-694c-5349-d64d387b1211">Can you point us to artifacts connected with your experiment that would be of interest to our readership? </b></p>

<p dir="ltr">We plan to open source the codebase, including the implementation and experiment codes based on Chameleon and CHI@Edge, on a public code repository once they are ready: <a href="https://github.com/ShadowFient/VAP-Concierge">https://github.com/ShadowFient/VAP-Concierge</a></p>

<p> </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-f560b925-7fff-694c-5349-d64d387b1211"><img height="200" src="https://lh6.googleusercontent.com/EAJ_3sv2-Jvt1vd9LveZBNnxHdlIieFmSkwxyu33y_p1Vipb9VCqGeKBMk0j9R7hTNg0yRO3X4p1t9Lzy3tVstnVd-Iy4rgpO5Nlax1LNg7VWtVpSNfZM4nCeyX8RhhV7y2URpVO" width="161"></b></p>

<p dir="ltr" style="text-align: center;">Image courtesy of the author</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-f560b925-7fff-694c-5349-d64d387b1211">About the author: </b></p>

<p dir="ltr">Junchen Jiang is an Assistant Professor of Computer Science at the University of Chicago. He received his PhD degree from Carnegie Mellon University in 2017 and his bachelor's degree from Tsinghua University in 2011. His research interests are networked systems and their intersections with machine learning. He is a recipient of Google Faculty Research Award in 2019, Best Paper Award at the Symposium of Edge Computing in 2020, and CMU School of Computer Science Doctoral Dissertation Award in 2017.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-f560b925-7fff-694c-5349-d64d387b1211">How do you stay motivated through a long research project? </b></p>

<p dir="ltr">As a student, my biggest drive to do research was the feeling that I'm the first to see something no one has seen before. Even if it's a trap ahead and I fall into it, that's still worth it. It was just that simple! </p>

<p dir="ltr"> </p>

<p dir="ltr">As a faculty, though this may sound surprising, the greatest drive for me has always been the passion of my students. It's true that I sometimes motivate students, but once they are warmed up with a project, I'm constantly fascinated by how students lead a project to new directions, and I've always enjoyed being "pushed" by students to bounce off ideas with them, give feedback, and work closely with them before the deadline. </p>