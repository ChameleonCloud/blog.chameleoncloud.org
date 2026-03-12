---
abstract: "<p>Whether you're provisioning your first bare metal node or building complex\
  \ edge computing experiments, finding the right documentation quickly can make the\
  \ difference between a productive research day and hours of frustration. Chameleon's\
  \ documentation ecosystem has grown to include multiple specialized resources\u2014\
  each designed for different needs. This guide will help you navigate to the right\
  \ place, the first time.</p>"
authors:
- Marc Richardson
categories:
- Tips and Tricks
date: '2025-07-21 16:53:55+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/6c/a6/6ca6e73f-68ac-42b1-be86-de51bc6d59a4/hackathon-600x400.jpg
related_posts:
- slug: chameleon-changelog-for-may-2025
  title: Chameleon Changelog for May 2025
- slug: chameleon-changelog-for-april-2025
  title: Chameleon Changelog for April 2025
- slug: major-documentation-update
  title: A (Major) Documentation Update
slug: the-hitchhikers-guide-to-chameleon-documentation-finding-answers-fast
subtitle: How to navigate Chameleon docs effectively
title: "The Hitchhiker\u2019s Guide to Chameleon Documentation: Finding Answers Fast"
---

<p>Whether you're provisioning your first bare metal node or building complex edge computing experiments, finding the right documentation quickly can make the difference between a productive research day and hours of frustration. Chameleon's documentation ecosystem has grown to include multiple specialized resources—each designed for different needs. This guide will help you navigate to the right place, the first time.</p>

<p><img alt="Image" src="https://chameleoncloud.org/media/filer_public/fd/cc/fdcc0a47-d9d0-455d-a12d-0e2cf8ad3f25/the-hitchhikers-guide-to-the-galaxy.jpeg"></p>

<p>We hope this helps as you navigate Chameleon and all the wonderful opportunities it offers. If you have recommendations or tips for us about our documentation, please reach out our documentation officer, Marc Richardson with comments (mtrichardson@uchicago.edu).</p>

<h3><strong>Your Documentation Roadmap</strong></h3>

<p>Think of Chameleon's documentation as a toolkit where each resource serves a distinct purpose. Here's when to reach for each tool:</p>

<h4><strong>Start with ReadTheDocs for Technical How-Tos</strong></h4>

<p>The official <a href="https://chameleoncloud.readthedocs.io/en/latest/">Chameleon Cloud Documentation</a> on ReadTheDocs is your technical command center. This is where you'll find comprehensive guides covering everything from your first instance launch to advanced FPGA programming. The documentation walks you through core workflows—resource discovery, reservations, monitoring—and dives deep into site-specific capabilities across TACC, UC, NCAR, and Edge locations.</p>

<p><strong>Best for:</strong> Step-by-step technical procedures, understanding Chameleon's architecture, learning about specific site capabilities, and mastering advanced features like custom images and complex deployments.</p>

<h4><strong>Check FAQs for Policy and Context</strong></h4>

<p>While your first instinct might be to check <a href="https://chameleoncloud.org/learn/frequently-asked-questions/#toc-general">FAQs</a> for troubleshooting, Chameleon's FAQ section actually focuses on the bigger picture. Here you'll find answers about project applications, allocation policies, user eligibility, and security best practices. This is also where you'll learn how to properly cite Chameleon in your publications and understand the consequences of policy violations.</p>

<p><strong>Best for:</strong> Understanding usage policies, project management questions, security requirements, citation guidelines, and eligibility criteria.</p>

<h4><strong>Automate with Python-CHI Documentation</strong></h4>

<p>If you're ready to move beyond the GUI and automate your workflows, the <a href="https://python-chi.readthedocs.io/en/latest/">python-chi documentation</a> is essential. This Python API lets you script everything from resource reservations to complex experimental setups. The documentation includes practical code examples you can adapt, whether you're working in Jupyter notebooks or building standalone automation tools.</p>

<p><strong>Best for:</strong> Scripting repetitive tasks, integrating Chameleon into your research pipeline, and building custom tools for your experiments.</p>

<h4><strong>Explore Edge Computing with CHI@Edge Docs</strong></h4>

<p>For those venturing into edge computing experiments, <a href="https://chameleoncloud.gitbook.io/chi-edge">CHI@Edge</a> has its own dedicated documentation. This specialized resource covers device enrollment, edge-specific workflows, and the unique considerations of distributed edge experiments. Don't assume that standard Chameleon workflows apply—edge computing often requires different approaches.</p>

<p><strong>Best for:</strong> Edge device management, understanding edge-specific constraints, and designing distributed experiments.</p>

<h4><strong>Share and Reproduce with Trovi</strong></h4>

<p><a href="https://chameleoncloud.gitbook.io/trovi">Trovi documentation</a> guides you through Chameleon's reproducibility platform. If you're looking to share your experimental artifacts (Jupyter notebooks, datasets, workflows) or reproduce someone else's research, this is your starting point. The documentation covers the entire artifact lifecycle from upload to collaboration.</p>

<p><strong>Best for:</strong> Packaging experiments for sharing, finding reproducible research artifacts, and understanding Chameleon's approach to open science.</p>

<h4><strong>Stay Current with the Blog and Forum</strong></h4>

<p>The <a href="https://chameleoncloud.org/blog/">Chameleon Blog</a>—especially the <a href="https://chameleoncloud.org/blog/category/tips/">Tips and Tricks</a> series you're reading now—bridges the gap between documentation and real-world usage. These posts often highlight new features, provide practical workflows (like <a href="https://chameleoncloud.org/blog/2024/11/18/building-mpi-clusters-on-chameleon-a-practical-guide/">building MPI clusters</a>), and share community wisdom. The <a href="https://forum.chameleoncloud.org/">Forum</a> complements this with user-submitted questions, troubleshooting discussions, and official announcements about maintenance or new hardware.</p>

<p><strong>Best for:</strong> Learning about new features, finding community-tested solutions, staying informed about platform changes, and getting help with specific use cases.</p>

<h4><strong>Do It Live with YouTube Webinars</strong></h4>

<p>Here's an often-overlooked resource: <a href="https://www.youtube.com/@ChameleonCloud">Chameleon's YouTube webinar series</a>. These recorded sessions demonstrate complex workflows in real-time, with experts explaining their thought process as they navigate the platform. Seeing someone actually click through the interface while explaining concepts can illuminate things that written documentation might miss.</p>

<p><strong>Best for:</strong> Visual learning, understanding complex multi-step processes, and seeing best practices demonstrated by experienced users.</p>

<h4><strong>Don't Forget OpenStack Documentation</strong></h4>

<p>Since Chameleon builds on <a href="https://www.openstack.org/">OpenStack</a>, the upstream <a href="https://docs.openstack.org/2025.1/">OpenStack documentation</a> can help you understand underlying concepts and find useful CLI features—especially for advanced networking or when you need to dig deeper into how services work. While not everything applies to Chameleon's specific configuration, it's invaluable for building your foundational knowledge.</p>

<p><strong>Best for:</strong> Understanding core cloud computing concepts, advanced networking theory, and troubleshooting edge cases that require deep technical knowledge.</p>

<h3><strong>Matching Questions to Resources</strong></h3>

<p><img alt="Picture of a decision tree with colored blocks on the ends of the branches." src="https://chameleoncloud.org/media/filer_public/b5/02/b502d2a8-0c9c-4e11-9bbb-5b7cbe988f06/decision_tree.png" width="200px"></p>

<p>Here's a quick decision tree for finding answers efficiently:</p>

<ul>
	<li><strong>"How do I configure/deploy/use...?"</strong> → ReadTheDocs</li>
	<li><strong>"Am I allowed to...?"</strong> or <strong>"What's the policy on...?"</strong> → FAQs</li>
	<li><strong>"I want to automate this task..."</strong> → python-chi documentation</li>
	<li><strong>"I'm working with edge devices..."</strong> → CHI@Edge documentation</li>
	<li><strong>"How can I share my experiment?"</strong> → Trovi documentation</li>
	<li><strong>"What's new?" or "Has anyone tried...?"</strong> → Blog and Forum</li>
	<li><strong>"Show me how it's done..."</strong> → YouTube webinars</li>
	<li><strong>"I need low-level building blocks or to dive deep behind..."</strong> → OpenStack documentation</li>
</ul>

<h3><strong>Pro Tips for Documentation Success</strong></h3>

<ol>
	<li>
	<p><strong>Use multiple resources</strong>: Complex problems often require insights from several documentation sources</p>
	</li>
	<li><strong>Check dates</strong>: Especially for blog posts and forum discussions—Chameleon evolves quickly</li>
	<li><strong>Contribute back</strong>: Found a novel solution? Share it on the forum or suggest documentation improvements</li>
	<li><strong>Build your reference library</strong>: Bookmark frequently-used pages and create your own notes linking different resources</li>
</ol>

<p>The key to productive research on Chameleon isn't just knowing where to look—it's understanding that each documentation resource was designed for specific types of questions. By matching your needs to the right resource, you'll spend less time searching and more time advancing your research.</p>