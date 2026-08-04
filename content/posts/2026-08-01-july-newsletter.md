---
abstract: '<p>Great news on Chameleon! I hope everybody is enjoying the vacation –
  in the meantime, in the July edition of Chameleon newsletter we are looking for
  REU students, looking at 10 years of Chameleon in a paper just presented at PEARC''26,
  and hope to see you at the MERIF workshop – read on, if you would like to represent
  Chameleon as a user. Our changelog has important announcements of upcoming changes
  in how bare metal versus VM instances are managed, news of base Chameleon Infrastructure
  (CHI) upgrades, and resource discovery for VM flavors. It''s been a super busy and
  productive summer and as a result we have two important migrations ongoing: one for
  the resource discovery capabilities and one for bare metal vs VM management – make
  sure to familiarize yourself with the new ways of doing things because the old ones
  will go away at the end of the fall semester/quarter. Don''t forget that the Ponte
  Veccio nodes are available for limited time only – use them while you can!</p>'
authors: []
categories:
- Chameleon Changelog
- Featured
date: '2026-08-01'
featured: true
hide_image: false
image: 'https://chameleoncloud.org/media/filer_public/02/5b/025bf2c5-14bc-43e0-84a4-55a74d67aa79/hasmik-ghazaryan-olson-n_grr8c2emk-unsplash1.jpg'
related_posts:
- slug: chameleon-newsletter-changelog-june-2026
  title: Chameleon Newsletter & Changelog June 2026
- slug: chameleon-newsletter-changelog-may-2026
  title: Chameleon Newsletter & Changelog May 2026
- slug: chameleon-newsletter-changelog-april-2026
  title: Chameleon Newsletter & Changelog April 2026
slug: chameleon-newsletter-changelog-july-2026
subtitle: 'Welcome to the Chameleon July 2026 Newsletter!'
title: 'Chameleon Newsletter & Changelog July 2026'
---

Great news on Chameleon! I hope everybody is enjoying the vacation – in the meantime, in the July edition of Chameleon newsletter we are looking for REU students, looking at 10 years of Chameleon in a paper just presented at PEARC'26, and hope to see you at the MERIF workshop – read on, if you would like to represent Chameleon as a user. Our changelog has important announcements of upcoming changes in how bare metal versus VM instances are managed, news of base Chameleon Infrastructure (CHI) upgrades, and resource discovery for VM flavors. It's been a super busy and productive summer and as a result we have two important migrations ongoing: one for the resource discovery capabilities and one for bare metal vs VM management – make sure to familiarize yourself with the new ways of doing things because the old ones will go away at the end of the fall semester/quarter. Don't forget that the Ponte Veccio nodes are available for limited time only – use them while you can!

## Community News

**We are looking for REU students to work with us in the fall semester/quarter.** We are looking for a Research Experience for Undergraduates (REU) students to work on projects in AI-driven reproducibility and experiment design during the fall semester/quarter. Students can work remotely at a time commitment of roughly 10 hours a week: we find that this usually works well for students taking a normal load of classes. Candidates must be U.S. citizens, U.S. nationals, or U.S. permanent residents. If you are interested in advancing experimental methodology and reproducibility, please [fill out this expression of interest form](https://docs.google.com/forms/d/e/1FAIpQLSdUpmWIve5PY63W-oEVqHCv3HAVar2O4gwC1sfizYqmNUp5Bg/viewform).

**"10 years of Chameleon" paper.** This month we presented [a paper looking at the first ten years of Chameleon](https://chameleoncloud.org/media/filer_public/43/b3/43b348a7-c54e-4001-9216-634b8501e041/pearc26-15_4.pdf) – from when the project went into public availability in late July 2015 to the end of 2025. The paper discusses community growth, resource usage, and research impact of our community which, to date, collectively published and impressive [1,309 research publications](https://chameleoncloud.org/user/projects/chameleon-used-research/)! Please, keep the good news coming: we of course prefer if you can [acknowledge or cite the use of Chameleon in your papers](https://chameleoncloud.org/learn/frequently-asked-questions/#toc-how-should-i-cite-chameleon-) – but if you inadvertently forgot, you can also [attest that your publication used Chameleon](https://chameleoncloud.readthedocs.io/en/latest/user/project.html#manage-publications) in your research. In addition, the paper also makes available the methodology and tools we used to present [user data](https://github.com/ChameleonCloud/user_project_reports), [usage information](https://github.com/ChameleonCloud/usage-exploration), and [publication counts](https://github.com/ChameleonCloud/magpub) in the hopes of making it easier for similar systems to provide comparable evaluations. It is an interesting place to look if you want to understand how the system evolves, both in terms of operational metrics and in terms of community engagement. The paper was presented at the PEARC conference – the same conference (then known as XSEDE) during which we originally announced public availability of the system.

**The MERIF conference.** The Midscale Experimental Research Infrastructure Forum ([MERIF conference](https://merif.renci.org)) will be held September 29–30, 2026, in Washington, D.C. MERIF is a workshop that brings together operators, users, and researchers involved with experimental cyberinfrastructure to share best practices, identify emerging research needs, and strengthen the ecosystem of NSF midscale research infrastructures. As such, it may be of interest to Chameleon users – the organizers sponsor a selected group of attendees to travel; [to apply go to the workshop website](https://merif.renci.org). In addition, if you would like to represent Chameleon at this venue as a user, please reach out directly to Kate at [keahey@uchicago.edu](mailto:keahey@uchicago.edu) – we have one slot left!

## New Resources Reminders

If you are just coming back from vacation, a couple of new resource reminders:

**Ponte Vecchio (Intel GPU).** CHI@TACC has 2 new nodes with Intel Ponte Vecchio GPUs available for a limited time. These nodes have Intel Xeon Platinum 8468 CPUs, 1TB of RAM, and 4x Ponte Vecchio XT GPUs and may be of interest to anyone interested in experimenting with new accelerators or 128GB of VRAM. For more details, please see [our May newsletter](https://blog.chameleoncloud.org/posts/chameleon-newsletter-changelog-may-2026/).

**New site at CHI@NCAR.** A reminder that [**CHI@NCAR**](https://chi.hpc.ucar.edu/project/) is now a full Chameleon site, and we've got plenty of capacity there; if you have a large class coming up in Fall 2027, this site could be useful for spinning up large clusters.

## Changelog

**Coming Soon: VMs and Bare Metal together!** While most people use Chameleon for [bare metal](https://chameleoncloud.readthedocs.io/en/latest/technical/baremetal/index.html) at CHI@UC, CHI@TACC, or CHI@NCAR, we also have a separate site [KVM@TACC](https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/index.html) just for virtual machines. This month, we have been working on creating a site that allows you to provision both bare metal and virtual machines together, and will soon deploy this to CHI@TACC. This not only means you can use the same API to configure any instance type, but you can have VMs and bare metal instances on the same network, making it easier to, for example, set up a dedicated VM for storing your node's metrics or data. This has been a long standing request on the testbed. Before we deploy this, we wanted to share our plans so that you can prepare before things change too much.

The main change that you will notice is the [Horizon web GUI](https://chameleoncloud.readthedocs.io/en/latest/technical/gui/index.html). Instead of the "Compute" tab, there will be dedicated "Bare metal compute" and a "Virtual compute" tabs. To see your VM instances, you will need to go to the "Instances" entry under "Virtual compute"; to see your bare metal instances you will need to go to " bare metal". We've also moved around instance-type specific options, so security groups, which only work with virtual machines, now appear under "Virtual compute". The "Leases" page will live under each instance-type separately. "Create Lease" and "Launch Instance" will both show different options depending on the type of instance you have selected. At the moment, it won't be possible to create a lease for both a VM flavor and bare metal node at once via the GUI, you must make two separate leases instead. In our CLI or python-chi interfaces, nothing will change if you are only using one type of instance. If you are using both VMs and bare metal, you will see all servers and leases merged together. You will be able to take an existing script for orchestrating a KVM experiment, and run it at CHI@TACC just by changing the site name.

Though we are only planning to add VMs to CHI@TACC, you will notice some changes elsewhere on the testbed. This week, you'll see this first change on CHI@UC, wherein the web UI there will show "Bare metal compute" as described above, though no "Virtual compute" tab. Early this month, CHI@TACC will get both "Bare metal compute" and "Virtual compute". Some of the idle hypervisors from KVM@TACC will show up on CHI@TACC, along with the compute flavors (`m1.tiny` through `m1.xxlarge`). At this point you will be able to use VMs on CHI@TACC with the same process as you have been using at KVM@TACC, but with the perks of CHI@TACC, such as an [object store](https://chameleoncloud.readthedocs.io/en/latest/technical/swift/index.html), [file shares](https://chameleoncloud.readthedocs.io/en/latest/technical/shares/index.html), and layer 3 external connectivity with [fabnetv4](https://chameleoncloud.readthedocs.io/en/latest/technical/networks/networks_fabnet.html).

While KVM@TACC and CHI@TACC can both be used as normal for the fall semester, we'll be retiring KVM@TACC on January 15, 2027. No leases can extend beyond this date, and we recommend [migrating VMs to CHI@TACC](https://blog.chameleoncloud.org/posts/how-to-port-your-experiments-between-chameleon-sites/) ahead of time. We'll be moving hypervisors over from KVM@TACC to CHI@TACC to ensure there is sufficient capacity for VMs. For the Spring 2027 semester, you'll need to update any coursework that points to KVM@TACC and change it to CHI@TACC.

If you have questions about this process, or any concerns, please let us know as soon as possible via [the Help Desk](https://chameleoncloud.org/user/help/).

**Virtual machines in Resource Discovery.** In more VM news, we have virtual machines in our [new resource discovery UI](https://discover.chameleoncloud.org/)! Last month, we were excited to share our new interface which makes it easier to find hardware and see availability. This month, we've added VMs to this interface. You are able to see what flavors of VMs we offer, and filter based on your requirements, similar to the workflow for finding hardware that fits your needs. In this same interface you can see the availability of each flavor. You can now get to the new resource discovery from the dropdown menu. For now, we've also left in the link to the old resource browser, but after the fall semester we will only be supporting the new version. If you have any suggestions or feedback about this, we'd love to hear from you via [the Help Desk](https://chameleoncloud.org/user/help/).

**Openstack upgrades for CHI@UC and CHI@Edge.** Chameleon is built on OpenStack, which is open source software for running clouds. In order to better serve our community, we customize and extend many OpenStack services to support things like device and network reservations, and we package these extensions into [CHI-in-a-box](https://github.com/ChameleonCloud/chi-in-a-box/). As a result of being based on OpenStack, we also benefit from upstream upgrades to these cloud services, which help add stability and security. This month, we upgraded CHI@UC to OpenStack 2024.1, and over the next week we will continue the upgrade to version 2025.1. On August 11, we'll roll out this upgrade to CHI@NCAR, and then to CHI@TACC on August 18. Our edge site, CHI@Edge was recently updated to version 2023.1, and soon will follow suit with upgrades to 2025.1

**Multi-Tenant networking at CHI@NCAR.** Chameleon's newest site, [CHI@NCAR](https://blog.chameleoncloud.org/posts/chameleon-newsletter-changelog-april-2026/), now supports multi-tenant networking. This means that instead of having to use `sharednet1` for all of your experiments, you can [create your own networks](https://chameleoncloud.readthedocs.io/en/latest/technical/networks/networks_vlan.html) to isolate traffic, configure multiple interfaces, and more.
