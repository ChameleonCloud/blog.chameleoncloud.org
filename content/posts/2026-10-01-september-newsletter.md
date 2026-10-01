---
abstract: '<p>Great news from Chameleon! Our new site at NCAR just got even better
  with the addition of 5 NVIDIA Grace A02 nodes (to the 40 Zen 5 nodes), Trovi got
  better now linking artifacts with relevant papers and videos, and resource discovery
  got better with the addition of VM flavors.</p>'
authors: []
categories:
- Chameleon Changelog
- Featured
date: '2026-10-01'
featured: true
hide_image: false
image: 'https://chameleoncloud.org/media/filer_public/50/b2/50b28623-6af0-44c0-a8dc-6fdab4887e04/ante-hamersmit-5mhmfz_cmy-unsplash.jpg'
related_posts:
- slug: chameleon-newsletter-changelog-august-2026
  title: Chameleon Newsletter & Changelog August 2026
- slug: chameleon-newsletter-changelog-july-2026
  title: Chameleon Newsletter & Changelog July 2026
- slug: chameleon-newsletter-changelog-june-2026
  title: Chameleon Newsletter & Changelog June 2026
slug: chameleon-newsletter-changelog-september-2026
subtitle: 'Welcome to the Chameleon September 2026 Newsletter!'
title: 'Chameleon Newsletter & Changelog September 2026'
---

Great news from Chameleon! Our new site at NCAR just got even better with the addition of 5 NVIDIA Grace A02 nodes (to the 40 Zen 5 nodes), Trovi got better now linking artifacts with relevant papers and videos, and resource discovery got better with the addition of VM flavors.

## Testbed Announcements and Reminders

Everywhere you look on the platform, things are getting better with new hardware and new features – but most importantly, the company now got much better with many users returning given that the quarter as well as the semester are now in full swing. Warm welcome to all our users coming back! To welcome you back here is a quick summary of the most important additions and changes.

**Feature migration.** We got a new resource discovery interface (as well as new resources, see below) – that now works for VM flavors as well as bare metal nodes. And that is not all – our site services now also work for both VMs and bare metal instances (see last month's changelog) so you can now more easily construct experiments that contain a mix of bare metal and virtualized instances. But there is a CATCH: for the next few months we will support both the old and new versions of resource discovery and service to allow time for migration but make sure to familiarize yourself with the new ways of doing things because the old ones will go away at the end of the fall semester/quarter. And once they are gone, they are gone.

**New hardware.** First, have a new site in [**CHI@NCAR**](https://chi.hpc.ucar.edu/project/) – we encouraged you to grab those instances before they were gone in the newsletter last month – and we can see that you read it! So we just added some more – of the GPU variety – read about it in the changelog below. Again, we do also have two new **Ponte Vecchio (Intel GPU)** nodes at CHI@TACC on loan for a limited time – did anybody read about that? I think they did! If you need any help, [let us know](mailto:help@chameleoncloud.org). If you need more hardware on Chameleon, please let your NSF program officer know!

**Join the Chameleon team.** We wrote about this last month so this is just a reminder: we are currently interviewing both for a [Chameleon staff member](https://uchicago.wd5.myworkdayjobs.com/External/job/Illinois-Chicago/Cloud-Computing-Developer_JR35029) at UChicago and [REU students](https://blog.chameleoncloud.org/posts/chameleon-reu-openings-fall-2026/) to work at a time commitment of roughly 10 hours a week in the fall semester/quarter. REU Candidates must be U.S. citizens, U.S. nationals, or U.S. permanent residents. Both positions are geared to helping us take the system to the next level and harness the power of AI to build a to make computer science experimentation better. If this is something you are interested in, it is not too late to let us know!

## Testbed Acknowledgement

This is very important so I will send out a separate message about that later: if you used Chameleon for your research, please do not forget to acknowledge this in your publications. As most of you know, we are very proud to serve a community that produces groundbreaking research, we track it, and [we showcase it on our web page](https://chameleoncloud.org/user/projects/chameleon-used-research/) – but this is not the only reason. NSF uses this information to assess the research impact of their investment so the more we can point to research produced using Chameleon resources, the better the demonstration of community impact, and the greater the likelihood that the system will be extended and continues to serve you in the future.

The best way to acknowledge the use of Chameleon is to simply state it in the text of your publication and [reference the platform](https://chameleoncloud.org/about/papers-and-tech-reports/#main-reference); this typically means that we will be able to eventually find it through research databases like scopus or search engines like google scholar. Another possibility is to reference Chameleon in the text or acknowledgement section of the paper without referencing the platform; this makes it harder to find but when we do find it, it is clear from the publication that the platform was used.

However, if for any reason you forgot to explicitly acknowledge the system directly in any of your publications, don't worry – you can still tell us about it via [the attestation process](https://chameleoncloud.readthedocs.io/en/latest/user/project.html#manage-publications). You can easily do it in two steps:

- Check if all your publications that used Chameleon resources have been reported to us. You can do this by accessing [your dashboard](https://chameleoncloud.org/user/projects/publications/) (first option in the drop down menu when you click on your name in the top right corner after logging in) and then clicking the publication tab. You will see a list of all your publications that were produced using the system – that we know of. If, after reviewing this list, you find that some publications are missing, we would appreciate it very much if you could add them by clicking the blue "add publication" button.
- The add publication button will guide you [to a page](https://chameleoncloud.org/user/projects/add/publications/) where you can report the publications as bibtex entries (multiple entries are supported) and will then ask you to explicitly attest that they were produced using Chameleon.

As you are embarking on a new academic year, we would greatly appreciate it if you could take the time to review this list briefly and add whatever publications are missing.

## Chameleon Events in October

**Chameleon tutorial at PACT 2026.** [The International Conference on Parallel Architectures and Compilation Techniques (PACT)](https://pact2026.github.io/index) is coming to Chicago this year and we will present [a live Chameleon tutorial](https://pact2026.github.io/workshops/chameleon-tutorial/) at the conference on October 19th in the afternoon. This is a great opportunity to meet members of the Chameleon team in person and learn about the system, whether you are a new user or a Chameleon veteran. We invite all our users in Chicago to come and say hello! Look for details in our [announcement](https://blog.chameleoncloud.org/posts/chameleon-tutorial-at-pact-2026/).

## Changelog

**GH200s at CHI@NCAR!** As (we hope) everybody knows by now, CHI@NCAR is now a Chameleon [core site, launched back in April](https://blog.chameleoncloud.org/posts/chameleon-newsletter-changelog-april-2026/) with 40 new Compute Zen 5 nodes. This month, the site has added 5 NVIDIA Grace A02 nodes, each with an NVIDIA GH200 Grace Hopper superchip. The GH200 pairs a Grace CPU and a Hopper GPU connected over by NVLink-C2C, a high-bandwidth link that allows the CPU and GPU to share a unified memory space. These nodes also have 480GB of memory, 2x100Gbps network interfaces, a 2TB SSD, and a 1TB NVMe drive. To make using these nodes easier, we've created the OS image `CC-Ubuntu24.04-CUDA-ARM64`, which is our ARM Ubuntu 24.04 image with CUDA preinstalled. If you have not tried the new Chameleon site yet, this is the time!

**Embedded Videos, Publications, and Comments in Trovi.** Trovi is our sharing portal, which lets you share digital artifacts with other users. Since some of our users have been pointing out for some time now that it would be good to associate the artifacts with relevant information, such as the paper in which the packaged result was published, or video of a demo or a presentation of the artifact. We have therefore extended Trovi so that you can embed a video after your artifact's description or add publication metadata if your artifact is featured in a publication. For more information on updating these, [see our docs](https://chameleoncloud.readthedocs.io/en/latest/technical/experiments/index.html). This month, we also added comments to artifacts, allowing you to reach out to an author with questions or feedback – or compliments! – or share tips for running the experiment with other users. As always on Chameleon, we trust that our users will observe code of conduct which is to be respectful to others. At the moment, users will not be notified via email of new comments or replies, but based on your feedback we may extend comments with this and more in the future. For more information, [see our docs](https://chameleoncloud.readthedocs.io/en/latest/technical/experiments/browsing_artifacts.html#commenting-on-artifacts) and, as always, please give us feedback via the helpdesk.

**CHI@TACC VMs in the Resource Discovery.** Last month, we were thrilled to announce that [CHI@TACC now supports VM and bare metal instances](https://blog.chameleoncloud.org/posts/chameleon-newsletter-changelog-august-2026/) through the same interface. This month, we've added VM flavors to our new [Resource Discovery interface](https://discover.chameleoncloud.org/), which lets you see exactly how many VMs of each flavor can be reserved at any time. This interface will replace the [old hardware browser](http://chameleoncloud.org/hardware/) and [availability calendars](https://chameleoncloud.readthedocs.io/en/latest/technical/reservations/gui_reservations.html#the-lease-calendars) in January, at which point we will also be [retiring the KVM@TACC site](https://blog.chameleoncloud.org/posts/chameleon-newsletter-changelog-july-2026/#changelog) in favor of the CHI@TACC VMs, so please if you have any questions or feedback about this process let us know.

**Improved Jupyter auth and load time.** This month, we've improved our [shared jupyterhub service](https://chameleoncloud.readthedocs.io/en/latest/technical/jupyter/index.html). This interface comes preconfigured with python libraries and CLI tools for interfacing with Chameleon, and your credentials will be automatically configured in this environment. We fixed an issue where credentials would not be refreshed properly after logged in, and you were required to manually re-authenticate. Additionally, an issue where poor I/O performance contributed to very long load times when starting jupyter environments. Thanks to power user Fraida Fund for solving this issue!
