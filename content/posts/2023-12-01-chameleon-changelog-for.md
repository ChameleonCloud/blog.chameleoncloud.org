---
abstract: <p>We had a busy month at Super Computing earlier this month and with IndySCC.
  We also have been preparing for a virtual reproducibility hackathon next month.
  Changes this month include improvements to resource reservations, CHI-in-a-box,
  appliance fixes, and JupyterHub updates.</p>
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2023-12-01 22:28:53+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/7d/61/7d61d7f9-dc06-4642-b506-6f3ce794f257/nov_changelog.jpg
slug: chameleon-changelog-for
subtitle: ''
title: Chameleon Changelog for November 2023
---

<p style="text-align: center;"><img media="" src="https://chameleoncloud.org/media/filer_public/7d/61/7d61d7f9-dc06-4642-b506-6f3ce794f257/nov_changelog.jpg"></p>

<p>Dear Chameleon Users,</p>

<p>It’s been a busy month for Chameleon.</p>

<p>If you were at Super Computing ’23 this month, you may have seen one of our <a href="https://chameleoncloud.org/blog/2023/11/10/chameleon-presents-at-sc23/">presentations or posters</a>. If you missed them, you can still <a href="https://chameleoncloud.org/about/papers-and-tech-reports/">find them online</a>, along with <a href="https://chameleoncloud.org/experiment/share/">corresponding Trovi artifacts</a>, allowing you to reproduce their experiments. Also for SC’23, Chameleon was used to provide infrastructure to <a href="https://sc23.supercomputing.org/students/indyscc/">the 2023 Indy Student Cluster Competition</a>. This allows for students to participate in a HPC competition remotely, using provided for hardware</p>

<p><b>Virtual Reproducibility hackathon</b>. On December 15, we are hosting a <a href="https://chameleoncloud.org/blog/2023/11/13/announcing-virtual-reproducibility-hackathon-december-15th-2023-hold-the-date/">virtual reproducibility hackathon</a>! If you are interested in creating an artifact that enables people to run your experiment with one-click on Chameleon, you may be interested in participating. The first part of this hackathon will be an introduction to Chameleon and the reproducibility tools that we have, and then there will be an open office hours time, where we will be standing by to help. Check out <a href="https://chameleoncloud.org/blog/2023/11/13/announcing-virtual-reproducibility-hackathon-december-15th-2023-hold-the-date/">the blog post</a> for more information.</p>

<p><b>Reservation resource reliability</b>. Since Chameleon is a shared environment, you must make reservations for resources before you can use them. This month, we worked to ensure there are fewer errors when your lease starts. Previously, users would see errors where reservations for IP addresses said the address was already allocated, but this issue should occur much less frequently.</p>

<p><b>CHI-in-a-box improvements</b>. CHI-in-a-box is the packaging which is used by Chameleon associate sites. For these site operators, we’ve now made doing maintenance on your nodes easier. We’ve updated the blazar reservation service so that hosts can be <a href="https://chameleoncloud.gitbook.io/chi-in-a-box/reference/resource-reservation#disabling-resources">marked as disabled</a>, preventing users from creating new reservations on it, while still allowing site admins to reserve and provision them. This can also be useful when retiring hardware, without impacting current users.</p>

<p><b>Appliance fixes. </b>Appliances on Chameleon refers to our set of OS images that can be used as a base for your experiments. This month, we’ve updated our CC-Ubuntu appliances to prevent issues detecting A100 GPUs, which has the added benefit of making your boot times a bit faster. Additionally, the serial console, accessed via the web dashboard, should be much faster. </p>

<p><b>JupyterHub. </b>Chameleon offers a JupyterHub environment, which lets you programmatically orchestrate resources on the testbed, using our python-chi library. We’ve updated our JupyterLab environment this month to fix an issue that prevented SSH Ubuntu 22 via python-chi. You may have seen in our outage earlier this month we migrated our JupyterHub service to a new host. Please let us know if you encounter any issues with service, or with anything on the testbed <a href="https://chameleoncloud.org/user/help/ticket/new/">via the help desk</a>.</p>

<p>Happy experimenting!</p>