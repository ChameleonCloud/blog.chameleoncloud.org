---
abstract: <p dir="ltr"><b id="docs-internal-guid-69858a62-7fff-9399-4600-64afc751c607">This
  month, we are preparing for a big upgrade on July 15th. Additionally, we have CHI-in-a-box
  for edge sites, new hardware at CHI@UC, and improvements to project management.</b></p>
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2024-07-01 23:14:21+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/9a/c9/9ac93787-ee91-4146-b60b-126f8a0c7fe6/chameleon-3051482_1280.jpg
related_posts: []
slug: chameleon-changelog-for-june-2024
subtitle: ''
title: Chameleon Changelog for June 2024
---

<p style="text-align: center;"><img height="500" media="" src="https://chameleoncloud.org/media/filer_public/9a/c9/9ac93787-ee91-4146-b60b-126f8a0c7fe6/chameleon-3051482_1280.jpg"></p>

<p>Dear Chameleon users,</p>

<p>This month, we’ve continued to work on the internal parts of Chameleon, and we have a date for the important Openstack upgrade at CHI@UC. We also found time to release new hardware with A100 GPUs, package CHI@Edge in CHI-in-a-box.</p>

<p><b>Openstack Upgrading on July 15th.</b> As many of you know, <a href="https://www.openstack.org/">Openstack</a> is the mainstream cloud infrastructure that Chameleon builds on under the hood. Last month, <a href="https://chameleoncloud.org/blog/2024/06/04/chameleon-changelog-for-may-2024/">we announced</a> that we are working to bring Openstack upgrades to Chameleon and now it is finally happening: we have set a final date for the upgrade at CHI@UC of July 15th. This outage will last all day. During this time, the site will not be accessible; CHI@TACC and other Chameleon sites will not be affected. For the full details, <a href="https://chameleoncloud.org/user/outages/chiuc-maintenance-window-for-openstack-version-upgrade/">see the outage notice</a>, but we wanted to alert you here so that you can plan accordingly.</p>

<p><b>CHI-in-a-box for Edge</b>. CHI-in-a-box packages the Chameleon infrastructure in such a way that anyone can set up their own Chameleon site. This is what powers our associate sites like CHI@NCAR and CHI@EVL. This month, <a href="https://chameleoncloud.org/blog/2024/04/01/chameleon-changelog-for-march-2024/">we’ve followed through on our promise</a> to support setting up edge sites in CHI-in-a-box, which means you can build your own CHI@Edge-like site. If you are interested, see our <a href="https://chameleoncloud.gitbook.io/chi-in-a-box/setup-guides/edge-in-a-box">new guide</a>. However, keep in mind that you can always <a href="https://chameleoncloud.gitbook.io/chi-edge/device-enrollment/edge-sdk">add your own devices to CHI@Edge</a>, so there is no need to set up a brand new site. CHI@Edge in a box is intended for users who wish to set up an <a href="https://github.com/ChameleonCloud/chi-in-a-box?tab=readme-ov-file#independent-testbed">independent edge testbed</a>.</p>

<p><b>New composable hardware at CHI</b>@UC. We now have 8 new GigaIO composable nodes available at CHI@UC. Currently, those nodes are statically configured so that each of them has 1x Nvidia A100 80GB GPU attached via PCIe, AMD EPYC 7763 64-Core processors, and 500GB of memory. However, you can also configure those nodes to represent flexible hardware configurations, e.g., support a configuration of 4 GPUs per node rather than one per node, <a href="https://www.chameleoncloud.org/blog/2022/09/01/chameleon-changelog-for-august-2022/">similar to the composable Liqid nodes at TACC</a>. You can make use of those nodes in the currently exposed static configuration by reserving a <a href="https://chameleoncloud.org/hardware/">“compute_gigaio” node</a> – or in order to experiment with composability, you can reserve multiple of these nodes at once, <a href="https://chameleoncloud.org/user/help">submit a help-desk ticket</a>, and we will recompose these nodes as requested. We hope to support user-facing API for composable node reconfiguration in the future depending on user demand. </p>

<p><b>Project membership improvements</b>. This summer, your Chameleon projects have started to grow very large in size! Due to this, we made modifications to better display project members. As part of this, we’ve added some clarifying numbers to the project overview page so you can see at a glance how many users are in a project, and if there are pending invitations or requests. </p>

<p>Happy experimenting!</p>