---
abstract: <p dir="ltr">This month, we are very excited to announce CHI@Edge is coming
  out of preview! We also have new artifacts that allow you to explore Fabnet with,
  and new per-user SU budgeting.</p>
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2024-04-01 22:14:12+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/2e/18/2e18c9db-23c5-4eb2-b11e-b13bacee0114/2024_march_changelog.jpg
slug: chameleon-changelog-for-march-2024
subtitle: ''
title: Chameleon Changelog for March 2024
---

<p style="text-align: center;"><img media="" src="https://chameleoncloud.org/media/filer_public/2e/18/2e18c9db-23c5-4eb2-b11e-b13bacee0114/2024_march_changelog.jpg"></p>

<p>Dear Chameleon Users,</p>

<p><strong>CHI@Edge is coming out of preview!</strong> You may have noticed a series of improvements to our edge computing testbed, CHI@Edge, over the last few months. CHI@Edge has been “in-preview” since we <a href="https://chameleoncloud.org/blog/2021/06/01/chameleon-changelog-may-2021/">introduced it almost three years ago</a>. As the final step in making the site production ready, we’ve deployed a proper UI and API for viewing resources, which you can <a href="https://chameleoncloud.org/edge/hardware/">browse here</a>. Additionally, we’ve updated our CHI@Edge Trovi artifacts so that they are up to date with the latest best practices: the introductory <a href="https://chameleoncloud.org/experiment/share/ae64bc9b-8315-41dc-96ec-abd86259ba3f">CHI@Edge Tutorial</a> and <a href="https://chameleoncloud.org/experiment/share/37991779-fd7b-4ab0-8d6f-e726a9204946">Edge to Cloud experiment pattern</a>. We’ll still be improving things over the coming weeks, and in particular making it possible to fully deploy new CHI@Edge sites with our <a href="https://github.com/ChameleonCloud/chi-in-a-box">packaged infrastructure CHI-in-a-box</a>, but we are excited to have a full feature set that we can call production ready!</p>

<p> </p>

<p><b>New Chameleon + Fabric artifact</b>. <a href="https://chameleoncloud.org/blog/2024/03/01/chameleon-changelog-for-february-2024/">Last month</a>, we announced a simple and convenient way to connect Chameleon experiments at UC and TACC to the Fabric testbed. Initially, this was limited access at CHI@UC, but after networking uplink upgrades, the feature is publically available. At the Fabric KNIT workshop earlier this month, we gave a tutorial about utilizing Chameleon resources with Fabric, and to go along with it we published this <a href="https://chameleoncloud.org/experiment/share/6c53cb25-0942-4d9c-ad27-e1bdb4e83fa5">new artifact</a> and<a href="https://chameleoncloud.org/blog/2024/03/18/tips-and-tricks-understanding-the-fabric-layer-3-connection/"> a blog post</a>, which showcases some of the networking capabilities you can do with this behavior. </p>

<p><b>User SU budgeting.</b> If you are a Chameleon user, you likely are familiar with our SU allocation system, which is used to track and limit how many resources projects can use on the testbed. This month, we made it possible to <a href="https://chameleoncloud.readthedocs.io/en/latest/user/project.html#set-su-budgets-for-project-members">give individual user’s SU budgets</a>, limiting how much of your allocation each user can use. This can be set on a per-user basis, or set for all project members. We anticipate this feature will be especially useful to projects with many members, such as educational projects, to ensure no one uses more than their fair share of the allocation.</p>

<p><b>Fixed filesystem package issues.</b> Chameleon has a <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/shares.html">shared filesystem service</a>, allowing you to mount network storage to your instances. This month, we fixed an issue where our Ubuntu images were missing packages required to mount these file shares by default. </p>

<p>Happy experimenting!</p>