---
abstract: "<p>This month we\u2019ve again been focusing on improvements to the Chameleon\
  \ backend, but we still are excited to show our CHI@Edge peripheral guide and new\
  \ CHI-in-a-box features. We also are preparing for an OpenStack upgrade on July\
  \ 1st.<br>\n\_</p>"
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2024-06-04 17:38:48+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/bb/06/bb06de7c-ff2d-4834-89ec-200442b94f0b/june_changelog.png
related_posts: []
slug: chameleon-changelog-for-may-2024
subtitle: ''
title: Chameleon Changelog for May 2024
---

<p style="text-align: center;"><img media="" src="https://chameleoncloud.org/media/filer_public/bb/06/bb06de7c-ff2d-4834-89ec-200442b94f0b/june_changelog.png" width="700"></p>

<p>Dear Chameleon Users,</p>

<p>This month, we’ve been focusing a lot on internal parts of Chameleon, but we still have a guide on CHI@Edge peripherals and a new release of CHI-in-a-box to share. Part of this is preparation for an upcoming OpenStack upgrade, which we discuss later in the changelog. </p>

<p><b>CHI@Edge Peripheral guide. </b>Our Edge device testbed, known as CHI@Edge, has been steadily receiving updates. We’ve recently <a href="https://chameleoncloud.org/blog/2024/04/01/chameleon-changelog-for-march-2024/">released it from preview</a>, and last month shared how to <a href="https://chameleoncloud.org/blog/2024/05/21/seamless-ssh-container-access-with-chiedge/">interactively develop container applications for it over SSH</a>. This month, we’ve <a href="https://chameleoncloud.gitbook.io/chi-edge/device-enrollment/peripherals-and-device-profiles">updated documentation on using CHI@Edge peripherals</a> and <a href="https://www.chameleoncloud.org/experiment/share/7d35f884-68d8-4b91-b42b-207717c9b742">published a Trovi artifact</a>, showcasing how to configure a Pi Camera module using the updated libcamera software stack. At the moment, we do not have Chameleon CHI@Edge devices with peripherals to play with, though we are working on adding more for development purposes. However, you can bring your own device with peripherals to CHI@Edge. We hope this development workflow documentation and Jupyter notebook will provide a useful example implementation that you can use to add peripheral support to your own devices.</p>

<p><b>Preparing for OpenStack Antelope Upgrade</b>. As you may be aware, Chameleon is built on a mainstream cloud implementation called <a href="https://www.openstack.org/">OpenStack</a>, which means that we benefit from working with this large development community. We’re currently working hard towards upgrading our versions of Chameleon services up to the OpenStack Antelope version. This upgrade will bring some “under the hood” improvements to the system, and we’ll be sure to bring you a full list of useful new features once the upgrade is complete. However, for now, we want to call out that this upgrade will bring a few days of downtime to the system at CHI@UC starting July 1, 2024. We’ll formally announce this maintenance window soon, so be on the lookout for the full details as you plan your work on Chameleon.</p>

<p><b>CHI-in-a-box release</b>. This month, we’re excited to announce a new release of <a href="https://www.chameleoncloud.org/blog/2021/04/19/turn-your-hardware-chameleon-associate-site-chi-box/">CHI-in-a-box</a>, the packaging of the Chameleon infrastructure. This technology significantly lowers the entry barrier to configuring and operating a Chameleon site and allows us to extend Chameleon beyond the core sites at UChicago and TACC, in particular to create CHI@NU, CHI@NCAR, and CHI@EVL. While working on the Antelope Upgrade, we’ve made some helpful updates and did a general cleanup of CHI-in-a-box that site operators can utilize right away. First, the cc-ansible script no longer will automatically upgrade dependencies, which sometimes broke the installation. Additionally, we added a playbook which runs end-to-end functional tests from the OpenStack tempest project for development sites, and can help verify that APIs are working properly. If you are interested in this ability, <a href="https://chameleoncloud.gitbook.io/chi-in-a-box/development/developing-openstack-services#running-end-to-end-functional-tests-with-tempest">check out our documentation</a> for it.</p>

<p>Happy experimenting!</p>