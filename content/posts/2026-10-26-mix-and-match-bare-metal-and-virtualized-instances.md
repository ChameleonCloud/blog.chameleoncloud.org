---
abstract: '<p>In our August Chameleon newsletter we announced a new feature: unified
  interface for VM and bare metal management, bringing our virtualized instances into parity with
  our bare metal offering, following on resource discovery for VMs. In this blog,
  we discuss the changes that this new feature will bring to your experimentation in
  practice.</p>'
authors:
- Kate Keahey
categories:
- Tips and Tricks
- Featured
date: '2026-10-26 14:00:00+00:00'
featured: true
hide_image: false
image:
related_posts:
- slug: bare-metal-or-kvm-which-should-you-choose-and-when
  title: Bare Metal or KVM? Which Should You Choose and When
- slug: experiment-pattern-bastion-host
  title: 'Experiment Pattern: Bastion Host'
slug: mix-and-match-combining-bare-metal-and-virtualized-instances
title: 'Mix and Match: Combining Bare Metal and Virtualized Instances in Your Experimentation'
---

In our [August Chameleon newsletter](https://blog.chameleoncloud.org/posts/chameleon-newsletter-changelog-august-2026/) we announced a new feature: unified interface for VM and bare metal management. This means that if a Chameleon site supports both bare metal and virtualized instances, they are now treated as one site instead of two separate sites. It follows a steady flow of new features that we introduced recently bringing virtualized instances on Chameleon into parity with our bare metal offering – following on [resource discovery for VMs](https://blog.chameleoncloud.org/posts/chameleon-newsletter-changelog-september-2026/), announced in September and [advance reservations and bounded leases](https://blog.chameleoncloud.org/posts/chameleon-changelog-for-july-2025/) announced in the July 2025 newsletter. In this blog, we discuss the changes that this new feature will bring to your experimentation in practice.

The fundamental change stems from the fact that VMs and bare metal instances are now on the same sharedwan, i.e., internal network. Among others, this means that instead of being routed out of the site and then back in, traffic between your VMs and bare metal instances is routed directly and thus more efficiently. Another big change this new configuration introduces is that VMs and bare metal instances are now part of the same experimental workflow which also reduces the complexity of creating an experiment that uses both. Bear those two in mind as we discuss their impact below.

If you mostly experiment on VMs, you have just hit a jackpot – by virtue of being on the same network as bare metal instances, you will now have access to features that historically were part only of bare metal sites. Specifically, you can now use the [object store](https://chameleoncloud.readthedocs.io/en/latest/technical/swift/index.html), which allows you to store large amounts of input or output data for your experiment. Further, you now can take advantage of layer 2 and layer 3 connections to FABRIC from your VM using [stitching](https://chameleoncloud.readthedocs.io/en/latest/technical/networks/networks_stitching.html) or [fabnetv4](https://chameleoncloud.readthedocs.io/en/latest/technical/networks/networks_fabnet.html). Not only could you use this to connect to FABRIC resources from your VM, but you can also use it to connect to Chameleon resources at CHI@UC or other sites over the FABRIC connection. Further, your VM experiment can now take advantage of [reservable IPs and networks](https://chameleoncloud.readthedocs.io/en/latest/technical/reservations/gui_reservations.html#creating-a-lease-to-reserve-resources), which also used to be the preserve of bare metal sites only. [File system shares](https://chameleoncloud.readthedocs.io/en/latest/technical/shares/index.html) can also now be used from your VM via a storage network reservation. These changes mean that it is now much easier to orchestrate your VM-based experiment with fewer edge cases – and importantly, you can now prototype on VMs and later switch to bare metal with almost no changes to your experiment packaging.

If you mostly experiment on bare metal, the advantages are somewhat fewer and more modest – since bare metal sites are the primary offering on Chameleon and therefore always had the best of everything. Previously, KVM@TACC was the only site running [Octavia](https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_lbaas.html), which is OpenStack’s load balancer as a service. This will be available for bare metal in the near future – we are working to configure this on CHI@TACC, which will mean that you can use your bare metal nodes in your load balancer pool. Unfortunately, bare metal instances still won’t work with [Cinder persistent volumes](https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_volumes.html) (I know), since these instances have no hypervisor to manage access to the volume – but keep reading because depending what you are working on, there may be a way around that.

The greatest advantage of this change however, is not so much adding new features to existing experiment patterns, as creating new patterns. The fundamental capability that this change created is **the ability to mix and match bare metal and virtualized instances easily, within one experimental workflow** -- important, since VMs are much more lightweight and take a smaller chunk of testbed capacity than bare metal. In other words, you can now use virtualized instances in lieu of bare metal ones whenever possible, saving both resource time – and your SUs. For example, let’s say you need to [create a bastion host](https://trovi.chameleoncloud.org/dashboard/artifacts/8e893a1e-4833-4a6b-b596-d046f12018ba) configuration  – there is no need to use a bare metal node as a bastion, you can use a VM, with no increase in experiment complexity or loss of efficiency.

And what of volumes? You can’t use them directly from bare metal, but you can now for example use Prometheus to export data from your experiment running on bare metal nodes to a data collection server set up on a virtualized instance connected to a Cinder volume allowing you to use volumes with your bare metal experimentation in practice – if somewhat indirectly. The same is possible in the opposite direction as well: if you have a volume with data that you want to use in your experimentation you can connect it to a VM and stream it from there (might be particularly useful for H100 experimentation).

All in all, we have been creating a lot of new options for your experimentation by steadily chipping away at the feature gap between our bare metal and virtualized offering of which this latest feature is the next installment. In fact, a year ago we published a blog on [when to choose VMs and when to choose bare metal](https://blog.chameleoncloud.org/posts/bare-metal-or-kvm-which-should-you-choose-and-when/) for your experimentation – many of the reasons we gave then – hardware discovery, support for advance reservations, and site configuration – were results of configuration decisions and given the latest innovations are no longer valid. Increasingly, the difference is the only one that it should be: the difference between whether your experiment really requires a bare metal node or whether it can get by with the cheaper virtualized instances.
