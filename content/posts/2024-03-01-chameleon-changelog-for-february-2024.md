---
abstract: "<p>This month, we have a packed changelog, we have a lot of exciting updates\
  \ with FABRIC connectivity, and we\u2019ve added a second interface to nodes on\
  \ CHI@UC that did not have one. Additionally, for Edge users, we have improvements\
  \ to interacting with containers and using Jetson Nano GPUs. Lastly, there are\_\
  updates\_to our lease stacking policies.</p>"
authors: []
categories:
- Chameleon Changelog
date: '2024-03-01 23:03:01+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/6e/7c/6e7c8bd2-aa53-4bfb-a8bb-b7faf52a635f/feb_2024_changelog.png
related_posts: []
slug: chameleon-changelog-for-february-2024
subtitle: ''
title: Chameleon Changelog for February 2024
---

<p style="text-align: center;"><img media="" src="https://chameleoncloud.org/media/filer_public/6e/7c/6e7c8bd2-aa53-4bfb-a8bb-b7faf52a635f/feb_2024_changelog."></p>

<p>Dear Chameleon Users,</p>

<p>This month, we have a packed changelog. If you like networking, we have a lot of exciting updates with FABRIC connectivity, and we’ve added a second interface to nodes on CHI@UC that did not have one. Additionally, for Edge users, we have improvements to interacting with containers and using Jetson Nano GPUs. Additionally, we’ve updated our lease stacking policies, so be sure to read on!</p>

<p><b>FABRIC Layer 3 connection</b>. <a href="https://whatisfabric.net/">FABRIC</a> is another NSF-funded testbed, with a focus on networking capabilities. Chameleon supports <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/networks/networks_stitching.html">Layer 2 stitching</a> to FABRIC, allowing you to create an experiment that uses resources on both testbeds. This month, we have set up a network VLAN at both CHI@UC and CHI@TACC that routes to the FABRIC internal network. Firstly, this means that you can route to FABRIC resources without having to set up custom Layer 2 stitching for common cases. Secondly, even if you are not a FABRIC user, you can take advantage of this network to route traffic between CHI@UC and CHI@TACC. Compared to routing via public IPs, using the FABRIC network between sites will have lower latency and higher bandwidth (up to 25Gb/s per flow), all without needing to set up FABRIC resources and reserve a Chameleon stitched network. If you are interested in using this network, please <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/networks/networks_fabnet.html">see our documentation</a>. Right now, this network is publicly available at CHI@TACC, but by request at CHI@UC. If you are interested in using it at CHI@UC, please contact the help desk indicating that you would like access to fabnet.</p>

<p><b>Chameleon at FABRIC Knit8 workshop. </b>In more news for networking buffs, this month there is a FABRIC Workshop from <a href="https://learn.fabric-testbed.net/knowledge-base/knit-8-a-fabric-community-workshop/">March 19-21</a>. If you plan on attending, be sure to check out the <a href="https://learn.fabric-testbed.net/knowledge-base/knit-8-a-fabric-community-workshop/#agenda">Chameleon + FABRIC Stitching Tutorial</a>. We’ll show you how to use both the Layer 2 and Layer 3 connection. Later in the day, there will also be a Chameleon + FABRIC hackathon which will be a great opportunity to package your networking experiment for practical reproducibility.</p>

<p><b>CHI@Edge updates.</b> This month, we’ve been working on improving our edge computing testbed, known as CHI@Edge. At this site, you can reserve devices like Raspberry Pis and Jetson Nanos and launch container workflows, all through our programmatic interface <a href="https://python-chi.readthedocs.io/en/latest/modules/container.html#chi.container.download">python-chi</a>. This month, we fixed some of the functionality regarding the container execute, download, and upload methods which allow you to execute commands, download files, and upload files inside of your container respectively. Additionally, we made it easier to use the Nvidia GPU on a Jetson Nano within your container. Previously, you had to set several environment variables when creating your container in order for this to work. Now, if you set runtime=”nvidia” in your call to container.create(), the GPU libraries will automatically be loaded. If you want to get started with CHI@Edge, <a href="https://chameleoncloud.gitbook.io/chi-edge/getting-started">see our documentation</a>.</p>

<p><b>New CHI@UC network interfaces. </b>Earlier this month, we were able to add new network interfaces to all of our phase 2 nodes at CHI@UC. This means you’ll be able to use separate interfaces in your experiment, such as one for experiment traffic and one for control. Additionally, you can also use this extra interface to get twice the bandwidth for these nodes. This now means all nodes at CHI@UC have 2 interfaces.</p>

<p><b>CHI@UC floating IP addresses</b>. The way most people connect to their Chameleon instances is via a floating IP. However, due to high usage, some of our users have been experiencing an error when trying to allocate one to their project at CHI@UC. This is because we have no free ad-hoc IPs left. If you have this error, you can still get a floating IP via our pool of <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/reservations.html">reservable addresses</a> by making a lease for one. You may also want to consider setting up a <a href="https://www.chameleoncloud.org/blog/2019/02/27/save-planet-use-fewer-ips/">bastion host</a>, which lets you connect to several nodes, while only needing one floating IP.</p>

<p><b>Policies update</b>. In order to promote fair usage of Chameleon’s resources, we monitor usage to ensure that no one project is unreasonably hoarding resources by “stacking” leases. While this behavior is rare, we want to ensure that everybody can get a chance to use our hardware, which in particular affects our highly demanded GPU nodes. This month, we made information about this <a href="https://www.chameleoncloud.org/learn/frequently-asked-questions/#toc-what-are-the-policies-on-chameleon-resource-usage-">policy more specific here</a>. If we find that your project is not adhering to this policy, we’ll discuss it with the PI first, but repeated offenses may result in lease termination. </p>

<p>Happy experimenting!</p>