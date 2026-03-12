---
abstract: "<p>Modern networks are growing increasingly complex, and managing them\
  \ effectively requires sophisticated policy configurations that can adapt in real-time.\_\
  Languages that enable direct programmability of network data planes, like P4, offer\
  \ unprecedented control over packet processing, but come at a steep learning cost.\_\
  This raises a crucial question: can we automate the generation of these complex\
  \ network policies while ensuring they're correct, efficient, and adaptable?\_NetPrompt\
  \ is a novel framework that harnesses the power of Large Language Models (LLMs)\
  \ to automatically generate and optimize P4 scripts for Software-Defined Networks\
  \ (SDN). Read more to learn how the research team implement NetPrompt using Chameleon.</p>"
authors:
- Kevin Kostage Kostage
categories:
- User Experiments
date: '2025-12-22 20:18:51+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/be/9d/be9db330-9698-4fbf-b67c-b7b76d89ba7b/screenshot_2026-01-04_at_110635pm.png
related_posts:
- slug: detecting-the-invisible-machine-learning-for-cloud-infrastructure-health
  title: 'Detecting the Invisible: Machine Learning for Cloud Infrastructure Health'
- slug: introducing-mincers-performance-measurement-and-reproducibility-appliance
  title: "Introducing MINCER\u2019s Performance Measurement and Reproducibility Appliance"
- slug: chameleon-authentication-demystified-common-issues-and-solutions
  title: 'Chameleon Authentication Demystified: Common Issues and Solutions'
- slug: tigon-a-distributed-database-for-a-cxl-pod
  title: 'Tigon: A Distributed Database for a CXL Pod'
slug: netprompt-ai-powered-network-policy-management-for-programmable-networks
subtitle: Using Large Language Models to Automate P4 Policy Generation for Dynamic
  Software-Defined Networks
title: 'NetPrompt: AI-Powered Network Policy Management for Programmable Networks'
---

<p>Modern networks are growing increasingly complex, and managing them effectively requires sophisticated policy configurations that can adapt in real-time. For applications like high-definition video streaming or social virtual reality, maintaining Quality of Service (QoS) and Quality of Experience (QoE) under dynamic conditions is critical—but it's also incredibly challenging. The problem becomes even more complex when working with P4 (Programming Protocol-independent Packet Processors), a language that enables direct programmability of network data planes.</p>

<p>While P4 offers unprecedented control over packet processing, it comes with a steep learning curve. Writing P4 code requires specialized expertise in protocol parsing, match-action pipelines, and hardware constraints. Even minor errors can lead to network outages, misrouting, or security vulnerabilities. This raises a crucial question: can we automate the generation of these complex network policies while ensuring they're correct, efficient, and adaptable?</p>

<p>NetPrompt is a novel framework that harnesses the power of Large Language Models (LLMs) to automatically generate and optimize P4 scripts for Software-Defined Networks (SDN). By combining prompt engineering with structured model refinement, NetPrompt translates high-level network requirements into production-ready P4 configurations—achieving up to 50% lower latency and 25-40% higher throughput compared to existing frameworks.</p>

<h3>Research Overview</h3>

<p>The challenge NetPrompt addresses is multifaceted. SDN environments require adaptive policy generation to ensure satisfactory QoS and QoE expectations under constantly shifting network conditions. While generative AI shows promise for automating network configuration, there's been a notable gap in methods for AI-driven policy automation—particularly when it comes to translating high-level network intent into suitable Service Function Chains (SFCs) using P4 switch configurations without introducing misconfigurations.</p>

<p><img alt="NetPrompt Architecture" src="https://chameleoncloud.org/media/filer_public/be/9d/be9db330-9698-4fbf-b67c-b7b76d89ba7b/screenshot_2026-01-04_at_110635pm.png"></p>

<p>NetPrompt's solution centers on a three-phase cyclic architecture. First, the <strong>LLM-Driven Policy Synthesis Phase</strong> generates structured P4 scripts using pre-trained LLMs fine-tuned with P4 best practices through in-context learning. The system begins with user-provided prompts specifying network behavior in terms of QoS and QoE requirements, then extracts key components like desired behavior, protocols, and forwarding rules. These extracted intents form the basis for constructing Service Function Chains—ordered sequences of low-level programmable network functions such as traffic classification, header rewriting, and packet tagging.</p>

<p>The second phase, <strong>Prompt Engineering with a Vectorized Database</strong>, refines policies through adaptive prompt selection and retrieval-augmented learning. The researchers evaluated multiple prompting strategies—Zero-Shot, Few-Shot, Chain-of-Thought, Meta-Prompting, and Self-Consistency—finding that Self-Consistency prompting achieved the highest accuracy (95% syntax accuracy, 92% execution validity) while reducing error rates by 50%. The vectorized database stores validated P4 configurations as dense vector embeddings, enabling efficient retrieval of structurally relevant past configurations and reducing redundant computations.</p>

<p>Finally, the <strong>Cyclic Validation Process</strong> ensures AI-generated policies undergo continuous refinement through both offline simulation and online testbed validation. Policies are first tested in controlled environments, then deployed to real-world testbeds where they're assessed under realistic traffic loads and congestion scenarios. This feedback loop enables NetPrompt to adaptively fine-tune its configurations for robustness under dynamic network conditions.</p>

<p>A key innovation is NetPrompt's strategic use of multiple LLMs based on task requirements. After extensive benchmarking, the researchers selected Claude Sonnet 3.7 as the primary model for policy generation due to its near-100% correctness across tasks, highest code readability, and superior edge case handling. For scenarios requiring faster iteration with acceptable reliability, DeepSeek-R1 serves as a secondary option with faster execution speeds.</p>

<h3>Experiment Implementation on Chameleon</h3>

<p>NetPrompt's validation required a sophisticated, geographically distributed testbed infrastructure—and Chameleon Cloud proved essential to the research team's success. The online experiments were conducted across a multi-cloud architecture integrating both Chameleon and FABRIC resources, with three primary environments: the HPC Cloud at CHI@TACC in Texas, the Transmission Cloud at CHI@UC in Illinois, and an Edge Cloud connected via Starlight.</p>

<p><img alt="Testbed Architecture" src="https://chameleoncloud.org/media/filer_public/51/99/51990984-99a8-4cb2-b174-97cf9fb0f503/screenshot_2026-01-04_at_110826pm.png"></p>

<p>The HPC Cloud at TACC served as a computational hub where LLM-based policy synthesis and refinement were executed, while the Transmission Cloud at UC acted as a centralized control plane, hosting LLM-driven P4 decision-making for optimized routing and traffic prioritization. The Edge Cloud interfaced directly with end-hosts, enabling real-time network adaptation based on feedback-driven policy adjustments.</p>

<p>Chameleon's bare-metal access was critical for deploying P4-programmable switches and ensuring controlled, reproducible test conditions. The team relied on Chameleon's hardware catalog for resource selection and utilized the platform's multi-site networking capabilities to construct practical network topologies. The distributed nature of Chameleon's infrastructure—spanning multiple geographic locations—allowed the researchers to test NetPrompt under realistic wide-area network conditions, evaluating performance metrics such as latency, throughput, and packet loss.</p>

<p>The validation workflow involved an iterative feedback loop. The team transmitted various data types, including video streams and tabular datasets, to simulate real-world network traffic. Pre-trained LLMs were used for in-context training with manual supervision to ensure alignment with network constraints. NetPrompt-generated P4 policies were deployed across the topology, and real-time telemetry ensured adherence to QoS/QoE objectives while continuously feeding back into the LLM model through prompt engineering.</p>

<p>For offline validation, the researchers used Mininet in a virtualized SDN environment on AWS EC2, testing both simple two-host topologies and more complex triangular configurations with three P4 switches to evaluate rerouting capabilities during simulated link failures.</p>

<h3>Results and Impact</h3>

<p>NetPrompt's performance exceeded expectations across multiple metrics. In online experiments focusing on packet forwarding and rerouting for video streaming applications, NetPrompt achieved notably lower latency than both Lucid 2.0 and Lyra, closely approaching Oracle-level performance from human-written P4 scripts. The latency distribution was also tighter, indicating more consistent responsiveness during packet delivery.</p>

<p>Most impressively, NetPrompt recorded the highest throughput of all tested approaches—surpassing even the Oracle baseline in some scenarios. This demonstrates that LLM-generated policies can not only match human expertise but sometimes exceed it by discovering optimizations that might not be immediately obvious to expert programmers.</p>

<p>In terms of code generation quality, Claude Sonnet 3.7 consistently achieved near-100% correctness across packet forwarding, dropping, and rerouting tasks, with the highest code readability scores (up to 9.2 out of 10) and lowest cyclomatic complexity. The Self-Consistency prompting method proved most effective, achieving 95% syntax accuracy and 50% error rate reduction compared to simpler approaches.</p>

<p>The real-world implications are significant. NetPrompt substantially reduces misconfigurations in network policy management, making programmable networks more accessible to practitioners who may not have deep P4 expertise. For applications like video streaming that require dynamic QoS/QoE optimization, NetPrompt enables automated, adaptive policy generation that maintains stable performance under changing network conditions—without manual intervention.</p>

<h3>Experiment Artifacts</h3>

<p>The NetPrompt team has made their work fully reproducible. All code and scripts used in the experiments are available in the <a href="https://github.com/kngbq/NetPrompt" target="_blank">NetPrompt GitHub repository</a>. The research paper, "NetPrompt: LLM-driven Programmable Network Policy Management and Optimization," was published at the 2025 34th International Conference on Computer Communications and Networks (ICCCN) (<a href="https://ieeexplore.ieee.org/abstract/document/11133886?casa_token=kERAOagYyPwAAAAA:5ROJUkUMo1eTMNDwjrQcr5yxzRddYY3PVZYrgKN3l3sHHkFL-MpPck1xH8xFbIhitwRCXhB69ok">available here</a>).</p>

<h3>About the Research Team</h3>

<p>This work represents a collaboration between researchers at the University of Missouri - Columbia and Florida Gulf Coast University. The team includes Kiran Neupane, Ashish Pandey, and Prasad Calyam from Missouri, along with Kevin Kostage, Sean Peppers, and Chengyi Qu from Florida Gulf Coast. Their research focuses on programmable networks, SDN optimization, and the intersection of artificial intelligence with network infrastructure management.</p>

<p>The NetPrompt project is supported by the U.S. Army Corps of Engineers, Engineering Research and Development Center—Information Technology Laboratory (ERDC-ITL) and the National Science Foundation (NSF). Looking ahead, the team plans to enhance code generation accuracy by expanding P4 training datasets, extend NetPrompt to support dynamic security policy adaptation through integration with intrusion detection systems, and test the lightweight deployment framework across diverse edge environments including IoT devices, drones, and HPC nodes.</p>

<p><strong>Thank you for sharing your work with the Chameleon community!</strong></p>