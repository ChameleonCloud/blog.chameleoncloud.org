---
abstract: <p>An overview of Chameleon's KVM cloud, and a new experiment pattern demo.</p>
authors:
- Adam Cooper
categories:
- Tips and Tricks
date: '2022-07-19 01:41:28+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/33/dd/33dd28aa-add7-4361-bd56-2d047fc6fbad/pexels-photo-1089438.png
slug: experimenting-with-virtual-machines-on-chameleon
subtitle: ''
title: Experimenting With Virtual Machines on Chameleon
---

<p>We all know how wonderful it is to work with the diverse array of bare metal compute resources offered by Chameleon, but what about research which doesn’t require all of the advantages of bare metal? This is what the Chameleon KVM cloud at TACC is for. It is often overshadowed by our bare metal sites – but this month it is in the spotlight!</p>

<p>Why do we have a KVM cloud as a companion to our bare metal offering? Virtualized clouds are more cost-effective because users can deploy multiple VMs on one node instead of allocating a whole bare metal node. This is important given that hardware manufacturers are now putting more cores than ever in one system: our new <a href="https://www.chameleoncloud.org/blog/2022/02/01/chameleon-changelog-for-january-2022/">AMD nodes at TACC</a> go up to 128 cores per node. At the same time, virtualized clouds do not provide the performance isolation that a bare metal cloud offers, which makes them unsuitable for many experiments – but when they can be used they are cheaper. Specifically, for bare metal use you are charged one SU for node hour, but VMs do not use any of your SU allocation. They instead have a <a href="https://chameleoncloud.org/learn/frequently-asked-questions/#toc-what-is-the-allocation-model-for-kvm-virtual-machines-">unique resource quota model</a>.</p>

<p>In addition, users can make <a href="https://chameleoncloud.org/learn/frequently-asked-questions/?edit_off=true#toc-what-is-the-allocation-model-for-kvm-virtual-machines-:~:text=KVM%20resources%C2%A0do%20not%C2%A0require%20a%20lease%2C%20and%20will%20remain%20active%20as%20long%20as%20your%20allocation%20is%20active.">open-ended deployments on the KVM partition</a>, while bare metal leases are limited to 7 days at most. This is why our KVM cloud is popular with educational projects, projects with long-running applications, as well as projects that explore scale. Plus, using KVM is easier than ever with the <a href="https://python-chi.readthedocs.io/en/latest/">python-chi interface</a>. We’ve also created an example Jupyter notebook that will help you to get started. Read on to see how using our KVM cloud is different from the bare metal offering, and how to use it to better support your experiments. </p>

<h2>Why should I use KVM?</h2>

<h3>Similarity to bare metal nodes</h3>

<p>If your experiment <strong>doesn’t</strong> require the use of a specific type of hardware, the delicate accuracy of precise hardware measurements, or power management, then KVM may be a good choice for you. KVM instances “feel” just like bare metal. They boot the same images, so you can run the same operating systems, install the same software, and run the same code on them. You can also, of course, connect to your KVM instance via SSH or the serial console in the web browser. </p>

<h3>Performance</h3>

<p>You may have heard that virtual machines are slow because of the overhead of emulating virtual hardware. While it is true that virtual machines will lag behind in terms of disk and network I/O, KVM is actually very comparable to bare metal in terms of CPU performance! For most applications, it is similar in performance to bare metal, and it is actually significantly faster to boot up a virtual machine than a bare metal instance,  a big plus especially if you are experimenting with scale or your experiment requires frequent reboots.</p>

<p>With KVM, we offer 7 different configurations, or “flavors,” which subdivide the node resources among different VMs in different ways and thus represent different "slices" of resource. This allows you to configure the exact type of virtual machine that you need for your experiment.</p>

<table align="center" border="1" cellpadding="1" cellspacing="1" style="width: 500px;">
	<caption> </caption>
	<thead>
		<tr>
			<th scope="col">Name</th>
			<th scope="col">VCPUs</th>
			<th scope="col">Memory</th>
			<th scope="col">Total Disk</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center;">m1.tiny</td>
			<td style="text-align: center;">1</td>
			<td style="text-align: center;">512 MB</td>
			<td style="text-align: center;">1 GB</td>
		</tr>
		<tr>
			<td style="text-align: center;">m1.small</td>
			<td style="text-align: center;">1</td>
			<td style="text-align: center;">2 GB</td>
			<td style="text-align: center;">20 GB</td>
		</tr>
		<tr>
			<td style="text-align: center;">m1.medium</td>
			<td style="text-align: center;">2</td>
			<td style="text-align: center;">4 GB</td>
			<td style="text-align: center;">40 GB</td>
		</tr>
		<tr>
			<td style="text-align: center;">m1.large</td>
			<td style="text-align: center;">4</td>
			<td style="text-align: center;">8 GB</td>
			<td style="text-align: center;">40 GB</td>
		</tr>
		<tr>
			<td style="text-align: center;">m1.xlarge</td>
			<td style="text-align: center;">8</td>
			<td style="text-align: center;">16 GB</td>
			<td style="text-align: center;">40 GB</td>
		</tr>
		<tr>
			<td style="text-align: center;">m1.xxlarge</td>
			<td style="text-align: center;">16</td>
			<td style="text-align: center;">32 GB</td>
			<td style="text-align: center;">40 GB</td>
		</tr>
		<tr>
			<td style="text-align: center;">m1.xxxlarge</td>
			<td style="text-align: center;">16</td>
			<td style="text-align: center;">64 GB</td>
			<td style="text-align: center;">40 GB</td>
		</tr>
	</tbody>
</table>

<p> </p>

<h3>Storage volumes</h3>

<p>KVM also has a storage volume feature, powered by <a href="https://docs.openstack.org/cinder/latest/">OpenStack Cinder</a>. This allows you to store large collections of data in a highly available, fault tolerant remote block storage. You can then mount these volumes on different VMs, allowing you to store all of your experiment data in one place, and use it on any VM. If you happen to need this remote storage capability on bare metal, then you may be interested in our new <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/shares.html">filesystem preview</a>!</p>

<h3>Security groups</h3>

<p>Another unique feature of KVM is Security Groups. You may have seen these on the bare metal sites before, but we disabled their behavior on those sites in favor of <a href="https://www.google.com/search?q=ufw+firewall">ufw</a>. On KVM, these groups are a convenient way to set network ingress/egress rules for all of your KVM instances. You can configure them before they are provisioned, or after they’ve already booted up. One important quirk to understand with these is that KVM instances do not allow SSH by default! The default security group blocks all incoming connections. To allow SSH to your instance, you’ll need to add the “Allow SSH” security group. There are other security groups to allow other types of traffic, or you can create your own. However, in almost all cases, you will not need any groups besides “Allow SSH.” We recommend using an SSH tunnel for any web-facing services, and reviewing our <a href="https://www.chameleoncloud.org/blog/2021/06/28/best-practices-making-your-experiments-secure/">security best practices blog</a> before making any changes to your security groups.</p>

<h3>Convenience</h3>

<p>In the spirit of a mainstream on-demand cloud, you can spin up a VM and just leave it running forever! As long as your allocation hasn’t expired, your VM will remain running. This is extremely useful for experiments that take a long time to run, or even experiments that require lots of re-visiting over a long period of time. This is why Chameleon operators regularly use KVM instances for our testing environments: they are always available whenever we need to test new features.</p>

<p>One highly advantageous use of KVM is to run a component of your experiment that must remain highly available for a long period of time, such as an API server, and have it receive requests from high performance compute nodes running in a bare metal site. This way, you can offload the most demanding parts of your experiment to bare metal, and leave book-keeping and data storage to a lower-performance VM. The benefit here is twofold: you save SUs in your allocation, and leave more bare metal hardware available for your fellow researchers. Who doesn’t love that?</p>

<h2>KVM Experiment Pattern Notebook</h2>

<p>And, we saved the best for last… We recently updated our python-chi interface to be compatible with KVM, so orchestrating your experiments with python code is now easier than ever. And to make it super easy, we also developed a <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/jupyter.html">Jupyter notebook</a> that represents an “experiment pattern” of a KVM experiment. First, it guides the user through resource discovery, resource provisioning and configuration, and all the experiment preparation stages and explains in detail how to use the python-chi interface for KVM to implement them. Second, it implements a simple “demo” experiment which is an exploration of Linux <a href="https://en.wikipedia.org/wiki/Cgroups">cgroups</a>. Each experiment consists of roughly two types of actions – experiment preparation and experiment content – so while your experiment will likely be doing something different, you may find that you could reuse the experiment preparation almost verbatim. In other words, feel free to copy and extend the notebook and use it to kickstart your own experiments. The <a href="https://chameleoncloud.org/experiment/share/1cc7be9e-045a-4390-a752-127d9c2fc9fa">experiment pattern notebook</a> is available on Trovi to get you started! If you prefer a tutorial on using the KVM@TACC GUI, check out <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm.html">our documentation</a>.</p>

<h3>Share with us!</h3>

<p>If you conduct some interesting research on KVM (or anywhere on Chameleon ;)) and would like to share with fellow researchers and the Chameleon team, consider uploading it to <a href="https://chameleoncloud.org/experiment/share/">Trovi</a>, our research sharing and reproducibility platform! For more information on how to share your research on Trovi, check out our <a href="https://chameleoncloud.org/blog/2022/06/01/sharing-experiments-with-trovi/">May 2022 tips and tricks blog</a> on the subject.</p>