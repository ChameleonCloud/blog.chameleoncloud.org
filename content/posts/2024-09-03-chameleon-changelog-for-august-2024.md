---
abstract: "<p>This month, we are excited to announce GigaIO nodes at TACC, the OpenStack\
  \ Antelope upgrade at TACC and an upgrade guide for associate sites, and a new associate\
  \ site CHI@NRP. Additionally, we finally have Raspberry Pi 5 support for CHI@Edge.\
  \ There is also a brand new Trovi dashboard (under preview). And we also improved\
  \ the reliability of phase 2 nodes at CHI@UC.<br>\n\_</p>"
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2024-09-03 21:22:02+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/e9/00/e9003369-18e4-4ced-8604-a10e7d6fa2c7/dsc00537_1.jpg
related_posts: []
slug: chameleon-changelog-for-august-2024
subtitle: ''
title: Chameleon Changelog for August 2024
---

<p style="text-align: center;"><img height="500" media="" src="https://chameleoncloud.org/media/filer_public/e9/00/e9003369-18e4-4ced-8604-a10e7d6fa2c7/dsc00537_1.jpg"><br>
<em>The Antelope upgrade spreads to more Chameleon sites</em></p>

<p>Dear Chameleon Users,</p>

<p>This month, we’ve been very busy with changes on the testbed as we prepare for the next phase of Chameleon to begin soon.</p>

<p><b>GigaIO at CHI@TACC. </b>In June, we added <a href="https://chameleoncloud.org/blog/2024/08/19/composible-hardware-on-chameleon-now/">new composable GigaIO hardware</a> to CHI@UC, and this month we are excited to announce 6 more GigaIO nodes on CHI@TACC. These nodes have Intel Xeon Platinum 9390 CPUs and 256 GB RAM. Additionally, this set of nodes have 4 recomposable A100-class PCIe GPUs, which can be reconfigured between nodes, you can find more information about the static configurations in <a href="https://chameleoncloud.org/hardware/">the hardware browser</a>. If you are interested in reconfiguring these nodes, <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/reservations.html">after making a reservation</a> for all the resources you will need, please <a href="https://chameleoncloud.org/help">submit a help desk ticket</a>, and Chameleon operators can recompose the resources once your lease begins.</p>

<p><b>Antelope Upgrade at CHI@TACC and Guide for Associate Sites.</b> Last month, we upgraded OpenStack at CHI@UC to Antelope, and this month, we upgraded CHI@TACC and wrote <a href="https://github.com/ChameleonCloud/chi-in-a-box/blob/stable/2023.1/docs/xena-antelope-upgrade.md">the official Antelope Release Notes and upgrade guide</a> for CHI-in-a-box site operators. This guide will enable associate sites, like CHI@EVL and CHI@NCAR to upgrade to the new Antelope release. New sites don’t need to follow the upgrade guide, since they’ll “start afresh” with Antelope, but may still find the release notes of interest.</p>

<p><b>New Associate Site CHI@NRP.</b> We are also excited this month to announce a new associate site, <a href="https://chi.nrp.ai/project/">CHI@NRP</a>. Right now, it only has 3 Haswell nodes online, but we’re working to bring some of NRP’s other nodes online, which will have a focus on the ESnet SmartNIC U55C, Nvidia A100 GPUs, Xilinx SN1000 FPGA, and Nvidia/Mellanox Bluefield2 NIC. We’ll make a separate announcement when those become available.</p>

<p><b>CHI@Edge Support for Raspberry Pi 5. </b>If you are interested in experimenting with edge computing, I am sure you know about <a href="https://chameleoncloud.gitbook.io/chi-edge">CHI@Edge</a>, which allows you to orchestrate deployments over edge and cloud resources using a familiar Chameleon interface for both. CHI@Edge allows you to  experiment with Raspberry Pi 4s and Jetson Nanos provided by Chameleon – or, if you have edge hardware of your own, you can also use our Edge SDK to <a href="https://chameleoncloud.gitbook.io/chi-edge/device-enrollment/edge-sdk">enroll your devices into the testbed</a>, either for private or public use. This month, we added support for <a href="https://chameleoncloud.gitbook.io/chi-edge/device-enrollment/edge-sdk">Raspberry Pi 5 devices in our Edge SDK</a>, meaning if you have new Raspberry Pis, you’ll be able to enroll and experiment with these too. We are also planning on getting some of these devices for our own deployment in Chameleon 4 as well, so stay tuned!</p>

<p><b>New Trovi Dashboard Preview</b>. We are committed to improving <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/sharing.html">Chameleon’s experimental artifact repository, Trovi</a>, over the next phase of the testbed. This month, we are excited to announce a preview of a <a href="https://trovi.chameleoncloud.org/dashboard/">new dashboard</a>, which seeks to modernize the Trovi frontend and integrate many requested improvements from our users. Please, note that this is just a preview so please continue using the existing Trovi dashboard for any serious work. For now, the preview only allows you to browse artifacts and search for ones related to your work and not create or edit them – it’s purpose is to provide a taste of what things might look like in the future and solicit your feedback on the general design while we can still make changes relatively easily – so please don’t be shy and let us know <a href="https://chameleoncloud.org/help">via the help desk</a> how you like it. We are counting on your assessment, it’s always been a partnership!</p>

<p><b>Phase 2 node fixes at CHI@UC. </b>Over the past few weeks, you may have seen unreliability and slow provisioning of some of the Phase 2 nodes at CHI@UC, such as the RTX6000 and Skylake nodes. This was due to a bad interaction between older network card firmware and newer versions of <a href="https://ipxe.org/">ipxe</a>, which we use for bare-metal provisioning after the Antelope upgrade. All of these nodes (aside from a few that have been in continuous use) have now had their network firmware updated, and been converted from BIOS-&gt;UEFI boot mode, and we’ve seen their boot times improve by more than 5 minutes.</p>

<p> </p>

<p>In circuits and code, our progress unfolds </p>

<p>New features emerge, as the future beholds </p>

<p>Chameleon adapts, with each passing day, </p>

<p>Empowering research in every way!</p>

<p> </p>

<p>Happy experimenting!</p>