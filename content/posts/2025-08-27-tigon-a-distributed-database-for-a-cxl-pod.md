---
abstract: <p>Traditional distributed databases are often slowed down by network communication
  overhead. The Tigon project introduces a new database design that tackles this bottleneck
  using Compute Express Link (CXL), a technology that allows multiple computer hosts
  to access a shared memory pool. Tigon employs a hybrid approach, keeping most data
  in fast, local host memory while moving only actively shared data to the CXL memory.
  This results in significant performance gains, achieving up to 2.5 times higher
  throughput than traditional databases. Since the multi-host CXL hardware required
  for this research was not yet commercially available, the project was brought to
  life by emulating the next-generation environment on Chameleon's bare-metal servers.</p>
authors:
- Yibo Huang
categories:
- User Experiments
date: '2025-08-27 20:34:34+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/b6/d2/b6d24f18-c96a-4a8e-b930-b31e3e997a1a/yibo_huang.jpg
related_posts:
- slug: minimizing-out-of-memory-failures-in-genomics-workflow-execution
  title: Minimizing Out-of-Memory Failures in Genomics Workflow Execution
- slug: rethinking-memory-management-for-multi-tiered-systems
  title: Rethinking Memory Management for Multi-Tiered Systems
- slug: exploring-process-in-memory-architecture-for-high-performance-graph-pattern-mining
  title: Exploring Process-in-memory Architecture for High-performance Graph Pattern
    Mining
slug: tigon-a-distributed-database-for-a-cxl-pod
subtitle: Leveraging Shared CXL Memory to Break Through Traditional Network Bottlenecks
title: 'Tigon: A Distributed Database for a CXL Pod'
---

<h2>Tigon: A Distributed Database for a CXL Pod</h2>

<h3>The Bottleneck in Today's Distributed Databases</h3>

<p>Imagine you are a manager leading a project that requires work from several departments in your company, each in a different city. To get the project done, you divide it into smaller tasks based on each department’s responsibility and email them their assignments. Then, you wait. Each department works on its task and emails the results back to you. Only after you have received and collected all the replies can you finalize the project.</p>

<p>This organizational structure is very similar to how today’s distributed databases work: they divide data into multiple partitions and store them on different hosts. And the multi-step process for completing the project mirrors how these databases execute transactions that need to access data on multiple hosts. A coordinator sends network requests to the relevant hosts, waits for them to complete their work, and then proceeds. This multi-step communication process, inherent to the partitioned design, introduces significant performance overhead.</p>

<h3>Tigon: Replacing Network Communication with Shared Memory</h3>

<figure style="text-align: center; margin: 1em 0;"><img alt="An architecture diagram showing 8-16 hosts with CPUs and DRAM connecting via PCIe to a Shared CXL Memory device." src="https://chameleoncloud.org/media/filer_public/ff/3f/ff3f56f0-c24b-4051-b502-98e9ab739217/cxl_ue_aug2025.png" style="height: auto;">
<figcaption>The Tigon architecture, which connects multiple hosts to a shared CXL memory device.</figcaption>
</figure>

<p>Our project, Tigon, tackles this overhead by leveraging a new technology called Compute Express Link (CXL). CXL allows multiple hosts to connect to a shared memory device via PCIe, creating what we call a "CXL pod". This architecture makes it possible to store all data in shared memory, enabling hosts to access any piece of data and synchronize with each other by performing atomic operations directly on that memory. This bypasses the slow and complex process of sending network messages entirely.</p>

<p>However, CXL memory must be used with care. While much faster than a network, it's slower than a host’s own local memory (DRAM) and has limited hardware support for inter-host cache coherence. To maximize CXL's benefits while avoiding its weaknesses, Tigon uses a hybrid approach. It starts by partitioning data across each host's local, high-speed DRAM. Then, Tigon intelligently moves <em>only</em> the small subset of data that is being actively accessed by multiple hosts into the shared CXL memory. This way, Tigon gets the massive speed benefit of direct memory access for shared data without being slowed down by CXL's limitations for local data.</p>

<p>The results are significant: Tigon achieves up to 2.5x higher throughput than traditional shared-nothing databases and 18.5x higher throughput than an RDMA-based distributed database.</p>

<h3>Developing and Evaluating Tigon on Chameleon</h3>

<p>Our research on Tigon was brought to life on Chameleon. CXL is a cutting-edge technology, and physical hardware for a multi-host CXL pod was not commercially available during our work. We needed a way to build and test for this future environment today. Chameleon’s powerful bare-metal servers gave us the low-level control needed to emulate this next-generation hardware. Using a <code>compute_icelake_r650</code> node at TACC, we were able to emulate CXL memory using remote NUMA memory. On a single physical node, we configured eight Virtual Machines (VMs) to act as the "hosts" in our CXL pod and configured them to share the emulated CXL memory device. This allowed us to precisely emulate the target environment for Tigon and run the extensive performance tests needed to validate our design.</p>

<h3>Explore Our Work</h3>

<ul>
	<li><a href="https://www.usenix.org/conference/osdi25/presentation/huang-yibo">Full Research Paper: OSDI '25</a></li>
	<li><a href="https://vldb.org/cidrdb/2025/pasha-an-efficient-scalable-database-architecture-for-cxl-pods.html">Short Vision Paper: CIDR '25</a></li>
	<li><a href="https://github.com/ut-datasys/tigon">Open-Source Code: GitHub</a></li>
</ul>

<hr>
<h3>About the Author</h3>

<div style="display: flex;"><img alt="Headshot of Yibo Huang." src="https://chameleoncloud.org/media/filer_public/b6/d2/b6d24f18-c96a-4a8e-b930-b31e3e997a1a/yibo_huang.jpg" style="width: 150px; height: 150px; border-radius: 50%;">
<div>
<p>I am Yibo Huang, a Ph.D. student at The University of Texas at Austin, advised by Prof. Emmett Witchel and Prof. Dixin Tang. My research focuses on efficient data systems on shared CXL memory.</p>

<p>For more details, please visit my homepage: <a href="https://yibo-huang.github.io/">https://yibo-huang.github.io/</a></p>
</div>
</div>

<h2>Most powerful piece of advice for students beginning research or finding a new research project?</h2>

<blockquote style="border-left: 4px solid #ccc; padding-left: 1em; margin-left: 0;">
<p>Be open-minded. Be ready to have your best ideas be wrong.</p>
</blockquote>

<h2>Why This Research?</h2>

<p>For decades, the architecture of distributed databases has been dictated by the limitations of the network. We've developed incredibly complex software to work around this fundamental bottleneck. When I started learning about CXL, I saw an opportunity to challenge that core assumption. What if the network was no longer the only way for computers to communicate? Exploring that question led directly to the ideas behind Tigon. It's exciting to work in an area where hardware advancements are opening the door to completely new software designs.</p>