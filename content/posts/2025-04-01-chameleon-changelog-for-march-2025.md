---
abstract: "<p>This month, we have reminders for KVM@TACC and CHI@Edge outages later\
  \ this month. Additionally, we have version 1.1 of python-chi, and improvements\
  \ to reservations!<br>\n\_</p>"
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2025-04-01 21:52:45+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/5e/fd/5efde162-ee66-4918-bdb3-3d1de25dbdc2/54405141082_05f813a704_w.jpg
slug: chameleon-changelog-for-march-2025
subtitle: ''
title: Chameleon Changelog for March 2025
---

<p style="text-align: center;"><img media="" src="https://chameleoncloud.org/media/filer_public/5e/fd/5efde162-ee66-4918-bdb3-3d1de25dbdc2/54405141082_05f813a704_w.jpg"></p>

<p style="text-align: center;"><a href="https://www.flickr.com/photos/amy_bayer/54405141082/in/photolist-2qVj6oo-2qTAyZQ-2qTsitA-2qTfmcj-2qS838v-2qRCvKv-2qRfHND-2qQQD9X-2qQJfif-2qQiXQV-2qPGwm6-2qPGqLp-2qPGqqj-2qPBR6v-2qPm35c-2qMLPjH-2qKDMps-2qKDMok-2qKyD7q-2qKuPmb-2qKpZgM-2qJfS3s-2qCRKVv-2qCK4FS-2qCPDNF">Amy Bayer via Flickr</a></p>

<p>Dear Chameleon users,</p>

<p>We have been preparing for big upgrades this month on Chameleon. First, <a href="https://chameleoncloud.org/user/outages/kvm-disruptive-maintenance-april-10-2025/">all CHI@KVM instances will be rebooted</a> on the morning of April 10. Please ensure that any work is saved to the persistent storage before this time. This disruption will make it possible for us to continue with further KVM upgrades, as we are working on bringing GPUs to CHI@KVM. Additionally <a href="https://chameleoncloud.org/news/outages/chiedge-scheduled-maintenance-20250429/">CHI@Edge will be down</a> as we work on upgrades to add high availability to the system. Please make sure to plan accordingly.</p>

<p><b>Python-chi 1.1</b>. We are excited to announce python-chi 1.1. Last fall, we announced version 1.0 of our programmatic interface to Chameleon, known as <a href="https://python-chi.readthedocs.io/">python-chi</a>. This library allows you to use python scripts to orchestrate your Chameleon experiments. New in version 1.1, we’ve improved the support for CHI@Edge with this interface. This includes the ability to query the CHI@Edge hardware API via hardware.get_devices. When creating a Server, Lease, or Container, you can now specify a custom timeout, which may be needed if your lease starts in the future, or you are using a large container image. Additionally, we’ve added a retry_on_error parameter, which will automatically retry resource creation if an issue arises. We’ve also added better cleanup to IPs when you delete your server or container. </p>

<p><b>Reservation Bug Fixes</b>. We’ve improved an issue with our reservation service where if leases were back-to-back on a node, a race condition would cause the second lease to experience an error. Additionally, we improved the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/reservations.html#reallocating-a-node-in-your-lease">reallocate command</a> to prevent issues in the case where a second host couldn’t be found. Previously, nodes would be removed from your lease with no replacement, making the lease useless.</p>

<p>Happy experimenting!</p>