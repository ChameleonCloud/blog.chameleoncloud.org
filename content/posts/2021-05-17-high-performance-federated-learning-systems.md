---
abstract: "<p>This work is part of George Mason University PhD student Zheng Chai\
  \ and Prof. Yue Cheng\u2019s research on solving federated learning (FL) bottlenecks\
  \ for edge devices. Learn more about the authors, their research, and their novel\
  \ FL training system, FedAT which already has impressive results, improving prediction\
  \ performance by up to 21.09% and reducing communication cost by up to 8.5 times\
  \ compared to state-of-the-art FL systems.</p>"
authors:
- Zheng Chai
categories:
- User Experiments
date: '2021-05-17 23:29:26+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/35/c7/35c7aeaf-5e67-4cb9-942f-a63299606549/system-overview.png
related_posts: []
slug: high-performance-federated-learning-systems
subtitle: ''
title: High-Performance Federated Learning Systems
---

<p dir="ltr">This work is part of George Mason University PhD student Zheng Chai and Prof. Yue Cheng’s research on solving federated learning (FL) bottlenecks for edge devices. Learn more about the authors, their research, and their novel FL training system, FedAT which already has impressive results, improving prediction performance by up to 21.09% and reducing communication cost by up to 8.5 times compared to state-of-the-art FL systems.</p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-cd6db26f-7fff-d779-017c-6d1c7389c06a">On the current research: </b></p>

<p dir="ltr">Our research is focused on solving traditional bottlenecks of Federated Learning (FL), FL is a machine learning technique that learns a shared model across decentralized edge devices without exchanging local devices data. First, a little background about FL. In a typical FL framework, a shared model is learned from a large number of distributed clients with the coordination of a centralized server. Different clients in a FL deployment do not share the training dataset with each other due to security and privacy reasons. Instead, each client trains a local model using its local data; the server aggregates the learned gradients of all local models in order to train a global model. Google keyboard next-word prediction (<a href="https://arxiv.org/pdf/1811.03604.pdf">Hard et al.</a> and <a href="https://arxiv.org/pdf/1812.02903.pdf">Yang et al.</a>) is a typical application of FL.</p>

<p dir="ltr">This form of collaborative learning exposes new challenges as well as new tradeoffs among model convergence speed, model accuracy, balance across clients, and communication cost. Some challenges include: </p>

<p dir="ltr">(1) straggler problem---Clients have training time (including transmission time) heterogeneity due to data or (computing and network) resource heterogeneity. In synchronous FL systems, the training time of one round depends on the training time of the slowest client. stragglers could slow down the training process and reduce the overall performance. </p>

<p dir="ltr">(2)<b> </b>communication bottleneck---where a large number of clients communicate their local updates to a central server and bottleneck the server. </p>

<p>Many existing FL methods focus on optimizing along a single dimension of the tradeoff space (e.g., <a href="https://arxiv.org/abs/1903.03934">Xie et al.</a>; <a href="https://ieeexplore.ieee.org/abstract/document/8945292">Chen et al.</a>; <a href="https://arxiv.org/abs/1811.11479">Jeong et al.</a>; <a href="https://ieeexplore.ieee.org/abstract/document/8917724">Mills et al.</a> ). Existing solutions use asynchronous model updating or tiering-based, synchronous mechanisms to tackle the straggler problem. However, asynchronous methods can easily create a communication bottleneck, while tiering the clients into different tiers may introduce biases that favor faster tiers with shorter response latencies. </p>

<p><br>
 </p>

<p dir="ltr"><b id="docs-internal-guid-cd6db26f-7fff-d779-017c-6d1c7389c06a">On approaching the research challenge: </b></p>

<p dir="ltr">To address these issues, we present FedAT, a novel FL training system with asynchronous tiers under Non-i.i.d. training data, Non-i.i.d. denotes Independent and Identically Distributed and means different data distribution among clients. FedAT synergistically combines synchronous, intra-tier training and asynchronous, cross-tier training. By bridging the synchronous and asynchronous training through tiering, FedAT minimizes the straggler effect with improved convergence speed and test accuracy. FedAT uses a straggler-aware, weighted aggregation heuristic to steer and balance the training across clients for further accuracy improvement. FedAT compresses uplink and downlink communications using an efficient, polyline-encoding-based compression algorithm, which minimizes the communication cost. Results show that FedAT improves the prediction performance by up to 21.09% and reduces the communication cost by up to 8.5 times, compared to state-of-the-art federated learning methods. </p>

<p> </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-cd6db26f-7fff-d779-017c-6d1c7389c06a"><img height="468" src="https://lh3.googleusercontent.com/uZ1skw2hKNIlVBkTVAs7htvPJwggWbFtXKxdsaoow7XZ4pcLURrAaDJxzJVpcKaoUadGfoARGN37Bg57REmqnOEAOgWrunx7wNBx7G33tP6urroelANcGtl1lr7r040Uuzv00ati" width="624"></b></p>

<p> </p>

<p dir="ltr">The figure above shows the training process of FedAT. The tiering module profiles and partitions involved clients into <em>M</em> tiers based on their response latencies. The server maintains a list of <em>M</em> models, one for each tier, reflecting the most updated view of per-tier local models, at a certain round <em>t</em>. Correspondingly, the server also maintains a global model w that gets asynchronously updated from <em>M</em> tiers. Each tier performs synchronous update process, a fraction of clients are selected randomly and compute the gradient of the loss on their local data, then send the compressed weights to the server for a synchronous update to the tier model on the server.</p>

<p dir="ltr">FedAT expands on our existing work called <a href="https://dl.acm.org/doi/abs/10.1145/3369583.3392686">TiFL [HPDC’20]</a>, which is a synchronous, tiered FL system that adaptively classifies clients into different tiers based on performance and training quality. </p>

<p><br>
 </p>

<p dir="ltr"><b id="docs-internal-guid-cd6db26f-7fff-d779-017c-6d1c7389c06a">On testbed needs: </b></p>

<p dir="ltr">Chameleon’s bare-metal feature is unique for us. Since communication efficiency is one of the advantages proposed by our model, the network traffic between the server and clients is a valuable evaluation metric when comparing our approach with other state-of-the-art FL methods. This feature allows us to record the traffic precisely. In addition, Chameleon’s bare-metal servers are equipped with powerful computing and memory resources; this enables us to conduct medium- and large-scale FL simulation studies that target a diversified range of hardware configurations for a large number of training clients. </p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-cd6db26f-7fff-d779-017c-6d1c7389c06a">On encountering obstacles that stand in the way of FL experimentation: </b></p>

<p dir="ltr">Due to the lack of a real-world FL testbed, current FL research work and research prototypes are evaluated on small- to medium-scale testbed clusters using simulated FL clients. While a simulated experimental deployment provides a well-controlled environment for verification and validation purposes, it is often difficult for simulated testbeds to faithfully capture all the workload assumptions that may exist in a real-world FL deployment. It would be desirable to have access to large-scale testbeds with real-world edge devices such as microservers and smartphones, for systems research such as FL systems optimizations and redesign. </p>

<p dir="ltr"> </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-cd6db26f-7fff-d779-017c-6d1c7389c06a"><img height="345.26073655779663" src="https://lh4.googleusercontent.com/NNrSmPXbDKgSQ4mT-R6h4yxIXfUx8eiGPyFfYEnUWZjVDqNA8tnfLwIgWjyza_w2YJGxKn1IcmXKZzfynKyQG-4yOWotqyPUT4pgtTaWJoqbh2Vpejo-X-eMtITpywKC6nuzIl6k" width="260">   <img height="310" src="https://lh6.googleusercontent.com/3J8Ks-K-nAnr1xPOq_SKS7IxkGRjA80d-SvMAhkZm-eLIj58XR9wDXf5x6uGiejHlx_dbRZGI-bKi7VXqgoFJiV1BDr8f7hRTQGlw76cEHuK-c-ufDQTDxV8Lsp_ZHh89MLEL6lH" width="277"></b></p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-cd6db26f-7fff-d779-017c-6d1c7389c06a">      </b>Images of Zheng Chai and Prof. Yue Cheng, courtesy of the authors</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-cd6db26f-7fff-d779-017c-6d1c7389c06a">About the authors:</b></p>

<p dir="ltr"><b id="docs-internal-guid-cd6db26f-7fff-d779-017c-6d1c7389c06a">Zheng Chai </b>(<a href="https://zheng-chai.github.io/">https://zheng-chai.github.io/</a>) is a third-year Ph.D. student of Computer Science at George Mason University. He is currently working with Prof. Yue Cheng on distributed systems and machine learning. His major research interests include distributed machine learning system, federated learning system, high-performance computing, and storage system. His research aims at: 1) building high-performance systems for large-scale machine learning, and 2) using machine learning technology to improve computer systems. He hopes to continue his research in systems and machine learning after graduating with a Ph.D. degree. In his free time, he loves running and traveling. </p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-cd6db26f-7fff-d779-017c-6d1c7389c06a">Yue Cheng</b> (<a href="https://cs.gmu.edu/~yuecheng/">https://cs.gmu.edu/~yuecheng/</a>) is an assistant professor of Computer Science at George Mason University. He received his Ph.D. in CS from Virginia Tech in 2017. His research interests include distributed and storage systems, cloud and serverless computing, high-performance computing, and machine learning systems. He is a recipient of several highly-competitive awards and honors such as NSF CAREER Award (2021) and Amazon Research Award (2020). His research has appeared at top conferences such as EuroSys, ATC, FAST, and SC. He has served on the Program Committee of a series of top venues including SC’20 and HPDC’18-21. </p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-cd6db26f-7fff-d779-017c-6d1c7389c06a">On their most powerful piece of advice: </b></p>

<p dir="ltr">By reading we enrich the mind; by conversation we polish it.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-cd6db26f-7fff-d779-017c-6d1c7389c06a">Additional reading: </b></p>

<p dir="ltr">Our latest paper is currently under review. Interested readers can find an arXiv version of the FedAT work at: <a href="https://arxiv.org/abs/2010.05958">https://arxiv.org/abs/2010.05958</a>. The corresponding software artifact will be open source for public use when our paper gets published. </p>