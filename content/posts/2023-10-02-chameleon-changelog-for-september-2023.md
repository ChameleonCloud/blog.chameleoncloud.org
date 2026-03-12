---
abstract: "<p>This month, we ran a hackathon at IC2E, new devices at CHI@Edge, improved\
  \ CHI@Edge networking, and fixed issues with network leases, project management,\
  \ cc-snapshot, and Doni.<br>\n\_</p>"
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2023-10-02 21:48:56+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/c5/75/c575132d-315f-4f40-840b-2cf0f6686f07/sep_changelog.jpg
related_posts: []
slug: chameleon-changelog-for-september-2023
subtitle: ''
title: Chameleon Changelog for September 2023
---

<p style="text-align: center;"><img media="" src="https://chameleoncloud.org/media/filer_public/c5/75/c575132d-315f-4f40-840b-2cf0f6686f07/sep_changelog.jpg"><br>
<em>A Chameleon taking care of bugs</em></p>

<p>Dear Chameleon Users,</p>

<p>Last week, we hosted a reproducibility hackathon at <a href="https://conferences.computer.org/IC2E/2023/">IC2E 2023</a>, and were delighted to meet Chameleon users there. During the event, we presented on and worked with students to package artifacts for the <a href="http://chameleoncloud.org/experiment/share/">Trovi artifact repository</a>, which is a great way to share your experiment in such a way it can be run with one-click. We also encourage <a href="https://chameleoncloud.org/media/filer_public/25/18/25189b96-c3a2-4a55-b99b-c25322fe6682/reproducibility_on_chameleon-3.pdf">practical reproducibility</a>, meaning both the packaging and the reproduction of your experiment are cost-effect. If you are interested in learning more about this, see our <a href="https://www.youtube.com/watch?v=-kXNibXcC6U">webinar from last summer</a> or stay tuned for an upcoming virtual hackathon this winter. </p>

<p><b>CHI@Edge new devices and networking improvements. </b><a href="https://chameleoncloud.org/experiment/chiedge/">CHI@Edge</a> is a version of the testbed where you can experiment with smaller, edge devices like Raspberry Pis and Jetson Nanos, even allowing you to <a href="https://chameleoncloud.gitbook.io/chi-edge/device-enrollment/edge-sdk">bring your own device</a>. This month, we added 18 new Raspberry Pis to the testbed, and revived a few others which had been unavailable, so you should now have an easier time finding free devices to use, especially when the testbed is busy. CHI@Edge also allows you to send traffic between your containers on different devices, even if they’re in different locations, using a wireguard tunnel backend. These tunnels also allow you to connect Chameleon’s Floating IPs to your device, accessing your container via one of our Public IPv4 Addresses. We’ve also improved the reliability of this networking backend in the past month, so you should find those two features to be more dependable.</p>

<p><b>Network lease bug fixes. </b>Chameleon is a great place for networking experiments, with support for <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/networks/networks_vlan.html">isolated VLANs</a>, <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/networks/networks_stitching.html">layer 2 stitching</a> between sites or to <a href="https://fabric-testbed.net/">Fabric</a>, and for <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/networks/networks_sdn.html">software defined networking</a>. When creating an isolated VLAN or stitching to Fabric, you’ll first need to <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/reservations.html#creating-a-lease-to-reserve-a-vlan-segment">reserve a VLAN</a> with a lease. We fixed an error with these reservations where leases got stuck cleaning up. While primarily a cosmetic concern, it led to old leases lingering in your project, which no longer should occur.</p>

<p><b>Project management improvements.</b> Improvements to project management were made this month. The <a href="https://chameleoncloud.readthedocs.io/en/latest/user/project.html#manage-user-roles-pi-delegate">manager role</a> has been updated to also allow renewal of allocations, meaning if you're a graduate student with a busy PI, you can recharge your project. Additionally, we encourage you to <a href="https://chameleoncloud.readthedocs.io/en/latest/user/project.html#manage-publications">add publications to your project</a> that were completed with support from Chameleon, as this information is valuable when reporting the testbed's impact to the NSF. We've resolved an issue with the BibTeX submission to ensure accurate error messages are provided.</p>

<p><b>More testbed usability issues. </b>We have a few more small changes to stuff on Chameleon. We updated our baremetal snapshot tool, <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images.html#the-cc-snapshot-utility">cc-snapshot</a>, so that now it works correctly if there are multiple disk labels. We also updated the hardware management tool, Doni, which is primarily used by <a href="https://github.com/ChameleonCloud/chi-in-a-box">CHI-in-a-box</a> site operators, to support unsetting properties on resources.</p>

<p>Happy experimenting!</p>