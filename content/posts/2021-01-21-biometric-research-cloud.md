---
abstract: "<p dir=\"ltr\">January\u2019s User Experiment\u2019s blog features Keivan\
  \ Bahmani, a PhD candidate at Clarkson University. Learn more about Bahmani and\
  \ his use of Chameleon for biometric research.</p>"
authors:
- Keivan Bahmani
categories:
- User Experiments
date: '2021-01-21 00:11:10+00:00'
featured: false
hide_image: true
image: ''
related_posts: []
slug: biometric-research-cloud
subtitle: ''
title: Biometric Research in The Cloud
---

<p dir="ltr"><b id="docs-internal-guid-916e52d5-7fff-ab61-179f-f900c4cb53ce">January’s User Experiment’s blog features Keivan Bahmani, a PhD candidate at Clarkson University. Learn more about Bahmani and his use of Chameleon for biometric research.</b></p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-916e52d5-7fff-ab61-179f-f900c4cb53ce">On his background:</b> I remember as a child, I was fascinated by computers and computer networks. Predictably, I got my bachelor of science in Electrical Engineering back in my home country (Iran). Afterward, I moved to Cyprus to continue my education and get my M.S. During my time in Cyprus, I was teaching C++ programming and Computer networking to undergraduate students. Finally, in 2016 I moved to Potsdam, NY to get my Ph.D. in Electrical and Computer Engineering. </p>

<p dir="ltr"> </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-916e52d5-7fff-ab61-179f-f900c4cb53ce"><img height="239" src="https://lh3.googleusercontent.com/dIuzRemyZPx14eO9KfUu3TYD-pGzJ1JW3T9wncMXv_mmbGg6rkbNlnOr5UMAyAcx9tD5PYuK2hcDZqTcC4v3vHDVjIKXyJ0JO___VJqW4KHNHhj35ZqObFPjiP7Sd36DWMZkdiVe" width="423"></b></p>

<p dir="ltr" style="text-align: center;">Figure 1: Teaching high school students about biometrics</p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-916e52d5-7fff-ab61-179f-f900c4cb53ce">On research and personal interests: </b>Currently, I am working under the supervision of Dr. Stephanie Schuckers. My work is mainly focused on pattern recognition and machine learning in Biometrics. More specifically, my current research is on deep learning-based liveness detection in face and fingerprint recognition systems. In my free time, I enjoy playing electric guitar and cooking.</p>

<p> </p>

<p><b id="docs-internal-guid-916e52d5-7fff-ab61-179f-f900c4cb53ce">On his current research and using Chameleon:</b></p>

<p> </p>

<table>
	<colgroup>
		<col width="342">
		<col width="246">
	</colgroup>
	<tbody>
		<tr>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-916e52d5-7fff-ab61-179f-f900c4cb53ce"><img height="233" src="https://lh4.googleusercontent.com/yZA2WhRnqHx_mylLD3xmihunq9DJIIV-jgDNmeZZgqyLG7mocCFwa2kOu_7ltUepHQ23kFeWd0ur3_vba76AfKWK2wRCNWgrieCAx6gNfrN_7XYjKbLYspXko8Ec2SL9oA7R95majTwgm6eI7g" width="269.17385137081146"></b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-916e52d5-7fff-ab61-179f-f900c4cb53ce"><img height="234" src="https://lh6.googleusercontent.com/R7v5VgxD7kabSG12topFDVar_KzrJnOVvQdORTgYBlPUwi-lsq251j9bwV_hy7s0lyqwClOSyFhh3L5JBo8d-NXP1zhXdUYoLwaKskexg7w1U1LBKJlWNxW3L3SxW_lDFECG5IqfS7cEtZ69uQ" width="177"></b></p>
			</td>
		</tr>
		<tr>
			<td>
			<p dir="ltr">Figure 2: Fingerprint Spoofs</p>
			</td>
			<td>
			<p dir="ltr">Figure 3: 3D printed mask</p>
			</td>
		</tr>
	</tbody>
</table>

<p dir="ltr"> </p>

<p dir="ltr">Researchers at the Center for Identification Technology Research (CITeR) have made significant use of Chameleon to support research focused on identification technology and biometric recognition. CITeR is a National Science Foundation (NSF) Industry/University Cooperative Research Center (IUCRC), and advances the state of the art through research defined in tandem with affiliates from government and industry [1].</p>

<p dir="ltr">Biometric recognition systems are designed to provide automatic and reliable identification based on the physiological or behavioral characteristics of a person. Researchers have developed and deployed a biometric pipeline to utilize Chameleon [2] to develop deep learning based biometric models for different tasks. One area of research is the development of presentation attack detection models, designed to distinguish between real and spoof samples (deliberately altered or artificially generated) [3,4] in order to protect biometric systems from spoof attacks. Figures 2 and 3 illustrate spoofs designed to attack fingerprint and face recognition systems.</p>

<p dir="ltr"> </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-916e52d5-7fff-ab61-179f-f900c4cb53ce"><img height="362" src="https://lh4.googleusercontent.com/BtjS4yM9yjl9E9cYM47bx38iyK2gxZr-0HrDQLqMLCyWudPBJ9tPYjxDjcOjGLaEJgkb6qg6d7JgZr32C76V3UR8m_OytDdpI457EB8ZknC_BPCL7zME8poflBbqMmkpZYELYcsn" width="486"></b></p>

<p dir="ltr" style="text-align: center;">Figure 4: Some spoofs being detected as live samples</p>

<p dir="ltr"> </p>

<p dir="ltr">Current state-of-the-art biometric models are increasingly relying on deep learning techniques [5]. Developing such models requires a large amount of computational resources. Our biometric pipeline leverages the diverse computational resources provided by Chameleon to effectively develop deep learning based biometric models at scale. Training state-of-the-art deep Convolutional Neural Networks (CNNs) on large datasets is very computationally expensive. This large computation requirement translates into slow model development even in the most powerful GPUs available. Fortunately, Chameleon infrastructure allows us to effectively distribute our model development among many GPU nodes. This drastically speeds up the model development and allows us to run experiments that are simply not possible in single GPU nodes in a reasonable time frame. Our biometric pipeline leverages the Neural Network Intelligence (NNI) platform developed at Microsoft [6].  NNI allows us to distribute our model development among many GPU nodes with very low overhead. NNI works in conjunction with modern deep learning libraries such as Tensorflow or PyTorch [7,8] to effectively scale our deep learning model development process across multiple CPU/GPU nodes at Chameleon. We believe this combination provides a unique balance of ease of use and performance that could potentially be attractive to deep learning practitioners/researchers on Chameleon. </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-916e52d5-7fff-ab61-179f-f900c4cb53ce"><img height="248.9725091457367" src="https://lh4.googleusercontent.com/JwN4VlbgVpkA4BRb4vCt23BwD_olvTB-BxDMPOUVLyCwdChOFOx1L7RclBpGgHqbpoZL19pCEv6y7FyR0yvzSEoACExCgvOKrwAqCJhx7TDV2roZjlpNNStfElxFLTLTaoqjrE2kvD_zQMD0lg" width="442"></b></p>

<p dir="ltr" style="text-align: center;">Figure 5: Outline of our biometric pipeline.</p>

<p dir="ltr"> </p>

<p dir="ltr">Figure 5 presents the outline of our biometric pipeline. We utilize the persistent memory (Object storage) provided by Chameleon to store the biometric samples (face and fingerprint images). Chameleon’s persistent storage handles the transfer of large datasets required for training deep models. The rest of the necessary communication between the nodes involves model parameters and performance metrics. These updates are much smaller in size and can be easily carried over the network connections between the nodes.</p>

<p dir="ltr"> </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-916e52d5-7fff-ab61-179f-f900c4cb53ce"><img alt="A screenshot of a cell phone

Description automatically generated" height="213" src="https://lh4.googleusercontent.com/Vrv-nXJe8VrvACEtIGltvorVk4JEmRAKc8dSo-dt84tfw4oNUd36XL5sLT1uCgbTDKGBwJMk3gyVCcBQHSy_bHFRSK_TttFGXdrQu7TYzF3LL1NBh9WNWVwdXYrcv6u7eBoPkEfaREfux_zwVw" width="264"></b></p>

<p dir="ltr" style="text-align: center;">Figure 6: Interpretability models developed on top of Chameleon.</p>

<p dir="ltr"> </p>

<p dir="ltr">This setup is relatively easy to configure and allows the user to easily scale the experiment to the available Chameleon nodes. For our biometric experiments, we usually utilize a CPU node as an NNI Core and several GPU nodes for training. Through this pipeline, we can simultaneously run several training experiments, compare the results, and update our model selection parameters over multiple nodes. NNI provides state-of-the-art algorithms as well as a very rich and user-friendly API for this task. Additionally, the computational capabilities provided by Chameleon allow us to leverage various explainable models and try to explain and interpret the decisions made by our biometric models [9]. Figure 6 depicts an example of the interpretability models developed on Chameleon for our deep learning-based fingerprint age estimation model. These explainable models can allow us to answer what parts of the fingerprint image are being used to estimate the age of the subject. </p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-916e52d5-7fff-ab61-179f-f900c4cb53ce">On obstacles that stand in the way of biometric experiments: </b>The limiting factor in many of our experiments is the availability of datasets. Our work involves collecting and analyzing biometric samples from human subjects. Due to privacy concerns, such datasets are not publicly available to researchers. This drastically limits the experiment we can run and sometimes makes it impossible to replicate previous work.</p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-916e52d5-7fff-ab61-179f-f900c4cb53ce">On why he chose to pursue research:</b> I like creating new things. It gives me pleasure to build a new system from the ground up and see people use it and enjoy it in their life. </p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-916e52d5-7fff-ab61-179f-f900c4cb53ce">On researchers he admires:</b></p>

<p dir="ltr">Dr. Carl Sagen for his incredible ability to put complex topics in simple words. </p>

<p dir="ltr">Dr. Richard Dawkins for helping us understand life and for the Richard Dawkins foundation for reason and science. </p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-916e52d5-7fff-ab61-179f-f900c4cb53ce">On his most powerful piece of advice for students beginning research: </b>Start with a goal and a clear plan to achieve it. Reevaluate your goal and plan regularly. It is easy to get lost in the noise and lose focus. </p>

<p dir="ltr"> </p>

<p dir="ltr"><strong>For interested readers</strong>, the “Clarkson Distributed Neural Search Engine (Clarkson_NNI_R)” Chameleon appliance at TACC center provides an implementation of this pipeline. You can learn more about the <a href="https://www.linkedin.com/in/keivanbahmani/">author on LinkedIn</a> or visit the <a href="https://citer.clarkson.edu/">CITeR – Center for Identification Technology Research</a> webpage. </p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-916e52d5-7fff-ab61-179f-f900c4cb53ce">References:</b></p>

<p dir="ltr">[1] <a href="https://citer.clarkson.edu/about/">https://citer.clarkson.edu/about/</a> </p>

<p dir="ltr">[2] <a href="https://chameleoncloud.org/">https://chameleoncloud.org/</a></p>

<p dir="ltr">[3] Plesh, Richard, et al. "Fingerprint Presentation Attack Detection utilizing Time-Series, Color Fingerprint Captures." 2019 International Conference on Biometrics (ICB). IEEE, 2019.</p>

<p dir="ltr">[4] <a href="http://livdet.org/">http://livdet.org/</a></p>

<p dir="ltr">[5] Sundararajan, K., &amp; Woodard, D. L. (2018). Deep learning for biometrics: A survey. ACM Computing Surveys (CSUR), 51(3), 1-34.</p>

<p dir="ltr">[6] <a href="https://github.com/Microsoft/nni">https://github.com/Microsoft/nni</a> </p>

<p dir="ltr">[7] <a href="https://github.com/tensorflow/tensorflow">https://github.com/tensorflow/tensorflow</a></p>

<p dir="ltr">[8] <a href="https://github.com/pytorch/pytorch">https://github.com/pytorch/pytorch</a></p>

<p dir="ltr">[9] Samek, Wojciech, et al., eds. Explainable AI: interpreting, explaining and visualizing deep learning. Vol. 11700. Springer Nature, 2019.</p>