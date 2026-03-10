---
abstract: <p>This month, we have updated appliances including Ubuntu 24.04! We also
  have Trovi dashboard updates and fixes to ARM64 nodes at CHI@TACC.</p>
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2024-11-01 21:02:52+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/88/ce/88ced487-0511-4b90-9bdc-5796c1823afc/54068530630_2a80d38f93_c.jpg
slug: chameleon-changelog-for-october-2024
subtitle: ''
title: Chameleon Changelog for October 2024
---

<p style="text-align: center;"><img media="" src="https://chameleoncloud.org/media/filer_public/88/ce/88ced487-0511-4b90-9bdc-5796c1823afc/54068530630_2a80d38f93_c.jpg" width="500"></p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-758f748d-7fff-17d7-6dd7-1a0c16c035c7"><a href="https://www.flickr.com/photos/30557460@N05/54068530630/in/photolist-2qnRmrm-2qnQFMm-2qkkCfa-2qfVCev-2qeiWHZ-2qcii6x-2pL1zbN-2q6Dp5e-2q6LcMy-2pJtcAg-2q4LHMG-2pVmTLn-2pVo2nK-2pVgcMo-2pSQfqm-2pRP8Uz-2pNBE7D-2pMQwSF-2pDEk4e-2pDye2u-2pDEk3T-2pDEk3Y-2pDEZce-2pDDKHF-2pDye29-2pDDKHv-2pCN5bN-2pagSSo-2pCiCrX-2pCpJ9U-2pCpago-2pCo551-2pCpJ9J-2pCqkYW-2pCqkZ2-2pCo54p-2pAAC79-2pArd7i-2pAoUTR-2pA84Wh-2pA959g-2pA958z-2pA84VW-2pA3Cxk-2pA3Cxf-2pA84Vv-2pA9MZM-2pxzze8-2pxAjF4-2pxyGKR">Scott Edmunds via Flickr</a></b></p>

<p>Dear Chameleon users,</p>

<p>This month, we are still working on things mostly behind the scenes that keep the testbed working reliably.</p>

<p><b>Appliance updates</b>. Chameleon’s <a href="https://chameleoncloud.org/appliances/">appliance catalog</a> is where you can find OS images that you can use when provisioning your instances. As part of keeping the testbed in working order, we have to regularly address updates to these images with their software upgrades, and follow the OS end of life system in place. </p>

<p>This month, we added Ubuntu 24.04 as a Chameleon supported image. Additionally, we updated our other Ubuntu images, 20.04 and 22.04, along with our CentOS Stream 9 image. These updates include CUDA 12 versions of all of our Ubuntu images. Due to driver compatibility, the CUDA 12 images do not work with K80 GPUs, but for these nodes you can use our Ubuntu 20.04 + CUDA 11 image. If you were previously using CentOS 7 or CentOS Stream 8, we recommend updating your experiment to CentOS Stream 9, as the older versions are beyond their end of life and no longer receive security updates.</p>

<p><b>Trovi dashboard updates. </b>A <a href="https://chameleoncloud.org/blog/2024/09/03/chameleon-changelog-for-august-2024/">few months ago</a>, we released the preview version of a new dashboard for our artifact sharing repository Trovi. This dashboard is a much more modern interface, and you should find that things load a lot faster! This month we added the essential “badges” for artifacts. These badges indicate whether an artifact is supported by the Chameleon team, <a href="https://repeto.cs.uchicago.edu/resources/about-trovi-repeto-badge/">a reproducible artifact</a>, or <a href="https://fount.cs.uchicago.edu/resources/trovi-fount-badge-application/">an educational module</a>. These are badges that we grant to artifacts that meet high standards for quality.</p>

<p><b>General testbed improvements</b>. Some of the other improvements to the testbed this month are fixes to the ARM64 nodes at CHI@TACC. These nodes have had issues provisioning since the Antelope upgrade at  TACC last month due to a configuration issue. Additionally we’ve enabled a 40G networking interfaces on these nodes, which makes them have the fastest networking at our main sites. We’ve also made it easier to access <a href="https://chameleoncloud.org/user/help/ticket/new/guest/">the Help Desk</a>: the header link for the help desk no longer requires you to log in, which caused problems if you need help with your account.</p>

<p>Happy experimenting!</p>