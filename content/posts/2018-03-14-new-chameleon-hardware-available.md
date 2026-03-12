---
abstract: '<p><span style=''font-family: "Source Sans Pro", Helvetica, sans-serif;
  font-size: 16px;''>We are pleased to announce immediate availability of the first
  installment of new hardware for phase 2 of Chameleon!</span></p>'
authors:
- Pierre Riteau
categories:
- Chameleon Changelog
- Announcements
date: '2018-03-14 19:02:44+00:00'
featured: false
hide_image: true
image: ''
related_posts: []
slug: new-chameleon-hardware-available
subtitle: ''
title: New Chameleon Hardware Available
---

<p><span style='font-family: "Source Sans Pro", Helvetica, sans-serif; font-size: 16px;'>We are pleased to announce immediate availability of the first installment of new hardware for phase 2 of Chameleon!</span><br style='font-family: "Source Sans Pro", Helvetica, sans-serif; font-size: 16px;'>
<br style='font-family: "Source Sans Pro", Helvetica, sans-serif; font-size: 16px;'>
<span style='font-family: "Source Sans Pro", Helvetica, sans-serif; font-size: 16px;'>This new hardware is composed of two 32-node racks of Skylake nodes. Each node is a PowerEdge R740 server with two Intel Xeon Skylake CPUs running at 2.60 GHz (each with 12 cores / 24 threads), 192 GiB of RAM, a Samsung SSD with 240 GB of storage, and 10 Gigabit Ethernet connectivity. 32 of those bare metal nodes are available on CHI@UC and 32 are on CHI@TACC.</span><br style='font-family: "Source Sans Pro", Helvetica, sans-serif; font-size: 16px;'>
<br style='font-family: "Source Sans Pro", Helvetica, sans-serif; font-size: 16px;'>
<span style='font-family: "Source Sans Pro", Helvetica, sans-serif; font-size: 16px;'>The nodes are connected at 10 Gigabit to Corsa switches: on CHI@TACC, to a Corsa DP2200, and on CHI@UC, to a Corsa DP2400. Both are using a 100 Gigabit uplink; at TACC, it is connected to a 100G network while at UC, connectivity to a 100G network will soon be available. Corsa switches offer advanced virtualization and OpenFlow capabilities which we plan to leverage in the near future to support user controlled networking experiments—for now, these switches are conventionally configured to support multi-tenant networking. Please note, however, that on CHI@UC the only isolated networks the new nodes can use are the VLANs stitchable to ExoGENI. We are working on allowing use of the full range of VLANs in the future.</span><br style='font-family: "Source Sans Pro", Helvetica, sans-serif; font-size: 16px;'>
<br style='font-family: "Source Sans Pro", Helvetica, sans-serif; font-size: 16px;'>
<span style='font-family: "Source Sans Pro", Helvetica, sans-serif; font-size: 16px;'>The new nodes can be reserved using the "compute_skylake" node type on the command line or by selecting "Compute (Skylake)" in the web interface. For consistency, the existing compute nodes have been renamed to "compute_haswell" and Infiniband nodes to "compute_haswell_ib": please adapt your scripts accordingly.</span><br style='font-family: "Source Sans Pro", Helvetica, sans-serif; font-size: 16px;'>
<br style='font-family: "Source Sans Pro", Helvetica, sans-serif; font-size: 16px;'>
<span style='font-family: "Source Sans Pro", Helvetica, sans-serif; font-size: 16px;'>We look forward to learn about all the exciting new experiments enabled by this new hardware—happy experimenting!</span></p>