---
abstract: <p>Researchers are using Chameleon's bare metal provisioning to design and
  prototype exascale operating systems and runtime software.</p>
authors:
- Makeda Easter
categories:
- User Experiments
- Announcements
date: '2016-02-29 18:02:38+00:00'
featured: false
hide_image: true
image: ''
slug: research-highlight-exascale-computing
subtitle: ''
title: 'Research Highlight: Exascale Computing'
---

<p>&lt;meta charset="UTF-8"&gt;</p>

<p><em>Argo project tests exascale prototype with Chameleon</em></p>

<p>Last year, President Obama announced <a href="https://www.whitehouse.gov/the-press-office/2015/07/29/executive-order-creating-national-strategic-computing-initiative">the Strategic Computing Initiative</a>, an executive order to increase the capacity of high performance computing (HPC) research, development, and deployment in the United States. One of the objectives is to accelerate towards exascale computing systems.</p>

<p>Exascale computing, capable of one exaFLOPs, or one billion billion calculations per second, will further advance research, enhance national security, and give the U.S. a competitive advantage. However, there exist many challenges in building a supercomputer 1,000 times more powerful than its predecessor, the first petascale computer, the IBM Roadrunner, in 2008. Scaling up existing technologies and architectures of current <a href="http://www.webopedia.com/TERM/P/petaflop.html">petaflop</a> systems will not lead to exascale. Researchers must redesign the entire system— from power, to memory, to system software— to make this future technology a reality.</p>

<p>Funded by the Department of Energy (DOE), the <a href="http://www.argo-osr.org/">Argo Project</a> is a three-year collaborative effort to develop a new approach for extreme-scale system software. The project involves the efforts of 40 researchers from three national laboratories and four universities working to design and prototype an exascale operating system and runtime stack.</p>

<p>Researchers are testing the project on <a href="https://www.chameleoncloud.org/">Chameleon</a>, a configurable experimental environment for large-scale cloud research, hosted by the University of Chicago and the Texas Advanced Computing Center (TACC).</p>

<p>“We have four goals for this project — the dynamic reconfiguring and partitioning of node resources in response to workload changes, allowance for massive concurrency inside the node, hierarchical and distributed control of the system for efficient resource usage and fault management, and an infrastructure to communicate and monitor the entire machine,” said Swann Perarnau, a postdoctoral researcher at Argonne National Laboratory, and collaborator on the Argo Project.</p>

<p>Perarnau took advantage of Chameleon’s large homogenous partition, comprising hundreds of nodes and deployed a small HPC cluster on top of it. Using Chameleon, he could test the four key innovations that define the project — 1) the Global Operating System, 2) the Node operating system, 3) the concurrency runtime, and 4) the backplane (BEACON).</p>

<p>The Global Operating System, or Argo Crew, handles machine configuration, deployment, monitoring, management, and application launching across the system. The Global OS was built on top of the <a href="https://www.openstack.org/">OpenStack</a> API provided by Chameleon, and additional provisioning tools such as Ansible and Salt. It manages nodes as enclaves — groups of nodes sharing the same configuration and controlled as a single entity.</p>

<p>The concurrency runtime, or Argobots, is a lightweight, low-level threading and tasking infrastructure over which applications are running on the exascale level. Argobots gives users total control over their resource utilization and provides a data movement infrastructure and tasking libraries for massively concurrent systems. </p>

<p>BEACON, the Backplane for Event and Control Notification, is a framework that provides an infrastructure and interfaces for gathering event data, based on components that can take appropriate action. And operating on each node of the Argo machine is the node operating system. It is based on Linux and provides new interfaces for the partitioning and control of future HPC architectures.</p>

<p>By using CHI, Chameleon’s <a href="https://www.chameleoncloud.org/docs/user-guides/bare-metal-user-guide/">bare metal provisioning</a> infrastructure, Perarnau was able to bypass issues of running the project on production HPC systems. “We wanted to validate the entire project, including the NodeOS that is based on patches to the Linux kernel. There’s not a lot of places we can do that — HPC machines in production are strictly controlled, and nobody will let us modify such a critical component,” he said.</p>

<p>Chameleon’s adaptability allows it to support a wide variety of cloud research and methods and architectures, enabling researchers to customize their software and hardware and test performance of their projects.</p>

<p>“The Argo project didn't have the right hardware nor the manpower to maintain the infrastructure needed for proper integration and testing of the entire software stack,” Perarnau added. “While we had full access to a small cluster, I think we saved weeks of additional system setup time, and many hours of maintenance work switching to Chameleon.”</p>

<p><img alt="" src="/media/uploads/2016/02/29/swann-sc15-demo-image.jpeg"></p>

<p>One of the major challenges in reaching exascale is <a href="http://spectrum.ieee.org/computing/hardware/power-problems-threaten-to-strangle-exascale-computing">energy usage and cost</a>. During <a href="http://sc15.supercomputing.org/">last year’s Supercomputing Conference,</a> the researchers were able to dynamically control the power of 20 nodes during a live demonstration running on Chameleon’s baremetal offering.</p>

<p>“The GlobalOS configures the nodes to be part of an enclave, the enclave receives a power budget and distributes it to the nodes using the backplane. And on the node, Argobots is able to reduce the number of cores it is using dynamically to reduce power usage,” Perarnau said.</p>

<p>Currently, the team is working with the DOE and plans for developing software targeting future platforms such as Argonne’s Aurora supercomputer that will be deployed in several years. Perarnau is certain that these innovative architectures developed through the project can be implemented on future exascale systems.<br>
<br>
Said Perarnau: “Argo was founded to design and prototype exascale operating systems and runtime software. We believe that some of the new techniques and tools we have developed can be tested on petascale systems and refined for exascale platforms.  We are currently working with our industry partners, such as Cray, Intel, and IBM to explore which techniques and features would be best suited for support on our next supercomputer.”</p>