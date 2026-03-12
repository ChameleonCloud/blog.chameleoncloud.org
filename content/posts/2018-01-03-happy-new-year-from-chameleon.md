---
abstract: "<p>The\_New Year Chameleon is back -- along with a few new features to\
  \ help you run your experiments in the New Year!\_</p>"
authors:
- Kate Keahey
categories:
- Announcements
date: '2018-01-03 17:44:57+00:00'
featured: false
hide_image: true
image: ''
related_posts: []
slug: happy-new-year-from-chameleon
subtitle: ''
title: Happy New Year from Chameleon!
---

<p>Dear Chameleon users,</p>

<p>Happy New Year!</p>

<p>May the New Year bring you health, happiness, and lots of groundbreaking research ideas as well as ever better ability to work on them!</p>

<p>Here are our initial contributions towards this last goal:</p>

<p><strong>Network stitching.</strong> Chameleon now supports stitching isolated layer 2 networks to ExoGENI VLANs or other networks connected to the Internet2 Advanced Layer 2 Service (AL2S). This feature enables direct layer 2 communication of Chameleon bare-metal nodes with ExoGENI virtual machines or other servers at various institutions connected to Internet2, unlocking the potential to perform powerful new networking experiments. For now, this feature is available on the University of Chicago site only but will be available throughout the system shortly. Please, see<a href="https://www.chameleoncloud.org/docs/bare-metal-user-guide/stitching-chameleon-isolated-networks/"> <u>our documentation</u></a> for more details.</p>

<p><strong>Network isolation.</strong> Those of you who have been using our dynamic VLANs feature will notice that they are now simpler to configure: no static route is required and the subnet IP address range doesn't have to be unique. We also now support isolation for storage nodes, in addition to compute nodes. This feature is available on the University of Chicago site only but will be available throughout the system shortly. Again, see<a href="https://www.chameleoncloud.org/docs/bare-metal-user-guide/network-isolation-bare-metal/"> <u>our documentation</u></a> to learn more. Note that the shared Neutron network has been recreated, resulting in a change of UUID: you may need to adapt some command-line scripts if they refer directly to it.</p>

<p><strong>Serial console access.</strong> While it has long been possible to request serial console access to bare-metal nodes via our help desk and have it configured manually by one of our administrators, it is now available for every node and without having to go through the help desk. Once your instance is deployed, simply click on the Console button in the instance contextual menu. For ease of use, our latest mages are configured to auto-login into the default Chameleon user account. Take a look at our <a href="https://www.chameleoncloud.org/configure-and-interact/#connect-to-the-serial-console"><u>serial console documentation</u></a> to learn more.</p>

<p><strong>Monitoring. </strong>We upgraded our monitoring tools to a more scalable solution. Thus, the Ceilometer API has been replaced by the Gnocchi API, which means that you need to use the<a href="https://docs.openstack.org/python-openstackclient/latest/"> <u>OpenStack client</u></a> with the<a href="http://gnocchi.xyz/client.html"> <u>Gnocchi</u></a> client plugin to access metrics. Collection of instance metrics is now performed by<a href="https://collectd.org"> <u>collectd</u></a> rather than a custom Ceilometer agent. This change gives you access to the<a href="https://collectd.org/wiki/index.php/Table_of_Plugins"> <u>large plugins collection</u></a> for collectd. While only a few are enabled by default in our images, you can easily activate additional plugins by modifying the collectd configuration. Please, refer to our<a href="https://www.chameleoncloud.org/monitor-and-collect/"> <u>documentation</u></a> for more details. Note that while our Ubuntu 16.04 appliance includes this new functionality, our Ubuntu 14.04 appliance won't be updated as it doesn't include the required dependencies.</p>

<p><strong>Usability improvements. </strong>We made several improvements that make using Chameleon easier and more intuitive. Leases can now be created to start immediately by passing the string “now” as a start date, either with the command-line (<a href="https://github.com/openstack/python-blazarclient/"><u>python-blazarclient</u></a>) or with the Blazar REST API. Further, the web interface now allows you to pass custom <a href="https://www.chameleoncloud.org/configure-and-interact/#scheduler-hints"><u>scheduler filters</u></a> to an instance launch request; this means that you can schedule an instance on a specific physical node without having to use the command line interface. The management of floating IPs through the web interface has moved from the Compute panel to the Network panel where it is easier to find, and the public network providing floating IPs has been renamed from “ext-net” to “public”.<strong> </strong>Many thanks to our users who signaled to us the need for those changes!</p>

<p><strong>Appliances update. </strong>We have updated all appliances supported by the Chameleon staff to reflect three important changes: the changes to monitoring console and auto-login for serial console discussed above, as well as an upgrade for cc-snapshot, our snapshoting tool. If you are using images that were snapshotted based on earlier versions of Chameleon appliances they of course will not include those changes; if they are relevant to your work we will be happy to assist you with appliance upgrades.</p>

<p>Many of the new features above were made possible as a result of upgrade of CHI to the<a href="https://www.openstack.org/software/ocata/"> <u>Ocata version of OpenStack</u></a>. This, as well as preparation for future enhancements necessitated some configuration changes. Specifically, region names have been changed from “regionOne” to “CHI@UC” and “CHI@TACC” in preparation for a future multi-region deployment that will simplify interacting with the testbed. If you use OpenStack command line tools to interact with Chameleon, you will need to update your OpenStack RC file or download them again from the Compute &gt; API Access panel.</p>

<p>Once again, all the best in the New Year -- we are looking forward to working with you!</p>

<p>The Chameleon Team</p>