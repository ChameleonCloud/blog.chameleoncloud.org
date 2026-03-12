---
abstract: <p>Scientific workflows often fail in unexpected ways, but traditional detection
  systems require massive amounts of training data. This groundbreaking approach generates
  just the right data needed to train anomaly detection models, improving accuracy
  while reducing resource consumption.</p>
authors: []
categories:
- User Experiments
date: '2025-02-26 22:14:53+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/79/b6/79b6b3dd-ddcd-4794-b4aa-4309a63d0edc/screenshot_2025-02-26_at_40629pm.png
related_posts:
- slug: if-at-first-you-dont-succeed-try-try-again-insights-and-llm-informed-tooling-for-detecting-retry-bugs-in-software-systems
  title: If At First You Don't Succeed, Try, Try, Again...? Insights and LLM-Informed
    Tooling for Detecting Retry Bugs in Software Systems
- slug: chameleon-and-simulating-self-propagating-malware-to-evaluate-detection-technology
  title: Chameleon, and Simulating Self Propagating Malware to Evaluate Detection
    Technology
- slug: automated-fast-flux-detection-using-machine-learning-and-genetic-algorithms
  title: Automated Fast-flux Detection using Machine Learning and Genetic Algorithms
slug: less-data-better-results-how-active-learning-improves-workflow-anomaly-detection
subtitle: Chameleon-Powered Research Shows the Path to Efficient Scientific Computing
title: 'Less Data, Better Results: How Active Learning Improves Workflow Anomaly Detection'
---

<p>Scientific workflows help orchestrate complex computations across distributed resources, but they're vulnerable to failures at large scales. Detecting these anomalies typically requires massive training datasets—an expensive and time-consuming process. <a href="https://www.sciencedirect.com/science/article/pii/S0167739X24005727?casa_token=WgPt9G18H8gAAAAA:_aBHQQyn3NQTzRAGSP4L9DrulDU57Pmb09zJ78JJW2A_UNSpsCFQRI1ttsGY62WHiOUdJhpnfg">Researchers</a> from USC, Argonne National Lab, UNC Chapel Hill, and Oak Ridge National Lab have developed an approach that learns more efficiently using active learning to generate only the most valuable training examples.</p>

<h3>Research Overview</h3>

<p class="whitespace-pre-wrap break-words">The research team developed a novel framework that combines active learning with an experimental platform designed specifically for computational workflows. This approach addresses a critical challenge in machine learning: how to minimize the amount of training data needed while maximizing model accuracy.</p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/79/b6/79b6b3dd-ddcd-4794-b4aa-4309a63d0edc/screenshot_2025-02-26_at_40629pm.png"></p>

<p class="whitespace-pre-wrap break-words">The key insight is that not all data is equally valuable for training. Rather than blindly collecting massive datasets, a system actively identifies which types of data would be most useful for improving model performance, and then generates precisely those examples on demand.</p>

<p>The solution comes in two parts:</p>

<ul>
	<li><strong>Poseidon-X</strong>: An experimental framework that leverages the Pegasus workflow management system and two NSF-funded cloud testbeds (Chameleon and FABRIC) to provide reproducible, on-demand data collection from workflow executions. This framework supports controlled injection of different types of anomalies, from CPU slowdowns to network issues.</li>
	<li><strong>Active Learning Module</strong>: A mathematical framework that guides the data generation process by measuring the model's confidence on training data and triggering new targeted experiments in areas of uncertainty.</li>
</ul>

<p><img src="https://www.chameleoncloud.org/media/filer_public/ad/b2/adb208c7-648e-4bb2-8d18-b2fb091a6860/screenshot_2025-02-26_at_40930pm.png"></p>

<p>The evaluation uses three computational workflows: 1000Genome, Montage, and Predict Future Sales. The findings demonstrate that active learning not only saves computing resources but also improves the accuracy of anomaly detection significantly.</p>

<h3>Experimental Implementation on Chameleon</h3>

<p>Chameleon's bare-metal infrastructure was essential to this research. The team provisioned three Cascade Lake nodes with 48 cores and 192GB RAM each, deploying Docker containers to create an HTCondor pool for workflow execution. cgroups were leveraged to inject controlled performance anomalies and establish a high-speed connection between Chameleon and FABRIC over a 25Gbps VLAN. This setup allowed precise control over experimental conditions and reproducible results.</p>

<h3>Experiment Artifacts</h3>

<p>The research artifacts include the Poseidon-X framework (available on <a href="https://github.com/PoSeiDon-Workflows/Poseidon-X">GitHub</a>) and the <a href="https://arxiv.org/abs/2306.09930">Flow-Bench dataset</a> containing pre-captured workflow traces. Jupyter notebook recipes provide step-by-step guidance for setup. You can find a link to the paper <a href="https://www.sciencedirect.com/science/article/pii/S0167739X24005727?casa_token=WgPt9G18H8gAAAAA:_aBHQQyn3NQTzRAGSP4L9DrulDU57Pmb09zJ78JJW2A_UNSpsCFQRI1ttsGY62WHiOUdJhpnfg">here</a>.</p>

<h3>About the User</h3>

<p><img src="https://www.chameleoncloud.org/media/filer_public/6c/9d/6c9d4496-9f5e-45de-8e48-b1a6407ab7ae/raghavan.jpg"></p>

<p><a href="https://www.anl.gov/profile/krishnan-raghavan">Krishnan Raghavan</a>, an Assistant Computational Mathematician at Argonne National Laboratory, led this research. He received his Ph.D. in computer engineering from Missouri University of Science and Technology in May 2019.  He has coauthored several papers on deep neural networks with applications to big data.</p>