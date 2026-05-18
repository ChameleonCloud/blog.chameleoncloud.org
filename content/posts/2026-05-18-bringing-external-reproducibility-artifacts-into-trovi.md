---
abstract: "<p>Trovi is expanding beyond user-uploaded artifacts to include selected
  reproducibility artifacts from major computer science conferences like EuroSys, SOSP,
  and SC. We’ve built a pipeline to crawl, index, and surface these external artifacts
  in the same interface you already use, and connected them to Chameleon so you can
  go from discovering an interesting artifact to running it on bare metal in minutes.</p>"
authors: 
- Paul Marshall
categories:
- Tips and Tricks
- Featured
date: '2026-05-18'
featured: true
hide_image: false
image: https://chameleoncloud.org/media/filer_public/62/f5/62f5db0c-462f-4608-b376-67e4a1442169/external-artifact-page.png
related_posts:
- slug: running-artifact-evaluations-on-chameleon
  title: Running Artifact Evaluations on Chameleon
- slug: the-practical-reproducibility-opportunity
  title: The Practical Reproducibility Opportunity
- slug: using-chameleon-for-artifact-evaluation
  title: Using Chameleon for Artifact Evaluation
slug: bringing-external-reproducibility-artifacts-into-trovi
subtitle: Bridging the gap between finding a systems research artifact and actually running it
title: Bringing External Reproducibility Artifacts Into Trovi
---

<p><a href="https://trovi.chameleoncloud.org">Trovi</a> is a collection of digital artifacts that support user-uploaded reproducible research and education — things like packaged experiments, tutorials, and appliances that can be launched directly on a system like Chameleon. Once an artifact is in Trovi, you can spin it up (e.g. as a Jupyter notebook that can then launch a bare metal system) and rerun or adapt it without rebuilding everything from scratch.</p>

<p>To expand the number of artifacts our users can discover and run, we're extending Trovi to include selected artifacts from publications that appeared in major computer science conference proceedings like EuroSys, SOSP, SC, and others. We've already released a small set of external artifacts on Trovi and plan to continue adding new artifacts over time. Read more below about this process and what we hope comes of it!</p>

<h2>Why External Artifacts in Trovi?</h2>

<p>Reproducibility artifacts are increasingly available, but they are not always easy to find and even less easy to run.</p>

<p>Collections like <a href="https://sysartifacts.github.io/">sysartifacts</a> have done a great job gathering systems artifacts tied to papers and conferences. However, once you find an interesting artifact, you still have to figure out where to run it and how to set up the environment. That gap between discovering an artifact and actually reproducing it is exactly what we're working to reduce by bringing external artifacts into Trovi and connecting them to resources, starting with the Chameleon testbed.</p>

<p>Our goal with this work is to meet artifacts where they already live, then bring them closer to a testbed where users can explore and run them. Our approach boils down to the following:</p>

<ul>
  <li>Crawling and indexing external sites, with an initial focus on systems-related reproducibility artifacts such as those listed at sysartifacts.github.io</li>
  <li>Surfacing those external artifacts in Trovi so you can browse them alongside native Trovi artifacts</li>
  <li>Providing a launch path that connects them to testbed resources for exploration and potential reproduction</li>
</ul>

<h2>How External Artifacts Look in Trovi</h2>

<p><img src="https://chameleoncloud.org/media/filer_public/62/f5/62f5db0c-462f-4608-b376-67e4a1442169/external-artifact-page.png" alt="Example External Artifact in Trovi showing the External Artifact badge and metadata" style="max-width: 100%;"></p>

<p><em>Example External Artifact in Trovi</em></p>

<p>External artifacts are clearly marked with a grey "External Artifact" badge (shown in the figure above) so you can distinguish them from artifacts created directly in Trovi. These artifacts contain the following:</p>

<ul>
  <li><strong>External Artifact label:</strong> Each entry includes an "External Artifact" badge</li>
  <li><strong>Description and metadata:</strong> The artifact page shows what our crawl could infer, such as:
    <ul>
      <li>A link to the artifact repository</li>
      <li>The conference or venue it was associated with, if applicable</li>
      <li>A brief description of the artifact</li>
      <li>Any author names that could be identified</li>
    </ul>
  </li>
  <li><strong>Provenance and claiming:</strong> At the bottom of the description, you'll see a note indicating that the artifact was discovered via a crawl. Authors are invited to contact us if they'd like to claim the artifact and manage it themselves on Trovi.</li>
</ul>

<p>This keeps the original source and attribution intact while making external artifacts discoverable in the same interface you already use for native Trovi artifacts.</p>

<p>To give a sense of what is already available, some of the first external artifacts we've added include:</p>

<ul>
  <li><a href="https://trovi.chameleoncloud.org/dashboard/artifacts/5e6af498-971e-4b5c-8520-00a7233bb45c">Reducing Energy Bloat in Large Model Training (SOSP'24)</a></li>
  <li><a href="https://trovi.chameleoncloud.org/dashboard/artifacts/f38df4cf-6d1a-4fa3-b3f5-49ac82df7e99">Halfmoon: Log-Optimal Fault-Tolerant Stateful Serverless Computing (SOSP'23)</a></li>
  <li><a href="https://trovi.chameleoncloud.org/dashboard/artifacts/156644a9-b6bb-42f7-beff-a681ad58b763">ndzip-gpu: Efficient Lossless Compression of Scientific Floating-Point Data on GPUs (SC'21)</a></li>
</ul>

<p>These and future external artifacts are being added from top conferences such as Supercomputing (SC), SOSP, EuroSys, and others.</p>

<h2>Launching External Artifacts on Chameleon</h2>

<p><img src="https://chameleoncloud.org/media/filer_public/f5/96/f5967201-8244-4f8e-b11f-5a5b59c1ae6a/launching-external-artifact.png" alt="Jupyter notebook to launch an environment for an external artifact" style="max-width: 100%;"></p>

<p><em>Jupyter notebook to launch an environment for an external artifact</em></p>

<p>External artifacts also include a launch option that ties them to actual hardware, with behavior tailored to their external nature. Integration with testbeds is accomplished with:</p>

<ul>
  <li><strong>Launch on Chameleon:</strong> Clicking the launch button provisions a notebook (shown in the figure above) that, when run, will set up a bare metal Ubuntu 24 system on Chameleon and clone the artifact's repository into it</li>
  <li><strong>Single node baseline:</strong> This gives you a clean single-node Ubuntu environment with the code already in place, ideal for exploring artifacts and potentially reproducing any that work on a single Linux machine</li>
  <li><strong>Manual setup for complex cases:</strong> For artifacts that require more complex setups — such as multiple nodes, different operating systems, or custom orchestration — you'll still need to follow the artifact's instructions to complete the configuration. If you do that for any artifacts, we'd love it if you turned your work into a Trovi artifact to provide a fully reproducible version for others in the community!</li>
</ul>

<p>In other words, we are not rewriting external artifacts, but we are giving you a faster path from an interesting repository to running on a testbed.</p>

<h2>Help Shape What Comes Next</h2>

<p>This is an early phase of integrating external artifacts, and we'd like your help to guide it. If you're an author of an external artifact that now appears in Trovi, let us know if you'd like to claim it or add more details. If you manage to fully set up an external artifact, consider packaging it as a Trovi artifact so others can reproduce your configuration more easily. And if you know of other good reproducibility artifacts or repositories in the computer systems space, please share them on our <a href="https://forum.chameleoncloud.org/t/discussion-finding-and-sharing-reproducibility-artifacts-for-systems-research/184">forum post</a> — we're actively looking for more sources to index.</p>

<p>Each external artifact added to Trovi is manually reviewed and approved by the Chameleon team, so you can expect these entries to appear gradually over time as we curate and validate them.</p>

<p>As always, if you have questions, run into any issues, or want to discuss how best to use external artifacts with Trovi and Chameleon, reach out to us via the <a href="https://chameleoncloud.org/user/help/">Help Desk</a>.</p>
