---
abstract: "<p>This month, we\u2019ve been working on improving the testbed with updates\
  \ to CHI@Edge device OSes, Trovi, the help desk, and a CC-snapshot bug-fix.</p>"
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2023-11-01 21:55:25+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/8d/58/8d58eaea-043c-48eb-8b34-909ab737c17c/oct_changelog.jpg
related_posts: []
slug: chameleon-changelog-for-october-2023
subtitle: ''
title: Chameleon Changelog for October 2023
---

<p style="text-align: center;"><img media="" src="https://chameleoncloud.org/media/filer_public/8d/58/8d58eaea-043c-48eb-8b34-909ab737c17c/oct_changelog.jpg"></p>

<p style="text-align: center;"><a href="https://commons.wikimedia.org/wiki/File:Montagne_d%27Ambre_leaf_chameleon_(Brookesia_tuberculata)_female_2.jpg"><em>Via Wikimedia</em></a></p>

<p>Dear Chameleon Users,</p>

<p>This month, we’ve been hard at work keeping the testbed running smoothly. We are focusing on improving the reliability of our services and their usability. </p>

<p><b>CHI@Edge OS upgrade</b>. <a href="https://chameleoncloud.org/experiment/chiedge/">CHI@Edge</a> is a version of the testbed where you can experiment with smaller, edge devices like Raspberry Pis and Jetson Nanos, even allowing you to <a href="https://chameleoncloud.gitbook.io/chi-edge/device-enrollment/edge-sdk">bring your own device</a>. <a href="https://chameleoncloud.org/blog/2023/10/02/chameleon-changelog-for-september-2023/">Last month</a>, we added 18 new Raspberry Pis to the testbed. This month, we’ve upgraded all our CHI@Edge devices to a new OS version, meaning they are now on a newer kernel. These upgrades should now <a href="https://chameleoncloud.gitbook.io/chi-edge/faq#how-do-i-run-a-gpu-workload-on-the-jetsons-xaviers">make it easier to use pytorch</a> or similar libraries that require the Nvidia runtime on the Jetson Nano devices.</p>

<p><b>Portal usability improvements</b>. Portal is the main website for Chameleon, that is a gateway for our federated sites. It also hosts various shared services, like our <a href="https://chameleoncloud.org/user/projects/chameleon-used-research/">list of publications using Chameleon</a>, allocations, and the <a href="https://chameleoncloud.org/hardware/">hardware discovery</a>. It also has an interface to <a href="https://chameleoncloud.org/experiment/share/">Trovi</a>, our artifact sharing repository. This month, we updated the Trovi metrics to clearly display the total for the artifact across all versions, and views and users won’t appear to reset when you upload a new version. Additionally, if your artifact has a DOI, it needs to be public so that it can be cited, and this is now more clear in the UI.</p>

<p>The portal is also where you can contact us via the <a href="https://chameleoncloud.org/user/help/ticket/new/">Help Desk</a>. We’ve fixed our guest help desk web form, allowing you to submit tickets if you are having trouble logging into your account. However, you are always free to contact us via email at <a href="mailto:help@chameleoncloud.org">help@chameleoncloud.org</a>. Lastly, we also fixed a text wrapping issue when viewing your tickets in the portal.</p>

<p><b>CC-snapshot improvements. </b>This month we updated our <a href="https://chameleoncloud.org/blog/2023/10/02/chameleon-changelog-for-september-2023/#:~:text=baremetal%20snapshot%20tool%2C-,cc%2Dsnapshot,-%2C%20so%20that%20now">cc-snapshot utility</a>, which is a program that lets you create an image from a baremetal server. Previously there was an issue where cc-snapshot failed to work on custom Ubuntu EFI boot images. Now, this should be fixed.</p>

<p>Happy experimenting!</p>