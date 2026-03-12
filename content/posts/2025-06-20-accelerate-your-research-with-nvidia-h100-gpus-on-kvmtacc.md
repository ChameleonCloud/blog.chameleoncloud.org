---
abstract: <p>NVIDIA H100 GPUs are now available on KVM@TACC through a new reservation-based
  system. Learn how to leverage cutting-edge GPU acceleration, persistent storage,
  and flexible networking to maximize your research productivity within time-limited
  virtual machines.</p>
authors:
- Cody Hammock
categories:
- Tips and Tricks
date: '2025-06-20 17:44:12+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/b2/45/b245516b-3014-43db-868a-0a2d4e177ed8/h100_nodes.png
related_posts:
- slug: teaching-cloud-computing-with-chameleon-making-complex-concepts-accessible
  title: 'Teaching Cloud Computing with Chameleon: Making Complex Concepts Accessible'
- slug: leveraging-new-and-improved-chameleon-images
  title: Leveraging New and Improved Chameleon Images
- slug: faster-multimodal-ai-lower-gpu-costs
  title: Faster Multimodal AI, Lower GPU Costs
slug: accelerate-your-research-with-nvidia-h100-gpus-on-kvmtacc
subtitle: Tips and tricks for making the most of Chameleon's new GPU resources and
  reservation-based workflow
title: Accelerate Your Research with NVIDIA H100 GPUs on KVM@TACC
---

<p>The wait is over—<a href="https://chameleoncloud.org/blog/2025/06/02/chameleon-changelog-for-may-2025/">NVIDIA H100 GPUs are now available on KVM@TACC</a>! Whether you're training large language models, running complex simulations, or pushing the boundaries of scientific computing, our <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_gui.html#creating-leases-for-vms-with-gpus">new reservation-based VMs for the H100s</a> gives you access to cutting-edge GPU acceleration in a flexible virtual environment. More flexibility with GPUs on KVM is coming soon, including multi-GPU support and fractional GPU access for smaller jobs.</p>

<p><img height="400px" src="https://chameleoncloud.org/media/filer_public/b2/45/b245516b-3014-43db-868a-0a2d4e177ed8/h100_nodes.png" width="auto"></p>

<p>Due to high demand and growing interest in these powerful accelerators across the testbed, we've focused on making our new H100s accessible to as many Chameleon users as possible. These nodes pack a lot of heat. Each <a href="https://www.dell.com/en-us/shop/ipovw/poweredge-xe9640">node contains a Dell PowerEdge XE9640</a> equipped with Intel Xeon Platinum processor with 4 NVIDIA HGX H100 GPUs, 1 TB DDR5-4800 RAM, 2x 447.13 GB PCIe NVMe and 1x 3.84 TB PCIe NVMe. The nodes are connected with 1x 25 GbE Ethernet. These GPUs excel at:</p>

<ul>
	<li>Large language model training and inference</li>
	<li>High-resolution scientific simulations</li>
	<li>Complex deep learning workloads</li>
	<li>Accelerated data analytics and visualization</li>
</ul>

<p>To maximize the impact of these powerful machines, we've prioritized (for now) a virtual approach over bare metal, as virtualization makes it possible to share these resources among multiple users simultaneously to enable broad access for many GPU-hungry users. Users must <strong>reserve</strong> a flavor (similar to bare metal) before launching a GPU-enabled VM, with leases lasting up to one week. Time-limited reservations further improve availability by timeboxing usage and allowing more users access over a given period. Non-GPU-enabled VMs remain on-demand with no reservations needed <a href="https://chameleoncloud.org/blog/2025/06/02/chameleon-changelog-for-may-2025/">for the time being</a>. But, during the summer, we'll be extending the reservation model to the rest of KVM@TACC. This transition will help ensure fair access to all KVM resources as demand continues to grow.</p>

<p>While time-limited VMs represent a shift in workflow, KVM@TACC offers a number of features that make it well-suited for many common workflows (including CPU and GPU workloads) on Chameleon. Below, we dive into some of the tips and tricks for utilizing KVM and the new GPUs effectively.</p>

<h2>Reproducibility and Infrastructure as Code</h2>

<p>KVM virtual machines can be provisioned in minutes, making them ideal for rapid experimentation. Whether you're running benchmarks, testing new configurations, or deploying a training cluster, you can get started quickly without waiting for physical hardware.</p>

<p>By using automation tools like <strong>OpenStack Heat</strong>, <strong>Terraform</strong>, or <strong>Ansible</strong>, you can:</p>

<ul>
	<li>Rebuild environments from scratch between leases</li>
	<li>Share templates with collaborators or students</li>
	<li>Ensure results are repeatable across runs</li>
</ul>

<p>Even if your final workload runs on bare metal, KVM is an efficient prototyping platform for developing and refining your setup first.</p>

<h2>Persistent Storage and Snapshots</h2>

<p>Even if your VM lasts only a week, your data doesn't have to. <strong>OpenStack Cinder volumes</strong> let you store data independently of your virtual machines. Volumes:</p>

<ul>
	<li>Persist across leases</li>
	<li>Can be attached and detached as needed</li>
	<li>Can be resized or snapshotted for backup and rollback</li>
</ul>

<p>Snapshots of both VMs and volumes make it easy to pause and resume work across leases. If you need to shut down early or something goes wrong, you can pick up where you left off during your next reservation. This is especially valuable for teaching, debugging, and long-running research pipelines where reliability and repeatability are essential.</p>

<h2>Flexible Networking</h2>

<p>Another key resource that persists between reservations is your user-defined networking.</p>

<p>With <strong>OpenStack Neutron</strong>, you can:</p>

<ul>
	<li>Build custom virtual topologies</li>
	<li>Use floating IPs and load balancers</li>
	<li>Define security groups and firewall rules</li>
</ul>

<p>Whether you're experimenting with cloud-native architectures, building testbeds for microservices, or teaching networking concepts, KVM's networking capabilities enable realistic, reusable environments—even within a short lease.</p>

<h2>Ideal for Education</h2>

<p>KVM@TACC is well-suited to classroom use. Instructors can provide students with isolated virtual machines, reproducible lab environments, and the freedom to explore and recover from mistakes. A one-week lease is typically more than sufficient for assignments or short-term projects, and snapshots or automated rebuilds make it easy to start over if needed.</p>

<p>This setup supports instruction across a range of subjects—from networking and systems to security and DevOps—while giving students hands-on experience with infrastructure tools they'll encounter in the field.</p>

<h2>Getting Started with GPU-Enabled VMs</h2>

<p>Ready to launch your first GPU-enabled virtual machine? We've made it easy to get started:</p>

<ol>
	<li><strong>Follow our hands-on tutorial</strong> - Visit our <a href="https://chameleoncloud.org/experiment/share/48c7e345-e27e-4717-9459-d0e19743622c">Trovi sharing portal</a> for an interactive walkthrough that covers:

	<ul>
		<li>Making your first GPU reservation</li>
		<li>Launching a VM with GPU support</li>
		<li>Verifying GPU access and running sample workloads</li>
		<li>Best practices for managing your one-week lease</li>
	</ul>
	</li>
	<li><strong>Dive into the documentation</strong> - For detailed technical information about the reservation system, check out the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_gui.html#creating-leases-for-vms-with-gpus">official Chameleon documentation on reservations</a>.</li>
	<li><strong>Plan your workflow</strong> - Remember that leases last up to one week, so familiarize yourself with our persistence features (covered above) to ensure your work continues smoothly between reservations.</li>
</ol>

<p>In short, the reservation-based model introduces a limited VM lifetime, but KVM@TACC continues to offer a fast, flexible, and resilient environment for research and education. Whether you're launching a one-hour benchmark or a week-long simulation, KVM provides the tools to build quickly, iterate confidently, and preserve what matters most.</p>