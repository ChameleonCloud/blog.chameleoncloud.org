---
abstract: <p>New hardware, virtual-clusters with one click, and new training materials
  -- we have some new tricks and not a few treats for our users!</p>
authors:
- Kate Keahey
categories:
- Announcements
date: '2016-10-31 16:55:53+00:00'
featured: false
hide_image: true
image: ''
related_posts: []
slug: trick-or-treat
subtitle: ''
title: Trick or Treat?
---

<p><img alt="" src="https://www.chameleoncloud.org/media/uploads/2016/10/31/chameleon-pumpkin-medium.png"></p>

<p>In the true Halloween spirit we declared war on – and vanquished (or at least did severe damage to) – several dangerous demons that we are all afflicted by on a daily basis:</p>

<p><strong>The Ghost of Complexity Past.</strong> Many of our users want to deploy “virtual clusters”, such as for example OpenStack installations or MPI clusters. They are often hard to deploy because their configuration involves exchange of information typically available only at deployment time, such as hostnames or security keys. These last configuration steps are therefore often carried out manually, increasing complexity and making reproducibility hard. To solve this problem we have deployed a tool for configuring such complex appliances so that they can be deployed automatically. Our complex appliance deployment orchestrator allows you to configure complex “virtual clusters” on bare metal hardware “with one click”. It takes an image (appliance) and a template – a document that defines how many instances of this appliance to deploy, what information to exchange, and what scripts to run on deployment – and then deploys a cluster of specified size automatically, and in exactly the same way, time and time again. It  also supports parameterizing deployments – for example, configuring the number of nodes of a cluster. Complex appliance support is currently available on CHI@UC and CHI@TACC. To get started, please check out <a href="https://www.chameleoncloud.org/docs/complex-appliances/"><u>our guide</u></a> to working with complex appliances.</p>

<p><strong>The time-sucking Vampire of Having-to-Do-Everything-Yourself.</strong> While we are confident that many of you will want to configure your own complex appliances representing interesting frameworks you have developed, we thought we’d get you started with a few. They include several of the most popular distributed applications and frameworks:</p>

<ul>
	<li>
	<p><a href="https://www.chameleoncloud.org/appliances/30/"><u>OpenStack Mitaka</u></a>: this complex appliance deploys OpenStack Mitaka with DevStack over one controller node and a configurable number of compute nodes</p>
	</li>
	<li>
	<p><a href="https://www.chameleoncloud.org/appliances/29/"><u>MPI bare-metal cluster</u></a>: this complex appliance deploys a bare-metal MPI cluster using the MVAPICH2 implementation</p>
	</li>
	<li>
	<p><a href="https://www.chameleoncloud.org/appliances/25/"><u>NFS share</u></a>: this complex appliance deploys an NFS server exporting a directory to a configurable number of NFS clients</p>
	</li>
	<li>
	<p><a href="https://www.chameleoncloud.org/appliances/28/"><u>MPI + SR-IOV KVM cluster</u></a>: this complex appliance deploys an MPI cluster of KVM virtual machines using the MVAPICH2-Virt implementation and configured with SR-IOV for high-performance communication over Infiniband</p>
	</li>
</ul>

<p>All of these complex appliances can be easily found in our <a href="http://www.chameleoncloud.org/appliances"><u>Appliance Catalog</u></a>; they are identified by a cluster icon in the top right corner. We hope that you will configure and share with other users complex appliances that represent the research you are working on using our instructions for <a href="https://www.chameleoncloud.org/docs/complex-appliances/#toc-customizing-an-existing-template"><u>customizing or writing new complex appliances</u></a> and <a href="https://www.chameleoncloud.org/docs/complex-appliances/#toc-sharing-new-complex-appliances"><u>sharing them</u></a>.</p>

<p><strong>The Nightmare of Knowing-about-Cool-New-Hardware-without-Being-Able-to-Use-It.</strong> Now you can lay your hands on non-volatile memory and FPGAs! We added two NVMe SSDs to each of our two storage hierarchy nodes. Each device is a 2.0 TB Intel SSD DC P3700, advertised with a sequential read throughput of 2,800 MB/s and a sequential write throughput of 2,000 MB/s. The storage hierarchy available on each of the storage nodes is now: 512 GiB of RAM, two NVMe SSDs of 2.0 TB each, four Intel S3610 SSDs of 1.6 TB each, and four 15K SAS HDDs of 600 GB each. We also made available four FPGA nodes. Each of these nodes is fitted with a <a href="http://www.nallatech.com/store/pcie-accelerator-cards/nallatech-385a-arria10-1150-fpga/"><u>Nallatech 385A board</u></a> with an Altera Arria 10 1150 GX FPGA (up to 1.5 TFlops), 8 GiB DDR3 of on-card memory, and dual QSFP 10/40 GbE support. They are configured to run OpenCL code, but they can be reconfigured (by a request to our help desk) to run compiled designs prepared with Altera Quartus. Due to export control limitations, access to the development toolchain requires verification of your user profile. We explain how to gain access to the development toolchain and execute code on the FPGA nodes in the <a href="https://www.chameleoncloud.org/docs/bare-metal-user-guide/fpga/"><u>FPGA guide</u></a>.</p>

<p><strong>The Specter of Too-High-Entry-Barrier.</strong> We replaced the dusty old spellbook that served us all so well with a fresh bare metal guide that is much easier to follow for different groups of users. We have now split <a href="https://www.chameleoncloud.org/docs/bare-metal-user-guide/"><u>the documentation</u></a> into two parts, one focusing on using Chameleon through its web interface, and the other focusing on using Chameleon through command-line and APIs. We also created a <a href="https://www.chameleoncloud.org/docs/community/"><u>Community Resources</u></a> space on the Chameleon website (currently available off the Documentation tab) and added two new training videos demonstrating how to use Chameleon for experimental research with a use case showing a performance evaluation of Spark – <a href="https://www.youtube.com/watch?v=J6UPmT41gq8"><u>one for Linux and OS X users</u></a> and <a href="https://www.youtube.com/watch?v=FRGehi9UVG4"><u>one for Windows users</u></a>. From now on, this will be the space where education and training materials using Chameleon will get released – we know that many of you are using Chameleon in classes and hope that these materials will be useful. As always, we are interested in your feedback, so please <a href="https://www.chameleoncloud.org/user/help/ticket/new/"><u>let us know</u></a> what types of training materials you would like to see or if you have any you would like to contribute!</p>

<p>Happy Halloween!</p>