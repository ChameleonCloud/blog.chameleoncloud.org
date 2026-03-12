---
abstract: "<p>This month, we bring a lot of updates to our CC-images. And we also\
  \ remind users about our user survey and upcoming maintenance at CHI@UC.<br>\n\_\
  </p>"
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2024-02-01 23:00:44+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/38/fc/38fcfbb3-dd65-49b0-a005-2dcba0d2e24c/53469197171_aac42e5697_w.jpg
related_posts: []
slug: chameleon-changelog-for-january-2023
subtitle: ''
title: Chameleon Changelog for January 2024
---

<p style="text-align: center;"><img media="" src="https://chameleoncloud.org/media/filer_public/38/fc/38fcfbb3-dd65-49b0-a005-2dcba0d2e24c/53469197171_aac42e5697_w.jpg"></p>

<p style="text-align: center;"><small><em><a href="https://www.flickr.com/photos/rod_waddington/53469197171/in/photolist-2psTBtR-2prp8mY-2p86ADF-2prZxLN">"Malagasy Giant Chameleon" by Rod Waddington, Flickr - CC BY-SA 2.0 DEED</a></em></small></p>

<p> </p>

<p>Dear Chameleon Users,</p>

<p>We are kicking off the first month of 2024 by focusing on improving Chameleon services, and we are looking for more things to improve too.</p>

<p><b>Give us your feedback! </b>There are only a few days left to submit your response to the <a href="https://chameleoncloud.org/blog/2024/01/16/announcing-the-2024-chameleon-user-survey-send-us-your-feedback/">Chameleon User Survey</a>. This survey is your opportunity to voice your needs, experiences, and suggestions, directly impacting the development of new hardware features and capacity improvements on Chameleon, and the deadline is February 6. So far, the main feedback we’ve heard is that users are very interested in more GPUs. If there are other special hardware requests that would aid in your research, please tell us. We are also looking to redesign the interface to python-chi, and if you have any suggestions, please let us know via <a href="https://chameleoncloud.org/user/help/">the help desk</a>.</p>

<p><b>Improved CC Images.</b> As you know, we provide a <a href="https://chameleoncloud.org/blog/2023/06/26/chameleon-images-overview/">core set of supported images</a> for use on the testbed for use in your experiments, which come with testbed utilities like <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images.html#the-cc-snapshot-utility">cc-snapshot</a> or special libraries like CUDA. This month, we did a major overhaul to our Ubuntu images, and their variants. Notably, we removed many outdated, infrequently used dependencies, reducing their size significantly, mainly affecting the <a href="https://wiki.openstack.org/wiki/TripleO">uncommon usage of TripleO</a>. Additionally, the following changes have been made:</p>

<ul>
	<li>Fixed issues with Nvidia-SMI not showing GPUs on A100 nodes</li>
	<li>Resolved network connection failures on nodes with qlogic or broadcom 25g interfaces</li>
	<li>Increased reliability of NTP time synchronization at CHI@TACC, authentication for CC-Snapshot and CC-Cloudfuse, and loading additional SSH public-keys.</li>
	<li>Corrected cases where SSH daemon would fail to start, and where the serial console did not automatically log in.</li>
	<li>Fixed DNS and other network timeouts when running “docker build”</li>
</ul>

<ul>
	<li>Baremetal nodes now have a “cloud-init <a href="https://cloudinit.readthedocs.io/en/latest/reference/datasources/configdrive.html">ConfigDrive</a> '', and their network config is now set up via cloud-init, the same way as for instances on KVM. This should give a more reliable experience when configuring nodes with multiple network interfaces. Notably, on ubuntu images, this network configuration is now under /etc/netplan, rather than under `/etc/network/interfaces`</li>
	<li><i>firewalld </i>has replaced <i>ufw. </i>There were issues with <i>ufw</i> and docker iptables rules that required this change. </li>
</ul>

<p>If you are interested in technical details of what to expect on one of these images, you can <a href="https://github.com/ChameleonCloud/CC-Images/blob/main/ImageDefs.md">read this document with all of our customizations</a>. These updates are deployed at CHI@UC, CHI@TACC, and KVM@TACC, and we are working with associate sites to roll out these updates. As always, if you have any issues with these images, or anything unexpected is happening on your nodes, please contact <a href="https://chameleoncloud.org/user/help/">the help desk</a>.</p>

<p><b>CHI@Edge device enrollment improvements</b>. This month we rolled out some improvements to the Bring Your Own Device (BYOD) capability of CHI@Edge. This means that things should now be more reliable when enrolling devices. We are working hard on rounding out other much-needed CHI@Edge features and will share them next month, so stay tuned for more!</p>

<p><b>CHI@UC Outage. </b>Lastly, we’d like to remind you that on Tuesday February, 6 <a href="https://chameleoncloud.org/user/outages/chiuc-site-maintenance-feb-6th-2024/">CHI@UC is undergoing total site maintenance</a>. </p>

<p>Happy experimenting!</p>