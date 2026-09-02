---
abstract: '<p>Fantastic news on Chameleon: our users are back in force – welcome to
  the new academic year! In the August newsletter we are looking for REU students,
  looking forward to meeting at least some of you at multiple upcoming research events,
  and looking after your needs in the changelog announcements. In particular, one interface
  for bare metal and VMs has finally landed – as have OpenStack upgrades!</p>'
authors: []
categories:
- Chameleon Changelog
- Featured
date: '2026-09-02  00:00:00+00:00'
featured: true
hide_image: false
image: 'https://chameleoncloud.org/media/filer_public/0d/5e/0d5e685b-0691-4476-bfd4-c24a06304c0c/pierre-bamin-k3qqlulqvvg-unsplash.jpg'
related_posts:
- slug: chameleon-newsletter-changelog-july-2026
  title: Chameleon Newsletter & Changelog July 2026
- slug: chameleon-newsletter-changelog-june-2026
  title: Chameleon Newsletter & Changelog June 2026
- slug: chameleon-newsletter-changelog-may-2026
  title: Chameleon Newsletter & Changelog May 2026
slug: chameleon-newsletter-changelog-august-2026
subtitle: 'Welcome to the Chameleon August 2026 Newsletter!'
title: 'Chameleon Newsletter & Changelog August 2026'
---

Fantastic news on Chameleon: our users are back in force – welcome to the new academic year! In the August newsletter we are looking for REU students, looking forward to meeting at least some of you at multiple upcoming research events, and looking after your needs in the changelog announcements. In particular, one interface for bare metal and VMs has finally landed – as have OpenStack upgrades!

## Testbed Announcements and Reminders

To all of you who are coming back from vacation – welcome back! We will post a blog about all the things that changed this summer later this month but here is an overview of the most important additions:

**New features.** We got a [new resource discovery interface](https://discover.chameleoncloud.org/) and today we are also announcing a unified interface for VM and bare metal management (see below in the changelog section). Both of these changes unlock new possibilities for how you can build your experiments but they change familiar interfaces. For the next few months we will support both the old and new interfaces at the same time to allow time for migration but make sure to familiarize yourself with the new ways of doing things because the old ones will go away at the end of the fall semester/quarter.

**New hardware.** First, have a new site in [**CHI@NCAR**](https://chi.hpc.ucar.edu/project/) and we've got plenty of capacity there (to which we will be adding soon) – grab those nodes before everybody else realizes they are there! Also we have a unique opportunity in that we have two **Ponte Vecchio (Intel GPU)** nodes at CHI@TACC on loan for a limited time. These nodes have Intel Xeon Platinum 8468 CPUs, 1TB of RAM, and 4x Ponte Vecchio XT GPUs; for more details, please see [our May newsletter](https://blog.chameleoncloud.org/posts/chameleon-newsletter-changelog-may-2026/). This is another "grab it while you can" opportunity!

## Join the Chameleon Team\!

**Opportunities for REU students to join the team in the fall semester/quarter.** If you like being a Chameleon user think how much you might like joining the team\! We are looking for a Research Experience for Undergraduates (REU) students to work on projects in AI-driven reproducibility and experiment design during the fall semester/quarter. Students can work remotely at a time commitment of roughly 10 hours a week: we find that this usually works well for students taking a normal load of classes.  Candidates must be U.S. citizens, U.S. nationals, or U.S. permanent residents. For details, see [our announcement](https://blog.chameleoncloud.org/posts/chameleon-reu-openings-fall-2026/). 

**Join the Chameleon team\!** And if you are looking for a more permanent position, we are also looking for a new team member who will help us take the system to the next level and harness the power of AI to build a better scientist. Check [our position posting](https://uchicago.wd5.myworkdayjobs.com/External/job/Illinois-Chicago/Cloud-Computing-Developer_JR35029) for details\! 

## Community News

**Reproducibility BOF at VLDB'26.** We invite all VLDB'26 attendees to join us for [an in-person BoF session](https://blog.chameleoncloud.org/posts/announcing-vldb-2026-bird-of-feather-bof-session-on-reproducibility/) to learn about packaging storage research experiments on Chameleon. We will discuss tools and services Chameleon provides to share experiments such as [Chameleon daypass](https://blog.chameleoncloud.org/posts/interactive-science-made-easy-with-chameleon-daypass/), and [Trovi](https://trovi.chameleoncloud.org/dashboard/), our sharing portal for digital research and education artifacts. The BOF will take place on **September 3, 2026 (15:45 - 17:15) at the STONE room**. For details, please see the [conference program](https://vldb.org/2026/program.html) or [our blog](https://blog.chameleoncloud.org/posts/announcing-vldb-2026-bird-of-feather-bof-session-on-reproducibility/).

**Chameleon and other experimental resources at MERIF.** The Midscale Experimental Research Infrastructure Forum ([MERIF conference](https://merif.renci.org)) will be held September 29–30, 2026, in Washington, D.C. MERIF is a workshop that brings together operators, users, and researchers involved with experimental cyberinfrastructure to share best practices, identify emerging research needs, and strengthen the ecosystem of NSF midscale research infrastructures. Chameleon will be represented by multiple users discussing both research and education projects on the system. For details, see the [workshop website](https://merif.renci.org).

**Chameleon tutorial at PACT 2026.** [The International Conference on Parallel Architectures and Compilation Techniques (PACT)](https://pact2026.github.io/index) is coming to Chicago this year and we will present [a live Chameleon tutorial](https://pact2026.github.io/workshops/chameleon-tutorial/) at the conference on October 19th in the afternoon. This is a great opportunity to meet members of the Chameleon team in person and learn about the system, whether you are a new user or a Chameleon veteran. We invite all our users in Chicago to come and say hello! Look for details in our [announcement](https://blog.chameleoncloud.org/posts/chameleon-tutorial-at-pact-2026/).

## Changelog

**One interface for VMs and bare metal.** [Last month](https://blog.chameleoncloud.org/posts/chameleon-newsletter-changelog-july-2026/#changelog), we announced an important change: VMs and bare metal experiments at the same site. For those of you just starting on the system, previously we had a situation where bare metal at TACC and VMs at TACC were treated as two distinct sites – now both virtualized and bare metal instances are available through the same interface and TACC is treated as one site. This means that you not only can provision either type of instance through the same API, you can now use VMs with the CHI@TACC [object store](https://chameleoncloud.readthedocs.io/en/latest/technical/swift/index.html), [file shares](https://chameleoncloud.readthedocs.io/en/latest/technical/shares/index.html), and layer 3 external connectivity with [fabnetv4](https://chameleoncloud.readthedocs.io/en/latest/technical/networks/networks_fabnet.html). The process for working with VMs [via the CLI](https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_cli.html) or [python-chi](https://trovi.chameleoncloud.org/dashboard/artifacts/48c7e345-e27e-4717-9459-d0e19743622c) is the same as the current KVM@TACC workflow – but with [the web GUI](https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_gui.html), you will notice a new tab "Virtual Compute," which is where you can reserve a flavor and launch VM instances. Currently, CHI@TACC only supports compute VMs, AKA the flavors prefixed with "m1" from KVM@TACC. We'll be slowly moving over the existing KVM@TACC hypervisors through January 15, at which point we are fully retiring the KVM@TACC.

**Openstack upgrade for CHI@NCAR and CHI@TACC.** If you are a veteran Chameleon user, you already know that OpenStack is the mainstream open source software powering Chameleon. [Last month](https://blog.chameleoncloud.org/posts/chameleon-newsletter-changelog-july-2026/), we announced that we upgraded CHI@UC to OpenStack version 2025.1, and this month, we are excited to bring these updates to both CHI@NCAR and CHI@TACC. These updates bring important security and stability improvements, at the cost of some short time instability as we were working through a few kinks. Those adventures should now be mostly behind us though as always let us know if you see something amiss.

**ARM Thunder back and improved uplink at CHI@NCAR.** This month, 4 [ARM ThunderX2 nodes](https://blog.chameleoncloud.org/posts/chincar-an-interview-with-the-newest-associate-site/) are back online at CHI@NCAR. These nodes were taken offline for maintenance, and have been down since the installation of the 40 AMD EPYC nodes at the site, but now are back. These nodes have 2x Marvell ThunderX2 CN9980 32-core ARM processors, and 256 total threads, 126GiB of RAM, and 4x 2TB HDDs. Additionally, CHI@NCAR now is connected via a 100G network uplink. While the current nodes have 25G NICs, this uplink is shared between all nodes at the site, and is the fastest out of any Chameleon site.

**Improvements to Trovi.** [Trovi](https://trovi.chameleoncloud.org/dashboard/) is Chameleon's repository of digital artifacts. To date, users have shared over 460 artifacts, including reproducible experiments, educational modules, examples, and more. This month, we fixed an issue where you would always be directed to the dashboard login page if you weren't logged in. This made it more difficult to view public artifacts, especially for people who haven't used Chameleon. Additionally, we fixed an issue with how Trovi metrics are tracked when versions are deleted. We track when users launch and run an artifact in our [Jupyter environment](https://chameleoncloud.readthedocs.io/en/latest/technical/jupyter/index.html). These metrics were tied to the specific artifact version that was launched. If that version was deleted by the author, the metrics tied to it were also deleted. Now, we keep these metrics tied to the artifact, so they persist even if the version is deleted.
