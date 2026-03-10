---
abstract: <p>Learn how to leverage Trovi's new GitHub integration to easily create
  and update reproducible research artifacts. This step-by-step guide shows you how
  to configure your GitHub repository with RO-crate metadata and import it directly
  into Trovi, enabling better collaboration and adherence to FAIR principles for your
  experiments.</p>
authors:
- Mark Powers
categories:
- Tips and Tricks
date: '2025-04-21 16:19:52+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/d3/99/d399f8f0-4c85-4b41-8b93-587f8ae93e8e/trovi-json.png
slug: importing-github-repositories-to-trovi-a-step-by-step-guide
subtitle: Streamline Your Research Workflow with Trovi's New GitHub Integration
title: 'Importing GitHub Repositories to Trovi: A Step-by-Step Guide'
---

<h1>Importing GitHub Repositories to Trovi: A Step-by-Step Guide</h1>

<h2>What is Trovi?</h2>

<p>Reproducibility is a major challenge in computer science research. While various software tools help package programs for reproduction on different machines, these solutions often fall short when dealing with bare metal experiments or complex topologies. That's why we developed <a href="https://trovi.chameleoncloud.org/dashboard/">Trovi</a> — an open-source service for packaging and sharing reproducible artifacts designed for testbeds.</p>

<p>Trovi serves as a flexible, standards-based service that can be adapted for various testbeds, not simply a Chameleon-specific repository. Currently, Chameleon users have shared over 200 artifacts publicly on Trovi. These artifacts serve diverse purposes, from educational modules to reproducible storage research, and experiment patterns that showcase testbed capabilities. When used with Chameleon, Trovi integrates seamlessly with the platform, enabling you to "launch" artifacts into a JupyterLab environment that automatically authenticates you and comes pre-equipped with commonly used libraries.</p>

<h2>Recent Improvements to Trovi</h2>

<p>Based on your feedback, we've been continuously enhancing the Trovi experience. Last fall, we introduced a <a href="https://trovi.chameleoncloud.org/dashboard/">preview of the new Trovi dashboard</a>, which improved user experience by making artifact searching and browsing faster and more intuitive.</p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/1f/c1/1fc1fc53-edeb-4f99-8d42-7541759c8eec/screenshot_2025-04-11_at_110903am.png"></p>

<p><a href="https://chameleoncloud.org/blog/2025/03/03/chameleon-changelog-for-february-2025/">Last month</a>, we announced important updates specifically for artifact authors on the ability to create and edit artifacts directly in the dashboard. Today, we're excited to share more details about our latest enhancement: seamless GitHub integration.</p>

<h2>GitHub Integration with Trovi</h2>

<p>When we surveyed our users, we discovered that over 90% were already using GitHub to share their experiments. Previously, while you could import artifact contents via git, you still had to manually configure the artifact's metadata. Our new first-class GitHub import changes that — now you can configure your GitHub repo with a metadata file for your artifact that includes details like title, description, and authorship.</p>

<p>Updating artifacts is now much simpler, too. Authors can make changes to their GitHub repository as normal, then click "Import" to create a new version in Trovi. This integration leverages GitHub's collaboration and sharing tools, addressing the challenge of multiple people working on an artifact simultaneously.</p>

<h3>The Power of RO-Crate</h3>

<p>The metadata file we use follows the <a href="https://www.researchobject.org/ro-crate/">RO-crate specification</a>. This format allows for detailed descriptions of a package, ensuring that future users can fully understand how it was created and how it should be used. Our adoption of this widely-used standard underscores Trovi's design as a portable, interoperable service rather than a platform-specific tool. RO-crate offers several advantages:</p>

<ul>
	<li>It's supported by a large community of users who have developed specialized tools</li>
	<li>It's highly extendable, allowing support for different experimental environments and metrics in the future</li>
	<li>It helps make artifacts align with <a href="https://www.go-fair.org/fair-principles/">FAIR principles</a> (Findable, Accessible, Interoperable, and Reusable)</li>
</ul>

<p>By keeping this metadata file closer to the artifact contents, authors can more easily adhere to these FAIR principles in their work, regardless of which testbed platform they ultimately use.</p>

<h2>How to Import an Artifact from GitHub: A Step-by-Step Guide</h2>

<p>Now that you understand the benefits of our GitHub integration, let's walk through the process of importing your GitHub repository as a Trovi artifact:</p>

<h3>1. Creating your GitHub Repository</h3>

<p>If you already have a public GitHub repository with your artifact files, you can skip to step 2.</p>

<p>Otherwise, login to <a href="https://github.com">GitHub</a> and go to <a href="https://github.com/new">the new repository page</a>. Follow the instructions to set up a new repository, making sure it's set to public.</p>

<p>Next, you'll see instructions for the command line. First, create a new directory for your artifact and navigate to it:</p>

<pre>mkdir my-trovi-artifact
cd my-trovi-artifact
</pre>

<p>Then copy and paste the repository instructions from GitHub into your command line.</p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/13/7a/137af4cd-632f-4db6-90d5-0de666faa526/github-repo-init.png"></p>

<p>After executing these commands, you should see output similar to:</p>

<pre>Initialized empty Git repository in /Users/mark/my-trovi-artifact/.git/
[main (root-commit) d8f7364] first commit
 1 file changed, 1 insertion(+)
 create mode 100644 README.md
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 237 bytes | 237.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:Mark-Powers/my-trovi-artifact.git
 * [new branch]      main -&gt; main
branch 'main' set up to track 'origin/main'.
</pre>

<p>If you refresh GitHub, you'll see a single file, <code>README.md</code>.</p>

<h3>2. Generating Your Metadata File</h3>

<p>For this step, you'll need <a href="https://pip.pypa.io/en/stable/installation/">Python and pip installed</a>. Run the following command to install the Trovi command line client:</p>

<pre>pip install git+https://github.com/ChameleonCloud/troviclient.git
</pre>

<p>You can verify the installation by running <code>trovi artifact generate -h</code>, which will display the available options:</p>

<pre>$ trovi artifact generate -h
Usage: trovi artifact generate [OPTIONS]

Options:
  --name TEXT                     The name of the artifact  [required]
  --short-description TEXT        Short one-line description of the artifact.
                                  [required]
  --description TEXT              Long explanation of artifact.  [required]
  --tag TEXT                      Relevant tags. See `trovi tag list`. Can be
                                  included multiple times.  [required]
  --environment_type [chameleon_jupyterlab]
                                  Type of experiment environment this artifact
                                  runs in.
  --author TEXT                   Author information formatted as
                                  'name:institution'. Can be included multiple
                                  times.  [required]
  --output_file TEXT              File to save metadata to. Defaults to
                                  `trovi.json`
  -h, --help                      Show this message and exit.
</pre>

<p>To view all allowed values for the <code>--tag</code> option, run <code>trovi tag list</code>.</p>

<p>Now, run <code>trovi artifact generate</code> with your artifact's details. Here's an example (split across multiple lines for clarity):</p>

<pre>trovi artifact generate \
  --name "Mark's Trovi Artifact" \
  --short-description "A demonstration artifact." \
  --description "This Trovi artifact is for demonstrating how to import from GitHub for the Chameleon blog." \
  --author "Mark Powers:markpowers@uchicago.edu:University of Chicago" \
  --tag example
</pre>

<h3>3. Uploading Your Metadata File to GitHub</h3>

<p>After generating the metadata file, you'll need to add it to your GitHub repository. Check the status with <code>git status</code> to confirm that a new file named <code>trovi.json</code> has been created:</p>

<pre>$ git status
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add &lt;file&gt;..." to include in what will be committed)
	trovi.json

nothing added to commit but untracked files present (use "git add" to track)
&lt;/file&gt;</pre>

<p>Add, commit, and push the file to GitHub:</p>

<pre>git add trovi.json
git commit -m "Add trovi.json"
git push
</pre>

<p>When you refresh your GitHub repository, you should see <code>trovi.json</code> in the file list.</p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/d3/99/d399f8f0-4c85-4b41-8b93-587f8ae93e8e/trovi-json.png"></p>

<h3>4. Submitting Your Repository to Trovi</h3>

<p>The final step is to import your GitHub repository into Trovi:</p>

<ol>
	<li>Navigate to the <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/add">Trovi dashboard</a> and click "Import" at the top.</li>
	<li>If you're not already logged in, you'll need to log in with your Chameleon account.</li>
	<li>Paste your GitHub repository URL into the form and click "Add Artifact."</li>
</ol>

<p>You should now see your artifact with all its metadata loaded into Trovi. By default, artifacts are imported as private. If you're satisfied with everything and want to make it publicly available, click "Edit" and change the visibility setting to "Public."</p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/35/7b/357b0aad-6131-4e39-a21a-6d959583bcff/artifact-page.png"></p>

<h3>5. Keeping Your Artifact Updated</h3>

<p>When you make changes to your experiment and commit them to GitHub, you can easily update your Trovi artifact:</p>

<ol>
	<li>Go to the "Edit" page for your artifact in Trovi</li>
	<li>Click "Import" at the bottom of the page to pull in the latest changes from GitHub</li>
</ol>

<p>This simple workflow ensures your Trovi artifact always reflects the current state of your GitHub repository.</p>

<h2>Conclusion</h2>

<p>The enhanced GitHub integration in the Trovi dashboard represents a significant step toward making experiment reproducibility more accessible for researchers. By streamlining the process of importing and updating artifacts from GitHub repositories, we've addressed a key workflow need expressed by our users.</p>

<p>These changes are just the beginning of our plans to expand Trovi beyond JupyterLab experiments and potentially to other testbed environments. The use of standards like RO-crate ensures that Trovi remains an adaptable, portable solution for experiment reproducibility across various research infrastructures. In future updates, we'll continue refining this workflow and introducing new features to the Trovi dashboard based on your feedback.</p>

<p>We encourage you to try out this new GitHub integration feature and let us know about your experience. Your input is invaluable as we work to make Trovi an even more powerful tool for computer science research.</p>