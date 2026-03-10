---
abstract: <p>The AutoAppendix project evaluates computational artifact reproducibility
  across SC24 conference submissions, revealing that most researchers struggle with
  creating truly replicable experiments despite their importance to scientific validity.
  By developing one-click reproduction templates for the Chameleon Cloud platform,
  this research aims to transform how computational scientists share and validate
  their work, potentially saving countless hours of frustration for both authors and
  reviewers.</p>
authors:
- "Klaus Kra\xDFnitzer"
categories:
- User Experiments
date: '2025-01-27 17:08:27+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/3a/d1/3ad10588-427b-4ccf-99aa-71d6605d75fd/avatar_huaeeec3b03949da7c9e65bafb346c02e7_1014633_270x270_fill_lanczos_center_3.png
slug: autoappendix-towards-one-click-reproduction-of-computational-artifacts
subtitle: Streamlining Scientific Validation Through Automated Reproducibility Infrastructure
title: 'AutoAppendix: Towards One-Click Reproduction of Computational Artifacts'
---

<p><em>Editor's note: Klaus Kraßnitzer presented this work at the <a href="http://reproduciblehpc.org">Community Workshop on Practical Reproducibility in HPC</a>, which we hosted just around the corner from SC24 in November 2024. We're delighted to share more details about this important contribution to reproducible science.</em></p>

<p>Reproducibility is the cornerstone of scientific research, yet it remains challenging in computational science. The <a href="https://ucsc-ospo.github.io/report/osre24/tuwien/autoappendix/20240904-kkrassni/">AutoAppendix</a> project takes a strategic approach to enhance artifact evaluation processes within the SC Conference Series by leveraging Chameleon's flexible infrastructure. This initiative recognizes high-performance computing as a pivotal domain where scientific rigor and reproducibility are paramount, aiming to streamline the often tedious process of reproducing computational research artifacts.</p>

<h2>Research Overview</h2>

<p>The primary aim of the AutoAppendix project is to conduct a comprehensive evaluation of <a href="https://sc24.supercomputing.org/program/papers/reproducibility-appendices-badges/">Artifact Description/Artifact Evaluation (AD/AE) appendices</a> submitted to SC24, particularly those utilizing Chameleon Cloud. By systematically testing these appendices, the project explores current capabilities and limitations in fostering reproducibility, identifying areas where automation can be introduced or enhanced.</p>

<p>Through evaluating multiple appendices from the SC24 conference, we discovered common patterns and challenges in artifact reproduction. Many artifacts suffer from incomplete documentation, failed software installations, or missing experiment data. Even when experiments conclude successfully, it's often unclear what the expected results should be. Our research highlighted the value of containerization solutions (Docker, VirtualBox, Singularity) and breaking experiments into distinct, well-documented steps.</p>

<h2>Experimental Implementation on Chameleon</h2>

<p>Our experimental methodology involved provisioning various Chameleon nodes to evaluate a subset of SC24 submissions over a period of five weeks. We used hardware ranging from standard compute nodes to specialized GPU configurations based on each artifact's requirements. The evaluation process was labor-intensive, often requiring multiple attempts to successfully execute experiments, particularly those needing specialized hardware like NVIDIA A100 GPUs.</p>

<p>A notable discovery was that only one out of 45 submissions leveraged Chameleon's <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/jupyter.html">Jupyter interface</a> and <a href="https://chameleoncloud.org/experiment/share">Trovi</a> artifact sharing service, which enables one-click reproducibility. This significantly simplified the evaluation process compared to other submissions that required manual configuration. The stark contrast between this streamlined approach and the tedious setups of other artifacts highlighted the potential for improvement in the reproducibility workflow.</p>

<p>Based on our evaluations, we identified key factors that contributed to successful reproduction:</p>

<ul>
	<li>Clear documentation of hardware and software requirements</li>
	<li>Automated dependency installation scripts</li>
	<li>Progress indicators for long-running operations</li>
	<li>Containerized environments to ensure consistent execution</li>
	<li>Well-structured experiment steps with expected outputs</li>
</ul>

<h2>Experiment Artifacts</h2>

<p>Read the full AutoAppendix report <a href="https://repeto.cs.uchicago.edu/2024/09/18/2024-summer-of-reproducibility-another-great-year-promoting-practical-reproducibility/">here</a>.</p>

<p>To address the identified challenges and promote better reproducibility practices, we developed three new Trovi templates that authors can use to automate their experiments:</p>

<ol>
	<li><strong><a href="https://chameleoncloud.org/experiment/share/a1665a4a-8e34-4229-a6be-e50b5b76fc40">Docker Template</a>:</strong> Installs the Docker environment and NVIDIA container toolkit when a GPU is available, executing sample operations inside a container.</li>
	<li><strong><a href="https://chameleoncloud.org/experiment/share/02e813c8-e025-4f7c-ae70-596f69b9e039">Nix Template</a>:</strong> Installs the Nix package manager and launches a reproducible environment for computing tasks like generating Mandelbrot set visualizations.</li>
	<li><strong><a href="https://chameleoncloud.org/experiment/share/9fc09e03-b9ee-4916-a7e6-5363e7fbc8af">Guix Template</a>:</strong> Provisions a node with the Guix package manager installed, demonstrating reproducible artifact execution with a real-world example from a 2006 paper.</li>
</ol>

<p>These templates all share a common structure with a central configuration file, making it easy for researchers to adapt them to their specific needs.</p>

<h2>About the Author</h2>

<p><img src="https://www.chameleoncloud.org/media/filer_public/3a/d1/3ad10588-427b-4ccf-99aa-71d6605d75fd/avatar_huaeeec3b03949da7c9e65bafb346c02e7_1014633_270x270_fill_lanczos_center_3.png"></p>

<p><a href="https://ucsc-ospo.github.io/author/klaus-kra%C3%9Fnitzer/">Klaus Kraßnitzer</a> is a Master’s student in the field of Computer Engineering at Vienna University of Technology (TU Wien). His research interests focus on Distributed and High Performance Computing as well as Computer-Aided Verification. Klaus's work with the <a href="https://ucsc-ospo.github.io/report/osre24/tuwien/autoappendix/20240904-kkrassni/">AutoAppendix</a> project during the <a href="https://repeto.cs.uchicago.edu/2024/09/18/2024-summer-of-reproducibility-another-great-year-promoting-practical-reproducibility/">UCSC Summer of Reproducibility</a> 2024 builds upon his expertise in systems engineering and scientific computing methodologies.</p>