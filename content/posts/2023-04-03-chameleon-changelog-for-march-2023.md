---
abstract: "<p>It\u2019s been a busy month on Chameleon! We finally have Fabric stitching\
  \ at CHI@TACC, improvements for educational use, trovi roles, improvements to JupyterLab,\
  \ and CHI-in-a-box updates.<br>\n\_</p>"
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2023-04-03 22:07:48+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/f4/64/f464db1f-2190-4763-b3ec-8a4891271c1e/dom-fou-yrmwvcdyhmi-unsplash.jpg
related_posts: []
slug: chameleon-changelog-for-march-2023
subtitle: ''
title: Chameleon Changelog for March 2023
---

<p><b id="docs-internal-guid-e7e0d986-7fff-5724-f535-e13b8a328c08"><img height="468" src="https://lh4.googleusercontent.com/15aaZJMUk4pRnpTODp9GHwaFm366jqkqN2DS3o3CEybvYo6e4dgy9Di9NoaqD7wtXVnMbjnsWqiiQb1sp_18nxmIhFurUYVlHyYb-etgfHov_ZORW49O0e57TZ56jTEgcFEO4SY2RUpWLscV-ySf5Z0" width="624"></b></p>

<p> </p>

<p>Dear Chameleon users,</p>

<p>It isn’t too late to send us a presentation proposal or register for the <a href="https://chameleoncloud.org/chameleon-cloud-users-meeting/user-meeting-2023/">Chameleon User Meeting</a>! We hope to see you all there – for more information, see our <a href="https://chameleoncloud.org/chameleon-cloud-users-meeting/user-meeting-2023/">webpage</a>. We just announced a keynote on <a href="https://chameleoncloud.org/blog/2023/04/03/a-roadmap-to-deeper-learning-using-research-infrastructure/">Teaching with Testbeds</a>, but the program contains other topics as well. There are a lot of updates to Chameleon this month, including some aimed at educators.</p>

<p><strong>FABRIC stitching at CHI@TACC! </strong>Last summer, we announced that you could <a href="https://chameleoncloud.org/blog/2022/08/01/chameleon-changelog-for-july-2022/">integrate Chameleon experiments with Fabric</a> at CHI@UC, which now is possible from CHI@TACC too. This allows you to run experiments utilizing both Chameleon’s resources and those of the <a href="https://fabric-testbed.net/">FABRIC networking testbed</a>. See <a href="https://www.chameleoncloud.org/experiment/share/9a63884a-5a89-46d6-9149-63946f45e2b1">this artifact</a> for examples of how to connect Chameleon and Fabric. If you have any questions about this feature, please let us know via the <a href="https://chameleoncloud.org/user/help/">help desk</a>, as always.</p>

<p><strong>New features supporting education use</strong>. Most projects on Chameleon are for research groups, but Chameleon is also used by many educators to run classes. <a href="https://chameleoncloud.org/blog/2023/03/01/chameleon-changelog-for-february-2023/">Last month</a>, we updated various OpenStack features to make them easier to use, especially for students with lesser experience, and for large groups. This month, we made it easier to manage large classes. Specifically, we’ve updated the project management portal so that you can <a href="https://chameleoncloud.readthedocs.io/en/latest/user/project.html#manage-users">remove all students</a> in bulk from a project once the semester is over. We also made it so you can share a <a href="https://chameleoncloud.readthedocs.io/en/latest/user/project.html#manage-users">”Request to join” link</a> for your project that you can send to students, rather than having to copy and paste their email addresses, which gets tricky during drop/add periods.</p>

<p><strong>Trovi roles</strong>. Many of you are familiar with <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/sharing.html">Trovi</a>, Chameleon’s repository of experimental artifacts represented as Jupyter notebooks. This month, we <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/sharing.html#assigning-roles-to-other-users">added roles</a> to Trovi artifacts. Before, only the artifact creator could update the artifact contents and metadata. Now, you can assign other users as “Collaborator” and “Administrator”, so that they can update the artifact as well. We hope this makes it easier for groups to collaborate and keep artifacts up to date.</p>

<p><strong>Improved JupyterLab experience</strong>. One of the main interfaces to the testbed is <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/jupyter.html">Jupyter</a>, an interactive, programmable, repeatable environment. Jupyter is integrated with Trovi: allowing you to easily import artifacts, or to export your jupyter files as an artifact. Some users have experienced bugs with how the integration worked, and the green folder icons, indicating the folder stored artifact files, would stop being linked if folders were moved or renamed. The integration is now more robust, and should prevent future errors. If you’ve encountered errors in the past, there is now a “Link” button to fix legacy issues. Some users have requested the ability to <a href="https://jupyterlab.readthedocs.io/en/stable/user/extensions.html#managing-extensions-using-the-extension-manager">install JupyterLab extensions via the sidebar</a>, which can enable extra functionality such as a code formatter or LaTeX typesetting in your notebook. This now should work. Additionally, we recognize many users want to interact with git in their notebooks, which has been possible via the command line. To make things easier, we now include Jupyter’s <a href="https://github.com/jupyterlab/jupyterlab-git">git extension</a> by default, so that you can use git via the GUI.</p>

<p><strong>CHI-in-a-box updates.</strong> The packaging of Chameleon Infrastructure, known as CHI-in-a-Box, has a number of incremental improvements and bugfixes this month as well. We’ve rebased onto the latest Xena version of OpenStack to pull in a large number of upstream fixes, in particular <a href="https://github.com/ChameleonCloud/kolla-ansible/commit/a1183525e25609ef6e675a50cbbaaff52e474b88">fixing an edge case with the oslo.log library that could cause multiple services to deadlock</a>. The per-site image distribution tool has been updated, by removing the default image pulls from the “post-deploy” step to avoid conflicts. For deploying new CHI@Edge sites, we’ve fixed a dependency between Zun and Kubernetes during initial setup, the deploy will now warn instead of fail if a kubeconfig file is not present in your site-config. Finally, using letsencrypt with your site is a little bit easier, we no longer fail if a `haproxy.pem` file is missing from your site config if letsencrypt is enabled.</p>

<p><strong>Appliance inquiry.</strong> On Chameleon, we have an <a href="https://chameleoncloud.org/appliances/">appliance catalog of images</a>, which are base OS images to help you get started on experiments. Right now, we have images for Ubuntu 20 + 22, CentOS 7, and CentOS Steam 8 (and CUDA variants). We are working to overhaul the way we build these images. While we do so, if there is some other operating system that you think we should support, please send us a message on the <a href="https://chameleoncloud.org/user/help/">help desk</a> for consideration. </p>

<p>Happy educating and experimenting!<br>
 </p>