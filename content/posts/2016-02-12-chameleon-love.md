---
abstract: '<p>Happy Valentine''s Day from Chameleon!</p>


  <p>To celebrate we have a bouquet of new capabilities for our users!</p>'
authors:
- Kate Keahey
categories:
- Announcements
date: '2016-02-12 18:03:54+00:00'
featured: false
hide_image: true
image: ''
slug: chameleon-love
subtitle: ''
title: From Chameleon, with Love
---

<p><img alt="" src="https://www.chameleoncloud.org/media/uploads/2016/02/13/chameleon-s3olo-v1-medium.png"></p>

<p>We love our users! That’s why for the last few months we have been working on a Valentine. Not the pretty picture – rather, we’d like to lay at your feet a bouquet of new capabilities that we hope will make your research easier and more productive. These include:</p>

<p>-    Support for custom kernel boot. You can now easily customize the operating system kernel or modify the kernel command line in your experiments! While it was possible (just barely) to boot from a custom kernel before, it was also inefficient and slow for those of you who needed to do it repeatedly: each time, a user had to upload a new image with the customized kernel to the repository and then boot from that image; both time-consuming operations. You now have the option of modifying the boot loader configuration to point it to a new kernel on the local disk, or specifying kernel parameters and then rebooting using this modified configuration. This will make updates to the kernel take effect quickly and means that experiments requiring kernel development will be much easier to run. If you are not working with kernels, you will see no changes in how images are deployed. However, we have had to change image format of bare-metal images (from partition images to whole disk images) as well as <u><a href="https://www.chameleoncloud.org/docs/user-guides/ironic/#snapshotting_an_instance">image snapshotting instructions</a> to make this happen</u>. To minimize the impact on you, we have converted all of the images supported by Chameleon and as many of the user images as we could; in order to convert others we may need to work with you on Monday (note, that your existing images have been renamed with a “.partition” suffix). To find out more, please read <a href="https://www.chameleoncloud.org/docs/user-guides/bare-metal-user-guide/#toc-kernel-customization"><u>our bare metal user guide</u></a>. We would like to thank our users <a href="http://www.mcs.anl.gov/~perarnau/"><u>Swann Perarnau</u></a> of Argonne National Laboratory and <a href="http://people.cs.pitt.edu/~yuyuzhou/"><u>Yuyu Zhou</u></a> of the University of Pittsburgh for helping us define the details of this capability and working with us to test and validate them!</p>

<p>-    Upgrade to Liberty. The OpenStack deployment which is a core component of CHI (Chameleon Infrastructure) has been upgraded to the most recent Liberty release. This upgrade not only facilitated the development of support for custom kernel boot, but also added multiple usability features, such as the ability to edit compute image metadata from the project dashboard or the ability to deactivate an image, improved error messaging, improved performance of many components, and added administrative features that will allow us to make Chameleon operate more smoothly.</p>

<p>-    Appliance Marketplace. The appliance marketplace allows you to discover, publish, and share appliances – bare metal or virtual machine images capturing the experimental environment – a key element of reproducibility. The initial version of the Appliance Marketplace announced in our New Year’s message was simply a static table of initial appliances provided and supported by the Chameleon team. The new Appliance Marketplace allows you to publish and share your own appliances so that others can discover them and easily play with the software and tools you developed. They can then use it either to reproduce the research of others or as a starting point for their own research and experimentation. To find out more, please read the <a href="https://www.chameleoncloud.org/docs/user-faq/#toc-appliances"><u>appliance documentation on our FAQ</u></a>. We would like to thank <a href="http://www.bsc.es/computer-sciences/grid-computing"><u>Rosa M. Badia and her team</u></a> of the Barcelona Supercomputing Center for motivating us to provide this capability sooner rather than later and for contributing the first external appliance representing <a href="http://compss.bsc.es"><u>COMPSs</u></a>, a task based programming model for distributed platforms!</p>

<p>-     Identity-based federation with <a href="http://www.geni.net"><u>GENI</u></a>. For some time now, GENI users have been able to access Chameleon by using their GENI credentials and charging to the GENI Federation Project. Now Chameleon users will be able to use their Chameleon credentials to access GENI without having to create a GENI account! This will enable multiple additional advanced research projects. To find out more, please read our <a href="https://www.chameleoncloud.org/docs/user-faq/#toc-what-infrastructures-is-chameleon-federated-with-">FAQ on GENI federation</a>. We would like to thank <a href="http://www.geni.net/?page_id=1927"><u>Tom Mitchell</u></a> and <a href="http://www.geni.net/?page_id=2080"><u>Marshall Brinn</u></a> of BBN on the GENI team for working with us to make this possible!</p>

<p>As most of you already know, these upgrades have already been applied at the University of Chicago site, and will be applied at TACC at the scheduled downtime next week.</p>

<p>We hope that these new features will reduce the time you spend wrangling logistics and put it back where it belongs: into your research. Thank you to all for sharing your requirements with us and inspiring us to make Chameleon a better testbed!</p>

<p>If you find Chameleon useful for your research, send us a Valentine at <a href="mailto:users@chameleoncloud.org"><u>users@chameleoncloud.org</u></a>! Here’s what we would like: a story of how you are using Chameleon for your research. Those stories are motivating not only to us in that they make us build a better testbed – but also to others who may get good ideas from your work on how to structure their own experiments. To encourage this sharing of experiences, we plan to highlight interesting research projects done by our users on the Chameleon portal as we have recently done with <a href="https://www.chameleoncloud.org/news/research-highlight-circumventing-cyber-attacks/"><u>the story on cybersecurity research</u></a>. In short, we’d like to challenge you to be an inspiration to others: if you have interesting stories to share, email them to <a href="mailto:users@chameleoncloud.org"><u>users@chameleoncloud.org</u></a>!</p>

<p>Happy Valentine’s Day!</p>

<p><br>
 </p>