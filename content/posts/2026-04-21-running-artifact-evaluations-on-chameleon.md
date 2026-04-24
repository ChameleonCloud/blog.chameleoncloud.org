---
abstract: "<p>Chameleon has supported artifact evaluations at more than 30 events
  across 16 major HPC and systems conferences. This guide distills those lessons into
  practical advice for AE organizers: how to plan hardware access, structure author
  and reviewer workflows, and keep reproducible artifacts alive after the evaluation
  closes.</p>"
authors:
- Marc Richardson
categories:
- Tips and Tricks
- Featured
date: '2026-04-21'
featured: true
hide_image: true
image: https://chameleoncloud.org/media/filer_public/ba/18/ba18782e-1296-4c59-b40f-28fb93d8a0b9/trovi_growth.png
related_posts:
- slug: using-chameleon-for-artifact-evaluation
  title: Using Chameleon for Artifact Evaluation
- slug: the-practical-reproducibility-opportunity
  title: The Practical Reproducibility Opportunity
- slug: extending-your-research-artifacts-lifespan
  title: Extending Your Research Artifact's Lifespan
slug: running-artifact-evaluations-on-chameleon
subtitle: A practical guide for AE organizers using shared research infrastructure
title: Running Artifact Evaluations on Chameleon
---

<p><em>This guide is written primarily for AE organizers planning to use Chameleon for their evaluation, though authors and reviewers will find the workflows section relevant to their own preparation.</em></p>

<p>The vision of <a href="https://chameleoncloud.org/blog/2023/03/20/the-practical-reproducibility-opportunity/">practical reproducibility</a>, where published experiments can be re-run, extended, and built upon as naturally as they can be read about, has been gaining real traction in the computer science research community. One measure of that is the growth of <a href="https://trovi.chameleoncloud.org/dashboard/">Trovi</a>, an experiment sharing platform integrated with shared infrastructure like Chameleon: of roughly 425 public artifacts currently hosted, 364 have been added by you, our users, since 2023. Those artifacts aren't just sitting idle either: on average, a user-uploaded artifact is launched around 60 times per year by about 16 unique users, and authors continue to actively maintain them, releasing at least 2 additional versions after initial upload on average. This suggests researchers are treating Trovi less as an archive and more as a living platform for infrastructure-integrated science, which is exactly the kind of engagement that makes reproducibility meaningful in practice.</p>

<p><img src="https://chameleoncloud.org/media/filer_public/ba/18/ba18782e-1296-4c59-b40f-28fb93d8a0b9/trovi_growth.png" alt="Cumulative growth of public artifacts on Trovi from 2020 to early 2026. Key inflection points are annotated on the graph." style="max-width: 80%;"></p>

<p><em><strong>Figure 1.</strong> Cumulative growth of public artifacts on Trovi from 2020 to early 2026. Key inflection points are annotated on the graph.</em></p>

<p>Conferences and journals contribute to this growing supply of reproducible artifacts by hosting artifact evaluations (AEs), which challenge authors to package their research in a reproducible manner and award badges to artifacts based on reviewer feedback. These venues have been using Chameleon to supply resources for AE authors and reviewers since at least 2021, and over the past few years — through the <a href="http://repeto.cs.uchicago.edu">NSF-funded REPETO project</a> — we've significantly expanded that partnership. To date, we've supported reproducibility initiatives at more than 30 events across 16 major HPC and systems conferences, including SC, MLSys, SOSP, OSDI, FAST, EuroSys, and ATC, among others. That experience has given us a clear picture of what makes evaluations on shared infrastructure go smoothly, and what tends to derail them. This blog seeks to disseminate those lessons more systematically.</p>

<p><img src="https://chameleoncloud.org/media/filer_public/c4/7f/c47f5cac-c3ab-4c6f-82ca-0f0578020ff9/artifact_distribution.png" alt="Distribution of 425 public Trovi artifacts across three categories: Environment and Experiment Pattern Artifacts, Educational Artifacts, and Reproducible and Data Artifacts." style="max-width: 80%;"></p>

<p><em><strong>Figure 2.</strong> Distribution of 425 public Trovi artifacts across three category groups — environment & experiment, educational, and reproducible & data artifacts — and their intersections. Categories were assigned automatically by Google Gemini 1.5 Pro in deterministic mode based on artifact titles and descriptions; author-supplied tags were not used, as many artifacts have none assigned. Overlapping regions reflect artifacts Gemini classified into multiple categories. These counts are hypothesis-generating and have not been validated against human judgment or other reference standards.</em></p>

<h2>Quick Reference: AE Organizer Checklist</h2>

<p>Below is a short reference for AE organizers planning to use Chameleon for evaluation summarizing the key tips of this blog. You can read more detailed guidance on specific checklist items in the sections that follow.</p>

<p><strong>6+ weeks before the evaluation</strong>:</p>
<ul>
  <li>Request PI eligibility on Chameleon if you don't already have it</li>
  <li><em>Survey authors on hardware requirements</em>; share the <a href="https://chameleoncloud.org/hardware/">resource discovery</a> page and <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images/index.html">available base images</a> (see survey example <a href="https://docs.google.com/forms/d/e/1FAIpQLScCZYWqpRHTJXZDkU2mvDE_9GwuYWn2XAc-oJ0FwURkQGex2Q/viewform?usp=dialog">here</a>)</li>
  <li><em>Make <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/reservations/index.html">advance reservations</a></em> for high-demand nodes based on survey responses and AE timelines</li>
  <li>Create separate Chameleon projects for authors and reviewers</li>
  <li>Set <a href="https://chameleoncloud.readthedocs.io/en/latest/user/project.html#set-su-budgets-for-project-members">per-user SU budgets</a> on both projects</li>
</ul>

<p><strong>Author preparation phase</strong>:</p>
<ul>
  <li><a href="https://chameleoncloud.readthedocs.io/en/latest/user/project.html#manage-users">Add authors</a> to project as survey responses come in</li>
  <li><em>Schedule an author office hours</em> session covering the availability calendar, base images, and a Chameleon walkthrough</li>
  <li>Communicate any unsupported hardware requirements early and work with author and/or the Chameleon team on alternatives</li>
  <li>Authors build, test, and <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images/cc_snapshot.html">snapshot</a> their environments; <em>package as <a href="https://trovi.chameleoncloud.org">Jupyter notebooks on Trovi</a></em> where feasible</li>
</ul>

<p><strong>Review phase</strong>:</p>
<ul>
  <li>Add reviewers to their project; schedule a separate reviewer onboarding session</li>
  <li>Encourage <em>shared environments per artifact and short lease lengths</em> (1–2 days)</li>
  <li><em>Set a hardware reservation deadline</em> for reviewers based on author requirements ahead of any period of high activity</li>
</ul>

<p><strong>Post-evaluation</strong>:</p>
<ul>
  <li>Encourage authors to publish their artifacts to <a href="https://trovi.chameleoncloud.org">Trovi</a> and <a href="https://zenodo.org/">Zenodo</a></li>
  <li>Share the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/daypass/index.html">DayPass option</a> with authors for future replication requests</li>
</ul>

<h2>Why Chameleon for AE?</h2>

<p>The core reason Chameleon works well for AE is that it gives reviewers access to the same experiment environment the authors used. Chameleon offers a wide range of <a href="https://chameleoncloud.org/hardware/">configurable resources</a>, from bare metal nodes with specialized hardware like A100 and H100 GPUs, FPGAs, and custom storage configurations; to <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/index.html">virtual machines</a> for experiments that don't require dedicated hardware; to <a href="https://chameleoncloud.org/experiment/chiedge/">containers</a> for experimentation in the edge to cloud continuum — making it possible to support a broad variety of systems experiments. Critically, authors can <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images/cc_snapshot.html">snapshot their configured environments</a> so that reviewers deploy the exact same software stack in a single step, eliminating the most common source of setup friction. <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/reservations/index.html">Advance reservations</a> let authors and reviewers lock in needed hardware before the evaluation window opens. Packaged experiments can be <a href="https://trovi.chameleoncloud.org/dashboard">shared via Trovi</a>, an infrastructure-integrated experiment repository, where they remain accessible long after the evaluation closes for teaching, follow-on research, or future replication. For authors who want to extend access beyond the reviewer pool, <a href="https://www.chameleoncloud.org/blog/2022/01/24/interactive-science-made-easy-with-chameleon-daypass/">DayPass</a> allows anyone to reproduce a result without needing a full Chameleon account.</p>

<p>That said, Chameleon is a shared research testbed, not a dedicated AE platform, and it has real constraints. High-demand nodes are often booked out long in advance. Not every hardware configuration researchers might need is available. And like any shared system, it requires some coordination to use well. The rest of this guide is about how to do that coordination effectively.</p>

<h2>Planning Your AE: The Steps That Matter Most</h2>

<p>The most common issue we encounter with AEs is hardware availability. GPU nodes on Chameleon are frequently booked out three weeks or more in advance, and an evaluation window that opens with authors and reviewers scrambling for resources that aren't available is a frustrating experience for everyone. Almost all of this is preventable with a bit of upfront work.</p>

<p><strong>Set up projects and user access.</strong> Organizers will need PI status on Chameleon before they can create a project — if you don't already have this, request it early, as approval can take a couple days. We recommend creating separate projects for authors and reviewers to keep allocations clean and, where anonymity matters, to avoid accidental cross-visibility. Chameleon supports <a href="https://chameleoncloud.readthedocs.io/en/latest/user/project.html#adding-and-removing-new-members">bulk member addition</a> and a <a href="https://chameleoncloud.readthedocs.io/en/latest/user/project.html#user-roles">PI delegate feature</a> for distributing the management workload. Setting a <a href="https://chameleoncloud.readthedocs.io/en/latest/user/project.html#set-su-budgets-for-project-members">per-user SU budget</a> at the project level is also worth doing early. Doing so prevents any single user from inadvertently consuming a disproportionate share of the allocation.</p>

<p><strong>Survey requirements from authors early.</strong> Before the evaluation window opens, send a short survey to accepted authors asking about their hardware requirements: specifically whether they need bare metal, what GPU configurations they expect to use, and roughly how long their experiments take to run. This doesn't need to be elaborate; even a simple Google Form will do. (<a href="https://docs.google.com/forms/d/e/1FAIpQLScCZYWqpRHTJXZDkU2mvDE_9GwuYWn2XAc-oJ0FwURkQGex2Q/viewform?usp=dialog">Click here</a> to view a sample template that you can use as a starting point.) The goal is to surface demand before it becomes contention. Point authors to Chameleon's <a href="https://chameleoncloud.org/hardware/">resource discovery page</a> and share the list of <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images/index.html">available base images</a> (including CUDA and other ML-ready environments) so they can assess fit before responding. The survey also serves as your primary tool for identifying hardware requirements that Chameleon can't support, e.g., configurations like multi-node NVLink setups or very large GPU counts may exceed what's available. If you spot gaps early, bring them to the Chameleon team; with enough lead time, we can often work with partner infrastructure providers to find alternatives.</p>

<p>In cases where the timeline is tight and you can't gather author requirements far enough in advance, a useful fallback is to reserve high-demand nodes as a block on the calendar based on your best estimate of demand. As the evaluation window approaches, you can release that block and let authors and reviewers make their own reservations. This isn't a perfect solution, as it doesn't prevent other users from grabbing those resources when you release them again for the AE, but it buys time and keeps options open. If you use this approach, communicate the release timing clearly to participants so they know when to log on and make reservations. And in either case: remind authors and reviewers to reserve only what they actually need. A two-hour experiment doesn't warrant a two-day lease.</p>

<p><strong>Make reservations before the evaluation windows open.</strong> Once you have a picture of hardware demand, make advance reservations for high-demand nodes as early as possible, ideally as soon as the evaluation timeline is known. Standard leases run up to one week and you can make multiple leases for node types with sufficient capacity (but be sure to avoid any <a href="https://chameleoncloud.org/learn/frequently-asked-questions/#toc-what-are-the-policies-on-chameleon-resource-usage-">lease stacking</a>); if your evaluation requires longer continuous access to less-contested resources, discuss this with the Chameleon team by opening a <a href="https://chameleoncloud.org/user/help/">Help Desk ticket</a>. It's also worth setting a deadline for authors and reviewers to make their own reservations ahead of any period of high activity. If reviewers are active starting July 14, for example, having them reserve hardware by June 14 ensures no one arrives on day one without access and no availability for weeks.</p>

<p><strong>Schedule a Chameleon webinar or office hours for onboarding.</strong> We recommend scheduling separate sessions for authors and reviewers; both groups benefit from a live walkthrough and can have different needs. An author session should cover the availability calendar, base images, the snapshotting workflow, and Trovi packaging. A reviewer session can focus on accessing a pre-built environment and what to expect from a well-packaged artifact. The Chameleon team is happy to co-facilitate these sessions. Reach out via the <a href="https://chameleoncloud.org/user/help/">Help Desk</a> to coordinate timing.</p>

<h2>Workflows During the AE</h2>

<p>Following some or all of the tips above should ensure that, come time for reviewers to evaluate authors' artifacts, everyone has hardware available for running experiments. Below, we discuss a few more suggestions to assist authors and reviewers with workflows once they are using Chameleon resources during the AE.</p>

<p><em>(A more extensive description of these guidelines is available in our <a href="https://zenodo.org/records/15306610">Community Report on the Challenges for Practical Reproducibility in HPC and Systems Research</a>.)</em></p>

<p><strong>Authors.</strong> Before the evaluation window opens, encourage authors to build and test their artifacts on Chameleon rather than waiting for reviewers to surface problems. The typical workflow is to start from a <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images/index.html">Chameleon base image</a>, i.e., CUDA, TensorFlow, or another pre-configured environment, customize it for the experiment, and then <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images/cc_snapshot.html">snapshot</a> the result so reviewers can deploy it without any setup work. Where feasible, packaging the experiment as a <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/jupyter/index.html">Jupyter notebook</a> and sharing it via <a href="https://trovi.chameleoncloud.org/dashboard/">Trovi</a> is worth encouraging. It gives reviewers a self-contained, launchable artifact rather than a set of instructions to follow. See examples of Trovi artifacts packaged for other conference AEs <a href="https://trovi.chameleoncloud.org/dashboard/artifacts?tags=reproducible+research">here</a>.</p>

<p><strong>Reviewers.</strong> Where possible, reviewers of the same artifact should share a single deployed environment rather than each spinning up their own. This reduces resource consumption and surfaces environment issues collaboratively rather than in parallel. Encourage reviewers to coordinate timing: one reviewer deploys, others reproduce results within the same environment. Keep lease lengths short (one to two days is usually sufficient) to keep resources flowing across the reviewer pool rather than sitting idle.</p>

<h2>Beyond the Evaluation</h2>

<p>The value of a well-packaged artifact doesn't have to end when the evaluation closes. Experiments shared via <a href="https://trovi.chameleoncloud.org/dashboard">Trovi</a> remain publicly accessible and launchable long after the evaluation window closes, which can be useful for teaching, follow-on research, and future replication. Trovi's recently updated dashboard makes it easier to manage artifacts over time, including improved GitHub integration so authors can keep artifacts in sync with their repositories as experiments evolve. From Trovi, authors can also publish to <a href="https://zenodo.org/">Zenodo</a> to obtain a citable DOI for long-term archival. For authors who receive replication requests after the evaluation, <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/daypass/index.html">DayPass</a> allows them to grant one-off access to anyone without requiring a full Chameleon account, serving as a lightweight way to keep artifacts alive and useful well beyond the conference.</p>

<h2>Additional Resources</h2>

<ul>
  <li><a href="https://www.chameleoncloud.org/blog/2021/11/22/using-chameleon-for-artifact-evaluation/">Using Chameleon for Artifact Evaluation</a> — the original 2021 guide</li>
  <li><a href="https://www.chameleoncloud.org/blog/2022/01/24/interactive-science-made-easy-with-chameleon-daypass/">Interactive Science Made Easy with Chameleon DayPass</a></li>
  <li><a href="https://www.youtube.com/watch?v=jx5xjK5DDLM">How to Organize Artifact Evaluations with Shared Infrastructure</a> — webinar by Bogdan Stoica (January 2026)</li>
  <li><a href="https://zenodo.org/records/15306610">Community Report on Practical Reproducibility in HPC</a> — SC24 workshop report</li>
  <li><a href="https://chameleoncloud.org/hardware/">Chameleon Hardware Catalog</a></li>
  <li><a href="https://chameleoncloud.readthedocs.io/en/latest/user/project.html">Chameleon Project Management Documentation</a></li>
  <li><a href="https://trovi.chameleoncloud.org/">Trovi Artifact Repository</a></li>
</ul>
