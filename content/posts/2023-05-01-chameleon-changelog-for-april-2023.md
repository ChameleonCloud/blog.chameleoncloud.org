---
abstract: "<p>As we prepare for the 2023 Chameleon User Meeting, we finish off April\
  \ with a new Trovi artifact, simple tools to build chameleon images, Xilinx improvements,\
  \ and blazar client fixes. Don\u2019t forget about the outage at CHI@UC May 7-12.</p>"
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2023-05-01 21:41:07+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/16/4a/164ae5f5-c010-4de1-ba05-35ae3ec6faa4/april.jpg
slug: chameleon-changelog-for-april-2023
subtitle: ''
title: Chameleon Changelog for April 2023
---

<p style="text-align: center;"><img src="https://chameleoncloud.org/media/filer_public/16/4a/164ae5f5-c010-4de1-ba05-35ae3ec6faa4/april.jpg" style="width: 600px;"></p>

<p> </p>

<p>Dear Chameleon users,</p>

<p>We are about to kick off the <a href="https://chameleoncloud.org/chameleon-cloud-users-meeting/user-meeting-2023/">2023 Chameleon User Meeting</a> tomorrow. We hope to see many of you there! We have a very exciting program, with sessions on education, CHI@Edge, CHI-in-a-Box, and reproducibility.</p>

<p><strong>Major CHI@UC outage!</strong> We have a bit of unfortunate news to mention before we dive into the fun new Chameleon features. Due to an extensive power and cooling upgrade in the datacenter hosting it, <a href="https://chameleoncloud.org/user/outages/datacenter-maintenance-affecting-chiuc-may-7-12/">CHI@UC will be down next week</a>, May 7-12. We recommend <a href="https://chameleoncloud.org/blog/2023/05/01/how-to-port-your-experiments-between-chameleon-sites/">migrating your experiment to another Chameleon site</a> in the meantime. We apologize for this inconvenience. </p>

<p><strong>Openstack Networking SDK artifact</strong>. If you have used Chameleon's Jupyter environment, you are probably familiar with python-chi. This library makes it easy to programmatically orchestrate testbed resources. Behind the scenes, it uses <a href="https://docs.openstack.org/openstacksdk/latest/user/index.html">OpenStack’s SDK</a> to interact with the various services at each site. This SDK is powerful, but complicated to use, with many ways to accomplish similar tasks, so python-chi was created to streamline common use cases for the testbed. However, more advanced features, or ones not yet supported in python-chi, can still be done by using the SDK directly. <a href="https://chameleoncloud.org/experiment/share/626a865a-d74f-4351-81bf-67363c3bc04f">This new artifact</a> demonstrates creating a server with two network interfaces, each connected to a separate L2 network. This allows for isolation between your control traffic (SSH and API access), and experiment traffic. In particular, automatic IP addressing is disabled on the second network, allowing for customized uses (such as running your own DHCP server)</p>

<p><strong>Image Builder Tool.</strong> <a href="https://chameleoncloud.org/blog/2023/03/01/chameleon-changelog-for-february-2023/">A few months ago</a> we announced that we finally had updated appliances, which are the base OS images used when launching instances. This month, we are releasing <a href="https://github.com/ChameleonCloud/CC-Images/">updated tooling for building Chameleon images</a>. Our goal was to streamline the process of building and extending images, which will make them easier to maintain and keep updated. If you are interested in building custom Chameleon images, you can <a href="https://github.com/ChameleonCloud/CC-Images#extending">browse the README</a> for more on extending our images. Or for advanced usage, you may find <a href="https://docs.openstack.org/diskimage-builder/latest/developer/developing_elements.html">Openstack’s documentation</a> helpful, as our tool uses their software under the hood.</p>

<p><strong>Xilinx JTAG and Debugging. </strong>The FPGA (Xilinx U280) nodes at UC now have a USB cable attached to JTAG the cards. It is now possible to reflash the FPGA with bitstreams that modify the PCIe interface, other low level modifications, or just to aid in troubleshooting. In particular, this provides a path forward to support P4 on these cards, such as with <a href="https://github.com/esnet/esnet-smartnic-hw">ESnet’s SmartNIC project</a>.</p>

<p><strong>CHI-in-a-Box Operator Client Improvements.</strong> This month, we fixed a few things with our version of the blazar client, which will be mostly noticed by CHI-in-a-Box associate site operators. We fixed unsetting properties on networks and hosts, fixed capability resources , and corrected the sorting when listing networks.</p>

<p>We are so excited to meet many of our users tomorrow! <br>
 </p>