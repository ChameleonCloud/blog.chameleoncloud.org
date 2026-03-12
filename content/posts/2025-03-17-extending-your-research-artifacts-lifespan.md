---
abstract: <p>Understanding how to preserve your valuable research on Chameleon Cloud
  is crucial for research continuity and community contribution. Here's how to extend
  the lifespan of your resources through smart public sharing</p>
authors:
- Marc Richardson
categories:
- Tips and Tricks
date: '2025-03-17 14:32:22+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/32/51/325117b9-2c4e-4ebf-8ecf-139b01358e1a/sunder-muthukumaran-n7ejhqwefei-unsplash.jpg
related_posts:
- slug: data-storage-management-and-sharing-on-chameleon
  title: Data Storage, Management, and Sharing on Chameleon
- slug: where-do-i-put-my-data-chameleon
  title: Where Do I Put My Data in Chameleon?
- slug: transferring-large-data-flows-chameleon
  title: Transferring Large Data Flows on Chameleon
slug: extending-your-research-artifacts-lifespan
subtitle: How to Preserve Your Valuable Data on Chameleon Cloud
title: Extending Your Research Artifacts' Lifespan
---

<p><img src="https://chameleoncloud.org/media/filer_public/32/51/325117b9-2c4e-4ebf-8ecf-139b01358e1a/sunder-muthukumaran-n7ejhqwefei-unsplash.jpg"></p>

<p>Understanding how to preserve your valuable research on Chameleon Cloud is crucial for research continuity and community contribution. Here's how to extend the lifespan of your resources through smart public sharing.</p>

<h2>Understanding Chameleon's Resource Retention Policy</h2>

<p>Chameleon's <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/faq.html#what-happens-to-my-resources-when-my-allocation-expires">retention policy</a> varies significantly based on resource type and visibility. The table below shows the retention period (defined as the period occurring after allocation expiration) for various Chameleon resource types:</p>

<p> </p>

<table>
	<tbody>
		<tr>
			<th><span style="color: #000000;">Resource Type</span></th>
			<th><span style="color: #000000;">Retention Period</span></th>
		</tr>
		<tr>
			<td>KVM instances</td>
			<td>Auto-shutdown and shelving after 48 hours, deleted after 1 year</td>
		</tr>
		<tr>
			<td>Bare metal instances, leases, networks</td>
			<td>Deleted immediately</td>
		</tr>
		<tr>
			<td>Private resources (images, volumes, object stores)</td>
			<td>Retained for 1 year</td>
		</tr>
		<tr>
			<td>Public resources (images, volumes, object stores)</td>
			<td>Retained for 5 years</td>
		</tr>
		<tr>
			<td>SSH keys</td>
			<td>Retained for the project lifetime</td>
		</tr>
	</tbody>
</table>

<p> </p>

<p><strong>Public resources are stored for free for 5 years</strong> to ensure persistent access to valuable research artifacts. As a testbed dedicated to reproducible science, we encourage public sharing to bolster transparency in CS research.</p>

<h2>Make Your Work Public: The #1 Strategy for Long-Term Retention</h2>

<p>The most important takeaway from Chameleon's retention policy is this: <strong>Public resources are kept for 5 years, while private resources are only retained for 1 year at most. </strong>This is to ensure persistent access to valuable research artifacts that are needed for further validation, reproduciblity, or new research avenues. As a testbed decidated to reproducible science, we encourage public sharing to bolster transparency in CS research.</p>

<p>This significant difference makes sharing your work publicly the single most effective strategy for preserving your research artifacts and contributing to science reproducibility.</p>

<h3>Benefits of Making Your Resources Public</h3>

<ul>
	<li><strong>Extended retention (5 years vs. 1 year)</strong> - Your work remains accessible five times longer</li>
	<li><strong>Research reproducibility</strong> - Other researchers can verify and build upon your results</li>
	<li><strong>Community impact</strong> - Your contributions can help advance work in your field</li>
	<li><strong>Visibility for your research</strong> - Public resources can lead to citations and collaborations. (Hint: You can even track your artifact usage through our Trovi service.)</li>
	<li><strong>Scientific legacy</strong> - Your work remains available even after your project concludes</li>
</ul>

<h3>What Types of Resources Should You Make Public?</h3>

<p>Not all resources are suitable for public sharing. Here's what to consider making public:</p>

<h4>Highly Recommended for Public Sharing</h4>

<ul>
	<li>Custom images with research software stacks; experiment environments; Heat templates</li>
	<li>Datasets that could benefit other researchers (non-sensitive) or that are needed for reproducibility</li>
	<li>Experiment configurations that demonstrate novel approaches</li>
	<li>Benchmarking results for particular hardware configurations</li>
	<li>Jupyter Notebooks with your experiment orchestration and/or results analyses</li>
</ul>

<h4>Less Suitable for Public Sharing</h4>

<ul>
	<li>Resources containing sensitive or proprietary information</li>
	<li>Incomplete or untested configurations</li>
	<li>Temporary or intermediary resources</li>
	<li>Resources with hardcoded credentials</li>
</ul>

<h2>Making Chameleon Resources Public: Step-by-Step</h2>

<p><img src="https://www.chameleoncloud.org/media/filer_public/e4/2e/e42e65d7-ae4d-4380-b4db-c363957630e6/screenshot_2025-03-18_at_94459am.png"></p>

<p>Most resources on the Chameleon Testbed include a <code>visibility</code> attribute that you can modify to make them public. Here's how to do it for different resource types:</p>

<h3>For Images (Bare Metal and Virtual Machine):</h3>

<ol>
	<li>Navigate to the appropriate site (<a href="https://chi.tacc.chameleoncloud.org">CHI@TACC</a>, <a href="https://chi.uc.chameleoncloud.org">CHI@UC</a>, or <a href="https://chameleoncloud.org/experiment/sites/kvm/">KVM@TACC</a> )</li>
	<li>Select "Compute" &gt; "Images" from the sidebar menu</li>
	<li>Find your image and click the dropdown in the "Actions" column</li>
	<li>Select "Edit Image" and change "Visibility" to "Public"</li>
	<li>Add documentation in the description and save changes</li>
</ol>

<div class="note">
<p><strong>Tip:</strong> When creating images with <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images.html#the-cc-snapshot-utility">cc-snapshot</a>, you can share them to your project automatically. These images can then be made public following the steps above.</p>
</div>

<h3>For Object Storage Containers:</h3>

<ol>
	<li>Navigate to "Object Store" &gt; "<a href="https://chameleoncloud.readthedocs.io/en/latest/technical/object-store.html">Containers</a>"</li>
	<li>Click on your container and then "Public Access" button</li>
	<li>Consider adding a README.md file explaining the contents</li>
</ol>

<h3>For <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/trovi.html">Trovi Artifacts</a>:</h3>

<ol>
	<li>Select your artifact in Trovi and click "Share"</li>
	<li>Check "Enable all users to find and launch"</li>
	<li>For maximum longevity, select "Publish with DOI" to publish to Zenodo</li>
</ol>

<h2>Using <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/trovi.html">Trovi</a> for Maximum Resource Longevity</h2>

<p>Chameleon's Trovi sharing portal is ideal for preserving research artifacts, with powerful integrations for long-term storage and version control.</p>

<h3>Trovi-Zenodo Integration</h3>

<p>When you publish a Trovi artifact with a DOI:</p>

<ul>
	<li>Your artifact is automatically archived in Zenodo with a permanent DOI</li>
	<li>The artifact becomes formally citable in academic publications</li>
	<li>All included resources follow Zenodo's long-term archival policies</li>
	<li>Your work becomes discoverable through both Trovi and Zenodo search interfaces</li>
</ul>

<h3>Trovi-Git Integration</h3>

<p>Trovi also supports Git integration for version-controlled artifacts:</p>

<ul>
	<li>Import existing Git repositories directly into Trovi artifacts</li>
	<li>Create new Trovi artifact versions from specific Git commits or branches</li>
	<li>Export Trovi content to Git repositories for collaborative development</li>
	<li>Link your artifact to external repositories on GitHub, GitLab, or other platforms</li>
</ul>

<p>To create a Trovi artifact:</p>

<ol>
	<li>Package your experiment in <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/jupyter.html">Jupyter</a> or prepare a Git repository</li>
	<li>For Jupyter: Click "Share" and select "Package as a new artifact"</li>
	<li>For Git: Use the "Import Artifact" function and select "Import from Git"</li>
	<li>Fill out metadata carefully and consider publishing with a DOI</li>
</ol>

<p>For detailed instructions on these integrations, see the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/trovi.html#creating-a-version-from-git">Trovi Git documentation</a> and <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/trovi.html#publishing-to-zenodo">Zenodo publishing guide</a>.</p>

<h2>Other Data Retention Strategies</h2>

<ul>
	<li>Keep your allocation active through <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/project.html#recharge-or-extend-your-allocation">timely renewals</a></li>
	<li>Download critical data before expiration (use the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/object-store.html#managing-object-store-using-the-cli">Swift command-line client</a> for large datasets)</li>
	<li>Use <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images.html#the-cc-snapshot-utility">cc-snapshot</a> to preserve your instances as images</li>
</ul>

<h2>Community Impact Through Sharing</h2>

<p>By making your artifacts public, you're contributing to a growing ecosystem of reusable research components. The most successful Chameleon projects have created resources used the researchers community, significantly amplifying their impact.</p>

<p>The key takeaway: If you want your Chameleon resources to have longevity and impact, make them public! The 5-year retention period benefits both your research continuity and the broader scientific community.</p>