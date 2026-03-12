---
abstract: "<p>Cloud infrastructures are powerful but often operate as isolated islands.\
  \ See how Germ\xE1n Molt\xF3 and his team are bridging these gaps, enabling massive,\
  \ collaborative scientific experiments by connecting clouds across the Atlantic\
  \ using the Infrastructure Manager to dynamically deploy custom testbeds.</p>"
authors:
- "Germ\xE1n Molt\xF3 Mart\xEDnez"
categories:
- User Experiments
date: '2025-07-28 18:04:09+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/0c/9c/0c9ca148-634a-4981-9cc4-bf96905f0243/headshot.png
related_posts:
- slug: infrastructure-without-scaling-limits
  title: Infrastructure without Scaling Limits
- slug: connecting-slices-ri-and-chameleon
  title: Connecting SLICES-RI and Chameleon
- slug: one-fish-two-fish-choosing-optimal-edge-topologies-for-real-time-autonomous-fish-surveys
  title: 'One Fish, Two Fish: Choosing Optimal Edge Topologies for Real-Time Autonomous
    Fish Surveys'
slug: connecting-continents-dynamic-deployment-of-transatlantic-computational-testbeds-via-the-infrastructure-manager
subtitle: Breaking down the barriers between cloud computing 'silos' to create unified,
  large-scale scientific environments that span across Europe and the United States.
title: 'Connecting Continents: Dynamic Deployment of Transatlantic Computational Testbeds
  via the Infrastructure Manager'
---

<p><em>We talked with Germán Moltó, Full Professor at Universitat Politècnica de València, about his work on interconnecting cloud infrastructures to support complex scientific research. His team’s recent experiment showcases how to bridge cloud federations in Europe and the United States, creating powerful, transatlantic computational testbeds.</em></p>

<figure><img alt="Germán Moltó giving a presentation" src="https://chameleoncloud.org/media/filer_public/0c/9c/0c9ca148-634a-4981-9cc4-bf96905f0243/headshot.png">
<figcaption>Germán Moltó presenting his research.</figcaption>
</figure>

<h2>Research Overview</h2>

<p>Cloud-based infrastructures provide the computational substrate to efficiently execute compute-intensive scientific experiments on customized virtualized resources which include disparate software configuration and/or hardware resources (e.g. GPUs). However, many cloud infrastructures operate as independent silos and, therefore, users find it difficult to collaboratively aggregate resources from different clouds in a unified customized testbed to untap access to large-scale computing capacity. This work focuses on the automated deployment of customized computational testbeds that span across distributed cloud infrastructures. This required introducing support in a cloud orchestrator that interacts with the underlying cloud infrastructures without requiring modifications in each particular cloud site, thus facilitating user adoption.</p>

<h2>Experiment Implementation on Chameleon</h2>

<h3>Our Approach</h3>

<p>This research involved introducing Chameleon cloud support in the Infrastructure Manager (IM), an open-source cloud orchestrator that deploys complex virtualized application architectures on multiple cloud back-ends (Amazon Web Services, Microsoft Azure, OpenStack, etc.). The IM is being used in production as the cloud orchestrator in the EGI Federated cloud. EGI is the largest federation of research data centres contributing with storage and compute facilities, while EGI Federated cloud is a large federation of OpenStack-based cloud sites contributed by more than 20 research centres mainly across Europe. As shown in the figure below, the IM provides a curated catalog of popular applications commonly used in scientific research and data-intensive processing (e.g. Galaxy, Dask, AirFlow, JupyterHub), thus providing users with the ability to deploy in minutes their preferred computational environment.</p>

<figure><img alt="A curated catalog of applications available in the Infrastructure Manager" src="https://chameleoncloud.org/media/filer_public/8f/ce/8fced85c-4b8b-4f9f-a6c0-d93658e520e0/im-apps2.png" width="800px"> <img alt="A curated catalog of applications available in the Infrastructure Manager" src="https://chameleoncloud.org/media/filer_public/5c/aa/5caa3b1a-7642-4563-abef-ab4e7a5080cb/im-apps.png" width="400px"> <img alt="A curated catalog of applications available in the Infrastructure Manager" src="https://chameleoncloud.org/media/filer_public/1f/dc/1fdcbd31-d0f7-460d-b458-d7938b987760/im-apps1.png" width="400px">
<figcaption>A curated catalog of popular applications available in the Infrastructure Manager.</figcaption>
</figure>

<p> </p>

<p>UPV (Universitat Politècnica de València), in Spain, provides a publicly available instance of the Infrastructure Manager, offered as part of the EGI service catalogue, openly accessible to anyone, to deploy on any of the supported cloud infrastructures on behalf of the user. Our approach involves introducing Chameleon Cloud as an additional cloud back-end supported by the IM and deploy transatlantic testbeds to execute use cases coming from European projects to unveil the benefits of aggregating computing resources from disparate cloud sites (e.g. EGI Federated cloud and Chameleon Cloud).</p>

<h3>Building the Experiment</h3>

<p>Integrating Chameleon Cloud to be used as a Cloud back-end for the Infrastructure Manager required understanding the platform via the documentation, accessing the capabilities and hardware availability via the hardware catalog and getting access to OpenStack’s Application Credentials which are securely stored in a Hashicorp’s Vault instance. Chameleon’s Helpdesk played a pivotal role in interacting with the team to facilitate access to relevant information.</p>

<p>Using the IM we deployed examples of transatlantic Virtualized Computing Infrastructures (VCIs) across the OpenStack-based Clouds provided by both Chameleon Cloud and EGI Cloud Compute service to facilitate distributed computation. In particular, we deployed two OSCAR clusters (an open-source event-driven serverless platform based on Kubernetes) via the IM, one in US (Texas Advanced Computing Center) and another in the EU (Portugal).</p>

<figure><img alt="Two OSCAR clusters deployed via the IM dashboard, one on Chameleon Cloud in the USA and one on EGI in the EU." src="https://chameleoncloud.org/media/filer_public/5e/aa/5eaa05c3-e9e3-4c85-854b-134bc1c7eb77/im-dashboard.png">
<figcaption>Two OSCAR clusters deployed via the IM dashboard, one on Chameleon Cloud in the USA and one on EGI in the EU.</figcaption>
</figure>

<p> </p>

<p>We supported a use case on distributed AI-based fish detection coming from the iMagine EU (European Union) project across the resources of this transatlantic testbed. For the deployment of services in each cluster, an OSCAR services replicated architecture has been used. This allows that invocations made to a service deployed in OSCAR Cluster @EU that have not been executed for a certain configurable amount of time (due to the lack of computing resources) are redirected to the corresponding services in the OSCAR Cluster @US. The invocations of the services executed in the OSCAR Cluster @US not only return the results in their local bucket but also return them to the bucket of the corresponding service in the OSCAR Cluster @EU.</p>

<figure><img alt="Diagram showing the OSCAR service replicated architecture across the US and EU clusters." src="https://chameleoncloud.org/media/filer_public/9e/31/9e312577-9d46-4f25-b489-b82f664c5c2a/cluster_diagram.png">
<figcaption>OSCAR service replicated architecture for the AI-based fish detection use case.</figcaption>
</figure>

<p> </p>

<p>We also supported another use case on Flood Assessment coming from the interTwin EU project where a CWL (Common Workflow Language) configuration is created from a Jupyter Notebook to include the configuration required for the Digital Twin and is later executed so that some computationally-intensive steps of the workflow are offloaded to a remote OSCAR cluster running on Chameleon Cloud. A Python script invoked by the CWL workflow, which performs all necessary operations within the OSCAR environment, ensuring that the model executes correctly, processes the required tasks, and retrieves and downloads the output seamlessly.</p>

<figure><img alt="Diagram showing the Flood Assessment workflow using a remote OSCAR cluster on Chameleon Cloud." src="https://chameleoncloud.org/media/filer_public/4c/3c/4c3cf4db-5fae-4679-914c-53993dd76701/cluster_diagram1.png">
<figcaption>Flood Assessment use case from the interTwin EU project.</figcaption>
</figure>

<h3>Essential Testbed Features</h3>

<p>This experiment was done using virtualized infrastructure provided by KVM@TACC, but a similar approach can be done in bare-metal resources since support for the Blazar reservation was introduced in the plugin developed to interact with Chameleon Cloud, and contributed upstream to the Apache Libcloud’s library.</p>

<h2>Experiment Artifacts</h2>

<p>For those interested in exploring this work further, the following resources are available:</p>

<ul>
	<li><a href="https://bit.ly/imcham-blog-slides" target="_blank">Supporting slides including video demos</a></li>
	<li><a href="https://github.com/grycap/oscar/tree/master/examples/fish-detector-replicas" target="_blank">GitHub repository for the Fish Detector replicas deployed across OSCAR clusters</a></li>
	<li><a href="https://www.chameleoncloud.org/experiment/share/ea0b7d1e-cacc-4f9d-8660-6f1827fdef92" target="_blank">Trovi artifact “Deploy Applications on Chameleon via the Infrastructure Manager (IM)”</a></li>
	<li>Related Press Notes:
	<ul>
		<li><a href="https://www.intertwin.eu/case-study/success-story-transatlantic-computational-testbeds-enabling-seamless-workflow-executions-of-flood-simulations" target="_blank">“OSCAR and DT Flood in the DISCOVER-US project”</a></li>
		<li><a href="https://ai4eosc.eu/ai4eosc-deployment-of-transatlantic-testbeds-for-scalable-ai-inference-via-the-infrastructure-manager-on-chameleon-cloud/" target="_blank">“AI4EOSC: Deployment of Transatlantic Testbeds for Scalable AI inference via the Infrastructure Manager on Chameleon Cloud”</a></li>
	</ul>
	</li>
</ul>

<h2>User Interview</h2>

<h3>About the Researcher</h3>

<p>Germán Moltó is Full Professor at Universitat Politècnica de València, specializing in distributed computing, cloud computing, and serverless computing. With a strong background in middleware technologies, orchestration, and cloud automation, our group’s research has contributed to the advancement of scalable deployment and execution of applications on distributed computing infrastructures. He has contributed to numerous European projects in the area of the European Open Science Cloud (EOSC) such as EOSC-Synergy, EOSC-Hub and EOSC-Beyond. His team is responsible for open-source developments in the area of cloud orchestration and execution of applications along the computing continuum.</p>

<h3>Motivation and Advice</h3>

<p><strong>Most powerful piece of advice for students beginning research or finding a new research project?</strong></p>

<blockquote>It’s not about being smart, it’s about consistency and discipline. Hard work always pays off.</blockquote>

<p><strong>How do you stay motivated through a long research project?</strong></p>

<blockquote>I like when research projects involve interconnecting multiple software systems and services to facilitate a specific area of the research lifecycle (e.g. access to computing capacity, deploying a virtual research environment, etc.). Providing gateways for scientific end users to take advantage of distributed computing infrastructures is a rewarding experience and being able to contribute with our research group’s expertise provides a significant energy boost.</blockquote>

<hr>
<p><small><em>Part of these results were funded via a research stay by the DISCOVER-US project, financed by the European Union’s Horizon Europe research and innovation funding programme under grant agreement number 101135064. Results presented in this presentation were obtained using the Chameleon testbed supported by the National Science Foundation. We acknowledge Grant PID2020-113126RB-I00 funded by MICIU/AEI/10.13039/501100011033. Part of this work was supported by the project AI4EOSC ‘‘Artificial Intelligence for the European Open Science Cloud’’ that has received funding from the European Union’s Horizon Europe Research and Innovation Programme under Grant 101058593. Also, the project iMagine ‘‘AI-based image data analysis tools for aquatic research’’ that has received funding from the European Union’s Horizon Europe Research and Innovation Programme under Grant 101058625. These results were achieved thanks to the support effort from Miguel Caballer, Estíbaliz Parcero and Vicente Rodríguez.</em></small></p>