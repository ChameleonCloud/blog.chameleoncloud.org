---
abstract: "<p dir=\"ltr\">Chameleon has added lots of new and exciting storage capabilites\
  \ in recent\_months - learn all about the resources available, how to conduct storage\
  \ research on Chameleon, and examples of storage experiments being conducted by\
  \ researchers at the University of Chicago, Carnegie Mellon University, Virginia\
  \ Tech, and Rutgers University. There's also a fully packaged experiment and accompanying\
  \ YouTube video that you can run on Trovi to practice with!</p>"
authors:
- Haryadi Gunawi
categories:
- Tips and Tricks
date: '2022-03-29 11:12:05+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/61/f6/61f6bf64-c5e4-4810-a478-6f8d6ee61d27/screen_shot_2022-03-29_at_111715_am.png
related_posts: []
slug: maximizing-storage-research-on-chameleon
subtitle: ''
title: Conducting Storage Research on Chameleon
---

<p dir="ltr"> </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-609902a6-7fff-6e6d-29c2-9404f5ebb47f"><img src="https://www.chameleoncloud.org/media/filer_public/83/4b/834b43aa-5c3d-46f2-b9c4-ce5374cb1d0d/nvme_nodes.png" style="width: 526px; height: 480px;"></b></p>

<p dir="ltr" style="text-align: center;">Chameleon NVME nodes<br>
 </p>

<p dir="ltr">Over the past decade, the storage market has grown enormously and with the explosion of big data, it continues to expand with efforts to optimize storing big data.  For example, the solid-state drive (SSD) market is currently valued at $20--34 billion according to multiple sources and forecasted to reach $47--80.34 billion by 2025.  Similarly, the non-volatile memory market is expected to reach $82 billion by 2022. As data is continuously collected and analyzed at large scales, storage research needs to continue to grow in all aspects, such as performance, reliability, manageability, security, among many others.  To support this research, Chameleon took steps to expand and diversify the range of storage solutions it provides to users. </p>

<p> </p>

<p dir="ltr">In the past few months, Chameleon has continued to expand its storage capabilities:</p>

<ul>
	<li dir="ltr">
	<p dir="ltr">10 Dell R6525 nodes, each with 960GB Kioxia NVME SSD, 256GB RAM, 200G HDR Infiniband, 2x 25G Ethernet.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">2 nodes each with 2x 7.68TB Intel Enterprise SSDs</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">2 nodes each with 2x 7.68TB Samsung Enterprise SSDs</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">2 nodes each with 4x 1.92TB Samsung Enterprise SSDs</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">2 nodes each with 2x 2TB Corsair Consumer SSDs</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">2 Dell R840 Quad-CPU nodes, with 112 Cores, 768Gb of RAM, and 3TB of Intel Optane NVDIMM, connected to the InfiniBand Fabric with 100GB/s HDR100</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Including previous storage hierarchy nodes (4x Seagate 600GB HDDs,, 4x Intel 1.6TB SSDs, 2x Intel 2TB Optane NVME SSDs P3700) and traditional storage nodes (20 nodes with 1x Intel 400G SSD)</p>
	</li>
</ul>

<p> </p>

<p dir="ltr">On top of all of these, Chameleon also provides many GPU nodes connected to the storage machines, fostering more hybrid storage/machine learning research.  The last decade has witnessed significant growth in the development and application of artificial intelligence (AI) and machine learning (ML).  Many industries, including storage, are either applying or planning to use AI/ML techniques to address their respective problem domains.  In literature, we see an increase of research that leverages machine learning for solving system problems, such as management of networking, CPU/GPU, memory, energy, code analysis/compilation, and many forms of distributed systems.  Likewise, with the significant increase of storage capabilities, Chameleon can cater to storage/machine learning research. </p>

<p> </p>

<p dir="ltr">For academia, an important support Chameleon provides is for heterogeneous research.  It can be challenging for academic researchers to acquire various storage devices from different vendors.  Strong publications require strong evaluation of the storage stack across different types of devices.  Typically academic researchers must reach out to some industry partners to have access to such devices.   Purchasing enterprise SSDs is also becoming non-economical as many different models are required to evaluate the function of storage prototypes on different types of SSDs, but the devices are only heavily used near publication deadlines.  For these reasons, the new Chameleon storage capabilities hopefully can meet the needs of the storage community in this space.  Below are sharings from several storage researchers on how the community can use the nodes.</p>

<p> </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-8d9664e2-7fff-773b-9766-d692dcd0fa00"><img src="https://www.chameleoncloud.org/media/filer_public/58/2d/582d4a1a-fa9d-4149-a8ee-f0e92159c8a1/linnos_architecture.png" style="width: 280px; height: 164px;"></b></p>

<p dir="ltr" style="text-align: center;">Figure 1: The LinnOS architecture with a light neural network that can learn heterogeneous consumer and datacenter SSDs.</p>

<p> </p>

<p dir="ltr"><a href="http://people.cs.uchicago.edu/~haryadi/">Prof. Haryadi Gunawi’s</a> team at the University of Chicago has been doing research on SSDs in the past few  years. A prime example of his prior work that could have benefited from the Chameleon storage infrastructure is LinnOS, <a href="https://ucare.cs.uchicago.edu/pdf/osdi20-LinnOS.pdf">published at OSDI 2020</a>, also<a href="https://chameleoncloud.org/blog/2020/11/01/chameleon-and-reproducibility-linnos-case-study/"> packaged as a shareable experiment with Chameleon Trovi</a>. This work addresses performance anomalies; such anomalies, even at the millisecond granularity, can cause monetary and productivity losses, and as a result, many varieties of storage products and services are advertised with percentile-based SLOs.A key to manage performance anomalies is latency prediction, which is becoming more challenging as devices are getting faster. In the LinnOS project, we examine whether we can build a machine learning model that can predict the speed (“fast” or “slow”) of every I/O that will be sent to an SSD device. For a strong evaluation of the model, his team needs to showcase that the model can work on various storage workloads and SSD models, both at consumer and enterprise levels. Fortunately his team managed to access three (expensive) enterprise-level SSDs. Various storage traces were run on various devices to collect different performance profiles with which the model can be trained. Chameleon’s support for heterogeneous SSDs will empower research like this one. </p>

<p> </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-8d9664e2-7fff-773b-9766-d692dcd0fa00"><img src="https://www.chameleoncloud.org/media/filer_public/91/9d/919d06d8-cde1-4eec-981f-8d4283a31c3c/ssd_time_windows.png" style="width: 478px; height: 169px;"></b></p>

<p dir="ltr" style="text-align: center;">Figure 2: IODA’s time window (TW) contract for predictable latencies that was evaluated on Linux-managed flash array.</p>

<p> </p>

<p dir="ltr"><a href="https://huaicheng.github.io">Dr. Huaicheng Li’s</a> recent work requires an array of SSDs for tail-latency profiling and evaluating software policy designs to achieve predictable latencies (published at SOSP 2021, under the title of <a href="https://dl.acm.org/doi/10.1145/3477132.3483573">“IODA: A host/device co-design for strong predictability contract on model flash storage”</a>). This is an important research problem to tackle as it can cause severe SLO violations on a large scale. Although IODA requires device-level access (hence the use of SSD emulators such as FEMU) to modify the host-SSD interface, the work requires baseline experiments running on bare flash arrays to show how Linux software RAID running on an array of SSDs suffers from performance limitations. Note SSDs are usually organized into RAID for reliability guarantees.  For this, his team had to purchase a high-end machine with at least more than 4 PCIe slots to attach 4 SSDs and other peripherals and set up a flash array using Linux software RAID. Today, Chameleon also supports flash array research with 2 nodes running 4 SSDs (including many other machines running multiple disks). Users can install their own Linux and modify the Linux Software RAID layer. Other papers that can use the Chameleon storage infrastructure include: <a href="https://dl.acm.org/doi/10.1109/MSST.2011.5937224">Harmonia [MSST 11]</a>, <a href="https://www.usenix.org/system/files/conference/fast13/fast13-final151.pdf">Geoko [FAST 13]</a>, <a href="https://www.usenix.org/system/files/conference/atc14/atc14-paper-skourtis.pdf">FlashOnRails [ATC 14]</a>, <a href="https://dl.acm.org/doi/10.1145/2723372.2742798">Purity [SIGMOD 15]</a>, <a href="https://www.usenix.org/system/files/atc19-kim-jaeho.pdf">SWAN [ATC 19]</a>, <a href="https://dl.acm.org/doi/abs/10.1145/3465406">RAIL [TOS 21]</a>.</p>

<p><br>
 </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-8d9664e2-7fff-773b-9766-d692dcd0fa00"><img src="https://www.chameleoncloud.org/media/filer_public/9e/54/9e54175f-1138-4a71-b69a-1ec77b5b6a4a/pactree.png" style="width: 299px; height: 191px;"></b></p>

<p dir="ltr" style="text-align: center;">Figure 3: PACTree achieves high performance and scalability on Intel Optane PM by reducing PM bandwidth consumption and asynchronous concurrency control.<b> </b></p>

<p> </p>

<p dir="ltr"><a href="https://multics69.github.io">Prof. Changwoo Min’s</a> team at Virginia Tech has been working on storage systems optimized for byte-addressable persistent memory (PM). One example is PACTree, a highly scalable persistent key-value store optimized for Intel Optane PM, published in SOSP 2021. His team first conducted a performance characterization study of Optane PM to understand the performance and scalability of the real PM hardware. The key findings are (1) PM bandwidth would be the first bottleneck in PM-optimized storage stacks and (2) slow PM write latency could be a scalability bottleneck. Based on the findings, his team designed the new key-value store, PACTree, which reduces PM bandwidth consumption and avoids the slow PM latency being a scalability bottleneck. His team needs a multi-core machine (with a high core count) with Optane PM to demonstrate the performance and scalability of PACTree. Through collaboration, his team could access such a high-core count PM machine. Today, Chameleon supports PM servers equipped with Optane PM (3TB) and 4-socket Xeon processors (112 cores). Not only <a href="https://dl.acm.org/doi/10.1145/3477132.3483589">PACTree [SOSP21]</a> but also other works, such as <a href="https://www.usenix.org/conference/atc21/presentation/krishnan">TIPS [ATC 21]</a> and <a href="https://dl.acm.org/doi/10.1145/3373376.3378483">TimeStone [ASPLOS 20]</a>, can be run on Chameleon infrastructure.<br>
 </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-8d9664e2-7fff-773b-9766-d692dcd0fa00"><img src="https://www.chameleoncloud.org/media/filer_public/06/4e/064ef341-757d-44b4-896f-a19388ba6936/file_system.png" style="width: 346px; height: 184px;"></b></p>

<p dir="ltr" style="text-align: center;">Figure 4: Cross-layered file system design split across the userspace, the storage, and the OS. Applications and runtimes use the cross-layered design to offload traditional I/O operations and data processing operations fused as CISC-styled operations to exploit the capabilities of in-storage computation. </p>

<p> </p>

<p dir="ltr"><a href="https://sudarsunkannan.github.io">Prof. Sudarsun Kannan's</a> team at Rutgers has been working on understanding the benefits and implications of near-storage computing and memory heterogeneity. For example, his group's recent near-storage computing and heterogeneity research appeared in venues like <a href="https://www.usenix.org/system/files/osdi20-ren.pdf">OSDI 2020 (CrossFS)</a>, <a href="https://www.usenix.org/conference/fast22/presentation/zhang-jian">FAST 2022 (FusionFS)</a>, and <a href="https://dl.acm.org/doi/10.1145/3445814.3446745">ASPLOS 2021 (KLOCs)</a>. CrossFS identified the benefits of disaggregating the file systems across the userspace, the storage, and the OS for higher I/O performance and fine-grained concurrency. FusionFS extended CrossFS to design CISC-styled (Complex Instruction Set Computer) I/O operations to organically offload data for near-storage processing and reduce I/O costs like data movement, system calls, and PCIe communication. In contrast, KLOCs explored the benefits of memory heterogeneity using Optane memory. Fortunately, his team got access to Optane PMs through collaboration with other groups but had to emulate near-storage computing devices. The presence of Optane PMs and near-storage computing devices (for example, <a href="https://www.xilinx.com/applications/data-center/computational-storage/smartssd.html">SmartSSD</a>) in Chameleon would provide an opportunity for his group and other researchers to conduct more detailed studies using real devices and explore new dimensions for utilizing near-storage computing and storage heterogeneity.</p>

<p> </p>

<p dir="ltr">To help the storage community test out the new storage nodes, Ray Andrew, a UChicago PhD student has created a simple experiment package (using Chameleon's Trovi feature) which you can reproduce and run here: <a href="https://www.chameleoncloud.org/experiment/share/81?s=a8199ef35ffa48d5828d4b9a45a6385e">https://www.chameleoncloud.org/experiment/share/81?s=a8199ef35ffa48d5828d4b9a45a6385e</a></p>

<p> </p>

<p dir="ltr">This experiment runs the FIO benchmarks on the NVMe devices and generates a simple read/write throughput graph. Ray has also provided a YouTube video on how to use this package: <b id="docs-internal-guid-8d9664e2-7fff-773b-9766-d692dcd0fa00"><a href="https://www.youtube.com/watch?v=grUOrKkiYuQ">https://www.youtube.com/watch?v=grUOrKkiYuQ</a></b></p>