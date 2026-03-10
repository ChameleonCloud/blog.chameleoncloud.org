---
abstract: '<p>Not sure whether to use bare metal or KVM for your next Chameleon experiment?
  You''re not alone. With KVM''s recent addition of H100 GPUs and advance reservations,
  the choice isn''t always obvious. This comprehensive comparison walks you through
  the practical trade-offs: when you need the isolation of bare metal for accurate
  benchmarking, when KVM''s 6-month leases and resource sharing make more sense, and
  how to navigate the different storage and networking options. Make informed infrastructure
  decisions that accelerate your research.</p>'
authors:
- Mark Powers
categories:
- Tips and Tricks
date: '2025-10-21 20:49:14+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/51/c8/51c8abe2-e544-45cc-a442-5fe108795396/group_8.png
slug: bare-metal-or-kvm-which-should-you-choose-and-when
subtitle: A detailed comparison of hardware access, reservation systems, and storage
  options for users
title: Bare Metal or KVM? Which Should You Choose and When
---

<p>Most of the Chameleon testbed is available via bare metal instances. This is because launching a bare metal instance gives you full control over a physical server in our data centers, allowing you to e.g., collect benchmarks and power usage without worrying about virtualization overhead or noisy neighbors. The drawback is that in order to provide sufficient isolation between experiments we can only have one experiment at a time on a bare metal node. This functionality is implemented through the <a href="https://www.openstack.org/">OpenStack</a> + <a href="https://docs.openstack.org/ironic/latest/">Ironic</a> mainstream open source Infrastructure-as-a-Service implementation that has been heavily modified to suit the science use case, for example, by adding <a href="https://chameleoncloud.readthedocs.io/en/latest/user/federation.html">support for federated identity</a>. The most important such addition is <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/reservations/index.html">support for advance reservations</a> that allow you to claim temporary ownership of specific resources in the future</p>

<p>In addition to bare metal we also support virtualized instances, currently through the KVM@TACC site. Virtualized instances introduce additional overhead but on the other hand we can host several virtual instances on one node – and therefore several experiments executing concurrently – allowing for a much better use of resources. Historically, KVM@TACC consisted of homogenous compute nodes, without GPUs or other interesting features, and while it was also operated using OpenStack, we did not support many of the features present on bare metal partition of the testbed, including advance reservations and allocation charging. This changed over the last few months: we now have virtualized instances with H100 GPUs and are in general looking to spruce up our virtualized offering in order to provide more cost-effective access to GPU resources. To ensure that you can make efficient use of those features we've been bringing the KVM@TACC experience up to parity with bare metal.</p>

<p>The table below calls out the most important differences that persist between the bare metal and virtualized offerings on the system.</p>

<table border="1" cellpadding="5" cellspacing="0" style="border-collapse: collapse;">
	<thead>
		<tr>
			<th>Feature</th>
			<th>Bare Metal*</th>
			<th>KVM</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>Hardware Discovery</td>
			<td><a href="https://chameleoncloud.org/hardware/">Hardware browser</a></td>
			<td><a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_hardware.html">Documentation</a></td>
		</tr>
		<tr>
			<td>Resource model</td>
			<td>Non-fungible resources</td>
			<td>Fungible resources</td>
		</tr>
		<tr>
			<td>Availability calendar</td>
			<td>Node calendar - individual availability per node</td>
			<td>Flavor calendar - aggregates availability over time</td>
		</tr>
		<tr>
			<td>Advance Reservations</td>
			<td>Physical nodes<br>
			Networks<br>
			Floating IPs</td>
			<td><a href="https://chameleoncloud.org/learn/frequently-asked-questions/#toc-how-are-kvm-instances-virtual-machines-charged-">Virtualized Flavors</a></td>
		</tr>
		<tr>
			<td>Lease limits</td>
			<td>1 week</td>
			<td>Depends on the flavor (1 week for GPU VMs, 6 months for other VMs)</td>
		</tr>
		<tr>
			<td>Snapshots</td>
			<td><a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images/cc_snapshot.html">cc-snapshot</a>, available from within your instance only</td>
			<td><a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_gui.html#creating-a-instance-snapshot">Snapshots via the API</a></td>
		</tr>
		<tr>
			<td>Storage</td>
			<td><a href="https://chameleoncloud.readthedocs.io/en/latest/technical/swift/index.html">Object store</a> <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/shares/index.html">NFS shares</a></td>
			<td><a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_volumes.html">Persistant cinder volumes</a></td>
		</tr>
		<tr>
			<td>Firewall Security</td>
			<td><code>firewalld</code> service, within your instance</td>
			<td><a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_gui.html#security-groups">security groups</a></td>
		</tr>
	</tbody>
</table>

<p><em>*These features apply to CHI@TACC and CHI@UC. The status of these features at CHI@NCAR is still in progress as the site is under construction.</em></p>

<p><strong>Bare Metal on Chameleon</strong>. To launch a bare metal instance, first you must make a reservation for a node, which refers to the physical server hardware you will be using. When making this reservation, you'll need to specify how many nodes you want (which will be how many instances you can provision), and you can specify a property filter for those nodes (such as matching a type of node, name, or other feature). You can use the <a href="https://chameleoncloud.org/hardware/">hardware browser</a> to see the specification of each node, and the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/reservations/gui_reservations.html#the-lease-calendars">hardware calendar</a> to see when each node is free to reserve. In order to share resources effectively between users on Chameleon, we enforce limits on reservations, including limiting maximum reservation length to 7 days.</p>

<p>Once your lease is active, you can <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/baremetal/launching_gui.html">provision an instance</a> onto the reserved nodes using a Chameleon supported image (or you are free to bring your own). The Chameleon supported images come with <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images/cc_snapshot.html">cc-snapshot</a>, which is a tool that can snapshot your running baremetal instance, which you can use to install and configure experiment software once, and reuse that work in the future.</p>

<p>Unique to bare metal sites, you can also reserve networks and floating IPs. These networks do things like setup <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/networks/networks_stitching.html">layer 2 stitching to FABRIC</a>. Reservable floating IPs work the same as ad-hoc floating IPs, but their lifecycle is tied to the corresponding lease's lifecycle. Only our bare metal sites have support for the Swift object store, which lets you store large amounts of data, meaning CHI@UC and CHI@TACC are the only sites that you can use <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/swift/swift_mount.html"><code>cc-mount-object-store</code></a>. Similarly, those sites are the only place that we support the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/shares/index.html">shared file system</a>, which lets you mount a persistent NFS share on your bare metal instance.</p>

<p><strong>KVM on Chameleon.</strong> KVM has undergone a transformation in recent months. Now to get started with your experiment, you'll need to make a reservation for a flavor. On KVM, resources are virtualized and fungible, and the hardware specification is abstracted away. Instead, the flavor contains a higher level specification for a number of CPU threads, GB of memory, GB or storage space, and in some cases GPUs. When making this reservation, you'll specify which of our <a href="https://chameleoncloud.org/learn/frequently-asked-questions/#toc-how-are-kvm-instances-virtual-machines-charged-">existing flavors</a> meets your requirements, and how many VMs you want to launch. Like for bare metal, we enforce some limits on flavor leases to ensure resources are shared between users. We permit up to 6 month leases for standard flavors, but for flavors using GPUs, leases must be no more than 7 days in length.</p>

<p>When a reservation is made, you'll be assigned a slot on one of KVM@TACC's hosts that your VM will run on. If you are interested in knowing what kind of hardware is being used, you can read <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_hardware.html">more in our documentation</a>. Similar to bare metal, we have an <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_gui.html#checking-availability">availability calendar</a> for flavor availability, which allows you to see the capacity of each type of resource request over time as a line graph. This is particularly useful for checking how many GPUs are available, which are relatively scarce.</p>

<p>Once your lease is active, you'll be able to <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_gui.html#launching-instances">launch an instance</a> using a new flavor that is tied to your reservation. The same Chameleon supported images work with VMs as on bare metal, but a few things are still different. On KVM@TACC, you can <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_gui.html#creating-a-instance-snapshot">create a snapshot</a> outside of your instance, which is a much quicker process. Additionally, you'll notice the <code>firewalld</code> service from our images is not enabled by default in a VM. Instead, you can manage traffic with <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_gui.html#security-groups">security groups</a>, and which you'll have to set up even for SSH.</p>

<p>While KVM@TACC does not have its own object store, you are able to <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/cli/authentication.html">configure an instance with authentication</a> to CHI@TACC's object store, which would allow you to read or write data there as on bare metal. Additionally, instead of the shared file system, KVM@TACC supports <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_volumes.html">persistent storage volumes</a>, which allow you to add persistent storage devices to your instances and mount them directly, rather than through our NFS server.</p>

<p><strong>The Future of KVM.</strong> As it stands currently, most workflows on bare metal have an equivalent workflow on KVM with the recent addition of bounded and advanced reservations. Over Phase 4 of Chameleon, we are looking at further improvements towards bringing bare metal and KVM usage together, by reducing friction with the shared file system, improving floating IP management, improving testbed interfaces (python-chi), and eventually hardware between bare metal and KVM. As always, we would love to hear from you if there are any features related to Chameleon infrastructure that helps us prioritize this work. Please feel free to join <a href="http://forum.chameleoncloud.org/t/discussion-bare-metal-vs-kvm-share-your-experiences-and-questions/142?u=mtrichardson">our discussion</a> &lt;here&gt; on the Chameleon forum.&lt;/here&gt;</p>