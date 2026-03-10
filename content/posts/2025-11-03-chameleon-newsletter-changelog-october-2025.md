---
abstract: <p>October was Performance Month for Chameleon Cloud. We're excited to share
  a variety of performance upgrades for various testbed services, a new Trovi feature,
  new webinars, user resources, and awesome Trovi artifacts developed by our users!</p>
authors:
- Marc Richardson
categories:
- Chameleon Changelog
date: '2025-11-03 22:49:32+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/d4/b0/d4b00b88-60b5-425e-9a69-2bd1ea8dbb95/chameleon_nov_2025.jpg
slug: chameleon-newsletter-changelog-october-2025
subtitle: Testbed updates, new features, webinars, and other exciting news from our
  user community
title: Chameleon Newsletter & Changelog - October 2025
---

<div>
<div>
<p><em>Welcome to the Chameleon Newsletter! With so many developments emerging from Chameleon and our surrounding community, our changelog has recently become quite full. Some of these updates are not quite "changelog material," so we are transitioning our monthly changelog into a monthly newsletter. Of course, the changelog will still remain front and center, serving as a valuable resource for important updates to Chameleon infrastructure and services. In addition, the newsletter will include other important announcements, calls for upcoming webinars and events relevant to the Chameleon community, featured community news and resources from and for our users, and a monthly survey question. Check it out below!</em></p>

<p><em>If you have interesting tools, research, or events that the Chameleon community would find valuable, please share them with us; we'd love to feature them here. Contact Marc Richardson, <a href="mailto:mtrichardson@uchicago.edu">mtrichardson@uchicago.edu</a>, to suggest newsletter items for inclusion each month.</em></p>
</div>

<div><img src="https://chameleoncloud.org/media/filer_public/d4/b0/d4b00b88-60b5-425e-9a69-2bd1ea8dbb95/chameleon_nov_2025.jpg">
<p> </p>

<p>Hello Chameleon Users!</p>

<p>October was Performance Month for Chameleon Cloud. We're excited to share a variety of performance upgrades for various testbed services, a new Trovi feature, new webinars, user resources, and awesome Trovi artifacts developed by our users!</p>
</div>

<section>
<h3>Changelog</h3>

<p><em>Changes to testbed capabilities and services this month.</em></p>

<div>
<p><strong>Trovi Collections and Citations</strong>. Trovi is Chameleon's repository of shared artifacts, allowing you to browse through hundreds of experiments that run on Chameleon. This month, we are excited to announce artifact collections. Now, you can <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/add?mode=manual">create an artifact</a> and then <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/sharing/packaging_artifacts.html#editing-related-artifacts">link it</a> to other related artifacts to form a collection. These links can be used to group together artifacts that are part of a series, such as part of a course, or artifacts that are a part of a conference. We are looking forward to seeing all of the collections that our users will share on Trovi over the next few months!</p>

<p>We've also added a panel in Trovi artifact detail page that shows <a href="https://chameleoncloud.org/learn/frequently-asked-questions/#toc-how-should-i-cite-trovi-artifacts-">how to cite</a> the current artifact. Previously, this information was only in our FAQ, which was difficult to find. Now you can easily copy the citation or bibtex information for any artifact from the dashboard directly.</p>
</div>

<div>
<p><strong>Improved Storage at CHI@TACC and KVM@TACC</strong>. We've installed new hardware for the CHI@TACC and KVM@TACC storage cluster, which is used by the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/swift/index.html">object store</a>, <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/shares/index.html">filesystem shares</a>, and <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_volumes.html">VM volumes</a>. Previously, this cluster was running on a combination of HDDs and SSDs, and now it entirely operates on NVMe SSDs. Additionally, we've improved the network connection on this cluster, and overall expect improvements to latency and bandwidth. Since this is a shared environment, we don't have guarantees on the performance you'll see in e.g., your KVM instances, but these changes should mean overall smoother IO performance and lower latency with fewer spikes.</p>
</div>

<div>
<p><strong>Improved Resource Discovery API</strong>. This month, we've made significant improvements to our <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/discovery/rest_api.html">Resource Discovery API</a>. This API is used internally by the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/discovery/hardware_catalog.html">Hardware Browser</a> but is also <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/discovery/rest_api.html">open for your use</a>. We've significantly improved the API response time, meaning that the hardware browser loads much faster. If you were previously using the REST API, please note that the API response has changed slightly. Mainly, we've removed parts of the response that were nonfunctional, such as the cluster status endpoint.</p>
</div>

<div>
<p><strong>Vendordata Improvements.</strong> Vendordata is one of the services that runs on the testbed. It's used to generate the openrc file and the "message of the day" text when you login to a node. This month, we've improved the API response time of the service. We also fixed an issue on KVM, where the generated openrc file would not work properly.</p>
</div>
</section>

<section>
<h3>Upcoming Webinars</h3>

<p><em>The Chameleon team hosts <a href="https://chameleoncloud.org/learn/webinars/">webinars</a> on a variety of topics ranging from how to use the testbed to showcasing specific tools, research workflows, and educational projects that users built on Chameleon. Register for an upcoming webinar below! All our past webinars are available to view on the <a href="https://www.youtube.com/channel/UCVP_TxAjuCiMoQRxC68Pt_A/">Chameleon Youtube channel</a>.</em></p>

<p><em>If you've developed artifacts or tools that could make research or teaching on Chameleon easier for others and are interested in presenting a webinar on that work, we'd love to hear from you! Reach out to us at the <a href="http://chameleoncloud.org/user/help">Help Desk</a> to discuss your ideas.</em></p>

<table style="width: 100%; border-collapse: collapse; margin: 20px 0; font-family: Arial, sans-serif;">
	<thead>
		<tr style="background-color: #f2f2f2;">
			<th style="border: 1px solid #ddd; padding: 12px; text-align: left; font-weight: bold; background-color: #4CAF50; color: white;">Title</th>
			<th style="border: 1px solid #ddd; padding: 12px; text-align: left; font-weight: bold; background-color: #4CAF50; color: white;">Date</th>
			<th style="border: 1px solid #ddd; padding: 12px; text-align: left; font-weight: bold; background-color: #4CAF50; color: white;">Description</th>
		</tr>
	</thead>
	<tbody>
		<tr style="background-color: #f9f9f9;">
			<td style="border: 1px solid #ddd; padding: 12px; vertical-align: top;"><a href="http://us02web.zoom.us/meeting/register/A3315sxdT4Obf4NZuE8PEA#/registration" style="color: #0066cc; text-decoration: none;"><strong>Chameleon: A Configurable Edge to Cloud Environment for Computer Science Research and Education</strong></a> - CMD-IT November Webinar</td>
			<td style="border: 1px solid #ddd; padding: 12px; vertical-align: top; white-space: nowrap;">November 6, 2025, 3:00 PM CT</td>
			<td style="border: 1px solid #ddd; padding: 12px; vertical-align: top;">Our classic Introduction to Chameleon webinar. <strong>Open to the public</strong>. Chameleon is a large-scale, reconfigurable testbed supporting research and education in systems, networking, AI/ML, edge computing, and more. This talk will introduce its capabilities and show how you can use Chameleon for your own projects. <a href="https://us02web.zoom.us/meeting/register/A3315sxdT4Obf4NZuE8PEA#/registration" style="color: #0066cc; text-decoration: none;"><strong>Register here</strong></a>.</td>
		</tr>
		<tr style="background-color: #ffffff;">
			<td style="border: 1px solid #ddd; padding: 12px; vertical-align: top;"><a href="http://uchicago.zoom.us/webinar/register/WN_ZN4PtuwhTY-lwG1SY6ICWA" style="color: #0066cc; text-decoration: none;"><strong>Teaching Machine Learning Operations (MLOps) at Scale</strong></a></td>
			<td style="border: 1px solid #ddd; padding: 12px; vertical-align: top; white-space: nowrap;">November 25, 2025, 11:00 AM CT</td>
			<td style="border: 1px solid #ddd; padding: 12px; vertical-align: top;"><strong>Professor Fraida Fund (NYU)</strong> will share a complete, openly available curriculum she developed for teaching operational ML skills at scale. Drawing from her Spring 2025 course serving nearly 200 students, she will present her pedagogical approach and hands-on learning materials made available through Chameleon's Trovi platform. Topics include cloud computing, DevOps for ML, distributed training, model serving, monitoring, and data systems. <a href="https://uchicago.zoom.us/webinar/register/WN_ZN4PtuwhTY-lwG1SY6ICWA" style="color: #0066cc; text-decoration: none;"><strong>Register here</strong></a>.</td>
		</tr>
	</tbody>
</table>

<p>Keep an eye on our <a href="http://chameleoncloud.org/learn/webinars">webinar calendar</a> as we announce new webinars for upcoming months. We already have two additional webinars scheduled for future months on creating MPI appliances and organizing artifact evaluations on Chameleon for HPC and computer systems.</p>
</section>

<section>
<h3>Other Upcoming Events</h3>

<p>Chameleon will be in St. Louis, MO for <a href="https://sc25.conference-program.com/">Supercomputing 2025</a> (SC25) this month! The SC activities kick off with our very own Kate Keahey, who will present a paper she co-authored with Fraida Fund, <em>The Cost of Teaching Operational ML</em>, at the <a href="https://sc25.conference-program.com/session/?sess=sess220">EduHPC-25 workshop</a> (<a href="https://nimbusproject.org/wp-content/uploads/sites/116/2025/09/The_Cost_of_Teaching_Operational_ML_EduHPC.pdf">paper</a>) on November 16 (10:45 AM). Following that, <a href="https://chameleoncloud.org/blog/2025/09/30/student-spotlight-three-chameleon-projects-heading-to-sc25/">three students who worked on projects with the Chameleon team</a> over the summer will present their research posters at the <a href="https://sc25.conference-program.com/session/?sess=sess527">ACM Student Research Competition</a> on November 18.</p>
</section>

<section>
<h3>Community News &amp; Resources</h3>

<p><em>Featured news and resources from Chameleon users for this month.</em></p>

<p>This month, we are excited to feature a <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/7424a8dc-0688-4383-9d67-1e40ff37de17"><strong>NEW Trovi artifact</strong></a> that Chameleon user Ken Raffenetti (ANL) and his student, Rohan Babbar (University of Delhi), built during the <a href="http://repeto.cs.uchicago.edu/sor">Summer of Reproducibility 2025</a>. This artifact is the focus of an <a href="http://chameleoncloud.org/learn/webinars">upcoming webinar</a> on MPI appliances in December 2025 that Ken Raffanetti will lead. The webinar will walkthrough the details of using the MPI artifact to <strong>set up a ready-to-use HPC cluster in the cloud</strong> with required libraries for running and managing MPI-based applications. Try it out and then come to the <a href="https://uchicago.zoom.us/webinar/register/WN_8fFbWZ7GQGaIz41NtN5CQw">webinar</a> to share your questions and feedback!</p>

<p>Lastly, don't miss out on these <strong>useful reads and resources from this month</strong>:</p>

<ul>
	<li>Tips&amp;Tricks - <a href="https://chameleoncloud.org/blog/2025/10/21/bare-metal-or-kvm-which-should-you-choose-and-when/">Bare Metal or KVM? Which Should You Choose and When</a></li>
	<li>User Experiment - <a href="https://chameleoncloud.org/blog/2025/10/31/introducing-mincers-performance-measurement-and-reproducibility-appliance/">Introducing MINCER's Performance Measurement and Reproducibility Appliance</a></li>
</ul>
</section>

<section>
<h3>Upcoming Maintenance</h3>

<ul>
	<li><a href="https://chameleoncloud.org/user/outages/tacc-network-maintenance-nov-10-2025/">TACC Network Maintenance Nov 10, 2025</a></li>
	<li><a href="https://chameleoncloud.org/news/outages/chiedge-maintenance-window/">CHI@Edge Maintenance Window (Tentatively Nov. 6, 2025)</a></li>
</ul>
</section>
</div>