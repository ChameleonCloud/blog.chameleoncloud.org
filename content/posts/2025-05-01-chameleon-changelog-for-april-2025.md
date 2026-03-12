---
abstract: "<p>This month, we have new OS images with AMD ROCm and Ubuntu 24 on ARM.\
  \ Additionally, we have improvements to mounting object store buckets using rclone,\
  \ a new message-of-the-day, and we\u2019ve fixed the firewall confusion on KVM@TACC.<br>\n\
  \_</p>"
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2025-05-01 21:59:32+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/ad/f6/adf620ad-a649-49cd-9c62-8f1698a20325/54482424167_a22739f815_w.jpg
related_posts: []
slug: chameleon-changelog-for-april-2025
subtitle: ''
title: Chameleon Changelog for April 2025
---

<p style="text-align: center;"><img media="" src="https://chameleoncloud.org/media/filer_public/ad/f6/adf620ad-a649-49cd-9c62-8f1698a20325/54482424167_a22739f815_w.jpg"></p>

<p>Dear Chameleon users,</p>

<p>This month, we have a lot of exciting updates to share about Chameleon OS images, also known as appliances, that we build as the base of your experiment.</p>

<p><b>New ROCm and ARM Images</b>! This month we’ve released a new <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images.html#chameleon-supported-images">Ubuntu appliance with AMD ROCm</a>, CC-Ubuntu24.04-ROCm. ROCm is the software equivalent of CUDA for AMD GPUs, and previously our users have reported difficulties with installing it into our base Ubuntu images. This new image is only for use with our nodes with AMD GPUs, which at the moment are the gpu_mi100 nodes at CHI@TACC., and we hope that this image makes it much easier to start experiments with these GPUs. Additionally, we added a new Ubuntu 24.04 image built for ARM architecture, which you can use on the compute_arm64 at CHI@TACC, or the arm_thunder nodes at CHI@NCAR.</p>

<p><b>General Image Improvements. </b>We’ve also published quality-of-life updates to all of our supported images. Previously, we included the cc-cloudfuse tool by default, which was custom software that we built in order to mount object store buckets as a file system. However, the performance and reliability of cc-cloudfuse often caused frustration. Now, we’ve switched from cc-cloudfuse to rclone as our supported way to <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/swift.html#mounting-object-store-as-a-file-system">mount object store buckets</a>. Additionally, we’ve updated the MOTD (message of the day) that is displayed upon login to an instance to provide important information. Now, you’ll see information about the firewall status of your instance, information about that instance’s lease, and a link with how to get help on Chameleon when you SSH into your instance. Lastly, on KVM@TACC, <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/networks/networks_basic.html#firewall">the firewall will be automatically disabled</a>. Since you already need to configure security groups for KVM instances to permit traffic to any ports, it was confusing to additionally have to open firewall ports from within the OS as well.</p>

<p><b>Image deprecation</b>. We updated the list of images to the dashboard so that you can now see image deprecation status better. Our schedule for this follows the end-of-life status for the base OS they are built on. For example, <a href="https://ubuntu.com/about/release-cycle">Ubuntu 20.04</a> will be end-of-life this month, May 2025, and so after this point we will stop supporting CC-Ubuntu20.04. For more information about what deprecation means on Chameleon, and how to securely use old images, <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images.html#chameleon-supported-images">see our documentation</a>.</p>

<p><b>GPU support status</b>. Lately, our GPU nodes have seen very high utilization. As a result, we’ve wanted to clarify the support that we can provide for this hardware. Due to their age, we are unable to support the K80 and M40 GPUs, which are only included on 4 nodes. All other GPUs are still supported, but P100 and V100 GPUs only are supported with their open source driver. The following list clarifies the status for each GPU model.</p>

<p>Supported (with either open source or proprietary driver):</p>

<ul>
	<li>Nvidia A100</li>
	<li>Nvidia A30</li>
	<li>Nvidia RTX 6000</li>
	<li>AMD MI100</li>
</ul>

<p>Support (requires open source driver):</p>

<ul>
	<li>Nvidia P100</li>
	<li>Nvidia V100</li>
</ul>

<p>Unsupported:</p>

<ul>
	<li>Nvidia K80</li>
	<li>Nvidia M40</li>
</ul>

<p>Happy experimenting!</p>