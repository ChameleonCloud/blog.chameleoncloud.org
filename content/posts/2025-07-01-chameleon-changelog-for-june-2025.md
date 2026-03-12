---
abstract: "<p>This month we have changes to KVM@TACC that allow you to launch any\
  \ VM flavor from a reservation, which soon will be required. In a few months, we\u2019\
  ll shut down VMs that aren\u2019t from a lease, so make sure to check out the details!\
  \ We\u2019ve extended python-chi with better support for KVM, adding methods for\
  \ flavor reservation, managing security groups, and volumes.</p>"
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2025-07-01 21:48:52+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/41/9e/419e83b3-0ea2-4e51-80eb-03834ca59891/54555435914_a9c7057247_w.jpg
related_posts: []
slug: chameleon-changelog-for-june-2025
subtitle: ''
title: Chameleon Changelog for June 2025
---

<p style="text-align: center;"><img media="" src="https://chameleoncloud.org/media/filer_public/41/9e/419e83b3-0ea2-4e51-80eb-03834ca59891/54555435914_a9c7057247_w.jpg"></p>

<p style="text-align: center;"><a href="https://www.flickr.com/photos/rod_waddington/54555435914/in/photolist-2r7SSq3-2r5JBQA-2r5HNKY-2r5HNKh-2r41qAM-2qzKyRT-2r3ozWA-2r33xhd-2r2ja8b-2r27cwB-2r1qEyP-2r1vxHW-2r1bB5c-2r1hnpa-2r1hnpk-2qZs2ak-2qZrxNe-2qZs28w-2qZrcVp-2qYpZG9-2qYjqTi-2qXGRh5-2qWKktG-2qWKYtW-2qWJ4sy-2qWDEYQ-2qWKkog-2qWrJk8-2qVGvqf-2qVj6oo-2qTAyZQ-2qTsitA-2qTqfKA-2qTfmcj-2qS838v-2qRCvKv-2qRfHND-2qQQD9X-2qQJfif-2qPGwm6-2qPGqLp-2qPGqqj-2qPBR6v-2qPm35c-2qMLPjH-2qKDMps-2qKDMok-2qKyD7q-2qKuPmb-2qKpZgM"><em>Rod Waddington via Flickr</em></a></p>

<p>Dear Chameleon users,</p>

<p>This month we have lots of new things to discuss with KVM@TACC!</p>

<p><b>Upcoming changes to KVM@TACC</b>. <a href="https://chameleoncloud.org/blog/2025/06/02/chameleon-changelog-for-may-2025/">Last month</a>, we were thrilled to release new H100 nodes on KVM@TACC, and the ability to launch VM instances with GPUs, and we released a <a href="https://chameleoncloud.org/blog/2025/06/20/accelerate-your-research-with-nvidia-h100-gpus-on-kvmtacc/">comprehensive blog post on KVM</a>. At the same time we noted the  upcoming changes to our KVM offering that brings is into parity with bare metal: in other words, to use KVM instances you will need to make a lease first, the same way you do this for bare metal instances. The new hardware is already working this way – but now we will begin a process of migrating all the KVM instances to <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_gui.html#creating-leases-for-vms">the same modus operandi</a>. This month’s changelog contains more detail about this process.</p>

<p dir="ltr">Currently, you can launch both on-demand VMs (a VM not tied to a reservation), and VMs from a reservation. Starting August 1st, we’ll disable launching on-demand VMs entirely. Throughout the month of August, if your currently running instance was deployed using on-demand (as opposed to via the new reservation-based method), you will be able to manually tie it to a reservation <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_instance_migration.html#migrating-an-ad-hoc-kvm-instance-to-a-reservation">following this process</a>. You will want to do this because on September 1st, we’ll snapshot and delete all on-demand VMs. This means that if at that point one of your VM instances is not tied to a reservation it will be deleted. If you forget to migrate your instance to a reservation, you will still be able to restore your instance from the snapshot, the process for which is <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_instance_migration.html#restoring-from-a-snapshot">described in our docs</a> – but waking up to see your instances gone can be a nasty surprise so this is a heads-up: you can avoid it!</p>

<p><b>KVM support in python-chi.</b> Last month, we released a guide to using GPU instances using the web GUI. This month, we’ve updated python-chi with methods to support flavor reservation and a <a href="https://chameleoncloud.org/experiment/share/48c7e345-e27e-4717-9459-d0e19743622c">new Trovi artifact showing this off</a>. As we explained above, you’ll soon need to create a flavor reservation for all KVM instances, so even if you are just using normal compute VMs on KVM with python-chi, you’ll want to see <a href="https://chameleoncloud.org/experiment/share/48c7e345-e27e-4717-9459-d0e19743622c">our example</a> for what to change. We’ve also added methods for using <a href="https://python-chi.readthedocs.io/en/latest/modules/network.html#chi.network.list_security_groups">security groups</a>, making it easy to configure SSH access to your new instances.</p>

<p><b>Docs and python-chi support for KVM volumes</b>. Since VMs tied to reservations are ephemeral, requiring you to keep an active flavor reservation, we wanted to ensure that it is easy to save data persistently. This month, we’ve added a <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_volumes.html">new section to our docs</a> about using KVM volumes. These volumes allow you to add persistent storage devices to your instances. When your instance is deleted, the volume (and your data) will remain. Additionally, we’ve added support for <a href="https://python-chi.readthedocs.io/en/latest/modules/storage.html#chi.storage.Volume">volumes to python-chi</a>, and <a href="https://python-chi.readthedocs.io/en/latest/modules/server.html#chi.server.Server.attach_volume">new server methods for attaching the volume</a> to an instance. Examples of how to use these new methods are included in the new <a href="https://chameleoncloud.org/experiment/share/48c7e345-e27e-4717-9459-d0e19743622c">KVM GPU artifact</a>.</p>

<p>If you need any other features to make your experimentation better, please make sure to reach out and let us know!</p>

<p>Happy experimenting!</p>