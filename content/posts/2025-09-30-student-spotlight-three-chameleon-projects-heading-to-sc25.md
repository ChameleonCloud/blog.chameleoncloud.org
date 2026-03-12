---
abstract: <p>This summer, three talented students used Chameleon to tackle challenges
  ranging from wildlife conservation to reproducibility and AI-assisted documentation.
  Their innovative work earned them spots at the ACM Student Research Competition
  at SC'25, where they'll present posters on autonomous bioacoustic monitoring, snapshot
  performance optimization, and intelligent documentation systems. Discover how Hudson
  Reynolds, Alex Tuecke, Zahra Temori, and Saieda Ali Zada leveraged Chameleon's infrastructure
  to create impactful solutions.</p>
authors: []
categories:
- User Experiments
date: '2025-09-30 18:38:27+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/49/1a/491aca35-f6c0-4c4d-9a43-ca4ce7946107/echoes_install.png
related_posts:
- slug: chameleon-takes-flight-at-sc24-advancing-research-and-collaboration
  title: 'Chameleon Takes Flight at SC24: Advancing Research and Collaboration'
- slug: chameleon-presents-at-sc23
  title: Chameleon presents AutoLearn, IndySCC'23 success, and more at SC'23
- slug: chameleon-at-sc-23
  title: Chameleon at SC '23
slug: student-spotlight-three-chameleon-projects-heading-to-sc25
subtitle: 'Bioacoustics, Snapshots, and AI: Student Innovations Pushing the Boundary
  of Science'
title: 'Student Spotlight: Three Chameleon Projects Heading to SC''25'
---

<p>This summer, three talented students used Chameleon to tackle challenges ranging from wildlife conservation to reproducibility and AI-assisted documentation. Their innovative work earned them spots at the <a href="https://sc25.supercomputing.org/program/posters/acm-student-research-competition/">ACM Student Research Competition at SC'25</a>, where they'll present posters on autonomous bioacoustic monitoring, snapshot performance optimization, and intelligent documentation systems. Discover how Hudson Reynolds, Alex Tuecke, Zahra Temori, and Saieda Ali Zada leveraged Chameleon's infrastructure to create impactful solutions.</p>

<p>This month's user experiment blog highlights groundbreaking work by summer students on Chameleon. We're thrilled that their research will be showcased at SC'25 in November through three posters at the ACM Student Research Competition: Zahra Temori's work on snapshot optimization, Saieda Ali Zada's AI-powered documentation assistant, and Hudson Reynolds and Alex Tuecke's autonomous bioacoustic monitoring system.</p>

<p>Read on to discover how these students pushed the boundaries of cloud testbed capabilities.</p>

<h2>Echoes of Earth</h2>

<p><img src="https://chameleoncloud.org/media/filer_public/bf/7c/bf7cd6cf-f9ae-4874-9c0c-b647862a3bc8/echoes_device.png"></p>

<p>In this project, students Hudson Reynolds and Alex Tuecke tackled an interesting problem involving solar panels, highly-sensitive microphones, and bengal tigers (oh my!). The students worked on developing a prototype system for real-time, inexpensive, high-quality soundscaping at scale to provide natural resource managers with bioacoustic information for biodiversity conservation. They created two key components: "Listener," a solar-powered recording and streaming device built with ESP32 and AudioMoth, and "Aggregator," based on Raspberry Pi 5, which collects audio streams from multiple Listeners over WiFi HaLow and performs local inference using the Cornell BirdNET model to analyze recordings.</p>

<p>The students leveraged Chameleon's infrastructure extensively for their cloud backend. They hosted their Grafana Dashboard, Prometheus metrics time series database, and InfluxDB3 analysis database on a Chameleon Kernel-Based Virtual Machine (CHI@KVM) and used the Chameleon Object Store (CHI@TACC) for storing raw recordings. They also utilized CHI@EDGE infrastructure and Balena Cloud Fleets to facilitate scalability, maintainability, and organization of their distributed sensor network. This cloud-testbed integration enabled them to build a complete end-to-end solution that eliminates the need for manual data retrieval from field devices.</p>

<p>At the end of the summer, the students had accomplished an impressive feat: they demonstrated that their system could sustain 25 concurrent audio streams without falling behind, achieving 81% average CPU utilization on the Aggregator. They plan to deploy the system at organic vineyards in Michigan, where it will provide real-time bioacoustic monitoring. The system could help reduce operational costs compared to industry-standard Wildlife Acoustics devices (which cost $600-$1000+) by eliminating the need for manual retrieval and expert maintenance, making large-scale biodiversity monitoring feasible for land managers.</p>

<p><strong>Link to poster:</strong> <a href="https://chameleoncloud.org/media/filer_public/9e/c0/9ec04238-2765-41aa-8649-debe540f73ae/echoes_of_earth_poster_hudsonalex.pdf" target="_blank">View Poster</a></p>

<p><strong>Link to abstract:</strong> <a href="https://chameleoncloud.org/media/filer_public/8f/c4/8fc4e85c-58e3-41b9-b0bb-57140a74fa3d/hudsonalexextendedabstract.pdf" target="_blank">View Abstract</a></p>

<h2>CC-Snapshot</h2>

<p><img src="https://chameleoncloud.org/media/filer_public/c2/58/c258dd46-9f69-40e7-8712-3e0de63ddf5d/cc-snapshot_graph.png"></p>

<p>In this project, student Zahra Temori evaluated the CC-snapshot tool and set about implementing robust changes to improve the performance and usability. These changes were featured in our recent <a href="https://chameleoncloud.org/blog/2025/10/01/chameleon-changelog-for-september-2025/">changelog</a>! She worked on two main areas: enhancing usability and optimizing performance. For usability improvements, Zahra reorganized the tool's codebase into five modular functions, added new command-line flags (including dry-run mode and custom source path support), and implemented automated testing with GitHub Actions to ensure reliability.</p>

<p>Zahra used Chameleon's bare metal resources to conduct comprehensive performance benchmarking of the cc-snapshot tool. She tested different image formats (QCOW2 and RAW) and compression algorithms (zlib and zstd) on Chameleon nodes using three different image sizes (small 4.47 GiB, medium 7.62 GiB, and large 12.7 GiB). This benchmarking was essential because HPC experiments are resource-intensive and depend on complex software environments, making efficient snapshotting critical for reproducibility.</p>

<p>At the end of the summer, Zahra had accomplished significant performance improvements for the Chameleon community. Her benchmarking revealed that zstd compression reduced snapshot creation time by approximately 80% compared to the default zlib compression, while maintaining similar compression efficiency and upload/boot performance. These findings demonstrate that snapshotting can be a practical and effective tool to support reproducibility in HPC experiments, enabling researchers to generate and share reproducible environments much faster and improve research turnaround time.</p>

<p><strong>Link to poster:</strong> <a href="https://chameleoncloud.org/media/filer_public/97/70/9770a10d-1ce2-4c34-a124-71aad8d45bbd/enhancing_usability_and_performance_in_experimental_environments_management.pdf" target="_blank">View Poster</a></p>

<p><strong>Link to abstract:</strong> <a href="https://chameleoncloud.org/media/filer_public/52/5b/525bfaea-7841-40d2-8d76-3b1e12d0b0bc/acm_conference_proceedings_primary_article_template_zahra.pdf" target="_blank">View Abstract</a></p>

<h2>Chameleon Concierge</h2>

<p><img src="https://chameleoncloud.org/media/filer_public/7d/0a/7d0a2364-a3c6-4d18-b52a-610716c170f8/concierge_diagram.png"></p>

<p>In this project, student Saieda Ali Zada innovated with LLMs, RAG systems, and Chameleon documentation, setting about to create a system that can respond to user queries automatically with sourced information from testbed official documents and internal documents (e.g., user tickets, and such). She worked on developing an AI-powered search system leveraging large language models with Retrieval-Augmented Generation (RAG) to unify various Chameleon documentation sources. The system collects information from Chameleon's ReadtheDocs website, FAQs, blogs, and public forum posts, processes them into searchable chunks, and uses semantic similarity search to retrieve relevant information. The system then uses Meta's Llama 3.1 model to generate accurate, context-aware answers with cited references.</p>

<p>Saieda leveraged Chameleon's computational resources throughout her development process. She conducted initial implementation work on the Perlmutter supercomputer, performed early development on an Apple M1 system, and ultimately deployed and evaluated the system on a KVM instance on Chameleon equipped with 1 NVIDIA H100 GPU (40GB). This GPU acceleration significantly reduced response latency from 10 minutes to just 20 seconds, making the system practical for real-time user assistance.</p>

<p>At the end of the summer, Saieda had accomplished a working RAG system (experimenting with over 14 iterations) that demonstrably outperforms generic LLMs (like base Llama 3.1) in answering Chameleon-specific questions. Through systematic evaluation using 20 test queries, she showed that her optimized models (particularly Models 7-14) won or tied against the negative baseline in 18-19 out of 20 comparisons. Her best-performing model (Model 12) even achieved performance comparable to proprietary models like OpenAI's GPT-5, winning 9 out of 20 head-to-head comparisons. This work demonstrates that well-designed open-source RAG systems can provide high-quality documentation assistance, potentially reducing the burden on support staff while improving the user experience.</p>

<p><strong>Link to poster:</strong> <a href="https://chameleoncloud.org/media/filer_public/43/46/4346f41f-f7ec-45dc-9164-108d3854a9bc/chameleon_concierge_poster.pdf" target="_blank">View Poster</a></p>

<p><strong>Link to abstract:</strong> <a href="https://chameleoncloud.org/media/filer_public/8e/5c/8e5caa2b-4be9-4197-9362-fd5abe45407b/chameleon_concierge_abstract.pdf" target="_blank">View Abstract</a></p>

<hr>
<p>These projects demonstrate the diverse capabilities of the Chameleon testbed—from supporting edge computing and real-time data processing to enabling large-scale performance benchmarking and GPU-accelerated AI workloads. The students' innovative approaches to real-world problems showcase how Chameleon empowers the next generation of researchers.</p>

<p>Join us at SC'25 in St. Louis this November to see these posters in person at the ACM Student Research Competition. Stop by to meet the students, learn more about their work, and discover what's possible with Chameleon. And don't miss Kate Keahey's presentation at the EduHPC workshop discussing our <a href="https://nimbusproject.org/wp-content/uploads/sites/116/2025/09/The_Cost_of_Teaching_Operational_ML_EduHPC.pdf">recent paper with Chameleon User Fraida Fund</a> on her experiences and lessons learned from teaching a 200-student course on machine learning operations with the testbed in Spring 2025. She is hosting a <a href="https://chameleoncloud.org/learn/webinars">webinar</a> on this experience as well on Nov. 25th, 2025. <strong><a href="https://uchicago.zoom.us/webinar/register/WN_ZN4PtuwhTY-lwG1SY6ICWA">Register here</a></strong>!</p>