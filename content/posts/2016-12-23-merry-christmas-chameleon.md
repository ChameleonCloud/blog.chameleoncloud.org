---
abstract: <p>New power management tools and toys from Santa Chameleon -- we're trying
  to save all the lumps of coal we can for the stockings!</p>
authors:
- Kate Keahey
categories:
- Announcements
date: '2016-12-23 17:54:39+00:00'
featured: false
hide_image: true
image: ''
slug: merry-christmas-chameleon
subtitle: ''
title: Merry Christmas from Chameleon!
---

<p>Merry Christmas from Chameleon!</p>

<p><img alt="" src="https://www.chameleoncloud.org/media/uploads/2016/12/23/chameleon-solo-christmas-medium.png"></p>

<p>… and we couldn’t finish the year without putting a little something under the tree, this time on a power management theme. Down the chimney come the following:</p>

<p><strong>New low power hardware.</strong> We made available 16 new servers from the HPE Moonshot family: 8 low power Xeon servers (HP ProLiant m710p with one 4-core Intel Xeon E3-1284L v4 processor) and 8 Atom servers (HP ProLiant m300 with one 8-core Intel Avoton-based System on a Chip). This new low power hardware is particularly well suited for experiments on energy-efficient computing. The new nodes are available on CHI@TACC ; the Atom nodes are compatible with our supported CentOS 7 and Ubuntu images <s>however the Xeon nodes do not yet support CentOS (we are working on it with the manufacturer and hope to work this out soon)</s>. <strong>Update: Our Xeon nodes are now compatible with our CentOS 7 images as well</strong>. The nodes can be discovered via our <a href="https://www.chameleoncloud.org/user/discovery/"><u>resource discovery interface</u></a> and can be selected when <a href="https://chi.tacc.chameleoncloud.org/dashboard/project/leases/"><u>creating reservations</u></a>.</p>

<p><strong>Power management tools. </strong>To facilitate experiments with power management we are making available a <a href="https://github.com/coolr-hpc/intercoolr"><u>power measurement tool</u></a> as part of our base images. This tool leverages APIs from Intel processors to measure power consumption of each CPU socket and of memory DIMMs. We would like to thank Chameleon user <a href="http://www.mcs.anl.gov/person/kazutomo-yoshii"><u>Kazutomo Yoshii</u></a> of <a href="http://www.anl.gov"><u>Argonne National Laboratory</u></a> for developing and sharing this tool. To learn how to use it, read our documentation at <a href="https://www.chameleoncloud.org/monitor-and-collect"><u>https://www.chameleoncloud.org/monitor-and-collect</u></a>. This utility is compatible with all our hardware except for the Intel Atom nodes, but we are hoping to extend support for them in the future.</p>

<p>Enjoy the new toys -- and most of all have a safe and happy Holiday Season and a fantastic New Year!</p>