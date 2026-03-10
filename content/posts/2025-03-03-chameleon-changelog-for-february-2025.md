---
abstract: <p>This month, we are excited to announce new updates to the Trovi dashboard,
  and the launch of the Chameleon User Forums. Additionally, please note our new data
  policies, as these will take effect soon!</p>
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2025-03-03 23:00:24+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/f4/03/f4031955-8fa9-4649-9089-231b3fb18731/54360124363_333796a2b0_w.jpg
slug: chameleon-changelog-for-february-2025
subtitle: ''
title: Chameleon Changelog for February 2025
---

<p style="text-align: center;"><img media="" src="https://chameleoncloud.org/media/filer_public/f4/03/f4031955-8fa9-4649-9089-231b3fb18731/54360124363_333796a2b0_w.jpg"></p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-0607c7a6-7fff-a526-f0fa-1f5228b4d68f"><a href="https://www.flickr.com/photos/42244964@N03/54360124363/in/photolist-2qPBR6v-2qPm35c-2qMLPjH-2qKDMps-2qKDMok-2qKyD7q-2qKuPmb-2qKpZgM-2qJfS3s-2qCRKVv-2qCK4FS-2qCPDNF-2qCPDMP-2qBVYTw-2qBVYTm-2qBVYTr-2qBNtWa-2qBUnjc-2qBNtG2-2qBVa2A-2qBT8sZ-2qBV9iS-2qBUryE-2qBUrpM-2qBUogS-2qBTcpM-2qBVdDa-2qBTco4-2qBUqWs-2qBTca8-2qBUqHG-2qBUnFU-2qBUpVj-2qBNw4r-2qBTaYv-2qBVc5i-2qBUmiZ-2qBUoPS-2qBUoMN-2qBTa5M-2qBUosu-2qBVbaC-2qBNuKz-2qBVb5h-2qBUoeP-2qBNuDT-2qBVaFS-2qBVaFw-2qBT99U-2qBVawZ">Frank Vassen via Flickr</a></b></p>

<p>Dear Chameleon users,</p>

<p>This month, we are excited to announce new updates to the Trovi dashboard, and the launch of the Chameleon User Forums. Additionally, please note our new data policies, as these will take effect soon!</p>

<p><b>Trovi Dashboard Updates! </b>This summer, we announced our new <a href="https://chameleoncloud.org/blog/2024/09/03/chameleon-changelog-for-august-2024/">Trovi dashboard in preview</a>. Previously, users had complained that <a href="https://chameleoncloud.org/experiment/share/">our Trovi dashboard</a> was slow and clunky. The new dashboard seeks to fix these issues, by being more modern and responsive. Our new dashboard was “read-only,” but this month we’ve added the ability to import artifacts from GitHub. This import method improves upon <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/sharing.html#importing-an-artifact">the old dashboard’s import</a> feature. Now, you can <a href="https://github.com/ChameleonCloud/troviclient?tab=readme-ov-file#trovi-artifact-generate">generate a metadata file</a> for your git repository, and when importing using our new dashboard, this metadata will be loaded directly into the artifact. We are hoping that these changes will benefit the user community in several ways:</p>

<ul>
	<li>Trovi artifacts are expanding beyond Jupyter notebooks. We are planning on implementing other methods of launching Trovi artifacts beyond the current Jupyterlab environment.</li>
	<li>By storing artifact metadata inside of a metadata file, we are hoping to improve accessibility and interoperability of Trovi artifacts.</li>
	<li>GitHub provides many useful features, such reporting issues, and collaboration tools. When surveyed, we found that the vast majority of our users were already using GitHub, and we wanted to embrace this. We hope this integration will lower the barrier to turning these repositories into Trovi artifacts.</li>
</ul>

<p>To learn more about this process, check out the “<a href="https://trovi.chameleoncloud.org/dashboard/artifacts/add">Import” page on the new dashboard</a>. We hope to share more soon about these changes, and please let us know if you have any questions or feedback, via the Help Desk or the user forums.</p>

<p><b>User Forums. </b>This month, we published our brand new <a href="https://forum.chameleoncloud.org/">user forum site</a>. As we mentioned in last month’s changelog, Chameleon has grown beyond the limits of the users mailing list in the last 10 years, which has been limited to just announcements for the past few years. However, the need for Chameleon users to be able to interact with each other has gone unfulfilled since. To fix this, we’ve introduced the User forums. These are not a replacement for our help desk, but instead another information resource. We hope that users can share how-tos and help for using the testbed on our forums. Additionally, we are planning on using these forums as a place to share useful information that normally gets hidden in tickets, such as python-chi snippets or tips for configuring hardware. <a href="https://forum.chameleoncloud.org/">Sign in</a> using your Chameleon login to stay up to date!</p>

<p><b>Updated Data/Cleanup Policies.</b> The use of Chameleon has been growing rapidly, with many users creating images, storing data, and often putting system resources to the limit. As a result, we found that we needed to clarify how Chameleon resources tied to your project are managed if you stop using the system. If you have an active allocation on Chameleon, nothing will change. If your allocation expires, and you don’t have a pending allocation, we may shutdown your instances (including on KVM), cleanup IPs in your project, private images and object store buckets, filesystem shares, or Jupyter storage. For a complete list of these policies, <a href="https://chameleoncloud.org/learn/frequently-asked-questions/#toc-what-happens-to-my-resources-when-my-allocation-expires-">see our FAQ</a>. We will start enforcing these policies on April 1, 2025 (no joke!).</p>

<p>Happy experimenting!</p>