---
abstract: <p>There is a poem about the 5th of November, but sadly I couldn't find
  a way to adapt it for this changelog. Anyways, learn about our new KVM cloud! And
  we also packed in a few other goodies this month.</p>
authors:
- Jason Anderson
categories:
- Chameleon Changelog
date: '2019-11-05 16:10:46+00:00'
featured: false
hide_image: true
image: ''
related_posts: []
slug: chameleon-changelog-october-2019
subtitle: ''
title: Chameleon Changelog for October 2019
---

<p dir="ltr" id="docs-internal-guid-78650b74-7fff-49bb-cbe3-1ac4b3efd87e" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 11pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">Great news in Chameleon-land!</span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 11pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">November is fast upon us, and that means two things: discount candy corn and Chameleon changelogs.</span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 11pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;"><strong>New KVM site online!</strong> In 2015, shortly after the release of the first version of the bare metal testbed, we </span><a href="https://www.chameleoncloud.org/news/new-openstack-kvm-cloud-available/" style="text-decoration: none;"><span style="">launched</span></a><span style="font-size: 11pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;"> the Chameleon KVM cloud as a companion platform for those who were more interested in a more flexible virtualized environment for experimentation. We’re happy to announce that we’ve given our KVM cloud a major facelift and have upgraded it to the recent OpenStack Rocky release. What this means in practice is better reliability, more capabilities, and better interfaces to the testbed. The new cloud is available today at </span><a href="https://kvm.tacc.chameleoncloud.org" style="text-decoration: none;"><span style="">kvm.tacc.chameleoncloud.org</span></a><span style="font-size: 11pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">. Both the new and old KVM site will be running simultaneously to allow you to migrate workloads over time. We anticipate an end-of-life for the old KVM cloud at January 1st, 2020, at which point the site will be taken offline. We have already migrated most of your images, key pairs, and other data tied to your project to the new environment (as of October 31), so you shouldn’t have to do any heavy lifting! Please let us know how you like it, and as always, you can checkout the documentation </span><a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm.html" style="text-decoration: none;"><span style="">here</span></a><span style="font-size: 11pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">.</span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 11pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;"><strong>Cloud trace data now available for bare metal sites.</strong> We have at various times released anonymized usage data on the Chameleon KVM cloud for use in simulations or analysis. This month, we have updated both our open-source </span><a href="https://github.com/ChameleonCloud/starcompactor" style="text-decoration: none;"><span style="">trace generator</span></a><span style="font-size: 11pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;"> and the </span><a href="https://scienceclouds.org/cloud-traces/cloud-trace-format/" style="text-decoration: none;"><span style="">trace format specification</span></a><span style="font-size: 11pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;"> to serve for both the virtual machine and bare-metal clouds. We also published a new KVM trace from our KVM site and bare-metal traces from the CHI@UC site and CHI@TACC site using the updated trace format version. For more information about cloud traces, please visit our </span><a href="https://press3.mcs.anl.gov/scienceclouds/cloud-traces/" style="text-decoration: none;"><span style="">cloud traces page on Science Clouds</span></a><span style="font-size: 11pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;"> and </span><a href="https://press3.mcs.anl.gov/scienceclouds/contact/" style="text-decoration: none;"><span style="">contact us</span></a><span style="font-size: 11pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;"> if you would like to either use our data or contribute your own.</span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 11pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;"><strong>Automatically enable jumbo frames for your networking experiments.</strong> In order to take full advantage of the 10G NICs in our bare metal nodes, it is generally advised to set a higher MTU on your network devices. However, this requires support across all switches/routers in the network path. We’ve done a thorough run-through of the Chameleon networking infrastructure to ensure this is the case, and in particular paid attention to the 100G link we have between the TACC and UC sites. You can rest assured that your packets are able to flow with maximum throughput. To find out how to easily set up your custom network for jumbo frames (and avoid having to set the MTU settings on your nodes manually!), check out </span><a href="https://chameleoncloud.readthedocs.io/en/latest/technical/networks/networks_jumbo_frames.html" style="text-decoration: none;"><span style="">a new section of our documentation about this</span></a><span style="font-size: 11pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">.</span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 11pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;"><strong>Usability improvements in the reservation system.</strong> We continue to make improvements to how the reservation UI works when you are reserving bare metal nodes and/or network resources on the testbed. In particular, this month we made sure all the displayed time zones in the </span><a href="https://chameleoncloud.readthedocs.io/en/latest/technical/reservations.html#the-lease-calendars" style="text-decoration: none;"><span style="">lease calendars</span></a><span style="font-size: 11pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;"> were consistent to avoid confusion about when a particular resource is available.</span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 11pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;"><strong>New appliances.</strong> Finally, we have two new appliances for your enjoyment this month. The first is a deployment of </span><a href="https://www.chameleoncloud.org/appliances/78/" style="text-decoration: none;"><span style="">perfSONAR</span></a><span style="font-size: 11pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">, a network performance monitoring tool that can be set up to continuously monitor end-to-end link performance over time. We’ve also updated the </span><a href="https://www.chameleoncloud.org/appliances/77/" style="text-decoration: none;"><span style="">DevStack appliance</span></a><span style="font-size: 11pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;"> for the OpenStack Rocky release, allowing you to easily launch an isolated OpenStack installation of your own. Hope you enjoy!</span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<h3 dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;">Webinars</h3>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 11pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">The following most recent webinars are now available for online viewing:</span></p>

<ul dir="ltr">
	<li style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 11pt; font-family: Arial; background-color: transparent; font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre-wrap;"><a href="http://bit.ly/2JgQUMZ"><span style="color: #3498db;">Programmable Networks: Software Defined Networking (Open Flow)</span></a></span></li>
	<li style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><a href="https://youtu.be/Ch94NJtZwSs"><span style="color: #3498db;"><span style="font-size: 11pt; font-family: Arial; background-color: transparent; font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre-wrap;">Introduction to Chameleon</span></span></a></li>
</ul>

<h4 style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 11pt; font-family: Arial; background-color: transparent; font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre-wrap;"><span style="color: null;">Upcoming</span></span></h4>

<ul dir="ltr">
	<li style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 11pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;"><strong>Nov. 14th @ 2-3pm CT</strong> | <a href="https://bit.ly/chameleonnov14"><em>Chameleon Advanced Topics: Bring Us Your Troubles and We Will Shoot Them!</em></a></span><br>
	<span style="font-size: 11pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">S</span><span style="font-size: 11pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">ubmit your questions: <a href="https://bit.ly/nov14questions">bit.ly/nov14questions</a></span></li>
	<li style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 11pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;"><strong>Dec. 10th @ 2-3pm CT</strong> | <a href="https://bit.ly/chameleondec10"><em>Make the Best Use of Your Allocations: Orchestrate Your Experiments</em></a></span></li>
	<li style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 11pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;"><strong>Jan. 14th @ 2-3pm CT</strong> | <a href="https://bit.ly/chameleonjan14"><em>Intro to Chameleon</em></a></span></li>
</ul>

<h3 style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;">Conferences</h3>

<div dir="ltr" align="left" style="">
<div dir="ltr" align="left" style="">
<table style="border: none; border-collapse: collapse;">
	<colgroup>
		<col width="63">
		<col width="66">
		<col width="367">
		<col width="130">
	</colgroup>
	<tbody>
		<tr style="height: 15pt;">
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 700; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">Sponsor</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 700; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">Abbreviation</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 700; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">Conference (full name)</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; text-align: center; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 700; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">Submission Date</span></p>
			</td>
		</tr>
		<tr style="height: 37pt;">
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">NSF-CISE funded project</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">MERIF</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">Midscale Experimental Research Infrastructure Forum</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; text-align: right; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">Nov 8, 2019</span></p>
			</td>
		</tr>
		<tr style="height: 15pt;">
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">ACM</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">SOSR</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">Symposium on SDN Research</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; text-align: right; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">Nov 8, 2019</span></p>
			</td>
		</tr>
		<tr style="height: 15pt;">
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">USENIX</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">--</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">Security Symposium</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; text-align: right; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">Nov 15, 2019</span></p>
			</td>
		</tr>
		<tr style="height: 15pt;">
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">--</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">ISCA</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">International Symposium on Computer Architecture</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; text-align: right; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">Nov 19, 2019</span></p>
			</td>
		</tr>
		<tr style="height: 15pt;">
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">USENIX</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">Vault</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">Linux Storage and Filesystems Conference</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; text-align: right; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">Nov 20, 2019</span></p>
			</td>
		</tr>
		<tr style="height: 15pt;">
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">ACM</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">PLDI</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">Conference on Programming Language Design and Implementation</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; text-align: right; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">Nov 22, 2019</span></p>
			</td>
		</tr>
		<tr style="height: 15pt;">
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">ACM</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">SIGMOD</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">International Conference on Management of Data</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; text-align: right; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">Nov 25, 2019</span></p>
			</td>
		</tr>
		<tr style="height: 15pt;">
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">ACM</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">SIGMOD</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">International Conference on Management of Data</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; text-align: right; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">Dec 13, 2019</span></p>
			</td>
		</tr>
		<tr style="height: 15pt;">
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">ACM</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">SIGMOD</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">International Conference on Management of Data</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; text-align: right; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">Dec 15, 2019</span></p>
			</td>
		</tr>
		<tr style="height: 15pt;">
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: rgb(0, 0, 0); font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre-wrap;"><span style="background-color: null;">USENIX</span></span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: rgb(0, 0, 0); font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre-wrap;"><span style="background-color: null;">ATC</span></span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: rgb(0, 0, 0); font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre-wrap;"><span style="background-color: null;">Annual Technical Conference</span></span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; text-align: right; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: rgb(0, 0, 0); font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre-wrap;"><span style="background-color: null;">Jan 15, 2020</span></span></p>
			</td>
		</tr>
		<tr style="height: 15pt;">
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">ACM</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">SIGIR</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">Conference on Research and Development in Information Retrieval</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; text-align: right; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">Jan 15, 2020</span></p>
			</td>
		</tr>
		<tr style="height: 15pt;">
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">IEEE</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">CEC</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">Congress on Evolutionary Computation</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; text-align: right; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">Jan 15, 2020</span></p>
			</td>
		</tr>
		<tr style="height: 15pt;">
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">ACM</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">SIGMOD</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">International Conference on Management of Data</span></p>
			</td>
			<td style="border-left: solid #cccccc 0.75pt; border-right: solid #cccccc 0.75pt; border-bottom: solid #cccccc 0.75pt; border-top: solid #cccccc 0.75pt; vertical-align: bottom; padding: 2pt 2pt 2pt 2pt; overflow: hidden;">
			<p dir="ltr" style="line-height: 1.38; text-align: right; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 10pt; font-family: Arial; color: #000000; background-color: transparent; font-weight: 400; font-style: italic; font-variant: normal; text-decoration: none; vertical-align: baseline; white-space: pre; white-space: pre-wrap;">Jan 15, 2020</span></p>
			</td>
		</tr>
	</tbody>
</table>
</div>

<p> </p>
</div>