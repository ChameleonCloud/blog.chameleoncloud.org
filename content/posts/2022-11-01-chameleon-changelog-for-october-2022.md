---
abstract: "<p>Things were pretty scary yesterday but we managed to pull a few tricks\
  \ and bring you some new treats to enjoy in November! Between new Fugaku nodes,\
  \ the ability to experiment with SGX, and a better way to work with networking at\
  \ CHI@Edge, we hope to keep you busy and entertained this next month!<br>\n\_</p>"
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2022-11-01 22:12:06+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/e6/1e/e61e99b3-da9a-477a-9fc7-caaa6b3e9b0a/chameleon-pumpkin-medium.png
related_posts: []
slug: chameleon-changelog-for-october-2022
subtitle: ''
title: Chameleon Changelog for October 2022
---

<p><b id="docs-internal-guid-7c2835d7-7fff-0d4d-7275-03bb487464c2"><img height="286" src="https://lh4.googleusercontent.com/yLAHKG_XavvM7TmJIggmLO7XH2-eTku1Em-FoHAPurnIcPN3UcFJEx-5vWcaxaZpvGUN1JKf5IC7S6dB2N_idCUVUv2j7JPM5KNYYUxu0Y_HKqoecyUy9Z3zVMWuQDjgst3aJ8QTzmPBY-3V_dLh8UrDwqRe-4s-l5wa_JfnTMC4kReLz8w_36wqJQ" width="300"></b></p>

<p> </p>

<p>Dear Chameleon users,</p>

<p>In lieu of candy (which doesn’t travel well, we find), we have a cornucopia of new features for your enjoyment this month. </p>

<p><strong>Fugaku nodes at CHI@TACC!</strong> You may have caught our mid-month release of 8 <a href="https://chameleoncloud.org/blog/2022/10/19/fugaku-nodes-now-at-chitacc/">Fugaku nodes</a> at CHI@TACC. For those of you who don’t follow supercomputing news, <a href="https://www.fujitsu.com/global/about/innovation/fugaku/">Fugaku</a> is the <a href="https://www.top500.org/lists/top500/2022/06/">2nd fastest supercomputer</a> in the world. Like the supercomputer, these nodes have high-bandwidth memory, and aarch64 architecture – and now you too can experiment with them via our bare metal reconfiguration and see for yourself what makes them tick! Follow the directions from <a href="https://chameleoncloud.org/blog/2022/10/19/fugaku-nodes-now-at-chitacc/">our announcement</a> and tell us how it goes.</p>

<p><strong>Experiments using SGX.</strong> More hardware news! <a href="https://chameleoncloud.org/blog/2022/08/01/chameleon-changelog-for-july-2022/">In July</a>, we announced new IceLake nodes, additionally equipped with A100 GPUs,  at CHI@UC. These nodes are <a href="https://www.intel.com/content/www/us/en/architecture-and-technology/software-guard-extensions.html">Intel Software Guard Extension (SGX) compatible</a>, but it took us a little bit of back and forth to enable this feature SGX. This feature allows for hardware based memory encryption, which will hopefully allow whole new types of experiments to be run on Chameleon. If you are interested in using SGX, please try out the <a href="https://chameleoncloud.org/hardware/">A100 nodes</a>. As always, <a href="https://chameleoncloud.org/user/help/ticket/new/">let us know</a> if you experience any difficulties.</p>

<p><strong>Improved networking policies for CHI@Edge</strong>. Chameleon’s Edge testbed, CHI@Edge, supports <a href="https://chameleoncloud.gitbook.io/chi-edge/device-enrollment/edge-sdk">Bring Your Own Device</a> which allows anyone to enroll their own devices into the testbed. We’ve made some improvements to the networking of these devices. Previously, if you enrolled a device in CHI@Edge, containers on that device could send traffic to the local network the device is on, which presents a privacy risk if this is a shared network. Now, as the device owner, you can block the device from sending traffic to local IPs. For information on this setting, see our device enrollment documentation <a href="https://chameleoncloud.gitbook.io/chi-edge/device-enrollment/edge-sdk">here</a>.</p>

<p><strong>New CHI-in-a-Box release</strong>. The packaging of CHameleon Infrastructure, known as CHI-in-a-box, is what allows operators to run Chameleon associate sites, the latest being <a href="https://chameleon.cs.iit.edu/project/">CHI@IIT</a>. This month, we bring you a new release of CHI-in-a-Box, packed full of features. Firstly, CHI-in-a-Box now provides packaging of CHI@Edge v2 (i.e., the version supporting Bring Your Own Device), though without reservations at the moment. Another major addition was supporting Let’s Encrypt so that it can automatically reload SSL certificates when they renew. We also have Ironic hardware metrics in Prometheus + grafana to view things like power consumption, temperatures, and other metrics. Lastly, we’ve fixed issues with Doni tasks getting stuck “in progress”. You can find the release <a href="https://github.com/ChameleonCloud/chi-in-a-box/releases/tag/v2022-10.12">here</a>.</p>

<p><strong>BYOC is back at CHI@UC.</strong> The Bring Your Own Controller (BYOC) for SDN experimentation on Chameleon is working again at CHI@UC! Some of you may have noticed that BYOC hasn’t operated at either CHI@UC or CHI@TACC for a few months due to hardware issues with our Corsa switches. We’ve gotten it back into working order for one rack of Skylake nodes at UC. See our <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/networks/networks_sdn.html#chameleon-and-openflow">updated documentation</a> for information on how to use it.</p>

<p><strong>Upcoming Scheduled Maintenance</strong>. At the beginning of December, we are planning on another upgrade to our authentication service, which will require about 1 hour of time in which you will not be able to authenticate to Chameleon sites, portal, and Jupyter, though running experiments will be unaffected. We know there are many deadlines at this time of year as the academic semester comes to a close, so please let us know if there are any critical deadlines you have that this might interfere with, and we can try to find a time that works for us and our users.</p>

<p>Until next month! <br>
 </p>