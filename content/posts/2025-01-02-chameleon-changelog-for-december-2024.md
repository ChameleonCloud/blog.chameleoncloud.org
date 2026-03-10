---
abstract: "<p>Happy New Year! We\u2019ve had a busy 2024 with new hardware and many\
  \ system improvements! In our changelog today we note a couple of nits that slid\
  \ under the wire in the last year and propose important changes to our virtualized\
  \ offering \u2013 please, read carefully we are asking for your feedback to make\
  \ sure that those innovations don\u2019t interfere with your ability to use the\
  \ system for your experiments.\_<br>\n\_</p>"
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2025-01-02 22:54:52+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/9b/49/9b499a4b-21bf-4ac8-a3df-096cf11dd69c/dec_changelog.jpg
slug: chameleon-changelog-for-december-2024
subtitle: ''
title: Chameleon Changelog for December 2024
---

<p style="text-align: center;"><img media="" src="https://chameleoncloud.org/media/filer_public/9b/49/9b499a4b-21bf-4ac8-a3df-096cf11dd69c/dec_changelog.jpg" width="400"></p>

<p>Dear Chameleon users,</p>

<p>Happy New Year! </p>

<p>2024 was a busy and momentous year on Chameleon. First, we’d like to thank the National Science Foundation (NSF) for its continuing the <a href="https://chameleoncloud.org/blog/2024/08/01/chameleon-testbed-secures-12-million-in-funding-for-phase-4/">support for Chameleon</a> – in addition to serving our community for another four years, Chameleon 4 will bring many innovations to the system that will allow us to support more experiments for more users (one small step forward in that direction below). </p>

<p>On the hardware front, we added <a href="https://chameleoncloud.org/blog/2024/07/01/chameleon-changelog-for-june-2024/">GigaIO</a> <a href="https://chameleoncloud.org/blog/2024/09/03/chameleon-changelog-for-august-2024/">nodes</a> with A100 GPUs to both CHI@UC and CHI@TACC; those nodes support <a href="https://chameleoncloud.org/blog/2024/08/19/composible-hardware-on-chameleon-now/">composable hardware experiments</a> but can also be used in a static configuration leveraging the powerful GPUs they bring. We also welcomed a new volunteer site, <a href="https://chameleoncloud.org/blog/2024/09/03/chameleon-changelog-for-august-2024/">CHI@NRP</a>, that will allow us to support more distributed experiments, and made experimenting across combined Chameleon and FABRIC resources easier by introducing <a href="https://chameleoncloud.org/blog/2024/03/01/chameleon-changelog-for-february-2024/">Fabric Layer 3 connections</a>. On the system front, we upgraded the testbed to <a href="https://chameleoncloud.org/blog/2024/08/02/chameleon-changelog-for-july-2024/">Openstack Antelope</a> and revamped our <a href="https://chameleoncloud.org/blog/2024/02/01/chameleon-changelog-for-january-2023/">Chameleon</a> images, in particular added a new <a href="https://chameleoncloud.org/blog/2024/11/01/chameleon-changelog-for-october-2024/">Ubuntu 24.04 appliance</a>. It was also an exciting year for our edge testbed, <a href="https://www.chameleoncloud.org/experiment/chiedge/">CHI@Edge</a>, which came out <a href="https://chameleoncloud.org/blog/2024/04/01/chameleon-changelog-for-march-2024/">preview</a> this year, with new support for edge in <a href="https://chameleoncloud.org/blog/2024/07/01/chameleon-changelog-for-june-2024/">CHI-in-a-box</a> and <a href="https://chameleoncloud.org/blog/2024/09/03/chameleon-changelog-for-august-2024/">Raspberry Pi 5 devices</a>. </p>

<p>Chameleon projects and community have been growing larger than ever before – over 1200 unique projects and 11,000 users as of this writing – and so we <a href="https://chameleoncloud.org/blog/2024/07/01/chameleon-changelog-for-june-2024/">improved user management</a> for project PIs and managers, now supporting per user <a href="https://chameleoncloud.org/blog/2024/04/01/chameleon-changelog-for-march-2024/">SU budgets</a>. To help welcome new users, we overhauled our <a href="https://chameleoncloud.org/blog/2024/08/02/chameleon-changelog-for-july-2024/">Getting Started guide</a>. Looking ahead to improving reproducibility in Chameleon 4, we also released a <a href="https://chameleoncloud.org/blog/2024/09/03/chameleon-changelog-for-august-2024/">new dashboard</a> preview for Trovi, and improved the python-chi library (<a href="https://chameleoncloud.org/blog/2024/10/01/chameleon-changelog-for-september-2024/">Python-chi</a> 1.0) to better support expressing experiments programmatically, and – last but not least – we hosted a Chameleon User Meeting as a <a href="https://chameleoncloud.org/blog/2024/04/12/save-the-date-november-18-2024-reproducibility-workshop/">workshop on practical reproducibility</a>.</p>

<p><b>Exciting developments for our VM offering coming soon! </b>Since increasingly more of our users use GPU instances in their research we need to share them more efficiently – for this reason, for the first time ever we will offer GPU instances via Chameleon’s <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm.html">virtualized offering</a> -- in fact, our new hardware, which will consist of nodes with H100 GPUs that we will deploy in the first quarter of 2025 will be available exclusively via virtualized instances to begin with (later in the year the same nodes will be available via bare metal reconfiguration as well). To make sure that they are shared efficiently we are making changes to the virtualized offering: gone are the “endless” leases (since we suspect nobody would give up a lease on a GPU instance ;-)) and in are advance reservations (so that you can make sure that the GPU instance will be there for you when you need it). You will also notice that those virtualized instances will now be a hit on your allocation balance. Will those changes to the virtualized offering limit your ability to experiment? Do you need to use the new hardware via bare metal? If any of those plans have the potential to create difficulties for you, please let us know via the comments section of this blog, through <a href="https://lists.chameleoncloud.org/mailman/listinfo/users">our mailing list</a>, or <a href="https://chameleoncloud.org/user/help/">via the help desk</a>. </p>

<p><b>Floating IP improvements at UC</b>. In December, some of you noted that after associating a floating IP at CHI@UC, it could take as long as several minutes to be able to use the IP. After successful negotiations with the system gremlins the same operation now takes a few seconds at all Chameleon sites.</p>

<p><b>Publications management improvements</b>. Reporting publications is exceptionally important as it helps NSF understand the extent to which Chameleon is useful and serves to support research. However, we noticed last year that it was not as easy for our users to report publications as it should be; in particular, this process was confusing when projects had multiple managers submitting publication information, or where a PI had multiple projects as it was not clear who reported what publications where. We’ve improved the <a href="https://chameleoncloud.org/user/projects/publications/">publication list</a> page, so that you can now see all submitted publications across all of your projects at once.</p>

<p>Happy New Year once again, we look forward to working with you in 2025 – and as always, happy experimenting!</p>