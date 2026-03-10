---
abstract: "<p>This past month brings 2025 to a close and also exciting updates, including\
  \ a year in review, Trovi improvements, and a CHI@Edge artifact, along with announcements\
  \ about <a href=\"http://chameleoncloud.org/learn/webinars\">upcoming webinars</a>\
  \ (next up: <a href=\"https://uchicago.zoom.us/webinar/register/WN_TTUYO1o8QRC3AFyuHKU4lA\"\
  >How to Organize Artifact Evaluations (AEs) with Shared Infrastructure</a> on Jan.\
  \ 13th), our <a href=\"https://chameleoncloud.org/blog/2025/12/13/call-for-presentations-chameleon-user-meeting-2026/\"\
  >call for presentations</a> for our <a href=\"https://chameleoncloud.org/blog/2025/11/13/save-the-date-sixth-chameleon-user-meeting-april-15-16-2026-boulder-co/\"\
  >sixth user meeting at NCAR\u2019s campus in Boulder</a>, and highlights from our\
  \ newly appointed reproducibility ambassadors.</p>"
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2026-01-05 22:53:15+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/71/3b/713ba884-f6c7-4720-a3f0-a5748421eee5/chameleon.jpg
slug: chameleon-newsletter-changelog-december-2025
subtitle: Testbed updates, new features, webinars, and other exciting news from our
  user community
title: Chameleon Newsletter & Changelog - December 2025
---

<p style="text-align: center;"><img src="https://chameleoncloud.org/media/filer_public/71/3b/713ba884-f6c7-4720-a3f0-a5748421eee5/chameleon.jpg" width="600"></p>

<p> </p>

<p>Chameleon December Newsletter</p>

<p>This past month brings 2025 to a close and also exciting updates, including a year in review, Trovi improvements, and a CHI@Edge artifact, along with announcements about <a href="http://chameleoncloud.org/learn/webinars">upcoming webinars</a> (next up: <a href="https://uchicago.zoom.us/webinar/register/WN_TTUYO1o8QRC3AFyuHKU4lA">How to Organize Artifact Evaluations (AEs) with Shared Infrastructure</a> on Jan. 13th), our <a href="https://chameleoncloud.org/blog/2025/12/13/call-for-presentations-chameleon-user-meeting-2026/">call for presentations</a> for our <a href="https://chameleoncloud.org/blog/2025/11/13/save-the-date-sixth-chameleon-user-meeting-april-15-16-2026-boulder-co/">sixth user meeting at NCAR’s campus in Boulder</a>, and highlights from our newly appointed reproducibility ambassadors.</p>

<h1>Publication Reporting Reminder</h1>

<p>With the start of the New Year – and the new semester and quarter – we would like to remind all how important it is for us to track which of your publications used Chameleon in your research. Referencing the system is something all Chameleon users agree to do in the terms and conditions of platform use – but it is not just a formality. NSF uses these numbers to assess the research impact of their investment so the more we can point to research produced using Chameleon resources, the more solid the demonstration of community need, and the greater the likelihood that the system will be extended – and we’d love to be able to continue serving you in the future!</p>

<p>The best way to acknowledge the use of Chameleon is to simply state it in the text of your publication and <a href="https://chameleoncloud.org/learn/frequently-asked-questions/#toc-how-should-i-cite-chameleon-">reference the platform</a>; this typically means that we will be able to eventually find it through research databases like scopus or search engines like google scholar. Another possibility is to reference Chameleon in the text or acknowledgement section of the paper without referencing the platform; this makes it harder to find but when we do find it, it is clear from the publication that the platform was used. However, if for any reason you forgot to reference the system directly in any of your publications, don’t worry – you can still tell us about it via an attestation process.</p>

<p>The way to do this is as follows:</p>

<ul>
	<li>Check whether all your publications that used Chameleon resources have been reported. You can do this by accessing your dashboard (first option in the drop down menu when you click on your name in the top right corner after logging in) and then clicking the <a href="https://chameleoncloud.org/user/projects/publications/">publication tab</a>. You will see a list of all your publications that were produced using the system – that we know of. If, after reviewing this list, you find that some publications are missing, we would appreciate it very much if you could add them by clicking the blue “<a href="https://chameleoncloud.org/user/projects/add/publications/">add publication</a>” button.</li>
	<li>The <a href="https://chameleoncloud.org/user/projects/add/publications/">add publication button</a> will guide you to a page where you can report the publications as bibtex entries (multiple entries are good) and will then ask you to attest that they were produced using Chameleon. The publications will be reviewed and displayed on <a href="https://chameleoncloud.org/user/projects/chameleon-used-research/">our user publications page</a>. Of course, please do report any publications that you see missing whether they explicitly reference Chameleon or not!</li>
</ul>

<h1>Last Year in Review</h1>

<p>2025 was a great year on the Chameleon testbed! We wanted to take a moment to highlight some of the biggest and most important changes.</p>

<ul>
	<li>We brought the virtualized Chameleon offering, <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/index.html">KVM@TACC</a>, into parity with our bare metal partition. This above all means that the virtualized partition now supports advance reservations and bounded leases, but also an availability calendar. For a full comparison between the bare metal and virtualized partition see our <a href="https://chameleoncloud.org/blog/2025/10/21/bare-metal-or-kvm-which-should-you-choose-and-when/">Tips &amp; Tricks post</a>. </li>
	<li>And we celebrated these momentous changes by adding  <a href="https://chameleoncloud.org/blog/2025/06/02/chameleon-changelog-for-may-2025/">H100 GPU hardware</a> to our virtualized offering  letting you configure up to 4 H100s in a single instance – see a <a href="https://chameleoncloud.org/learn/frequently-asked-questions/#toc-how-are-kvm-instances-virtual-machines-charged-">catalog of our new virtualized instance types</a>. In the New Year we are planning to implement a feature that will allow us to transition them flexibly between bare metal and virtualized configurations for more flexible support of all types of experiments. </li>
	<li><a href="https://chameleoncloud.readthedocs.io/en/latest/technical/sharing/index.html">Trovi</a>, Chameleon’s artifact repository continues to grow: we now support 314 artifacts ranging from teaching curricula to reproducible artifacts from results presented at recent conferences. Last year we updated Trovi to support <a href="https://chameleoncloud.org/blog/2025/11/19/from-github-to-publication-using-trovi-effectively/">collections</a>, allowing you to link together related artifacts such as e.g., reproducible results from a specific conference, or exercises relating to the same class. We also added <a href="https://chameleoncloud.org/blog/2025/04/21/importing-github-repositories-to-trovi-a-step-by-step-guide/">first-class GitHub importing</a> using <a href="https://www.researchobject.org/ro-crate/">RO-crate</a>. Lastly, we gave it all an upgraded interface in the new <a href="https://trovi.chameleoncloud.org/dashboard/">Trovi Dashboard</a>, which greatly improves the user experience.</li>
	<li><a href="https://python-chi.readthedocs.io/en/latest/">Python-chi</a>, which is Chameleon’s programmatic interface, was updated with new widgets for browsing hardware and leases to help in orchestrating reproducible experiments. These rich UI elements make it easier for experimenters to run and repeat your experiments. Additionally, python-chi was updated to work better with CHI@Edge, and to work with the new KVM reservations and also to support using <a href="https://python-chi.readthedocs.io/en/latest/modules/storage.html#chi.storage.Volume">volumes</a> and <a href="https://python-chi.readthedocs.io/en/latest/modules/server.html#chi.server.Server.add_security_group">security groups</a>. </li>
	<li>The <a href="https://chameleoncloud.org/hardware/">Hardware Browser</a>, which lets you search and browse through all of Chameleon’s hardware, was updated and now it is 10x faster and integrates with CHI@TACC and CHI@UC to simplify lease creation. The hardware browser interface was simplified as well. Stay tuned for a Tips &amp; Tricks post later this month for more information on resource discovery.</li>
	<li><a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images/index.html">Chameleon images</a> are the OS images that are used by most instances on the testbed. This year, we added new images for AMD ROCm and ARM, and improved all of our images with a helpful message-of-the-day and better tools to <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/swift/swift_mount.html">mount object store buckets</a>.</li>
	<li>The <a href="https://forum.chameleoncloud.org/">Chameleon forum</a>, where users can discuss their use of the testbed, was launched this year.</li>
	<li>CHI@EVL and CHI@IIT, two of Chameleon’s associate sites, were retired this year.We’d like to thank the operators of these sites for their hard work in expanding the Chameleon community!</li>
</ul>

<h1>Changelog</h1>

<p><b>Trovi load time and search improvements</b>. Most of you already know that Trovi is an open repository of shared artifacts that integrates with Chameleon. Today, you can <a href="https://trovi.chameleoncloud.org/dashboard/">browse over 300 artifacts</a> to find reproducible research, educational modules, and Chameleon examples. We are thrilled to wrap up the last year with significant improvements to the performace of the Trovi API: previously, it took over 30 seconds to fully load all of the artifacts on Trovi – now, it only takes around 4 seconds! Additionally, the search feature is greatly improved. You can now search exact phrases, exclude terms, or include conditional operators in your query. We hope these changes will help you better navigate Trovi’s growing collection of artifacts.</p>

<p><b>CHI@Edge artifacts</b>. CHI@Edge is Chameleon’s edge testbed, where you can experiment with Raspberry Pis, Jetson Nanos, and peripherals attached to them. This month, we’ve updated our <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/1b8cdcba-e10c-4cae-8b1e-145037bc4cda/">CHI@Edge Sensors and GPIO artifact</a> to work with the official Raspberry Pi sense hat and the waveshare sense hat. These artifacts demonstrate how to use the hat’s accelerometer and gyroscope to measure movement, environmental sensor to measure temperature and pressure, and color sensor to measure the color of objects. To get the full potential out of these peripherals, you may want to <a href="https://chameleoncloud.gitbook.io/chi-edge/device-enrollment/edge-sdk">enroll similar devices</a> of your own into CHI@Edge and use them in your own lab!</p>

<h1>Upcoming Webinars</h1>

<p><i>The Chameleon team hosts </i><a href="https://chameleoncloud.org/learn/webinars/"><i>webinars</i></a><i> on a variety of topics ranging from how to use the testbed to showcasing specific tools, research workflows, and educational projects that users built on Chameleon.</i></p>

<table>
	<tbody>
		<tr>
			<td>
			<p><b>Title</b></p>
			</td>
			<td>
			<p><b>Date</b></p>
			</td>
			<td>
			<p><b>Description</b></p>
			</td>
		</tr>
		<tr>
			<td>
			<p><a href="https://uchicago.zoom.us/webinar/register/WN_TTUYO1o8QRC3AFyuHKU4lA"><b>How to Organize Artifact Evaluations (AEs) with Shared Infrastructure</b></a></p>
			</td>
			<td>
			<p>January 13, 2026, 11:00 AM CT</p>
			</td>
			<td>
			<p><b>Bogdan Stoica (UIUC)</b>, drawing from his recent experience chairing the EuroSys 2025 Artifact Evaluation (AE), will talk about challenges and best practices for organizing AEs to support HPC and computer systems research. He will also demonstrate how public research infrastructure, like Chameleon Cloud, can facilitate the process.<a href="https://uchicago.zoom.us/webinar/register/WN_TTUYO1o8QRC3AFyuHKU4lA"> <b>Register here</b></a>.</p>
			</td>
		</tr>
		<tr>
			<td>
			<p><a href="https://uchicago.zoom.us/webinar/register/WN_Irf32cHvRM-78QW2EZ0W-w"><b>How to Use CHI@Edge to Enable Edge to Cloud Experimentation</b></a></p>
			</td>
			<td>
			<p>February 17, 2026, 12:00 PM CT</p>
			</td>
			<td>
			<p><b>Michael Sherman</b>, lead engineer and developer of CHI@Edge, will present new features and functionality for CHI@Edge, demonstrate how to use the platform effectively, and present examples from real users who have found innovative ways to leverage edge computing to deliver exciting experiment results on Chameleon. <a href="https://uchicago.zoom.us/webinar/register/WN_Irf32cHvRM-78QW2EZ0W-w">Register here</a>.</p>
			</td>
		</tr>
	</tbody>
</table>

<p>Keep an eye on our <a href="http://chameleoncloud.org/learn/webinars">webinar calendar</a> as we announce new webinars for upcoming months.</p>

<h1>Community News &amp; Resources</h1>

<p><b>Call for Presentations for the 6th Chameleon User Meeting - DUE February 6, 2026</b>: Our <a href="https://chameleoncloud.org/blog/2025/12/13/call-for-presentations-chameleon-user-meeting-2026/">Call for Presentations</a> for the 6th Chameleon User Meeting is now live; we are actively accepting applications! We are particularly interested in presentations that address artificial intelligence (AI) and machine learning (ML) research on cloud testbeds. Submissions should focus on infrastructure requirements (hardware, configuration, etc.), experimental apparatus, challenges, and lessons learned. Presenters are invited to attend the meeting from April 15-16th, 2026 at the National Center for Atmospheric Research (NCAR) campus in Boulder, CO. <a href="https://chameleoncloud.org/blog/2025/12/13/call-for-presentations-chameleon-user-meeting-2026/">Read the Call </a>for more information and submission requirements.</p>

<p><b>New Reproducibility Artifacts on Trovi</b>: In October 2025, we began recruiting students to serve as “reproducibility ambassadors” with the aim of fostering reproducibility communities and encouraging best practices at computer systems and high-performance computing conferences (e.g., FAST, SC, CCS, EuroSys, and more). In preparation for attending conferences, ambassadors package reproducible artifacts on <a href="http://trovi.chameleoncloud.org">Trovi</a>, replicating previously published experiment results from their conference of interest. Below, we list some artifacts that these students have completed to date, all of which you can run yourself through Trovi. </p>

<p>P.S. If you have students or are a student yourself who’d like to participate, send an email to Marc Richardson (<a href="mailto:mtrichardson@uchicago.edu">mtrichardson@uchicago.edu</a>) with the subject title: “Reproducibility Ambassador Sign Up.”</p>

<p><b>New Artifacts</b></p>

<ul>
	<li><a href="https://trovi.chameleoncloud.org/dashboard/artifacts/cd014119-03f6-4f14-8bde-bd0d07a9279d"><b>Reproducing ASPLOS' 23: LeaFTL: A Learning-Based Flash Translation Layer for Solid-State Drives - Trovi</b></a></li>
</ul>

<ul>
	<li><a href="https://trovi.chameleoncloud.org/dashboard/artifacts/39d048b4-03f7-4be4-a2be-bd7074d03bc5"><b>FAST'25: 3L-Cache - Trovi</b></a></li>
</ul>

<ul>
	<li><a href="https://trovi.chameleoncloud.org/dashboard/artifacts/6010704e-910b-4d66-8c77-602c2434b785"><b>FAST'25: HiDPU - Trovi</b></a><b> </b></li>
</ul>

<ul>
	<li><a href="https://trovi.chameleoncloud.org/dashboard/artifacts/c5e87d87-314b-4f2a-b3fe-e9fa1be83a4d"><b>Reproduction of Building Verified Neural Networks for Computer Systems with Ouroboros from MLSys 2023 - Trovi</b></a><b> </b></li>
</ul>

<ul>
	<li><a href="https://trovi.chameleoncloud.org/dashboard/artifacts/b357b901-c595-4548-a84b-b6809cbb1858"><b>Reproducing the BrewER (VLDB '23) Entity Resolution Experiment - Trovi</b></a><b> </b></li>
</ul>

<ul>
	<li><a href="https://trovi.chameleoncloud.org/dashboard/artifacts/b27c6c0e-0e21-4b29-bdcb-b04f2a45ecf1"><b>Reproduction of TSB-Clustering (VLDB 2025) - Trovi</b></a></li>
</ul>

<ul>
	<li><a href="https://trovi.chameleoncloud.org/dashboard/artifacts/7c7ebab9-6a94-4b81-b25b-717df71bc0bc"><b>Observatory Row Order Insignificance: Reproduction and Bug Discovery - Trovi</b></a></li>
</ul>

<ul>
	<li><a href="https://trovi.chameleoncloud.org/dashboard/artifacts/a9d3fb64-afae-42e4-a932-b288f8c194da"><b>Reproduced an Evaluation for ML-Based MS/MS Similarity Prediction (BMC Bioinformatics 2025) - Trovi</b></a></li>
</ul>

<ul>
	<li><a href="https://trovi.chameleoncloud.org/dashboard/artifacts/856a6f65-4035-4fc8-a638-287e970f9b60"><b>Optimizing Video Analytics with Declarative Model Relationships - Trovi</b></a></li>
</ul>

<ul>
	<li><a href="https://trovi.chameleoncloud.org/dashboard/artifacts/b21f40cb-3125-45f4-942e-34f0a83cd78d"><b>On the Detectability of ChatGPT Content: Benchmarking, Methodology, and Evaluation Through the Lens of Academic Writing - Trovi</b></a></li>
</ul>

<p><b>MPI Webinar Recording Available</b>: Our Dec. 2025 webinar recording with Ken Raffenetti’s talk, “How to Create an MPI Cluster on a Cloud”, is now available online. We are grateful to Ken for his time and interesting presentation as well as for the fantastic attendance (over 40 attendees!) and all the thoughtful questions asked. Watch Ken’s talk <a href="https://www.youtube.com/watch?v=U3Q80dRJpiE">here</a>.</p>

<p><b>Tips&amp;Tricks Blog of the Month</b>: <a href="https://chameleoncloud.org/blog/2025/12/15/tickets-of-the-year-2025/">Tickets of the Year: 2025 | Chameleon</a> </p>

<p><b>User Experiment Blog of the Month</b>: <a href="https://chameleoncloud.org/blog/2025/12/22/netprompt-ai-powered-network-policy-management-for-programmable-networks/">NetPrompt: AI-Powered Network Policy Management for Programmable Networks | Chameleon</a> </p>

<p> </p>