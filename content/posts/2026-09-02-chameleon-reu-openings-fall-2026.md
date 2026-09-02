---
abstract: <p>We're looking for two undergraduate researchers to join the Chameleon
  team this fall, funded by NSF's Research Experiences for Undergraduates program.
  One position works on Trovi and artifact reproducibility, the other on automated
  verification of testbed hardware. Roughly 10 hours a week, and remote applicants
  are welcome.</p>
authors:
- Paul Marshall
categories:
- Announcements
- Featured
date: '2026-09-02 14:00:00+00:00'
featured: true
hide_image: false
image: https://chameleoncloud.org/media/filer_public/51/cf/51cf2baf-03f8-4e29-a938-ddf2be37bd03/reu-fall-2026.png
related_posts:
- slug: tips-and-tricks-getting-access-to-chameleon-as-a-student
  title: Getting Access to Chameleon as a Student Researcher
- slug: bringing-external-reproducibility-artifacts-into-trovi
  title: Bringing External Reproducibility Artifacts Into Trovi
slug: chameleon-reu-openings-fall-2026
subtitle: Two undergraduate research positions this fall
title: "Join the Chameleon Team: Fall 2026 REU Openings"
---

<p>We're excited to announce a new opportunity to join the Chameleon team for the fall semester or quarter as a Research Experience for Undergraduates (REU) student. As a Chameleon REU you become part of our team and help us investigate how AI can improve experimental methodology and reproducibility. We usually find that a time commitment of roughly 10 hours a week is consistent with a normal course load while still letting students make real progress on a research project. Both positions can be done remotely, so remote applicants are welcome.</p>

<p>These positions are funded by NSF's Research Experiences for Undergraduates program. Eligibility is limited to U.S. citizens, nationals, and permanent residents enrolled in an undergraduate degree program.</p>

<p><strong><a href="https://docs.google.com/forms/d/e/1FAIpQLSdUpmWIve5PY63W-oEVqHCv3HAVar2O4gwC1sfizYqmNUp5Bg/viewform">Apply here.</a></strong></p>

<p>We are recruiting for two positions this fall, described in full below.</p>

<h2>Trovi</h2>

<p>Contribute to research on scientific artifact discoverability and reproducibility by sourcing, evaluating, and integrating systems research artifacts into <a href="https://trovi.chameleoncloud.org/">Trovi</a>, a high-quality, searchable repository of research and educational artifacts. Trovi aims to make computer systems research not just archived but genuinely reusable, which requires both a well-curated collection and a platform designed around what that collection actually looks like. This position works on both sides of that problem: building out and analyzing the artifact corpus, and improving the search, metadata, and execution mechanisms that determine whether the best artifacts surface and actually run.</p>

<p>Responsibilities may include:</p>

<ul>
  <li>Discover, evaluate, and integrate systems research artifacts.</li>
  <li>Assess scope and reusability; occasionally perform lightweight validation or reproduction checks of the artifacts.</li>
  <li>Extract and normalize metadata (DOIs, versions, descriptions, licenses, and so on).</li>
  <li>Write concise summaries and usage notes; apply a consistent taxonomy, categorizing artifacts with appropriate labels and tags.</li>
  <li>Identify coverage gaps, and engage with authors to clarify missing details.</li>
  <li>Refine curation criteria, schemas, and tooling (templates, scripts).</li>
  <li>Investigate and implement discovery mechanisms (search, ranking, filtering, quality signals) that surface high-value artifacts within a large and uneven collection.</li>
  <li>Extend how artifacts are represented and executed, so that a broader class of artifacts can be launched and reproduced on testbed resources.</li>
  <li>Analyze coverage, usage, and trends, and report insights that shape the dataset, platform design, and evidence for subsequent analyses and publications.</li>
</ul>

<p>Useful background: Python, Git, and the command line; some familiarity with Linux, containers, or Jupyter; interest in reproducibility and research infrastructure. Web development or API experience is a plus.</p>

<h2>Verification for Reproducibility</h2>

<p>Contribute to research on the verifiability and reproducibility of experimental environments by developing automated correctness checks for resources provisioned on research cloud testbeds. Testbeds publish detailed descriptions of the hardware they offer, but nothing today closes the loop between that description and the machine a researcher actually receives. Failed disks, swapped network cards, missing memory, and dead accelerators all drift silently away from the catalog description. This position works on closing that loop: determining which of a testbed's claims about its resources can be checked and how, implementing and testing those checks against real hardware, and reporting results in a form that both a researcher and an automated AI agent can act on.</p>

<p>Responsibilities may include:</p>

<ul>
  <li>Investigate what a testbed asserts about its resources and identify which claims are verifiable in practice.</li>
  <li>Implement checks that compare a provisioned environment against its published description (hardware inventory, network configuration, accelerators, storage, and so on).</li>
  <li>Test checks against real allocations across heterogeneous hardware; diagnose and characterize the mismatches that turn up.</li>
  <li>Design failure output that is legible to humans and machine-readable for automated tooling.</li>
  <li>Distinguish stale or incorrect records from genuinely faulty hardware, and route each appropriately.</li>
  <li>Extend coverage to current images and platforms; refine the check framework, packaging, and documentation.</li>
  <li>Analyze results across resources and report trends that inform testbed operations, validation methods, and evidence for subsequent analyses and publications.</li>
</ul>

<p>Open questions include how far a check can trust the resource it is running on, how much of a claim can be verified from inside the environment versus outside it, and how these checks should compose into a larger system that plans, provisions, and validates environments on a researcher's behalf.</p>

<p>Useful background: Python, Git, and the Linux command line (SSH, package management, reading logs, inspecting system state); coursework in operating systems, computer architecture, networking, or distributed systems. Familiarity with bare-metal provisioning or cloud APIs is a plus.</p>

<h2>How to Apply</h2>

<p>Fill out <a href="https://docs.google.com/forms/d/e/1FAIpQLSdUpmWIve5PY63W-oEVqHCv3HAVar2O4gwC1sfizYqmNUp5Bg/viewform">the application form</a> and tell us which position interests you. If you have questions about either project, reach out through the <a href="https://forum.chameleoncloud.org/">Chameleon forums</a> or the <a href="https://www.chameleoncloud.org/user/help/ticket/new/guest/">Help Desk</a>.</p>

<p>We're looking forward to working with you!</p>
