---
abstract: "<p>Great news in Chameleon-land!</p>\n\n<p>We\u2019ve had an outstanding\
  \ June with many hard won features coming to successful completion and thus have\
  \ a few fireworks to brighten your Holiday! Our new features make possible new groundbreaking\
  \ networking experiments, make the testbed easier to use for distributed experiments,\
  \ provide new ways of measuring power consumption, and bring you new hardware to\
  \ experiment with. Read on to learn about the details!</p>"
authors:
- Kate Keahey
categories:
- Chameleon Changelog
date: '2018-07-02 20:19:42+00:00'
featured: false
hide_image: true
image: ''
slug: chameleon-changelog-june-2018
subtitle: ''
title: Chameleon Changelog for June 2018
---

<p>Great news in Chameleon-land!</p>

<p>We’ve had an outstanding June with many hard won features coming to successful completion and thus have a few fireworks to brighten your Holiday! We made the following news in the past month:</p>

<p><strong><a href="https://chameleoncloud.readthedocs.io/en/latest/technical/networks/networks_sdn.html#software-defined-networking">Bring Your Own Controller (BYOC) functionality. </a></strong>This new feature allows you to create isolated network switches managed using an OpenFlow controller that you provide; use it to  experiment with SDN or for experiments with non-standard networking requirements. To make such experiments easier BYOC comes with an <a href="https://www.chameleoncloud.org/appliances/56/">OpenFlow Quick Start Appliance</a> designed to provide a simple hands-on experience with this new capability as well as a base template for designing your own SDN experiments. It deploys a complete BYOC SDN experiment including an example Ryu OpenFlow controller compatible with the Chameleon switches, a Chameleon OpenFlow network connected to the Ryu controller, and a set of nodes that will use the use the network. The BYOC functionality is currently supported at the University of Chicago site only; we are working on making it available at TACC soon.</p>

<p><strong><a href="https://chameleoncloud.readthedocs.io/en/latest/technical/gui.html#project-and-region-menu">Multi-region configuration.</a> </strong>As you know, up until a short while ago, CHI@TACC and CHI@UC were completely separate sites, each with its own web interface. If you wanted to use both sites at the same time, you had to log in to each site separately; this was inconvenient for users who frequently used both sites or worked on multi-site experiments. This month we reconfigured the testbed so that you authenticate to the testbed once and can then use both sites; in other words, each site is now a "region" of the same cloud. If you use the web interface, you can now log into one site, and switch to the other site <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/gui.html#project-and-region-menu">with one click</a>. If you are creating and managing leases from the command-line, you will need to <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/reservations.html#blazar-client-installation">install a new version of python-blazarclient </a>that allows you to select the correct site.</p>

<p><strong><a href="http://chameleoncloud.readthedocs.io/en/latest/technical/metrics.html#power-consumption-metrics-for-low-power-nodes">Power consumption metrics for low power nodes.</a></strong> We implemented a feature that automatically collects power usage data on all low power nodes in the system via the IPMI interface on the chassis controller for the nodes. This approach does not consume additional power on the node itself and runs even when the node is powered off. Low power nodes for which power usage data are now being collected include all Intel Atoms, low power Xeons, and ARM64s. To learn more, read <a href="http://chameleoncloud.readthedocs.io/en/latest/technical/metrics.html">the monitoring section of our documentation</a> -- though you may also like to take a look at <a href="https://www.chameleoncloud.org/blog/2018/06/22/monitoring-power-consumption-low-power-nodes/">the example we published on our blog</a>.</p>

<p><strong>More new hardware.</strong> We have released another rack of 32-node racks of Skylake nodes at the University of Chicago site. This is a twin of <a href="https://www.chameleoncloud.org/blog/2018/03/14/new-chameleon-hardware-available/">the Skylake rack we released at University of Chicago a few months ago</a> (though with a more recent BIOS version): each node is a PowerEdge R740 server with two Intel Xeon Skylake CPUs running at 2.60 GHz (each with 12 cores / 24 threads), 192 GiB of RAM, a Samsung SSD with 240 GB of storage, and 10 Gigabit Ethernet connectivity -- and with a  DP2400 Corsa switch. We thus now have two racks at University of Chicago that support the BYOC functionality (see above).</p>

<p><strong>Appliances.</strong> In addition to the new appliances supporting network experiments described above we also updated <a href="https://www.chameleoncloud.org/appliances/32/">the CC-CentOS7-FPGA appliance</a>  with the latest version of Chameleon tools, including cc-snapshot and cloudfuse.</p>

<p>Last, but not least, June marked our first publication of a great contribution by one of our users: <a href="https://www.chameleoncloud.org/blog/2018/06/11/enos-framework-experimenting-openstack/">the ENOS framework</a> making experimentation with OpenStack easier. If you are experimenting with OpenStack, it is worth looking up -- we know that quite a few of Chameleon users are already taking advantage of this excellent tool!</p>

<p>As a reminder, the legacy links to our old documentation have been taken offline at the end of June following our documentation update in March; if you find that you are unable to access any specific content, please let us know.</p>

<p>Enjoy the new features and have a happy 4th!</p>

<p> </p>
