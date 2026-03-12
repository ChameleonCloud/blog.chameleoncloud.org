---
abstract: <p>Learn how cutting-edge research is shedding light on the energy dynamics
  of I/O operations in HPC environments, potentially reshaping future storage designs.</p>
authors:
- Maya Purohit
categories:
- User Experiments
date: '2024-09-30 17:16:40+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/b4/79/b4790644-2a5d-4e5b-a5f5-a77508eb613b/photo.jpg
related_posts:
- slug: power-measurement-and-management-on-chameleon
  title: Power Measurement and Management on Chameleon
- slug: maximizing-performance-distributed-system-power-budget
  title: Maximizing Performance in Distributed Systems with a Power Budget
- slug: monitoring-power-consumption-low-power-nodes
  title: 'Power to People: Monitoring Power Consumption of Low Power Nodes'
slug: power-patterns-understanding-the-energy-dynamics-of-io-for-parallel-storage-configurations
subtitle: 'Powering Through Data: Energy Insights for Parallel Storage Systems'
title: 'Power Patterns: Understanding the Energy Dynamics of I/O for Parallel Storage
  Configurations'
---

<p>As high performance computing (HPC) applications become more I/O intensive, understanding their power consumption patterns is necessary to develop energy-saving solutions. In our research project, we evaluated the energy consumption of I/O operations on two popular HPC parallel file systems: Lustre and DAOS. We developed models to predict the energy usage of sequential writes and evaluated their accuracy against our gathered benchmarks. Our models can be used to enhance the accuracy of energy-predicting frameworks by allowing them to consider storage configuration when estimating total energy consumption.</p>

<h2>Research Overview</h2>

<figure><img alt="Visual representation of our Disk, Memory, Lustre and DAOS Configuration" src="https://www.chameleoncloud.org/media/filer_public/6f/26/6f267ba1-3009-4c31-9baa-a98201aaf585/image2.png">
<figcaption style="margin-bottom: 20px;">Figure 1: Visual representation of our Disk, Memory, Lustre and DAOS Configurations</figcaption>
</figure>

<p> </p>

<p>Figure 1 displays a diagram representing the four different local and remote storage configurations we utilized and implemented for this research project. Typically, a parallel file system contains three different types of machines: the client node which allows for user interaction, the metadata node which stores data regarding file location, permissions, etc., and the storage nodes which hold the data itself. In our configurations, both file systems contained three nodes representing each type of machine.</p>

<figure><img alt="Energy Consumption Analysis for Lustre Read" src="https://www.chameleoncloud.org/media/filer_public/57/16/5716f3b7-6fa9-4df3-92bf-a0be51a15478/image4.png" style="float: left; width: 50%;"> <img alt="Energy Consumption Analysis for Lustre Write" src="https://www.chameleoncloud.org/media/filer_public/cb/7f/cb7f5a11-2e08-4b49-a782-09d0da4b7117/image1.png" style="float: left; width: 50%;">
<div style="clear: both;"> </div>

<figcaption style="margin-bottom: 20px;">Figure 2: Energy Consumption (J) Analysis for Performing I/O Operations on Disk and Memory and Lustre (Write on left, Read on right)</figcaption>
</figure>

<p>We measured the IPMI, CPU, and RAM power consumption for each node in Lustre and DAOS when performing I/O operations (writing and reading) and compared their energy performance to permanent (Disk) and temporary (Memory) local storage configurations. The results are shown below in Figures 2 and 3. We found there to be a statistically significant difference in energy consumption between Disk, Memory and Lustre for both reading and writing. In contrast, energy consumption in DAOS is comparable to Memory when writing but significantly different than Disk and Memory when reading. We also modeled total energy consumption for each individual node in Lustre and DAOS when writing. Although there is a strong linear relationship between the model prediction and observed values, our current models typically overestimate total energy. For more detail on our model design, please refer to the poster and write-up linked below.</p>

<figure><img alt="Energy Consumption Analysis for DAOS Write" src="https://www.chameleoncloud.org/media/filer_public/fb/76/fb760a10-0e05-4608-83b7-3558114e5abb/image3.png" style="float: left; width: 50%;"> <img alt="Energy Consumption Analysis for DAOS Read" src="https://www.chameleoncloud.org/media/filer_public/44/82/44820065-7d5d-4564-ba94-259c89c99905/image7.png" style="float: left; width: 50%;">
<div style="clear: both;"> </div>

<figcaption style="margin-bottom: 20px;">Figure 3: Energy Consumption (J) Analysis for Performing I/O Operations on Disk and Memory and DAOS (Write on Left, Read on Right)</figcaption>
</figure>

<figure><img alt="Energy relationship for Lustre" src="https://www.chameleoncloud.org/media/filer_public/30/c5/30c5e700-d61f-4586-8514-0c31a7f38ffc/image5.png" style="float: left; width: 50%;"> <img alt="Energy relationship for DAOS" src="https://www.chameleoncloud.org/media/filer_public/31/e5/31e5185c-efd8-4e65-a3f8-3238885ba775/image6.png" style="float: left; width: 50%;">
<div style="clear: both;"> </div>

<figcaption style="margin-bottom: 20px;">Figure 4: Energy relationship between model prediction and observed energy (J) of I/O for Lustre and DAOS Nodes</figcaption>
</figure>

<p> </p>

<p>Our research demonstrates that the energy consumption of I/O operations can vary significantly depending on the parallel file system and storage configuration used. By understanding these energy dynamics and utilizing energy-efficient solutions like DAOS, HPC facilities can reduce their environmental impact and operational costs, while also potentially improving system performance.</p>

<h2>Experimental Implementation on Chameleon</h2>

<p>We deployed Lustre and DAOS on bare-metal nodes in the Chameleon Cloud. The bare metal nodes allowed us to ensure that we recorded only energy measurements for the I/O tasks we intended to benchmark. Our Lustre deployment had one Client Node, one Metadata Server/Target (MDS/T) with one 223.6GB SSD and one Object Storage Server/Target (OSS/T) with 16 2TB SSDs. For DAOS, we deployed one Client/Admin Node with one 447.1GB SSD and two DAOS Storage Server nodes with 15TB of NVMe storage.</p>

<p>Since both Lustre and DAOS require multiple machines with particular attributes to be implemented, the hardware catalog and the host availability browser were incredibly helpful throughout the planning process. The detailed information regarding storage capacity and networking capabilities for the compute and storage nodes in the Chameleon testbed were crucial for our research project. Specifically for DAOS, our original implementation required storage machines with Optane Persistent Memory, NVMe storage, and Infiniband capabilities. The hardware catalog helped us find the compute and storage nodes that met our specific needs.</p>

<p>To gather power metrics for each node in Lustre and DAOS when performing I/O intensive tasks, we heavily utilized the command line and bash scripts. We measured total, CPU, and RAM power consumption using the Running Average Power Limit (RAPL - A feature that provides fine-grained energy usage information for CPU and memory) interface on Intel machines and the Intelligence Platform Management Interface (IPMI - A standardized system interface for monitoring hardware) from the Baseboard Management Controller (BMC - A specialized microcontroller that manages the interface between system management software and platform hardware). <a href="https://chameleoncloud.org/blog/2024/06/18/power-measurement-and-management-on-chameleon/">This Chameleon blog post</a> provided us with multiple resources to access and gather total power metrics on Chameleon machines, significantly improving the data we were able to collect.</p>

<p>To implement Lustre, we needed to install kernel versions and packages that were compatible with the latest version of Lustre that has been released. Chameleon's custom kernel boot was incredibly important for implementing a functional version of Lustre for energy benchmarking. Additionally, the support the Chameleon testbed has for infiniband will be helpful for our research project as we look to expand from using ethernet to Infiniband for the DAOS file system.</p>

<h2>Experiment Artifacts</h2>

<p><a href="https://github.com/MayaPurohit/Energy_Python">Github Repo</a></p>

<p><a href="https://www.chameleoncloud.org/media/filer_public/62/49/62492767-1a19-469b-b042-bb44927a860e/maya_abstract.pdf">Poster Write-up</a></p>

<p><a href="https://www.chameleoncloud.org/media/filer_public/8f/ec/8fec206b-a06a-4114-846b-a57ab9a3ab05/maya_sc_poster.pdf">Poster</a></p>

<p><strong>This research poster was accepted into the <a href="https://sc24.supercomputing.org/program/posters/acm-student-research-competition/">SC24 ACM Undergraduate Poster Competition</a>.</strong></p>

<h2>User Interview</h2>

<figure><img src="https://www.chameleoncloud.org/media/filer_public/b4/79/b4790644-2a5d-4e5b-a5f5-a77508eb613b/photo.jpg" style="float: left; width: 50%;">
<div style="clear: both;"> </div>

<figcaption style="margin-bottom: 20px;">Author Photo</figcaption>
</figure>

<h3>Tell us a little bit about yourself</h3>

<p>I am currently an undergraduate junior at Colby College partaking in the Dual Degree Engineering program at Dartmouth College. I am majoring in Computer Science and Engineering with a minor in Mathematics. After earning my bachelor's degree, I would like to pursue graduate school. In my freetime, I like to learn new recipes to cook and play tennis!</p>

<h3>Most powerful piece of advice for students beginning research or finding a new research project?</h3>

<p>It may seem obvious, but I think it is important to be patient with yourself. When I first started this research project, I naively thought that the questions we were trying to answer would have clear and neat solutions. I found myself feeling discouraged when the results did not fit with our intuitive understanding of the file systems we were testing. However, after witnessing my mentor and the other researchers around me approach difficult problems with resilience and persistence, I learned that I needed to readjust my mindset. Approach research with patience and open-mindedness.</p>

<h3>Why did you choose this direction of research?</h3>

<p>At the start of the summer, I did not have a specific research direction in mind. I did not have any prior professional or academic experience working with computer systems, so I viewed this research project as a great opportunity to immerse myself deeply in the field and see if it interested me. With guidance and support from my mentor, I was able to broaden my understanding of system administration and the different disciplines associated with computer science.</p>

<p>Thank you for sharing your knowledge with the Chameleon community!</p>