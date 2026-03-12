---
abstract: "<p>Graph Pattern Mining (GPMI) applications are considered a new class\
  \ of data-intensive applications --\_they generate massive irregular computation\
  \ workloads and pose memory access challenges, which degrade the performance and\
  \ scalability significantly. Researchers at the Illinois Institute of Technology\
  \ approach the problem by using the emerging process-in-memory architecture.\_</p>"
authors:
- Rujia Wang
categories:
- User Experiments
date: '2022-06-20 18:31:14+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/16/34/163493c0-79a1-4cca-843b-84fc9acd1ed0/experiment_authors.png
related_posts: []
slug: exploring-process-in-memory-architecture-for-high-performance-graph-pattern-mining
subtitle: ''
title: Exploring Process-in-memory Architecture for High-performance Graph Pattern
  Mining
---

<h3>Experiment Section</h3>

<p><strong>What is the central challenge/hypothesis your experiment investigates?</strong><br>
Bioinformatics, social network analysis, and computer vision are linked by the need to identify connections. Specifically, graph pattern mining (GPMI) need to find all subgraphs with different patterns that meet an application’s requirements, such as counting the number of 4-vertex connected subgraphs. 4-vertex connected subgraphs are subgraphs that contain 4 vertices and each vertex has edges to other 3 vertices. For example, in a social network, a 4-vertex connected subgraph refers to a group of people where each person knows each other. Such applications are considered a new class of data-intensive applications - they generate massive irregular computation workloads and pose memory access challenges, which degrade the performance and scalability significantly.</p>

<p><br>
<strong>How is your research addressing this challenge?</strong><br>
Leveraging emerging hardware, such as process-in-memory (PIM) technology, could potentially accelerate applications like GPMI. PIM integrates processing units inside the memory to reduce the overhead of frequent data movement. Compared with CPU, PIM has more processing units and stronger computing power. In addition, PIM has higher bandwidth and lower latency to access memory, making it ideal for memory access-intensive applications such as GPMI. There are two most prominent memory technologies on PIM, Hybrid Memory Cube (HMC) and High Bandwidth Memory (HBM). Among them, the HBM-PIM is currently the most promising PIM hardware with its superior internal and external bandwidth. As shown in Figure 1, the HBM-PIM incorporates PIM cores inside of memory banks, and the PIM cores access the memory banks with different access paths (the arrows in Figure 1(b)).</p>

<p style="text-align: center;"><img alt="figure1" src="https://www.chameleoncloud.org/media/filer_public/eb/e4/ebe4c166-db14-4b09-b568-a7449100979b/figure1.png" width="50%"></p>

<p style="text-align: center;"><strong>Figure 1</strong>: HBM-PIM architecture and internal bank organization.</p>

<p><br>
In this project, we use PIM architecture to accelerate data-intensive operations in graph mining tasks. We first identify the code blocks that are best suitable for PIM execution. Then, we observe a significant load imbalance on PIM architecture and analyze the root cause for such imbalance in graph mining applications. Lastly, we evaluate several data placement and scheduling schemes that help reduce the load imbalance and discuss potential optimizations to enhance overall performance further. With our optimizations, GPMI applications could leverage general purpose PIM architecture for performance acceleration and save computation energy significantly.</p>

<p><br>
<strong>How do you structure your experiment on Chameleon?</strong><br>
In our experiment, we use Cascade Lake R (CPU) nodes on CHI@UC. We run our baseline GPMI systems on Cascade Lake R nodes. For our graph mining applications on process-in-memory architecture, we use ZSim and Ramulator to simulate PIM systems on Cascade Lake R nodes.<br>
What features of the testbed do you need in order to implement your experiment?<br>
Since the execution time of the simulator is long and the simulated time is not related to the node performance, we use multiple nodes on Chameleon to run our graph mining applications on PIM architecture with different graphs at the same time. This is possible because Chameleon provides a lot of computing resources, so being able to run experiments simultaneously greatly reduces the time I spend running experiments.<br>
Can you point us to artifacts connected with your experiment that would be of interest to our readership?<br>
Our preliminary paper was published on https://ieeexplore.ieee.org/abstract/document/9511207. The full version of this work is currently under review.</p>

<h3>Author Profile Section</h3>

<p><strong>About the Authors</strong></p>

<p><img alt="author1" src="https://www.chameleoncloud.org/media/filer_public/65/15/65152020-6a99-484f-ac59-eea867b8aa3a/author1.png" width="30%"></p>

<p>Jiya Su is a Ph.D. student at Illinois Institute of Technology, working with Dr. Rujia Wang. She completed her master’s degree at Illinois Institute of Technology, and her bachelor's degree at Renmin University of China. Her research interests involve Processing-In-Memory, computer architecture and parallel and distributed computing.</p>

<p><img alt="author2" src="https://www.chameleoncloud.org/media/filer_public/dc/a5/dca5881c-a801-4032-8d41-f91c41621d1c/author2.png" width="30%"></p>

<p>Dr. Rujia Wang is an assistant professor of the Department of Computer Science at Illinois Institute of Technology. Her research involves designing secure and reliable memory architectures for future computing systems. Her interests span multiple areas including novel memory architecture, secure computing architecture, system reliability and high-performance computing.</p>

<p><strong>Most powerful piece of advice for students beginning research or finding a new research project?</strong><br>
For students just beginning their research, finding an advisor who is relevant to their research interests is critical. A good advisor can help students quickly understand the flow of research.</p>

<p><br>
<strong>Why did you choose this direction of research?</strong><br>
Computer architecture is the foundation of all computer research. Processing-in-memory (PIM) is considered a promising computer architecture solution to enhance the performance of memory-bounded data-intensive applications. With PIM architecture, it is possible to integrate general-purpose or specialized computation units in or near the memory module, thereby reducing the massive data movement, read latency and increasing the bandwidth. PIM is currently a very new research direction, especially for the system community, and there are many open research questions to be answered.<br>
 </p>