---
abstract: "<p>Pardon our dust! This month, we have been\_revising, modernizing, and\
  \ upgrading to improve Chameleon services. We have updates on the upcoming KVM plans,\
  \ FPGA changes, and more.</p>"
authors:
- Kate Keahey
categories:
- Chameleon Changelog
date: '2025-02-04 23:00:06+00:00'
featured: false
hide_image: true
image: ''
related_posts: []
slug: chameleon-changelog-for-january-2025
subtitle: ''
title: Chameleon Changelog for January 2025
---

<p style="text-align: center;"><img media="" src="https://chameleoncloud.org/media/filer_public/16/eb/16ebca23-bf49-44cf-ad7a-2f5f7232bf92/pexels-3096301-4704637.jpg"></p>

<p>Dear Chameleon users,</p>

<p>Pardon our dust! As many of you know, this year Chameleon will turn 10 – this means we started this year on a note of revising, modernizing, and upgrading to give you better services and get rid of longstanding inconveniences. This will continue – please, keep us posted on how these changes affect your work and we will make whatever adjustments we can to make the testbed function smoothly for you.   </p>

<p><b>KVM update: pardon our dust!</b> First, may thanks for the feedback we received to our KVM <a href="https://chameleoncloud.org/blog/2025/01/02/chameleon-changelog-for-december-2024/">plans announced in the last changelog</a>. Given that a mid-semester move to AR/bounded leases would cause short-term inconvenience to projects relying on the current set of APIs, we will hold it off till the summer, i.e., support the current APIs on the current hardware – however, any new KVM hardware we manage to put online will support the new leases. In the meantime we will focus on upgrading KVM. This last month we have migrated our KVM service to a highly available control plane (you may have noticed somewhat faster response time), and will be bringing it up to date with more recent OpenStack versions in the coming weeks. There will be occasional bumps in the service – we appreciate your patience!</p>

<p><b>FPGA updates: more dust!</b> KVM is not the only element of the system requiring a bit of an overhaul: so is our existing support for FPGAs. The Altera FPGA nodes have seen very limited interest lately due to their age and the software tools are no longer supported; we are therefore retiring those nodes as well as the compilation via the <i>fpga01.tacc.chameleoncloud.org</i> host at TACC. Chameleon’s Xilinx FPGA nodes are still supported. We’ve <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/fpga.html">updated our documentation to reflect these changes</a>. Stay tuned for more information regarding new FPGA hardware soon, and as always, please <a href="https://chameleoncloud.org/user/help/ticket/new/guest/">contact us via the Help Desk</a> with any questions, feedback, or suggestions.</p>

<p><b>Chameleon User Forums: even more dust.</b> The users mailing list (and mailman) was a great communication vehicle 10 years ago when we first started – but it did not scale as our community grew and the subscription management has long been a source of frustration. As a result, for the last several years, we've had to limit the user mailing list to testbed announcements leaving the community without a good option to interact. To remedy this situation we are trialing the use of User Forums (look for announcement by the end of this week) where  users will once again be able to share interesting ideas, questions, and generally interact  – and have better control over subscription preferences. We will continue to provide <a href="https://chameleoncloud.org/user/help/ticket/new/guest/">testbed support via the helpdesk</a> – but we hope to support user questions and discussions via the forum. </p>

<p><b>Python-chi bug fixes</b>. Chameleon’s python interface, known as <a href="http://python-chi.readthedocs.io">python-chi</a>, is a great way to interact with the testbed via a programmable interface. This is why this month, we’ve put some effort into making it better. We’ve improved <i>Server.associate_floating_ip</i>, fixing an issue where if your server had multiple network interfaces, the wrong network was used. For CHI@Edge users, we’ve fixed an issue when downloading files from a container with some versions of python. Additionally, we’ve fixed an issue where creating a server at KVM@TACC raised an error. Let us know what else we should fix! </p>

<p>Happy experimenting!</p>

<p> </p>