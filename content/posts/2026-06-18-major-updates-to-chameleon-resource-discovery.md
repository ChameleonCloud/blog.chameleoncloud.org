---
abstract: <p>Chameleon's redesigned resource discovery service is now in preview, offering
  availability-aware browsing across all CHI sites. Find free bare metal nodes in
  real time, generate ready-to-run reservation commands, and get conflict detection
  — all in one unified interface.</p>
authors: []
categories:
- Announcements
date: '2026-06-18'
featured: true
hide_image: true
image: https://chameleoncloud.org/media/filer_public/db/8b/db8b7089-7852-4e0d-84d2-6f6016f1f1eb/resource_discovery_ui.png
related_posts: []
slug: major-updates-to-chameleon-resource-discovery
subtitle: Resource discovery on Chameleon now supporting availability-aware browsing
  and more!
title: Redesigned Chameleon Resource Discovery in Preview Now
---


<p>The Chameleon Cloud team is excited to announce the release of a preview of our redesigned service for resource discovery on Chameleon. With the new <a href="https://discover.chameleoncloud.org/"><strong>Chameleon Resource Browser</strong></a>, you can browse bare metal nodes (and, coming soon, VMs) across <strong>all CHI sites</strong> using both the same hardware properties exposed in the legacy service <em>and</em> real-time availability data for when nodes are actually free to use. No more finding a node on the resource discovery page, only to discover that it is booked for two weeks.</p>

<strong><a href="https://discover.chameleoncloud.org/">Click here</a></strong> to check out the new browser!

<img src="https://chameleoncloud.org/media/filer_public/3a/b0/3ab0b83d-a8d3-4aaa-981f-5676ab4bdd5f/first.png">
<img src="https://chameleoncloud.org/media/filer_public/7b/ee/7beef25d-87b0-4050-bca9-e48dd07bb553/second.png">

<p>Please note that these updates to resource discovery do <strong>not</strong> affect existing workflows or scripts for reserving Chameleon resources. Lease creation using the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/reservations/index.html">Horizon GUI</a>, <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/cli/index.html">OpenStack CLI</a>, and <a href="https://python-chi.readthedocs.io">python-chi</a> remains the same as before. Our <a href="https://chameleoncloud.org/hardware/">old resource browser</a> is also not going away (yet) — you can still access it in the usual place (on the <a href="https://chameleoncloud.org/">Chameleon Portal</a> homepage, first item under the "Experiment" tab in the menu bar). We plan to replace the old browser completely with the new one in the coming months and will make an announcement of the exact date in an upcoming changelog to give users sufficient notice. Read more about the differences between the old and new browsers in our <a href="https://chameleoncloud.org/learn/frequently-asked-questions/#toc-what-changed-with-the-new-chameleon-resource-discovery-browser-">updated FAQ</a>.</p>

<p>We welcome your feedback on the new service and interface. You can leave feedback in the browser itself by clicking on the <strong>feedback icon</strong> in the top right corner of the page. While you familiarize yourself with the new browser, let us know about any bugs you find, features you think could enhance discovery, missing components that hinder your work, or anything you find confusing. Love the new interface? Let us know what excites you as well!</p>

<img src="https://chameleoncloud.org/media/filer_public/c0/d3/c0d335dc-231c-4f48-be57-bb4f6e8a7061/resource_discovery_ui_feedback.png">

<h2>What's New in the Resource Browser</h2>

<ul>
  <li><strong>Filter by availability</strong> — find hardware that's free starting now, within 7 days, or at a custom time and duration.</li>
  <li><strong>Auto-generated reservation commands</strong> — copy ready-to-run snippets for the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/cli/index.html">OpenStack CLI</a> or <a href="https://python-chi.readthedocs.io">python-chi</a>, pre-filled with your selection.</li>
  <li><strong>Conflict detection + auto-adjust</strong> — warns when your time window clashes with existing reservations and shifts you to the next free slot in one click.</li>
  <li><strong>Unified multi-site search</strong> — browse UC, TACC, and NCAR together, with availability shown per site.</li>
  <li><strong>Multi-node cart</strong> — select multiple nodes across sites and reserve by node type or specific node name.</li>
  <li><strong>Deeper filtering with live counts</strong> — GPU, CPU, cache, architecture, RAM, FPGA, network, storage (NVMe/SSD), and RDMA (GPUDirect, NVMe-oF) facets, each with running result counts.</li>
  <li><strong>Richer node details</strong> — processor internals, network rates, storage, BIOS, chassis, rack placement, job types, and energy monitoring.</li>
  <li><strong>Live availability status</strong> — Available / Reserved / Maintenance badges on every node.</li>
  <li><strong>In-app feedback</strong> — send feedback or open a <a href="https://chameleoncloud.org/user/help/">support ticket</a> directly from the browser.</li>
  <li><strong>Coming soon</strong> — virtual machine (VM) resources.</li>
</ul>

<p>Happy experimenting!</p>
