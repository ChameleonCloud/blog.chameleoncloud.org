---
abstract: "<p>Did you ever wonder what makes your favorite testbed \u201Cgo\u201D\
  ? The answer is \_CHameleon Infrastructure, or CHI for short \u2013 packaged as\
  \ CHI-in-a-Box so that anybody can run their own testbed. We blogged about it a\
  \ year or so ago, and a lot can change in a year, so this blog brings you some important\
  \ updates. Not least, there is now a paper on CHI-in-a-Box so you can join the testbed\
  \ as an Associate Site!</p>"
authors:
- Michael Sherman
categories:
- Tips and Tricks
date: '2022-06-28 01:21:47+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/47/c6/47c61298-faf0-4ec8-9287-11e569f0e0c3/chameleon_box.png
related_posts:
- slug: chincar-an-interview-with-the-newest-associate-site
  title: 'CHI@NCAR: An Interview with the Newest Associate Site'
- slug: turn-your-hardware-chameleon-associate-site-chi-box
  title: Turn Your Hardware into a Chameleon Associate Site with CHI-in-a-Box
- slug: setting-associate-site-interview-northwestern-university
  title: 'Setting Up an Associate Site: An Interview With Northwestern University'
slug: chi-in-a-box-update
subtitle: ''
title: CHI-in-a-Box Update
---

<p style="text-align: center;"><b id="docs-internal-guid-210c9fba-7fff-ed62-8f3e-64a4aa0d28c6"><img src="https://chameleoncloud.org/media/filer_public/0d/f1/0df1ae73-c987-4768-97bd-6b552842a0ad/cham_p3_front.png" style="width: 177px; height: 393px;"><img src="https://chameleoncloud.org/media/filer_public/21/cf/21cf0366-6ffd-4162-a736-f27cdebfa761/cham_p3_single.png" style="width: 177px; height: 393px;"><img src="https://chameleoncloud.org/media/filer_public/4d/07/4d073a94-b5b1-41bf-82ca-21098d19d8a0/cham_p3_rear.png" style="width: 177px; height: 393px;"></b></p>

<p style="text-align: center;">P3 nodes at University of Chicago</p>

<p>The Chameleon Testbed is composed of a set of services and systems, together referred to as CHameleon Infrastructure, or CHI for short. Much of it is based on the open source cloud platform called <a href="https://www.openstack.org/">OpenStack</a> – but roughly half of it is customizations to support the research use case and shared services, such as the user portal, hardware discovery page, or JupyterHub integration. CHI-in-a-Box is a packaging of the Chameleon Infrastructure, to allow others to configure a testbed on their own hardware, either independently, or as Chameleon Associate Site, that leverage shared services, common user base, and user support provided by the Chameleon team. You can find out more from the <a href="https://www.chameleoncloud.org/blog/2021/04/19/turn-your-hardware-chameleon-associate-site-chi-box/">blog</a> we wrote more than a year ago so we though it was time for an update – though if you are in the mood for a deeper dive, check out our recent paper: <a href="https://chameleoncloud.org/media/filer_public/69/2a/692a6558-eeba-4a7f-a729-33e22eefccc8/ciab-pearc22-23-final.pdf">CHI-in-a-Box: Reducing Operational Costs of Research Testbeds</a>, – we will be presenting it at the <a href="https://pearc.acm.org/pearc22/">PEARC conference</a> in a few weeks, so if you plan to be there, <a href="https://web.cvent.com/event/7b4eff30-d151-4cf4-91f0-b68c4a6c88c9/websitePage:645d57e4-75eb-4769-b2c0-f201a0bfc6ce">come say hello and ask questions</a>: 11AM on July 12th! And if you want to give it a whirl, go straight for <a href="https://github.com/ChameleonCloud/chi-in-a-box">the code and documentation at our github page</a>.</p>

<p>A growing number of sites have joined Chameleon as Associate Sites. <a href="https://www.chameleoncloud.org/blog/2021/02/19/setting-associate-site-interview-northwestern-university/">Northwestern</a> contributed 5 Haswell and 2 Skylake nodes with 100G networking, excellent for network experiments.  <a href="https://www.chameleoncloud.org/blog/2022/02/28/chincar-an-interview-with-the-newest-associate-site/">The National Center for Atmospheric Research</a> (NCAR), added 5 ARM ThunderX2 nodes, of interest to folks working on architecture research, and especially high core-counts and low power systems, and <a href="https://www.chameleoncloud.org/blog/2022/03/02/chameleon-changelog-for-february-2022/">EVL at University of Illinois in Chicago (UIC) has also stood up a site</a>. We are actively working with more potential sites so if you are interested in more hardware or more geographical distribution, watch this space! And now for what’s new in CHI-in-a-Box.</p>

<p><strong>New Features. </strong>We took requirements and suggestions from each Associate Site above, and made CHI-in-a-box more flexible and powerful. Among others, we added support for flat networks with bare metal (i.e, without management access to a switch, as this is sometimes a difficult ask). To support the ARM nodes at NCAR, we added new ARM64 disk images, as well as support for the UEFI boot mode, the machines not supporting BIOS boot. This support allowed us to quickly add hardware to UC as well, as the new SSD nodes require UEFI to boot from NVME SSDs. As a side-benefit, nodes boot faster with UEFI! For reliability, we’ve added automatic database backups, including uploading them to S3 compatible storage (such as the Chameleon Object Store at UC or TACC).</p>

<p><strong>New Operational Tools. </strong>New since last year is also support for usage monitoring which gives site operators an idea of how well their resources are being utilized – as well as usage enforcement that keeps users from overspending their allocation.</p>

<p><strong>Bring Your Own Device (BYOD). </strong>Bring Your Own Device (BYOD). Chameleon Infrastructure now has a new service called Doni for managing hardware enrollment and availability. Its primary function is to manage adding and removing resources dynamically, a feature important for some sites as well as our <a href="https://chameleoncloud.org/experiment/chiedge/">CHI@Edge testbed</a>, but it also makes managing inventory easier for operators. Read more about it in our <a href="https://chameleoncloud.org/media/filer_public/69/2a/692a6558-eeba-4a7f-a729-33e22eefccc8/ciab-pearc22-23-final.pdf">PEARC paper</a>.</p>

<p><strong>Taking a Train to Xena. </strong>CHI-in-a-Box is also now caught up with OpenStack’s Xena release, which brings a slew of bug fixes and tools for operator quality of life. In particular, it brings <a href="https://docs.openstack.org/ironic/xena/admin/hardware-burn-in.html">burn-in testing of new hardware</a>, faster image downloads using HTTP instead of ISCSI, <a href="https://docs.openstack.org/kolla-ansible/xena/reference/storage/external-ceph-guide.html#radosgw">built-in support for Object Stores via Ceph RGW</a>, container health checks for each container, and last but not least, faster deployment and more helpful error messages.</p>

<p><strong>Simpler way to try out CHI-in-a-Box. </strong>Finally, thanks to our current CHI in a Box users, who have given us tremendously helpful feedback, we were able to make the deployment process more streamlined and better documented. In particular, with the help of practical defaults everywhere, you can now deploy a very minimal demo site with only 3 lines of configuration! You can test that the API works, and what the UI and tools look like, before putting effort into a “production ready” site.</p>

<div style="background: #ffffff; overflow: auto; width: auto; border: solid gray; border-width: .1em .1em .1em .8em; padding: .2em .6em;">
<pre style="margin: 0; line-height: 125%;">kolla_base_distro: ubuntu
network_interface: eth0
kolla_internal_vip_address: 10.10.10.254
</pre>
</div>

<p>To enable more features, simply add lines from the new annotated examples, and rerun the deploy in a few minutes.</p>