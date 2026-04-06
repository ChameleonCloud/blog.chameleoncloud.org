---
abstract: <p>This month we're highlighting an exciting keynote announcement for our
  upcoming User Meeting, reproducibility work at FAST 2026, a new webinar recording,
  and several platform updates including improvements to Trovi, cc-snapshot, CHI@Edge,
  and python-chi.</p>
authors: []
categories:
- Announcements
date: '2026-03-02 22:54:41+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/33/7b/337bbae3-a02e-45d0-838a-562f93ef3728/sunira-moses-mlqzti51lta-unsplash.jpg
related_posts:
- slug: chameleon-newsletter-changelog-january-2026
  title: Chameleon Newsletter & Changelog - January 2026
- slug: chameleon-newsletter-changelog-december-2025
  title: Chameleon Newsletter & Changelog - December 2025
- slug: chameleon-newsletter-changelog-november-2025
  title: Chameleon Newsletter & Changelog - November 2025
slug: chameleon-newsletter-changelog-february-2026
subtitle: Welcome to the Chameleon February 2026 Newsletter!
title: Chameleon Newsletter & Changelog February 2026
---

<p>Welcome to the Chameleon February 2026 Newsletter! This month we're highlighting an exciting keynote announcement for our upcoming User Meeting, reproducibility work at FAST 2026, a new webinar recording, and several platform updates including improvements to Trovi, cc-snapshot, CHI@Edge, and python-chi.</p>

<p><img src="https://chameleoncloud.org/media/filer_public/33/7b/337bbae3-a02e-45d0-838a-562f93ef3728/sunira-moses-mlqzti51lta-unsplash.jpg" height="300px"></p>

<h2>Community News &amp; Resources</h2>

<p><strong><a href="https://www.anl.gov/profile/valerie-e-taylor">Dr. Valerie Taylor</a> (ANL) to present keynote at 6th Chameleon User Meeting</strong>: We're excited to announce that Dr. Valerie Taylor, Director of the Mathematics and Computer Science Division and a Distinguished Fellow at Argonne National Laboratory, will give the featured keynote at our upcoming User Meeting in Boulder, CO on April 15–16. Her research is on high-performance computing, with a focus on energy efficient methods and the use of Large Language Models for parallel, scientific code generation. As head of <a href="https://cmd-it.org/">CMD-IT</a>, Dr. Taylor has also spent her career championing broader participation in computing. We're excited to feature her perspective on the future of infrastructure for AI research and education. <strong>Be sure to save your spot today by <a href="https://www.eventbrite.com/e/6th-chameleon-user-meeting-tickets-1982009337282">registering online</a>.</strong></p>

<p><strong>Reproducibility Ambassadors at FAST 2026:</strong> <strong>Sabiha Afroz</strong> and <strong>Hansen Idden</strong>, PhD students from Virginia Tech, attended <a href="https://chameleoncloud.org/blog/2026/02/18/announcing-fast-2026-bird-of-feather-bof-session-on-reproducibility/">FAST 2026</a> as Chameleon Reproducibility Ambassadors — part of a reproducibility initiative that sponsors students to attend major systems conferences and advocate practices that enable reproducible CS experiments. During the conference, they led two Birds of a Feather (BoF) sessions on reproducibility and showcased packaged experiments from published FAST papers as publicly reproducible artifacts on Chameleon Trovi:</p>

<ul>
	<li><a href="https://trovi.chameleoncloud.org/dashboard/artifacts/189f8f54-a85d-4880-bae4-a82147c916e7">Cylon: Fast and Accurate Full-System Emulation of CXL-SSDs</a> (FAST 2026 – <a href="https://www.usenix.org/conference/fast26/presentation/yoon">link to paper</a>) — CXL-SSDs expose flash storage as byte-addressable memory, but real hardware is scarce. Cylon combines QEMU's CXL emulation with FEMU's SSD timing engine to let researchers evaluate CXL-SSD caching policies and application behavior without physical devices.</li>
	<li><a href="https://trovi.chameleoncloud.org/dashboard/artifacts/fcef45a2-aaee-48e7-997d-77003bf4c773">NVMeVirt: A Versatile Software-defined Virtual NVMe Device</a> (FAST 2023 – <a href="https://www.usenix.org/conference/fast23/presentation/kim-sang-hoon">link to paper</a>) — NVMeVirt is a Linux kernel module that emulates NVMe devices — conventional SSDs, ZNS SSDs, key-value SSDs, and more — at the PCI layer, presenting them as native devices to the host. It removes the hardware dependency for storage systems research.</li>
	<li><a href="https://trovi.chameleoncloud.org/dashboard/artifacts/6010704e-910b-4d66-8c77-602c2434b785">HiDPU: A DPU-Oriented Hybrid Indexing Scheme for Disaggregated Storage Systems</a> (FAST 2025 – <a href="https://www.usenix.org/conference/fast25/presentation/zhu">link to paper</a>) — Address translation is a major bottleneck when running storage indexing on resource-constrained DPUs. HiDPU proposes a multi-level indexing structure that segments storage mappings to exploit address continuity and reduce latency in disaggregated storage deployments.</li>
	<li><a href="https://trovi.chameleoncloud.org/dashboard/artifacts/39d048b4-03f7-4be4-a2be-bd7074d03bc5">3L-Cache: Low Overhead and Precise Learning-based Eviction Policy for Caches</a> (FAST 2025 – <a href="https://www.usenix.org/conference/fast25/presentation/zhou-wenbin">link to paper</a>) — ML-based cache eviction policies make better decisions than heuristics like LRU, but their CPU overhead makes them impractical in production. 3L-Cache reduces that overhead by 60–95% compared to prior learning-based policies while still achieving the best byte and object miss ratios across thousands of evaluated traces.</li>
</ul>

<p><em>If you'd like to learn more about the ambassador program — including how to nominate a student from your group — please reach out to Marc Richardson (<a href="mailto:mtrichardson@uchicago.edu">mtrichardson@uchicago.edu</a>) or Rani Irawan (<a href="mailto:raniayu@uchicago.edu">raniayu@uchicago.edu</a>).</em></p>

<p><strong>CHI@Edge Webinar Recording Available</strong>: Our Feb. 2026 webinar recording with Michael Sherman's talk, "How to Use CHI@Edge to Enable Edge to Cloud Experimentation," is now available online! We are grateful to the attendees for their time and excellent feedback. <a href="https://www.youtube.com/watch?v=P4LazPMiXF4">Watch the webinar here</a>.</p>

<p><strong>Tips &amp; Tricks Blog of the Month</strong>: <a href="https://chameleoncloud.org/blog/2026/02/17/managing-persistent-storage-with-volumes-at-kvmtacc/">Managing Persistent Storage with Volumes at KVM@TACC | Chameleon</a></p>

<p><strong>User Blog of the Month (Education)</strong>: <a href="https://chameleoncloud.org/blog/2026/02/24/a-holistic-approach-to-teaching-cloud-computing/">A Holistic Approach to Teaching Cloud Computing | Chameleon</a></p>

<h2>Changelog</h2>

<p><strong>Chameleon Appliances in Trovi.</strong> As per our announcement <a href="https://chameleoncloud.org/blog/2026/02/02/chameleon-newsletter-changelog-january-2026/">last month</a>, we have been working on streamlining the artifacts that are helpful in using the testbed so that you can find them all in one place. This month, we have moved the content from the appliance catalog into Trovi. Now, you can <a href="https://trovi.chameleoncloud.org/dashboard/artifacts?tags=appliance">filter Trovi artifacts by the 'appliance' tag</a> to find a Chameleon-supported OS image or a <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/729fc749-15da-419f-952a-0d3457baa09e">heat template</a>. This means that whether you are looking for a Jupyter notebook or an image, you can find either one via Trovi. The Appliance Catalog is still there for continuity, but you can no longer add appliances to it — instead, if you want to publish a new appliance, you can do so via the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/sharing/packaging_artifacts.html#editing-artifacts">"edit" menu</a> of your Trovi artifact. The Appliance Catalog will eventually disappear, so please <a href="https://trovi.chameleoncloud.org/dashboard/artifacts?tags=appliance">start looking for appliances via Trovi</a>!</p>

<p><strong>External Artifacts in Trovi.</strong> To make it even easier to discover research in digital form — in particular, experiments packaged for reproducibility — we are now trialing support for <a href="https://trovi.chameleoncloud.org/dashboard/artifacts?q=auto-generated">external artifacts in Trovi</a>, meaning they are not adapted to work with Chameleon specifically. These artifacts are sourced from systems conference reproducibility initiatives, and so don't use python-chi or scripts to set up Chameleon resources. However, to make them as accessible as possible, we developed a notebook that will automatically provision a node on Chameleon and download the artifact's contents onto it. From there, you can take over the experiment execution via SSH, with the help of the artifact's internal documentation. Our goal is to make these artifacts more accessible and simpler to execute on Chameleon, and to make them more discoverable to Chameleon users. If you have any questions or suggestions relating to external artifacts, please let us know via <a href="https://chameleoncloud.org/user/help/">the Help Desk</a>.</p>

<p><strong>Updates to cc-snapshot.</strong> In order to take a snapshot of your baremetal instances, we've developed <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images/cc_snapshot.html">the cc-snapshot utility</a>. This script will turn your running instance into a bootable glance image — this means that once you configure your experimental environment to your satisfaction you can simply save it and boot from the saved image next time you are using the system. You can also share this snapshotted image with others and, for example, streamline creating images for a class or for collaborators. This month, we've added a new <code>-z</code> option, which uses an improved compression method that reduces the time to create a snapshot by 50–70%. Snapshots made with this option are only compatible with our sites running OpenStack Antelope, which for now means CHI@TACC, CHI@UC, and CHI@NCAR. Additionally, we've added a new <code>-o</code> option, which will use existing environment variables to authenticate to glance. Without this option, cc-snapshot tries to authenticate based on your running instance. However, if your instance is having issues and you'd like to take a snapshot, this option lets you <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/cli/rc_script.html">source an openrc file</a> to set the authentication credentials.</p>

<p><strong>CHI@Edge updates.</strong> This month, we hosted a <a href="https://www.youtube.com/watch?v=P4LazPMiXF4">CHI@Edge webinar</a>, which contains up-to-date information about our edge testbed and devices. To go along with this webinar, we've updated CHI@Edge Trovi artifacts for <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/4b08e80c-df0a-4866-bf29-19b5ad6a2950">SSHing to a device</a> and <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/1b8cdcba-e10c-4cae-8b1e-145037bc4cda/">showcasing peripheral use</a>. Additionally, we've updated our <a href="https://chameleoncloud.gitbook.io/chi-edge">documentation</a> for CHI@Edge, with new information about <a href="https://chameleoncloud.gitbook.io/chi-edge/hardware-info/device-type">device types</a> and <a href="https://chameleoncloud.gitbook.io/chi-edge/hardware-info/peripheral-types">peripherals</a>.</p>

<p><strong>Python-chi improvements.</strong> Python-chi is the programmatic interface to the testbed, and the primary interface for CHI@Edge. This month, we've improved the <a href="https://python-chi.readthedocs.io/en/latest/modules/container.html">CHI@Edge module in python-chi</a> with better error handling and more information about container status during launch. Also, we've improved how python-chi handles <a href="https://python-chi.readthedocs.io/en/latest/modules/storage.html#chi.storage.Volume">volumes</a>, fixing an issue with <code>get_volume</code> and an error getting servers that are launched from a volume.</p>

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
			<td><strong><a href="https://uchicago.zoom.us/webinar/register/WN_DvTqtj0KTjS2S3-EvvD0ug">How Researchers Are Tackling Reproducibility Challenges on Chameleon</a></strong></td>
			<td>March 10, 2026, 12:00 PM CT</td>
			<td>Reproducibility remains a persistent challenge in computer systems and high-performance computing research. In these settings, experimental results are highly sensitive to hardware, software, and configuration differences. In this webinar, <strong>Jhonny Gonzalez (University of Texas at El Paso)</strong> shares how his team developed MINCER (Monitoring Infrastructure for Network and Computing Environment Research), a user-built tool designed to address these challenges on Chameleon Cloud. MINCER leverages containerized environments and the Performance Application Programming Interface (PAPI) to automate experiment setup, collect system metadata, and record performance, power, and energy metrics across CPUs and NVIDIA and AMD GPUs. <a href="https://uchicago.zoom.us/webinar/register/WN_DvTqtj0KTjS2S3-EvvD0ug">Register here</a>.</td>
		</tr>
	</tbody>
</table>

<p>Keep an eye on our <a href="https://chameleoncloud.org/learn/webinars">webinar calendar</a> as we announce new webinars for upcoming months.</p>