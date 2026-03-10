---
abstract: <p>Trovi helps you package and share computational artifacts that run on
  Chameleon, from Jupyter notebooks to complete experimental workflows. Whether you're
  importing code from GitHub, organizing artifacts into Collections, collaborating
  with co-authors, or publishing work to get a citable DOI, these tips will help you
  make the most of Trovi for your research and teaching.</p>
authors:
- Mark Powers
categories:
- Tips and Tricks
date: '2025-11-19 20:04:51+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/7b/ff/7bff7f50-4513-4cc2-b502-39caeb44d686/image2.png
slug: from-github-to-publication-using-trovi-effectively
subtitle: How to organize, share, and publish your Chameleon experiments
title: 'From GitHub to Publication: Using Trovi Effectively'
---

<p>Over the last decade of the testbed, Chameleon users have launched hundreds of experiments, and from these experiments, generated a lot of digital artifacts in the form of Jupyter Notebooks, programs, scripts, images, and complex appliances. To simplify the process of packaging and sharing these artifacts, we developed <a href="http://trovi.chameleoncloud.org">Trovi</a> - a service for storing, sharing, and finding computer science artifacts that run on shared Cyberinfrastructure like Chameleon.</p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/e2/2f/e22f2c80-616d-4b6f-ac28-156a9e927134/image1.png"></p>

<p>Trovi integrates with Chameleon on multiple levels. With one simple click on Trovi, you can "launch" an artifact and set it up into an experimental environment in a preconfigured JupyterLab server on Chameleon, letting you automatically orchestrate Chameleon resources. You can also take work that you have stored on Chameleon (like a folder on your Jupyter interface or an experiment on a bare metal server) and easily upload it to Trovi as a private or public artifact. Finally, you can even import Trovi artifacts from GitHub repositories (assuming you have appropriate GitHub permissions) with a simple config file.</p>

<p>To date, over 280 artifacts have been shared on the platform, including fully reproducible experiments, educational courses, and software examples.</p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/7b/ff/7bff7f50-4513-4cc2-b502-39caeb44d686/image2.png"></p>

<p>The <a href="https://trovi.chameleoncloud.org/dashboard">Trovi Dashboard</a> is the primary interface for users, where you can browse, search, and launch artifacts as well as create and manage your own artifacts. In addition to the dashboard, we also serve an <a href="https://chameleoncloud.gitbook.io/trovi/api-reference/artifacts">open API</a> where you can perform the same actions programmatically.</p>

<p>In the past few months, we've been working to improve Trovi's capabilities, and wanted to share some tips for how to make the most of the service for your research and education.</p>

<h2>Making the most of Trovi for your experiments</h2>

<p><strong>Starting with existing work</strong>. If you already have code or notebooks in a GitHub repository, you can <a href="https://chameleoncloud.org/blog/2025/04/21/importing-github-repositories-to-trovi-a-step-by-step-guide/">import them directly to Trovi</a> using an RO-crate config file—no need to reorganize your existing work structure. Once imported, anyone can launch your artifact with a single click, automatically setting it up in a preconfigured JupyterLab environment on Chameleon. This makes it easy to turn your GitHub projects into immediately executable experiments. You can also use existing Trovi artifacts as starting points for your own work: browse artifacts related to your research area, launch them to see how they work, then modify and save your own version.</p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/41/2a/412a2511-b183-4ffe-bfea-5edfe78d6c5f/image3.png"></p>

<p><strong>Organizing related artifacts with Collections</strong>. With over 280 artifacts on Trovi, Collections help you group related work together. <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/sharing/packaging_artifacts.html#editing-related-artifacts">Link artifacts together</a> to create logical sequences or thematic groupings. For example, if you're submitting an experiment for conference evaluation, you might have one artifact that creates the environment and another that runs the analysis—linking them guides reviewers through the complete workflow. Educators can use Collections to organize course units that build on each other, like this <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/3785c5f5-4c98-4dae-b66d-9e693544a269">series on evaluating ML systems</a> or these <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/ee09076b-8507-49a1-9f85-ff8f020e7be7">getting started tutorials</a>. Collections appear both in your artifact's description and in the sidebar when other artifacts link to yours.</p>

<p><strong>Collaborating and sharing strategically</strong>. Trovi's sharing controls let you work at your own pace. Keep artifacts private while you're iterating, then use <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/sharing/packaging_artifacts.html#adjusting-sharing-settings">private sharing links</a> to share work-in-progress with specific collaborators or reviewers without making it publicly discoverable. When you're ready to add co-authors, you can <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/sharing/packaging_artifacts.html#editing-artifacts">edit artifact roles</a> to give others full editing permissions or just credit them as contributors. This is particularly useful for student projects, collaborative research, or when you want feedback before publishing.</p>

<p><strong>Publishing and tracking impact</strong>. When your work is ready to share broadly, Trovi makes it easy to get credit. Each artifact has a citation button that generates a properly formatted reference and BibTeX entry—useful for papers, grant reports, or your CV. You can also <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/sharing/packaging_artifacts.html#adjusting-sharing-settings">publish directly to Zenodo</a> to get a DOI and ensure long-term archival. The dashboard shows metrics for each of your artifacts including views and launches, helping you understand which work is getting traction and providing concrete numbers for impact statements in grants or tenure packets.</p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/9c/1a/9c1abf55-9e54-42f5-8cf4-9512057ba0ca/image4.png"></p>

<p><strong>Better artifact management</strong>. Trovi gives you complete control over your artifacts throughout their entire lifecycle. You can create new artifacts, manage versions, adjust sharing settings between public and private, add collaborators or co-authors, and delete artifacts when they're no longer needed. This flexibility supports diverse workflows—whether you're iterating on a research experiment, maintaining educational materials that need regular updates, creating demos for conferences, or prototyping new approaches. With granular permission controls and full lifecycle management, you can organize and share your work exactly how you need to, without friction.</p>

<h2>The future of Trovi</h2>

<p>We are still working on improving Trovi, and soon are planning to add better search features and improve the user experience. As always, if you have any feedback or suggestions, please feel free to let us know via the <a href="https://chameleoncloud.org/user/help/">Help Desk</a>.</p>