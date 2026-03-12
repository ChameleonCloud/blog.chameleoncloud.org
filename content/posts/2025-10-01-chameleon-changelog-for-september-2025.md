---
abstract: "<p>This month we have some exciting updates to Trovi\u2019s dashboard,\
  \ support for 4xGPU instances on KVM@TACC, improvements to cc-snapshot, and a new\
  \ webinar series!</p>"
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2025-10-01 22:22:19+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/0e/70/0e7018c1-36b6-4f28-b26e-9a4ebee80fd7/49058450518_671fd78f2e_w.jpg
related_posts: []
slug: chameleon-changelog-for-september-2025
subtitle: ''
title: Chameleon Changelog for September 2025
---

<p style="text-align: center;"><img media="" src="https://chameleoncloud.org/media/filer_public/0e/70/0e7018c1-36b6-4f28-b26e-9a4ebee80fd7/49058450518_671fd78f2e_w.jpg"></p>

<p style="text-align: center;"> </p>

<p style="text-align: center;"><a data-track="attributionNameClick" href="https://www.flickr.com/photos/krishnacolor/" rel="author" title="Go to Hari K  Patibanda’s photostream">Hari K Patibanda</a><a href="https://www.flickr.com/photos/krishnacolor/49058450518/in/photolist-2mWiRrz-2maaEaF-21dVKnf-26e9d4q-2mac8PC-ZEeMUR-2ie1zFB-TL1dzP-22jxArA-219v4YL-Tius4Y-Tzxmpq-U2xDCs-XoWD3u-T2Nna9-288Uym2-2mzMoCn-6pGs4W-2paJGqT-2iY69ta-XBqkic-2kLVTrj-2hK8oaL-2oKWHM2-2m4M6G9"> via flickr</a></p>

<p>Dear Chameleon users,</p>

<p>This month we have some exciting updates to Trovi’s dashboard, support for 4xGPU instances on KVM@TACC, improvements to cc-snapshot, and a new webinar series! </p>

<p><b>New Trovi Dashboard</b>. <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/sharing/index.html">Trovi</a> is Chameleon’s repository for research and education artifacts, letting you find and share digital resources developed for the testbed, such as e.g., <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/1eb302de-4707-4ae9-ae2d-391b9b8e5261">materials for an ML class</a> or <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/585c1fc0-924c-4501-b143-ad6476339aa8">reproducing disk benchmarks</a>. Since its creation, users have shared over 270 artifacts on the platform. Last year, we announced a <a href="https://chameleoncloud.org/blog/2024/09/03/chameleon-changelog-for-august-2024/">new dashboard for Trovi</a> under preview, with improvements to the UI, faster load times, better searching, and other improvements. This month, we are excited to announce that this new dashboard is complete. You get all the features from the old dashboard, and plus new features such as <a href="https://chameleoncloud.org/blog/2025/04/21/importing-github-repositories-to-trovi-a-step-by-step-guide/">improved import from GitHub</a>, and the ability to delete artifacts. Compared to the old dashboard, you’ll notice overall improvements to usability and design, better load times, and improved error messages. Please pardon any rough edges as we work through the transition to this new dashboard, and make additions over the next few months. As always, let us know if you have any feedback or encounter any issues via our <a href="https://chameleoncloud.org/user/help/ticket/new/guest/">Help Desk</a>.</p>

<p><b>New KVM 4 GPU flavor</b>. Last month, we announced <a href="https://chameleoncloud.org/blog/2025/09/03/chameleon-changelog-for-august-2025/">more H100 nodes</a> on KVM@TACC. Using this GPU offering, you can create a VM with access to a single GPU via PCIe passthrough by <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_gui.html">making a reservation for the<i> g1.h100.pci.1</i> flavor</a>. This month, by user request, <a href="https://chameleoncloud.org/learn/frequently-asked-questions/#toc-how-are-kvm-instances-virtual-machines-charged-">we’ve added a new flavor <i>g1.h100.pci.4</i></a>, which will configure all 4 GPUs on a node with PCIe passthrough. We are excited to see what new experiments this new extra large VM flavor will enable on the testbed!</p>

<p><b>CC-snapshot improvements</b>. As most of you (hopefully!) know, you can snapshot your bare metal nodes with a utility<a href="https://chameleoncloud.readthedocs.io/en/stable/technical/images/cc_snapshot.html"> called cc-snapshot</a>. You can find this utility on all the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images/index.html">Chameleon supported images</a> or you can <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images/cc_snapshot.html">install it manually</a>.  This month, we’ve added a dry run mode, added a parameter for a custom root path, and improved an issue with system consistency.</p>

<p><b>Chameleon Webinar Series</b>. We're excited to announce the launch of our <a href="http://chameleoncloud.org/learn/webinars">Chameleon Webinar Series</a> for the coming year, featuring presentations from both the Chameleon team and our amazing users. Upcoming webinars will cover a range of topics including education, reproducibility, tools to enhance your Chameleon experience, and research projects leveraging the testbed's unique capabilities. Our first webinar, an <b>Introduction to Chameleon 2025</b> with Marc Richardson on Oct. 21, 2025 at 11 AM CT, will rehash for new and returning users how to access and use the testbed's unique capabilities (<a href="https://uchicago.zoom.us/webinar/register/WN_ckwNXP5FTTiA5Xj612DPIA">register here</a>). Our second webinar, <b>Teaching Machine Learning Operations (MLOps) at Scale</b> with Professor Fraida Fund from NYU on November 25, 2025 at 11:00 AM CT, will share her open source Trovi artifacts and insights from recently teaching a graduate-level operational ML course to nearly 200 students on Chameleon (<a href="https://uchicago.zoom.us/webinar/register/WN_ZN4PtuwhTY-lwG1SY6ICWA">register here</a>). Visit our <a href="https://chameleoncloud.org/learn/webinars/">webinar page</a> to view the schedule of upcoming webinars and access recordings from past sessions. If you’ve developed artifacts that could make research or teaching on Chameleon easier for others and are interested in presenting a webinar on that work, we'd love to hear from you—reach out to us at our <a href="http://chameleoncloud.org/user/help">Help Desk</a> to discuss your ideas.</p>

<p>Happy experimenting!</p>