---
abstract: <p>This month we have presentations from the 5th Chameleon User Meeting
  on practical reproducibility, and lots of housekeeping on Chameleon. These include
  improvements to IP availability, and fixes to the core testbed, Trovi, and CHI@Edge.</p>
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2024-12-02 22:00:56+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/55/d0/55d02ce2-5c52-48ba-8349-c73271886f20/chameleon_sweeping.png
related_posts: []
slug: chameleon-changelog-for-november-2024
subtitle: ''
title: Chameleon Changelog for November 2024
---

<p style="text-align: center;"><img media="" src="https://chameleoncloud.org/media/filer_public/55/d0/55d02ce2-5c52-48ba-8349-c73271886f20/chameleon_sweeping.png" width="500"></p>

<p>Dear Chameleon Users,</p>

<p>It has been an busy month for Chameleon. On November 18th, in Atlanta, we hosted <a href="https://reproduciblehpc.org/">the 5th Chameleon User Meeting on the topic of practical reproducibility</a> featuring keynotes from Dr. Kate Keahey (Argonne) and Dr. Torsten Hoefler (ETH Zürich), and most importantly, <a href="https://repeto.cs.uchicago.edu/2024/12/02/presentations-from-community-workshop-on-practical-reproducibility-in-hpc/">fantastic presentations from many of our users</a> who participated either as experiment authors or reviewers in various reproducibility initiatives and used Chameleon as part of this activity. This workshop carried over into a <a href="https://sc24.conference-program.com/presentation/?id=bof166&amp;sess=sess589">BoF session</a> we hosted, which allowed us to discuss how to support reproducibility initiatives better. Also, at Supercomputing ‘24, we hosted a <a href="https://sc24.conference-program.com/presentation/?id=tut157&amp;sess=sess416">Chameleon Tutorial</a>, which covered a range of topics from getting started with the testbed, to reproducible workflows, to advanced orchestration with Heat and Ansible. Chameleon was featured in several ACM <a href="https://chameleoncloud.org/blog/2024/11/19/chameleon-takes-flight-at-sc24-advancing-research-and-collaboration/">Student Research Competition posters</a> from students who worked with us this summer.</p>

<p>When we were not busy meeting and interacting with our users, we have been working hard on making the system work better for them. We’ve been investing in end of the year housekeeping, to ensure a smooth kick-off to the new year; this is unglamorous work, but we hope that it will make the system more robust and easier to use. If you are having any problems with Chameleon or general usability issues, this is  a great time to let us know about them <a href="https://chameleoncloud.org/user/help/ticket/new/guest/">via our help desk</a> – operators are standing by. Here are some of the things that should work better now:</p>

<p><b>Improved Floating IP availability. </b>Most users will need to use a public IP to access their node once it is provisioned (unless you are connecting over the private network via <a href="https://www.chameleoncloud.org/blog/2023/01/23/experiment-pattern-bastion-host/">a bastion host</a>). Chameleon sites have 2 pools of floating IPs (“floating” means that they get assigned to nodes ephemerally, effectively “floating” between nodes): <a href="https://chameleoncloud.readthedocs.io/en/latest/getting-started/index.html">ad-hoc</a> and <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/reservations.html">reservable</a>, and often it is the case that one of these pools is fully used up by experiments while the other is not. If you get an error while trying to reserve/allocate an IP, we recommend trying to use the other pool. That said, this month, we have expanded the reservable pool of IPs at CHI@TACC, which will reduce the number of times we run out of IPs at the site. Additionally we’ve optimized our floating IP reaper, which ensures that allocated ad-hoc IPs are not idle, similar to our idle lease reaper for nodes, to <a href="https://chameleoncloud.org/learn/frequently-asked-questions/#toc-what-are-the-policies-on-chameleon-resource-usage-">prevent resource hoarding</a>. Please keep in mind as you use Chameleon, that resources are shared between experimenters, so be mindful of others and release IPs or other resources when not in use.</p>

<p><b>Testbed improvements</b>. This month we’ve also improved several parts of the core testbed. First, sometimes when extending or updating a lease, users would see a “wrong number of charges” error, which now is fixed. Additionally, we fixed an issue with our <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/complex.html">orchestration service</a>, Heat, where it would not properly allow you to specify your reservation when launching an appliance. The web dashboard Horizon was also fixed, where users were unable to create <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/swift.html">object store</a> containers via the GUI. Behind the scenes, we’ve also been improving our operator testing system, which allows us to detect Chameleon service faults and hardware issues before users encounter them. </p>

<p><b>Trovi version bugfix. </b>Our <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/sharing.html">repository of artifacts, Trovi</a>, allows users to upload experimental artifacts to share with other users. Trovi integrates with Chameleon, allowing users to launch and execute your artifact with one click. Trovi also allows you to version artifacts, tracking historical versions of the artifact files for reproducibility purposes. This month, we’ve fixed a bug where sometimes multiple versions would be given the same name, which meant that you couldn’t launch the specific version selected or delete an older version.</p>

<p><b>CHI@Edge device enrollment fixes. </b><a href="https://chameleoncloud.org/experiment/chiedge/">CHI@Edge</a> is the version of Chameleon that allows you to orchestrate applications on edge hardware, like Raspberry Pis and Jetson Nanos. If you have your own hardware, you can use <a href="https://chameleoncloud.gitbook.io/chi-edge/device-enrollment/edge-sdk">the Edge SDK</a> to bring your own device (BYOD) to CHI@Edge, and share it with the Chameleon community, or limit it to your own project. This month, we’ve fixed issues where BYOD was not fully working.</p>

<p>Happy experimenting!</p>