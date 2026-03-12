---
abstract: <p>Reproducibility is a cornerstone of scientific computing, yet achieving
  consistent results across different hardware environments remains a significant
  challenge in HPC research. The MINCER project tackles this problem head-on by providing
  researchers with an automated performance measurement appliance on Chameleon Cloud.
  Using Docker containers and the PAPI framework, MINCER enables standardized collection
  of performance metrics across CPUs, NVIDIA GPUs, and AMD GPUs, making it easier
  to compare results and understand how system-level factors influence computational
  performance. This post explores how MINCER is helping make HPC experiments more
  reproducible and accessible to the research community.</p>
authors:
- Gonzalez, Jhonny
categories:
- User Experiments
date: '2025-10-31 19:05:01+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/31/ed/31ed5344-9756-4849-9e0d-f9d8743c3574/headshot.jpg
related_posts:
- slug: repeto-releases-report-on-challenges-of-practical-reproducibility-for-systems-and-hpc-computer-science
  title: REPETO Releases Report on Challenges of Practical Reproducibility for Systems
    and HPC Computer Science
- slug: autoappendix-towards-one-click-reproduction-of-computational-artifacts
  title: 'AutoAppendix: Towards One-Click Reproduction of Computational Artifacts'
- slug: building-mpi-clusters-on-chameleon-a-practical-guide
  title: 'Building MPI Clusters on Chameleon: A Practical Guide'
slug: introducing-mincers-performance-measurement-and-reproducibility-appliance
subtitle: Building a Standardized Framework for Reproducible Performance Measurements
  Across Diverse HPC Architectures
title: "Introducing MINCER\u2019s Performance Measurement and Reproducibility Appliance"
---

<p>A common occurrence in computer systems research is the struggle with reproducibility, which is the ability to rerun experiments while obtaining exact or similar results. Experiments involve differences in hardware, software, and configurations which make reproducibility difficult especially for complex high performance computing environments. Our project, <a href="https://icl.utk.edu/files/print//mincer-poster.pdf">MINCER</a> (Monitoring Infrastructure for Network and Computing Environment Research), addresses the issue with a developing performance and reproducibility appliance on Chameleon Cloud. MINCER provides utility for monitoring, collecting, and comparing performance data across CPUs and GPUs (NVIDIA and AMD) in a consistent manner. The goal is to make it easier for researchers to replicate results and understand how system level factors influence performance. A push towards improved reproducibility and performance visibility with MINCER helps ensure scientific results are trustworthy, portable, and comparable across computing platforms.</p>

<h2>Research Overview</h2>

<p>MINCER automates the setup and monitoring of experiments using Docker containers that include performance measurement tools like PAPI (Performance Application Programming Interface). With PAPI, we are able to log system metadata (hardware, OS, GPUs) and performance metrics such as power usage, memory operations, and instruction rates. In the appliance, we include various example proxy applications such as XSBench, LULESH, Gunrock, and 3D-UNET to demonstrate reproducibility on real workloads. Each proxy application runs on different architectures for CPUs, AMD GPUs, and NVIDIA GPUs available on Chameleon cloud with the same scripts to follow proper comparisons. We use PAPI to collect metrics for performance, energy, etc., to help users identify bottlenecks or variations across runs. Reducing complexity across experiment setups with MINCER enables Chameleon users to collect accurate and repeatable measurements without needing to manually configure each environment. The HPC community benefits by making reproducible performance studies more accessible and standardized.</p>

<h2>Experiment Implementation</h2>

<p>We use Chameleon-bare-metal instances to run experiments since they allow full control of operating systems and hardware environment as it is significant for accurate performance measurements. We use the command line to download the MINCER appliance, build docker images based on the hardware being CPU, AMD, or NVIDIA, and execute our experiments with a python script. The results are automatically logged with timestamps, system metadata, and PAPI metrics. The hardware catalog is essential since it lets us determine the right nodes for our AMD and NVIDIA GPU experiments. To start, it may be best to try the CPU based tests before CPU and move to GPU from there.</p>

<p>MINCER relies on Chameleon's bare-metal reconfiguration to ensure consistent hardware performance across runs. The ability to customize the software environment using Docker and having OS-level access allows us to use specific versions of PAPI, CUDA, and ROCm. Without Chameleon, this experiment would be harder since Chameleon already provides a great level of control and various resources available to test and use.</p>

<h2>Artifacts</h2>

<p>Our files and code are available on GitHub. We are currently cleaning and updating files to have a complete version of this experiment to share. This repository will include setup scripts, performance measurement examples, and the data collection utilities for PAPI on CPU, AMD, and NVIDIA platforms. We show how to collect performance and energy metrics in the XSBench, LULESH, Gunrock, and 3D-UNET proxy apps. We are currently working on setting up an artifact to make it easier to share with other Chameleon users.</p>

<h2>User Interview</h2>

<p><img src="https://chameleoncloud.org/media/filer_public/31/ed/31ed5344-9756-4849-9e0d-f9d8743c3574/headshot.jpg" width="50%"></p>

<p><strong>How do you stay motivated through a long research project?</strong></p>

<p>There are a few things I do to stay motivated. One is to focus on breaking the project down into small milestones. It motivates me when I know I am progressing through those tasks. I also accept that hitting a wall is a part of the process. I know that I will be reaching out to my mentor or peers with any questions I have. Letting them know about these issues helps guide me to new attempts to get through the frustration.</p>

<p><strong>What has been a tough moment for you either in your life or throughout your career? How did you deal with it? How did it influence your future work direction?</strong></p>

<p>The toughest moment was not academic, but instead personal. I had chosen that I would be leaving my home and family to pursue a Master's degree. I had avoided making plans that would take me far from my hometown, which is where I completed my undergraduate studies. At first it was difficult, but over time, I got used to calling my family and talking to them about how it had been and what I was up to. It helped to talk to them and I enjoyed planning what to do when I was back. This was also accompanied by exploring the new city I was in and having fun with friends. This experience has helped me accept being far from home and even look forward to the new places I will get to see.</p>

<p><strong>Why did you choose this direction of research?</strong></p>

<p>My research direction in performance measurement came from a great internship I attended during summer 2024. I enjoyed learning more about how metrics are gathered and the types of metrics used. I later met my current mentor, Dr. Shirley Moore who helped me use the skills I learned into my current research. Now, I get to continue learning more about performance and the tools that help record it.</p>

<p><strong>Thank you for sharing your knowledge with the Chameleon community!</strong></p>