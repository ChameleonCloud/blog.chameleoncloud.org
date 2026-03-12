---
abstract: "<p>This month on Chameleon, we are excited to announce the Fount project,\
  \ 52 new Ice Lake nodes at CHI@TACC, multi-node launch improvements, and improvements\
  \ for CHI-in-a-Box site operators.<br>\n\_</p>"
authors: []
categories:
- Chameleon Changelog
date: '2023-09-01 21:28:37+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/ef/43/ef43457c-8a6e-4958-a6a3-30d833089b33/fount_logo_with_text_backg.png
related_posts: []
slug: chameleon-changelog-for-august-2023
subtitle: ''
title: Chameleon Changelog for August 2023
---

<p>Dear Chameleon users,</p>

<p>This month, we bring more exciting updates to Chameleon.</p>

<p><img media="" src="https://chameleoncloud.org/media/filer_public/ef/43/ef43457c-8a6e-4958-a6a3-30d833089b33/fount_logo_with_text_backg.png"></p>

<p><b>Introducing FOUNT Project! </b>Last month, we announced <a href="https://chameleoncloud.org/blog/2023/08/01/chameleon-changelog-for-july-2023/">the REPETO project</a> to foster practical reproducibility on open platforms. This month, we are excited to announce <a href="https://fount.cs.uchicago.edu/">the FOUNT project</a>, which aims to develop scaffolded, education modules on open clouds and testbeds. These courselets are developed with literate programming, enabling students to explore their contents hands-on. Right now, there is <a href="https://voices.uchicago.edu/fount/educational-artifacts-in-trovi/">one educational artifact</a> published on Trovi, which showcases a module using self-driving cars to teach machine learning concepts. If you are an educator, and have developed educational modules, you can submit them to <a href="https://voices.uchicago.edu/fount/trovi-fount-badge-application/">this form</a>. You can join <a href="https://groups.google.com/g/chameleon-education">the mailing list</a> and follow on <a href="https://twitter.com/fountproject">Twitter</a> or <a href="https://www.linkedin.com/company/founthandsonlearning/about/">LinkedIn</a> to stay up to date with the project. Please feel free to join in the discussion.</p>

<p><b>Ice Lake nodes at CHI@TACC. </b>Last month we announced 20 new nodes on CHI@TACC. We’ve added even more this month, with 52 new Ice Lake nodes. These nodes are Dell R750 servers, each with 2x Intel Platinum 8380 CPUs, for a total of 80 cores and 160 threads, as well as 256GB of ram. They’re configured with 2x 25G ethernet interfaces, and a 480GB SATA SSD for the boot drive. Additonally, the compute_icelake_r650 nodes have Mellanox ConnectX-6 cards for their network-interfaces, and can be used as SmartNICs by advanced users. You can find more information about them in the <a href="https://chameleoncloud.org/hardware/">hardware browser</a>. </p>

<p><b>CHI-in-a-Box hardware management improvements. </b><a href="https://chameleoncloud.org/media/filer_public/00/fb/00fb4562-d381-4e7e-b642-bab7268d5321/pearc22-chi-in-a-box.pdf">CHI-in-a-Box</a> packages the Chameleon infrastructure into a portable tool that powers associate sites like CHI@NCAR and CHI@EVL. This month, we updated the hardware management tool, Doni. Now, you can use names instead of UUIDs when working with resources, and see worker status and last errors in the list view. This should improve the operator experience, especially when enrolling large numbers of nodes.</p>

<p><b>Improved multi-node launches. </b>If you ever tried to launch multiple instances at once on our baremetal sites, you may have seen a timeout error occur. This was caused due to slow reconfiguration in the switch vendor’s OS, but we’ve worked around this by batching multiple requests at once. We’ve tested launches of 30+ nodes, so you should be able to launch any number of instances you like at once, provided you have an active lease for the nodes.</p>

<p><b>Updated A100 image. </b>Users reported issues with networking on the A100 NVLink node at UC. <a href="https://bugs.launchpad.net/ubuntu/+source/linux/+bug/2012335">This was caused by a bug in Intel’s ICE driver</a>. We’ve updated CC-Ubuntu20.04-CUDA and CC-Ubuntu22.04-CUDA with newer kernels to fix this issue.</p>

<p>Happy experimenting!</p>