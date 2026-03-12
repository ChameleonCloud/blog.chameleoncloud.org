---
abstract: "<p>Great news in Chameleon-land!</p>\n\n<p>We\u2019ve been busy in July\
  \ and added\_new hardware, support for whole disk image boot for ARM64 nodes, lease\
  \ end alerts and Bring Your Own Controller (BYOC) support at TACC!</p>\n\n<p>\_\
  </p>"
authors:
- Kate Keahey
categories:
- Chameleon Changelog
date: '2018-08-02 18:33:47+00:00'
featured: false
hide_image: true
image: ''
related_posts: []
slug: chameleon-changelog-july-2018
subtitle: ''
title: Chameleon Changelog for July 2018
---

<p>Great news in Chameleon-land!</p>

<p>We’ve been busy in July and have a few new features for you to try out: </p>

<p><strong>New hardware. </strong>A <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/swift.html">new object store service</a> is now available at University of Chicago! The new object store can be accessed via the OpenStack Swift interface and is currently backed by a 0.5PB Ceph storage cluster with double replication, providing an effective 0.25 PB for general use. Just as <a href="https://www.chameleoncloud.org/news/happy-independence-day-chameleon/">our object store at TACC</a>, the UC object store can be used from anywhere on the Internet – but users running experiments in UC may find it convenient to take advantage of it to reduce latency on storage operations. As a reminder, all appliances derived from Chameleon include a FUSE module that will <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/swift.html#mounting-object-store-as-a-file-system">help you to conveniently mount objects from the store</a>. </p>

<p><strong>Whole disk image boot support for ARM64 nodes.</strong> We now have whole disk image boot support for our ARM64 nodes. To make it easier to use we developed a <a href="https://www.chameleoncloud.org/appliances/35/">new appliance</a> for those nodes, based on Ubuntu 16.04, that includes specially prepared U-boot kernel is in the full-disk partition and provides the same features as our other Chameleon-supported appliances. You can collect <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/metrics.html#power-consumption-metrics-for-low-power-nodes">power consumption metrics</a> in the same way as you would for the Atom and low power Xeon nodes.</p>

<p><strong>Lease end alerts.</strong> We implemented a feature whereby <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/reservations.html#disable-blazar-notification">Chameleon can implement various actions</a> before a lease ends. In particular, by default it will send an email reminder to users 48 hours before their leases end (for leases whose duration is less than 48 hours an email will be dispatched immediately). As a reminder, any<a href="https://chameleoncloud.readthedocs.io/en/latest/technical/reservations.html#lease-policy"> lease can be extended within 48 hours of its expiration</a> if the resource has not been claimed by another user. This feature has been deployed a few days ago, so some of the users might already received notification emails about their existing leases! </p>

<p><strong>BYOC now available at TACC</strong>. In our <a href="https://www.chameleoncloud.org/blog/2018/07/02/chameleon-changelog-june-2018/">June Changelog</a> we announced the availability of the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/networks/networks_sdn.html#software-defined-networking">Bring Your Own Controller (BYOC)</a> feature at our University of Chicago site. We are happy to announce that now this feature is available at TACC as well! </p>

<p>As always, please let us know what you think. If you have questions or suggestions about any of these features, please leave a comment. </p>
