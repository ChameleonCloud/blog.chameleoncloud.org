---
abstract: <p>This month we announce some exciting improvements towards CHI@Edge 2.0,
  new hardware at Northwestern and with KVM, and improvements to CHI-in-a-Box!</p>
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2022-04-04 22:54:50+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/80/b7/80b7c541-1374-49ec-842a-19637afa0629/screen_shot_2022-04-05_at_95145_am.png
related_posts: []
slug: chameleon-changelog-for-march-2022
subtitle: ''
title: Chameleon Changelog for March 2022
---

<p style="text-align: center;"><b id="docs-internal-guid-0a5a4425-7fff-dc10-21a3-04175a439403"><img height="550" src="https://lh3.googleusercontent.com/gGEb4NdFWk8Y3pyiAboeawiNbMlrPpo_KlxqjyJ6z4hoAetysmrtoq75zZDTDldIq_xVqfn2Psp4HAcngDX3JKzBBuvPNeHxJFD1DYAoM05JD2ct-s04GQRY5rALlDo4y8eQ4F5D" width="453"></b></p>

<p>Dear Chameleon users,</p>

<p>No updates this month. </p>

<p>April fools! We have lots of updates, including some exciting news about CHI@Edge.</p>

<p><strong>CHI@Edge 2.0 News</strong>. Last month we announced an open enrollment preview for CHI@Edge 2.0, and we are now happy to announce another major step forward. At this time CHI@Edge 2.0 works with Raspberry Pis and Jetson Nanos. You can take a look at our <a href="https://chameleoncloud.org/experiment/chiedge/hardware-info/">Edge resource pool</a> for which devices are running the latest version use it today – or you can <a href="https://chameleoncloud.gitbook.io/chi-edge/device-enrollment/edge-sdk">use the SDK</a> to add your own Pi or Nano device to the testbed. You may notice other changes with version 2.0, such as faster container launches and a more stable web console. Devices can now communicate on their local networks, allowing traffic to pass between containers without going to the central site first. For a more complete list of differences, see <a href="https://chameleoncloud.gitbook.io/chi-edge/faq#what-is-the-difference-between-v1-and-v2-of-the-chi-edge-platform">this FAQ</a>. We are actively working on making 2.0 fully feature complete (see the FAQ mentioned for a status of feature completeness) and expect to accomplish it by the end of this month. Throughout this month, we will also be converting over devices in the Chameleon Edge device pool to the new version, and plan to deprecate 1.0 deployment by the end of the month – though as always let us know if this interferes with your plans. If you have any questions – please check out the <a href="https://groups.google.com/g/chameleon-edge-users">chameleon-edge-users</a> group.</p>

<p><strong>New hardware at Northwestern</strong>. This month, Northwestern increased their inventory, adding three new Haswell nodes. The original three CHI@NU nodes have Mellanox ConnectX-5 100GE cards, allowing for <a href="https://www.chameleoncloud.org/blog/2021/02/19/setting-associate-site-interview-northwestern-university/">100G networking experiments</a>. This additional hardware will allow for more experiments interacting with the specialized nodes. These new compute_haswell nodes were previously a part of the testbed at CHI@TACC.</p>

<p><strong>KVM SSD volume storage</strong>. <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm.html">KVM</a> SSD volumes can now be utilized to give your virtual machines faster storage. When creating a volume, you can select its type to be “ceph-ssd”, which will store your data on our faster SSD pool, which has a more limited capacity of 77 TiB, so please keep that in mind when creating very large volumes.</p>

<p><strong>CHI-in-a-Box usage reporting</strong>. For those of you who are tracking how CHI-in-a-Box is getting on, in this month’s update, we’ve added in usage reporting, which allows operators to monitor bare metal node usage across all Chameleon sites via our internal Grafana dashboard and the weekly KPI report emails.</p>