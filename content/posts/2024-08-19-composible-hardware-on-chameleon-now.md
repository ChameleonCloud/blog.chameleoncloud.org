---
abstract: <p>Exciting news for Chameleon users! We're introducing GigaIO's composable
  hardware at CHI@UC and CHI@TACC. This innovative technology allows for flexible
  GPU configurations, supporting up to 8 GPUs per node. Learn how this new feature
  can enhance your research capabilities and improve hardware utilization. Discover
  the specifications and unique advantages of our new composable systems in this blog
  post.</p>
authors:
- Mike Sherman
categories:
- Tips and Tricks
- Announcements
date: '2024-08-19 20:14:54+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/0c/d0/0cd0107c-c751-4b74-8252-8f207a9728b9/uc-hardware.png
related_posts:
- slug: chameleon-testbed-secures-12-million-in-funding-for-phase-4
  title: Chameleon Testbed Secures $12 Million in Funding for Phase 4
- slug: chameleon-changelog-for-august-2022
  title: Chameleon Changelog for August 2022
slug: composible-hardware-on-chameleon-now
subtitle: Introducing new GigaIO nodes with A100 GPUs
title: Composable Hardware on Chameleon NOW!
---

<h1>Composable hardware in Chameleon!</h1>

<p>We're excited to announce the availability of GigaIO's composable hardware at both CHI@UC and CHI@TACC.</p>

<p>These systems consist of a set of bare metal nodes, accelerators, and a configurable PCIe backplane to connect them. GigaIO's own overview can be found <a href="https://gigaio.com/products/fabrex-system-overview/">here</a>.</p>

<p>Composable hardware enables more flexibility in how a node is configured. For example, at UC the system currently consists of 8 nodes and 8 A100 GPUs. By default, each node is connected to 1 GPU, but it is possible to connect up to all 8 GPUs to a single node, or any combination in between. This means that we can now support configurations that would have been too expensive before (scaling with 8 GPUs), as well as improving utilization of the available hardware (an experiment with 2 GPUs and one with 6 GPUs can be run at the same time).</p>

<h2>What you can do with it!</h2>

<p>The backplane is technically a fabric of interconnected PCIe Switches but can be thought of as a larger "Virtual Switch", allowing any of the accelerators to be attached to any node, where it will appear to the OS as if directly connected.</p>

<p>Due to the complexity of reconfiguring not just "GPU 1 to Node 4", but provisioning a path through the switch fabric, we do not have an API for reconfiguration available directly. Instead, each node's "default" configuration is available in the reference-api and for reservation. If you would like to reserve 4 GPUs and 1 node, you'll instead need to reserve all 4 nodes, since they each "come with" one GPU. After making your reservation, please submit a helpdesk ticket, and we will trigger the re-composition of the resources when your reservation starts.</p>

<p>The diagram below shows some example configurations and the corresponding reservations.</p>

<p><img src="https://chameleoncloud.org/media/filer_public/6f/aa/6faab8b0-16ce-4a23-b151-87750db23c26/gigaio-reservation-diagram.png"></p>

<p><em>Note: The 2x 25G Ethernet connections are not shown.</em></p>

<p>As compared to the existing LIQID deployment at TACC, the GigaIO systems support host-host and device-device communication, not just host-device. (Host-host is in beta and requires specific kernel support.)</p>

<ul>
	<li>In Device-Device mode, this allows technologies with Nvidia's GPUDirect "peer to peer" mode to operate, enabling memory access, transfers, and synchronization between GPUs without going through the CPU or memory controller of the host system. For more details, see <a href="https://gigaio.com/wp-content/uploads/2020/12/GigaIO-USC-V3.0-1.pdf">GigaIO/Nvidia's whitepaper</a> on this mode.</li>
	<li>In Host-Host mode, it is possible to use the PCIe connection as a lossless data transport, similar to InfiniBand, and e.g. MPI jobs can leverage the high bandwidth and low latency. <a href="https://gigaio.com/wp-content/uploads/2022/01/GigaIO-FabreX-composability_v1-1.pdf">Additionally, this mode allows DMA between servers, both for memory pooling, and for access to I/O and peripherals.</a></li>
</ul>

<h2>Hardware in CHI@UC:</h2>

<h3>Servers</h3>

<p>8 Dell R6525 servers, with node_type "compute_gigaio"</p>

<ul>
	<li>2x AMD EPYC 7763 64-Core Processors, for a total of 256 threads</li>
	<li>512 GB of RAM</li>
	<li>2x 480GB SATA SSDs</li>
	<li>2x 25G NICs</li>
	<li>8x lanes of PCIe 4.0 to the backplane: (128 Gb/s) Half Duplex, (256 Gb/s) Full Duplex</li>
</ul>

<h3>Accelerators</h3>

<p>8 Nvidia A100 PCIe GPUs, with:</p>

<ul>
	<li>80 GB RAM</li>
	<li>8x lanes of PCIe 4.0 to the backplane: (128 Gb/s) Half Duplex, (256 Gb/s) Full Duplex</li>
</ul>

<h3>Connectivity</h3>

<p><img src="https://chameleoncloud.org/media/filer_public/0c/d0/0cd0107c-c751-4b74-8252-8f207a9728b9/uc-hardware.png" width="50%"></p>

<h2>Hardware in CHI@TACC:</h2>

<h3>GigaIO:</h3>

<p>6 PowerEdge R650 nodes, of node type "compute_gigaio"</p>

<ul>
	<li>Intel Xeon Platinum 8380</li>
	<li>256 GB RAM</li>
	<li>1x 40 GbE NIC</li>
	<li>1x 480 GB SATA SSD</li>
	<li>8x lanes of PCIe 4.0 to the backplane: (128 Gb/s) Half Duplex, (256 Gb/s) Full Duplex</li>
</ul>

<p>4 Nvidia A100-class PCIe GPUs</p>

<ul>
	<li>2x GA100 [A100 PCIe 40GB]</li>
	<li>2x GA100GL [A30 PCIe]</li>
</ul>

<p><img src="https://chameleoncloud.org/media/filer_public/41/d1/41d19d38-67ef-4ca1-a310-173ef8cd0c7b/tacc-hardware.png" width="50%"></p>

<h3>LIQID:</h3>

<p>8 PowerEdge R6525 nodes, of node type "compute_liqid"</p>

<ul>
	<li>AMD EPYC 7763</li>
	<li>256 GB RAM</li>
	<li>1x 480 GB SATA SSD</li>
	<li>16x lanes of PCIe 4.0 to the backplane</li>
</ul>

<p>10 x GA100 [A100 PCIe 40GB]<br>
16 x Samsung NVMe "Honeybadger" 3839 GB</p>