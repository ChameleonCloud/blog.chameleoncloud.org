---
abstract: <p>Explore the cutting-edge research of Professor Dong Li from UC Merced
  as he tackles the challenges of managing multi-tiered memory systems. Learn how
  his innovative MTM (Multi-Tiered Memory Management) system optimizes page profiling
  and migration in large heterogeneous memory environments. Discover how Chameleon's
  unique hardware capabilities enabled this groundbreaking experiment, and gain insights
  into the future of high-performance computing memory management. This blog offers
  a glimpse into the complex world of computer memory hierarchies and how researchers
  are working to make them more efficient and accessible.</p>
authors:
- Dong Li
categories:
- User Experiments
date: '2024-07-22 20:35:42+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/4a/20/4a2029e8-f444-46cd-87af-b15141b9d2ac/dong-li-profile_1.png
related_posts:
- slug: exploring-process-in-memory-architecture-for-high-performance-graph-pattern-mining
  title: Exploring Process-in-memory Architecture for High-performance Graph Pattern
    Mining
slug: rethinking-memory-management-for-multi-tiered-systems
subtitle: Exploring Efficient Page Profiling and Migration in Large Heterogeneous
  Memory
title: Rethinking Memory Management for Multi-Tiered Systems
---

<p>The memory hierarchy in computer systems - the arrangement of different types of memory from fastest and smallest to slowest and largest - is becoming more complex. It's adding more tiers and becoming more heterogeneous (diverse in type) to cope with performance and capacity demands from applications. Multi-tier memory systems, which started from multi-socket non-uniform memory access (NUMA) architecture (where memory access time depends on the memory location relative to the processor), are now a standard solution for building scalable and cost-effective memory systems.</p>

<p>Most page management systems, which handle how data is organized and moved in memory, for multi-tier heterogeneous memory (HM) consist of three components:</p>

<ol>
	<li>A profiling mechanism: This identifies performance-critical data in applications, often by tracking page accesses. A page is a fixed-length contiguous block of virtual memory.</li>
	<li>A migration policy: This chooses which pages to move to top tiers.</li>
	<li>A migration mechanism: This moves pages across tiers, ideally with low overhead.</li>
</ol>

<h2>Research Overview</h2>

<p>Emerging multi-tiered large memory systems call for rethinking of memory profiling and migration to address unique problems unseen in traditional single- or two-tier systems with smaller capacity. The large memory capacity brings challenges to memory profiling. The limitation in profiling quality comes from (1) the rigid control over profiling overhead and (2) the ad-hoc formation of memory regions.</p>

<p>In addition, rich memory heterogeneity brings challenges to page migration. Existing solutions, e.g., tiered-AutoNUMA for multi-tiered memory, are built upon an abstraction extended from traditional NUMA systems. In these systems, page migration occurs between two neighboring tiers with awareness of no more than two NUMA distances (the relative cost of accessing memory from different locations). However, such an abstraction limits multi-tiered memory systems. Migrating pages from the lowest to the top tier in tier-by-tier steps requires multiple migration decisions, which can take several seconds and fails to timely migrate pages for high performance.</p>

<h3>Our Research Approach</h3>

<p>We argue that the following principles must be upheld to address the above problems:</p>

<ol>
	<li>Connecting the control of profiling overhead with the profiling mechanism to enable high-quality profiling</li>
	<li>Building a page migration policy specifically for multi-tiered memory to achieve high performance</li>
	<li>Introducing awareness of huge pages (memory pages larger than the standard size, used to improve performance)</li>
</ol>

<p><img src="https://www.chameleoncloud.org/media/filer_public/c1/fc/c1fce54d-121a-49e4-945a-6e5cc484bfdf/image1.png" width="100%"></p>

<p>We contribute a page management system called MTM (Multi-Tiered Memory Management) that realizes these principles on large four-tier memory. MTM decouples the control of profiling overhead from the number of memory regions, connecting it directly with the number of PTE (Page Table Entry) scans. This allows profiling quality and overhead to be distributed proportionally according to the variation of both spatial and temporal locality (how close data accesses are in memory and time).</p>

<p>MTM breaks the barrier that blocks the construction of a universal page-migration policy across tiers. It uses overhead-controlled, high-quality profiling to establish a global view of all memory regions in all tiers and considers all NUMA distances to decide page migration. In particular, MTM enables a "fast promotion and slow demotion" policy for high performance. Hot (frequently-accessed) pages identified in all lower tiers are ranked and directly promoted to the top tier, minimizing data movement through tiers. When a page is migrated out of the top tier to accommodate hot pages, it's moved to the next lower tier with available space.</p>

<h3>Running the Experiment on Chameleon</h3>

<p>To test MTM, we use a Chameleon node with four NUMA nodes. These NUMA nodes provide a four-tier memory system for our study. We find that Chameleon's hardware catalog is very useful for finding such a machine. There aren't many machines available like this in the Chameleon cloud, so using the hardware catalog helps us quickly find what we need.</p>

<h2>Experiment Artifacts</h2>

<p>Our paper on this research, <em>MTM: Rethinking Memory Profiling and Migration for Multi-Tiered Large Memory</em>, has been published in EuroSys'24.</p>

<p><a href="https://dl.acm.org/doi/pdf/10.1145/3627703.3650075">Read the paper!</a></p>

<h3>User Interview</h3>

<p><img src="https://www.chameleoncloud.org/media/filer_public/ed/34/ed34af2d-c882-4b57-80f9-5500e52d4b5f/image2.png" width="60%"></p>

<p><strong>Tell Us About Yourself!</strong></p>

<p>I'm Dong Li, an associate professor at University of California, Merced. My research focuses on high-performance computing (HPC), particularly memory systems in HPC and building efficient HPC systems to support AI/ML workloads.</p>

<p>My dream is to make HPC systems more scalable and more approachable by regular people.</p>

<p><strong>Do you have any advice for budding researchers?</strong></p>

<p>To students beginning their research journey, my advice is: Be patient and go deep into the research.</p>

<p><strong>How do you deal with research challenges?</strong></p>

<p>When facing challenges like paper rejections, I've learned to be patient and persistent, while being open-minded to reviewers' comments. These experiences have influenced my future work direction by helping me choose research topics more carefully.</p>

<p><strong>Why did you choose this field of research?</strong></p>

<p>I chose this direction of research because it aligns with my vision of future systems becoming more disaggregated and intelligent.</p>

<p>Looking ahead, we're seeking testbeds with more NUMA nodes and larger memory capacity. Given the upcoming CXL (Compute Express Link) memory, a new technology for high-speed CPU-to-device and CPU-to-memory connections, we're also looking for testbeds with CXL memory components to improve our experiments.</p>

<p><strong>Thank you for sharing your research with the Chameleon community!</strong></p>