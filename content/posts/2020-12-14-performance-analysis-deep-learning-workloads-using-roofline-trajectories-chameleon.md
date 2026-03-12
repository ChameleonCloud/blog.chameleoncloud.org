---
abstract: <p>Dr. Xiaoyi Lu is a research assistant professor at The Ohio State University
  focusing on High Performance Interconnects and Protocols, Big Data Computing, Deep
  Learning, Parallel Computing, Virtualization, and Cloud Computing. In this blog
  post, we explore his research and usage of Chameleon Cloud.</p>
authors:
- Xiaoyi Lu
categories:
- User Experiments
date: '2020-12-14 23:49:00+00:00'
featured: false
hide_image: true
image: ''
related_posts: []
slug: performance-analysis-deep-learning-workloads-using-roofline-trajectories-chameleon
subtitle: ''
title: Performance Analysis of Deep Learning Workloads Using Roofline Trajectories
  on Chameleon
---

<p dir="ltr"><b id="docs-internal-guid-ace60b3f-7fff-53ab-d7af-cb720f260d5d"><img height="316" src="https://lh3.googleusercontent.com/vVGfwEbbgbiUYu3s88ZF3xNYuWXN4i8yJu1-ZCO82CCtsZ3PwKVvaZfUv1iewVNJeOBEpG23JG0xHr-pON3X_bWk_qAph-iZuxvF-KHpaEWVfG-nYQa9sBFCfu5HLWuzfpyseh2M" width="316"></b></p>

<p dir="ltr"><b>Image Courtesy of Dr. Lu</b></p>

<p dir="ltr">Dr. Xiaoyi Lu is a research assistant professor at The Ohio State University focusing on High Performance Interconnects and Protocols, Big Data Computing, Deep Learning, Parallel Computing, Virtualization, and Cloud Computing. In this blog post, we explore his research and usage of Chameleon Cloud. </p>

<p dir="ltr"><b id="docs-internal-guid-97b83534-7fff-22af-4310-943d29516e27">On his current research project: </b>Over the last decade, technologies derived from convolutional neural networks (CNNs) called Deep Learning applications, have revolutionized fields as diverse as cancer detection, self-driving cars, virtual assistants, etc. However, many users of such applications are not experts in Machine Learning itself. Consequently, there is limited knowledge among the community to run such applications in an optimized manner. For such users to make effective use of resources at their disposal, concerted efforts are necessary to figure out optimal hardware and software configurations.<b id="docs-internal-guid-97b83534-7fff-22af-4310-943d29516e27"> </b></p>

<p dir="ltr"><b id="docs-internal-guid-97b83534-7fff-22af-4310-943d29516e27">On approaching the research challenge:</b> In this context, my team at The Ohio State University, collaborated with Dr. Ibrahim from Lawrence Berkeley National Laboratory, proposed to use the Roofline Trajectory model to perform a systematic analysis of representative CNN models and identify opportunities for black box and application-aware optimizations. Our approach is able to identify various bottlenecks that allow us to significantly improve the training performance of these CNN models. We hope that our study would be helpful for scientists, especially those who may not have enough knowledge of low-level systems, to optimize their Deep Learning model training processes and maximize the performance. Using the findings from our study, we are able to obtain up to 3.5× speedup compared to vanilla TensorFlow-based CNN training with default configurations. We perform our research tasks on the Chameleon Cloud platform, which include writing &amp; debugging codes, running experiments, collecting results, and data analysis.</p>

<p dir="ltr"><b id="docs-internal-guid-97b83534-7fff-22af-4310-943d29516e27">On testbed needs: </b>Chameleon Cloud can provide bare-metal machines with root permission access. This is significantly important since many of our experiments need to monitor and collect low-level hardware and systems counters. Without bare-metal machines with root permission, it is impossible to do these kinds of studies. This is one of the major differences between Chameleon Cloud and other HPC platforms.</p>

<p dir="ltr"><b id="docs-internal-guid-97b83534-7fff-22af-4310-943d29516e27">On the origins of the direction of this research: </b>This work was done by one of my students, Mr. Haseeb Javed. He did his internship job at LBNL with Dr. Ibrahim. We think this is an interesting research direction for his thesis. </p>

<p dir="ltr"><b id="docs-internal-guid-97b83534-7fff-22af-4310-943d29516e27">On his most powerful piece of advice for students beginning research: </b>Think Big, Start Small, Move Fast!</p>

<p dir="ltr"> </p>

<p dir="ltr">Interested readers can explore the results of Dr. Lu’s research published as <a href="https://link.springer.com/article/10.1007/s42514-019-00018-4">Performance analysis of deep learning workloads using roofline trajectories</a>. </p>