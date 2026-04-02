---
abstract: <p>This month we're highlighting the last chance to register for the Sixth
  Chameleon User Meeting, a new webinar recording from UTEP's MINCER team, platform
  updates including multi-instance GPU support, new cloud traces, switch performance
  improvements, and several testbed usability enhancements.</p>
authors: []
categories:
- Announcements
- Featured
date: '2026-04-02'
featured: true
hide_image: false
image: https://chameleoncloud.org/media/filer_public/4a/1d/4a1df331-a28e-4f72-b542-1e966d389e09/laura-hayek-8_lwfkp0-zo-unsplash.jpg
related_posts:
- slug: chameleon-newsletter-changelog-february-2026
  title: Chameleon Newsletter & Changelog - February 2026
- slug: chameleon-newsletter-changelog-january-2026
  title: Chameleon Newsletter & Changelog - January 2026
- slug: chameleon-newsletter-changelog-december-2025
  title: Chameleon Newsletter & Changelog - December 2025
slug: chameleon-newsletter-changelog-march-2026
subtitle: Welcome to the Chameleon March 2026 Newsletter!
title: Chameleon Newsletter & Changelog March 2026
---

<p>Welcome to the Chameleon March 2026 Newsletter! This month we're highlighting the last chance to register for the Sixth Chameleon User Meeting, a new webinar recording from UTEP's MINCER team, and several platform updates including multi-instance GPU support on KVM, new cloud traces, switch performance improvements, and more.</p>
 
<h2>Community News &amp; Resources</h2>
 
<p><strong>TOMORROW — Last Day to Register for the User Meeting (April 2):</strong> Don't miss out on this marquee Chameleon event! At our <a href="https://chameleoncloud.org/chameleon-cloud-users-meeting/sixth-chameleon-user-meeting/">Sixth Chameleon User Meeting</a> (Boulder, CO | April 15–16), Day 1 will bring presentations from top AI researchers and educators from around the country, along with a keynote from <a href="https://www.anl.gov/profile/valerie-e-taylor">Valerie Taylor</a> (Argonne) on her LLM-based framework (LASSI-EE) for refactoring parallel scientific code for energy efficiency. Day 2 includes interactive tutorials covering all aspects of Chameleon for research and education led by Chameleon staff, as well as two expert-led mini-symposia focusing on AI for reproducibility and education. Arrive early and join us for a meet-and-greet hike on the evening of April 14! <strong><a href="https://www.eventbrite.com/e/6th-chameleon-user-meeting-tickets-1982009337282">Register today.</a></strong></p>
 
<p><strong>New Webinar Recording Available:</strong> We posted the slides and recording for the March 2026 webinar co-hosted with Dr. Shirley Moore's HPC group at the University of Texas at El Paso. Postdoc Jhonny Gonzalez demoed the MINCER toolkit for robust performance measurement across heterogeneous hardware configurations. <a href="https://chameleoncloud.org/learn/webinars/">Watch the webinar here</a> and learn how you can use this tool for your experiments on Chameleon.</p>
 
<p><strong>Tips &amp; Tricks Blog of the Month:</strong> <a href="https://blog.chameleoncloud.org/posts/chi-fabric-stitch-ports/">Running LLMs on Chameleon GPUs from FABRIC via Stitch Ports</a> — Learn more about the new Trovi artifact from FABRIC demonstrating the full end-to-end workflow for cross-testbed experiments.</p>
 
<p><strong>User Blog of the Month:</strong> <a href="https://blog.chameleoncloud.org/posts/wax-optimizing-data-center-applications-with-stale-profile/">Wax: Making Stale Profiles Work for Data Center Optimization</a> — Tawhid Bhuiyan (Columbia University) shows how leveraging source code and debug information can recover 65–93% of fresh-profile performance gains when optimizing data center applications with stale profiles.</p>
 
<p><strong>Updates for International Users and PIs on Chameleon:</strong> Chameleon has been seeing exceptionally high usage in recent months; we are happy to see the interest but also concerned that all the users who need the system most are able to use it. To ensure this, going forward we will be less lenient in enforcing our <a href="https://chameleoncloud.org/learn/frequently-asked-questions/#toc-what-are-the-policies-on-commercial-and-international-usage-">policies on commercial and international usage</a> and stricter in requiring evidence of research publications in open venues. If you are working on a project with US academic collaborators, we strongly encourage you to use a project created by them &mdash; please bear in mind that in those cases your use of the system affects their standing. Our support for reproducibility initiatives in open conferences will be unaffected, even if led by international PIs.</p>
 
<h2>Changelog</h2>
 
<p><strong>New Multi-Instance GPU Flavor on KVM.</strong> Last year, we released an H100 flavor on KVM@TACC, which allowed you to run experiments utilizing H100 GPUs via PCI passthrough — meaning you could launch a VM with an entire H100 GPU. This month, we have configured 2 of these H100 nodes with Multi-Instance GPU (MIG) support. Instead of PCI passthrough, you'll receive a 1/7th-sized slice of an H100, which means we can now support 28 instances per node rather than 4. To launch one of these instances, make a reservation for the <code>g1.h100.vgpu.1g.12gb</code> flavor and use the <code>CC-Ubuntu24.04-cuda-vgpu-preview</code> instance snapshot as your instance's source.</p>
 
<p><strong>New Cloud Traces.</strong> We've updated our cloud traces for CHI@UC, CHI@TACC, and KVM@TACC. These traces contain instance events for all instances at these sites going back to 2015! Additionally, you can find information about machine events, though this current release does not yet include the full machine history — some of that can be found in our previous traces on the Science Clouds website. As always, please let us know if you have any questions about this data via the <a href="https://chameleoncloud.org/user/help/">Help Desk</a>.</p>
 
<p><strong>Switch Performance Improvements.</strong> When provisioning a bare metal instance, many steps happen behind the scenes in order to network boot, load an image onto the disk, reboot onto the new image, and then switch from the provisioning network to your network. This switching happens 4 times in that flow, and for the switches we have in Chameleon it previously took 15–30 seconds per change, with changes queuing up if many nodes on the same switch were modified simultaneously. This month, we improved that median from 20 seconds down to 5, saving roughly 1 minute per instance launch. Performance when launching many nodes simultaneously should be greatly improved as well, since we now avoid queuing up the changes. This resolves a longstanding issue with Dell OS10 switches that is fixed in the newest version of OpenStack.</p>
 
<p><strong>Resource Discovery Admin Notes.</strong> The hardware browser lets you browse through hundreds of nodes across Chameleon sites to find the resources you need for your experiments. While it's easy to filter nodes by memory or CPU specs, some node features of great interest are configuration-specific rather than hardware-specific — such as the SGX capabilities of a node. To help solve this problem, we've added admin notes to resource discovery. Nodes that have special features or quirks will now display a banner with more information, and importantly, you can search for this text when filtering nodes.</p>
 
<p><strong>Calendar Timezone Support.</strong> The node availability calendar at CHI@UC and CHI@TACC lets you see exactly when a node is free to reserve. Until this month, all times on that page were shown in UTC, which could be tricky to interpret. Now, under your user settings, you can set your preferred timezone, which will be used across the availability calendar and lease list and detail pages to show all lease times in your local time.</p>
 
<p><strong>Deprecating Vendor-Data Login.</strong> Currently, when you provision an instance on Chameleon, we automatically place an <code>openrc.sh</code> file in your home directory for authenticating via the OpenStack CLI. This same process — known as "vendor-data" — is also used by cc-snapshot to automatically upload snapshots to a site. Because this method doesn't work consistently for all users and instances, we've built a replacement: <code>cc-login</code>. This command generates an openrc or <code>clouds.yaml</code> file for CLI authentication or cc-snapshot use. When you run it, you'll be asked to open a URL in your browser to confirm your authentication, and you can use it to generate long-lasting credentials for use in scripts. <strong>Next month, we will remove the old vendor-data authentication method</strong> — please let us know via the <a href="https://chameleoncloud.org/user/help/">Help Desk</a> if you foresee any issues with this change.</p>
 
<h2>Upcoming Webinars</h2>
 
<p>The Chameleon team hosts <a href="https://chameleoncloud.org/learn/webinars/">webinars</a> on a variety of topics ranging from how to use the testbed to showcasing specific tools, research workflows, and educational projects that users built on Chameleon.</p>
 
<table>
	<thead>
		<tr>
			<th>Title</th>
			<th>Date</th>
			<th>Description</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td><strong>Teaching Storage Systems with Interactive Courselets on Chameleon</strong></td>
			<td>April 13, 2026, 12:00 PM CT</td>
			<td>This webinar introduces storage-focused, interactive Jupyter notebook "courselets" from the NSF-funded FOUNT project, hosted on Trovi and designed to run on the Chameleon Cloud testbed. Erez Zadok and Tyler Estro (Stony Brook University) will demonstrate these courselets, offering educators and researchers practical methods for integrating reproducible, cloud-based FOUNT materials into systems teaching. <a href="https://chameleoncloud.org/learn/webinars/">Register here.</a></td>
		</tr>
	</tbody>
</table>
 
<p>Keep an eye on our <a href="https://chameleoncloud.org/learn/webinars/">webinar calendar</a> as we announce new webinars for upcoming months.</p>