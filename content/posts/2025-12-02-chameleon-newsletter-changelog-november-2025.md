---
abstract: "<p dir=\"ltr\">This month brings exciting updates including enhanced hardware\
  \ browser integration, CHI@Edge stability improvements, and expanded support for\
  \ distributed training on AMD GPUs, along with announcements about <a href=\"http://chameleoncloud.org/learn/webinars\"\
  >upcoming webinars</a> and our <a href=\"https://chameleoncloud.org/blog/2025/11/13/save-the-date-sixth-chameleon-user-meeting-april-15-16-2026-boulder-co/\"\
  >sixth user meeting at NCAR\u2019s campus in Boulder</a>.</p>"
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2025-12-02 22:14:04+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/45/ab/45ab956c-92bc-4375-b5cd-eb480bda1831/54227546483_d8ec90edd8_w.jpg
slug: chameleon-newsletter-changelog-november-2025
subtitle: Testbed updates, new features, webinars, and other exciting news from our
  user community
title: Chameleon Newsletter & Changelog - November 2025
---

<p style="text-align: center;"><img src="https://chameleoncloud.org/media/filer_public/45/ab/45ab956c-92bc-4375-b5cd-eb480bda1831/54227546483_d8ec90edd8_w.jpg"><br>
<a href="https://www.flickr.com/photos/196141305@N06/54227546483/in/photolist-2r9r2AC-2r7SSq3-2qCRKVv-2qCK4FS-2qCPDNF-2qCPDMP-2qBVYTm-2qBVYTr-2qBNtWa-2qBUnjc-2qBNtG2-2qBVa2A-2qBT8sZ-2qBV9iS-2qBUixU-2qBUisJ-2qBUmem-2qBNy3X-2qBUryE-2qBUrpM-2qBUogS-2qBVdDa-2qBTco4-2qBUqWs-2qBTca8-2qBUqHG-2qBUnFU-2qBUpVj-2qBNw4r-2qBTaYv-2qBVc5i-2qBUmiZ-2qBUoPS-2qBUoMN-2qBTa5M-2qBUosu-2qBVbaC-2qBNuKz-2qBVb5h-2qBUoeP-2qBNuDT-2qBVaFS-2qBVaFw-2qBT99U-2qBVawZ-2qBT981-2qBNuaB-2qBdjK7">Rhett Butler via Flickr</a></p>

<p>Welcome to the November Chameleon newsletter! This month brings exciting updates including enhanced hardware browser integration, CHI@Edge stability improvements, and expanded support for distributed training on AMD GPUs, along with announcements about <a href="http://chameleoncloud.org/learn/webinars">upcoming webinars</a> and our <a href="https://chameleoncloud.org/blog/2025/11/13/save-the-date-sixth-chameleon-user-meeting-april-15-16-2026-boulder-co/">sixth user meeting at NCAR’s campus in Boulder</a>.</p>

<h1>Changelog</h1>

<p><em>Changes to testbed capabilities and services this month.</em></p>

<p><b>New Hardware Browser Integration</b>. The <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/discovery/hardware_catalog.html#the-hardware-catalog-on-the-chameleon-portal">hardware browser</a> is the tool that lets you easily search and explore all of the hardware resources across Chameleon’s baremetal sites, letting you find nodes with e.g., specific CPU or GPU models. This month, we are excited to announce improvements in how the hardware browser integrates with these sites. From the node detail view in the hardware browser, you can simply click a button to check that node's availability or to reserve it. We have also improved the site availability calendar, which shows when each node is reserved, so that clicking on a node name will automatically fill in the lease create form to reserve it. Additionally, we fixed an issue where deep links did not work if you were logged out of a site. Now, links to specific pages (such as the site calendar) will redirect you properly after you log in.</p>

<p><b>CHI@Edge improvements</b>. We’ve been working to improve the stability and usability of <a href="https://chameleoncloud.org/experiment/chiedge/">CHI@Edge</a> over the last few months, and wanted to highlight a few of these improvements. First, we’ve fixed issues with CHI@Edge floating IP traffic, where sometimes traffic wouldn’t flow to newly associated IPs.. Additionally, we’ve fixed several cases where containers would move to an “error” state instead of launching correctly, particularly when peripherals are mounted. Lastly, we’ve migrated the CHI@Edge control-plane to a new, more powerful, controller node with fast disks to resolve cases where the kubernetes backend was timing out.   Internally, we’re now deploying the k3s control-plane with chi-in-a-box + kolla-ansible, improving isolation and our ability to update configuration and versions without downtime.</p>

<p><b>Updated AMD ROCm image to support distributed training</b>. CHI@TACC has a wide variety of hardware, with 18 node types. This includes 8 gpu_mi100, which are the only nodes with AMD GPUs on Chameleon, with each node having 2 MI100 GPUs. Similar to our CUDA images for Nvidia GPUs, we support a <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images/supported_images.html">CC-Ubuntu24.04-ROCm image</a> which is preconfigured with settings and software to work with these MI100 GPUs. This month, we’ve updated the ROCm image, setting the IOMMU to the recommended passthrough mode, which makes it easier to run distributed training on these GPUs.</p>

<h1>Upcoming Webinars</h1>

<p><i>The Chameleon team hosts </i><a href="https://chameleoncloud.org/learn/webinars/"><i>webinars</i></a><i> on a variety of topics ranging from how to use the testbed to showcasing specific tools, research workflows, and educational projects that users built on Chameleon.</i></p>

<table style="width: 100%; border-collapse: collapse; margin: 20px 0; font-family: Arial, sans-serif;">
	<thead>
		<tr style="background-color: #f2f2f2;">
			<th style="border: 1px solid #ddd; padding: 12px; text-align: left; font-weight: bold; background-color: #4CAF50; color: white;">Title</th>
			<th style="border: 1px solid #ddd; padding: 12px; text-align: left; font-weight: bold; background-color: #4CAF50; color: white;">Date</th>
			<th style="border: 1px solid #ddd; padding: 12px; text-align: left; font-weight: bold; background-color: #4CAF50; color: white;">Description</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>
			<p><a href="http://uchicago.zoom.us/webinar/register/WN_8fFbWZ7GQGaIz41NtN5CQw"><b>MPI Appliances for HPC on Chameleon</b></a></p>
			</td>
			<td>
			<p>December 16, 2025, 11:00 AM CT</p>
			</td>
			<td>
			<p><b>Ken Raffenetti (ANL)</b> will present newly available MPI Appliances for Chameleon Cloud. These appliances utilize the Spack package manager, which enables users to precisely define software environments for experiments. Paired with Ansible playbooks to handle the complex multi-node cluster configuration, Chameleon users can build and run HPC experiments with ease. We will look at the artifacts associated with these appliances, including new MPI-based disk images (with GPU support), a Heat Orchestration Template for launching multiple nodes, and Jupyter Notebooks for defining and launching clusters from Python.<a href="https://uchicago.zoom.us/webinar/register/WN_8fFbWZ7GQGaIz41NtN5CQw"> <b>Register here</b></a>.</p>
			</td>
		</tr>
		<tr>
			<td>
			<p><a href="https://uchicago.zoom.us/webinar/register/WN_TTUYO1o8QRC3AFyuHKU4lA"><b>Organizing Artifact Evaluations: A Primer on Facilitating Reproducible Research</b></a></p>
			</td>
			<td>
			<p>January 13, 2026, 11:00 AM CT</p>
			</td>
			<td>
			<p><b>Bogdan Stoica (UIUC)</b>, drawing from his recent experience chairing the EuroSys 2025 Artifact Evaluation (AE), will talk about challenges and best practices for organizing AEs to support HPC and computer systems research. He will also demonstrate how public research infrastructure, like Chameleon Cloud, can facilitate the process.<a href="https://uchicago.zoom.us/webinar/register/WN_TTUYO1o8QRC3AFyuHKU4lA"> <b>Register here</b></a>.</p>
			</td>
		</tr>
	</tbody>
</table>

<p> </p>

<p>Keep an eye on our <a href="http://chameleoncloud.org/learn/webinars">webinar calendar</a> as we announce new webinars for upcoming months.</p>

<h1>Community News &amp; Resources</h1>

<p><b>Save the Date! Sixth Chameleon User Meeting on April 15-16, 2026 (Boulder, CO)</b>: Our sixth user meeting will take place at the National Center for Atmospheric Research (NCAR) in Boulder, CO this year! The<a href="https://chameleoncloud.org/chameleon-cloud-users-meeting/sixth-chameleon-user-meeting/"> Chameleon User Meeting</a> is an in-person forum held over two days for users to discuss their research and education projects, share experiences of working with the Chameleon testbed, solve challenges together, and propose new features that will make their experiments and education projects easier. Mark the dates on your calendar and watch our <a href="https://chameleoncloud.org/chameleon-cloud-users-meeting/sixth-chameleon-user-meeting/">webpage</a> for incoming updates.</p>

<p><b>Machine Learning Webinar (Recap): </b>Fraida Fund presented her work running a 190-student class on machine learning operations (MLOps) to a group of educators and Chameleon users on Nov. 25. We had almost 100 sign-ups and close to 50 attendees. Watch the presentation <a href="https://youtu.be/oELTtE51kbk">here</a> and <a href="https://www.chameleoncloud.org/media/filer_public/46/90/46900676-d977-489c-ab37-d928513b9ea6/teaching_ml_systems__operations_-_chameleon_webinar.pdf">download the slides</a>.</p>

<p><b>Chameleon at SC25</b>: Four students who worked with us over the summer (Saieda Ali Zada, Hudson Reynolds, Alex Tuecke, and Zahra Temori) presented posters at Supercomputing (SC) 2025 this year. Read about their work in our <a href="https://chameleoncloud.org/blog/2025/09/30/student-spotlight-three-chameleon-projects-heading-to-sc25/">student highlight</a>. Kate Keahey also presented a <a href="https://nimbusproject.org/wp-content/uploads/sites/116/2025/09/The_Cost_of_Teaching_Operational_ML_EduHPC.pdf">paper</a> (co-authored with Fraida Fund from NYU) highlighting Fund’s <a href="https://ffund.github.io/ml-sys-ops/docs/instructor">open-source material</a> for teaching machine learning operations (MLOps) at scale.</p>

<p><b>Tips&amp;Tricks Blog of the Month</b>: <a href="https://chameleoncloud.org/blog/2025/11/19/from-github-to-publication-using-trovi-effectively/">From GitHub to Publication: Using Trovi Effectively | Chameleon</a></p>

<p><b>User Experiment Blog of the Month</b>: <a href="https://chameleoncloud.org/blog/2025/10/31/introducing-mincers-performance-measurement-and-reproducibility-appliance/">Introducing MINCER’s Performance Measurement and Reproducibility Appliance | Chameleon</a> </p>

<h1>Upcoming Maintenance</h1>

<p>Nothing to announce!</p>