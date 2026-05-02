---
abstract: <p>This month we're welcoming CHI@NCAR as a full Chameleon site with 40
  new AMD EPYC nodes, announcing baremetal H100 GPUs at CHI@TACC, adding Jetson Orin
  devices on CHI@Edge, previewing our new AI Documentation Assistant, sharing a revamped
  documentation site, and highlighting recordings from the Sixth Chameleon User Meeting
  along with upcoming community events at NSDI '26.</p>
authors:
categories:
- Announcements
- Featured
date: '2026-05-01'
featured: true
hide_image: false
image: https://chameleoncloud.org/media/filer_public/66/89/6689b9d9-5d40-4cd7-a161-239c68d1c5d5/april_chameleon_2026.jpg
related_posts:
- slug: chameleon-newsletter-changelog-march-2026
  title: Chameleon Newsletter & Changelog - March 2026
- slug: chameleon-newsletter-changelog-february-2026
  title: Chameleon Newsletter & Changelog - February 2026
- slug: chameleon-newsletter-changelog-january-2026
  title: Chameleon Newsletter & Changelog - January 2026
slug: chameleon-newsletter-changelog-april-2026
subtitle: Welcome to the Chameleon April 2026 Newsletter!
title: Chameleon Newsletter & Changelog April 2026
---

<p>Welcome to the Chameleon April 2026 Newsletter! This month is packed with hardware news: CHI@NCAR is now a full Chameleon site with 40 new AMD EPYC nodes and 75 TB of object storage, we've added baremetal H100 GPUs at CHI@TACC, and four new NVIDIA Jetson Orin devices have joined CHI@Edge. On the platform side, we're previewing a new AI Documentation Assistant and releasing a revamped documentation site. In the community, we're sharing recordings from the Sixth Chameleon User Meeting and announcing BoF sessions at NSDI '26.</p>

<h2>Community News &amp; Resources</h2>

<p><strong>User Meeting Presentations and Recordings Posted:</strong> Thank you to everyone who came out to support our Sixth Chameleon User Meeting! We learned a lot from you and appreciate the contributions from all of our users. We're excited to announce that <a href="https://chameleoncloud.org/chameleon-cloud-users-meeting/sixth-chameleon-user-meeting/#program">presentations from our User Meeting</a> are now available on our event website. You can also view <a href="https://www.youtube.com/playlist?list=PLE8dVtsVJCUEFMaeNK9aKq7wxfdGGW1hF">recordings of presentations, keynotes, and symposia</a> on our <a href="http://youtube.com/channel/UCVP_TxAjuCiMoQRxC68Pt_A/">YouTube Channel</a>. Stay posted for more as we prepare a community report based on the presentations, discussions, and insights that arose from the meeting.</p>

<p><strong>Chameleon at NSDI '26 — BoF Sessions on Reproducibility (May 4 &amp; 5):</strong> The <a href="http://repeto.cs.uchicago.edu">REPETO project</a> is hosting two Bird-of-Feather sessions at the <a href="https://www.usenix.org/conference/nsdi26">23rd USENIX Symposium on Networked Systems Design and Implementation (NSDI 2026)</a> focused on packaging and sharing reproducible storage research experiments using Chameleon and Trovi. Sessions will include a Chameleon/Trovi overview, a panel with NSDI authors who packaged their experiments on Chameleon, and interactive hands-on exercises. Both sessions are in-person; exact times TBD at the conference. This event is led by <strong>Reproducibility Ambassador Sabiha Afroz (Virginia Tech)</strong>. <a href="https://blog.chameleoncloud.org/posts/announcing-nsdi-2026-bird-of-feather-bof-session-on-reproducibility/">Read the full announcement.</a></p>

<p><strong>New "Teaching Storage Systems with Chameleon" Webinar Available:</strong> We posted the slides and video for the April 2026 webinar co-hosted with Professor Erez Zadok from Stony Brook University. Zadok describes the storage courselets for the <a href="http://fount.cs.uchicago.edu">NSF FOUNT project</a> that he created with his graduate student Tyler Estro for a graduate level course on advanced storage topics, including NFS, specialized storage nodes, RAID, and more. They also presented demos of the materials, where to <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/89d7f2bc-0ee6-4e15-966d-52718a8ac87c">find their storage courselets on Trovi</a>, and how to use them. <a href="https://www.youtube.com/watch?v=6V1Mwv5e3uo&amp;list=PLE8dVtsVJCUHsi5aFkW1sJwxqNJU-OHrp">Watch the webinar here</a> and learn how you can incorporate these courselets into your own classes on Chameleon.</p>

<p><strong>Tips &amp; Tricks Blog of the Month:</strong> <a href="https://blog.chameleoncloud.org/posts/running-artifact-evaluations-on-chameleon/">Running Artifact Evaluations on Chameleon</a> — Learn how to use Chameleon and Trovi to package and run artifact evaluations for your research.</p>

<p><strong>User Blog of the Month:</strong> <a href="https://blog.chameleoncloud.org/posts/openmcp-reproducible-benchmarking-mcp-agents/">OpenMCP: A Reproducible Benchmarking Harness for Evaluating Computer-Use Agents on Chameleon</a> — Learn how OpenMCP uses Chameleon to provide a reproducible environment for benchmarking computer-use AI agents.</p>

<h2>Changelog</h2>

<p><strong>New Core Site at CHI@NCAR.</strong> As a part of <a href="https://blog.chameleoncloud.org/posts/chameleon-testbed-secures-12-million-in-funding-for-phase-4/">Phase 4 of Chameleon</a>, CHI@NCAR became an official site of the Chameleon project, and this month it is ready for a full release. <a href="https://blog.chameleoncloud.org/posts/chincar-an-interview-with-the-newest-associate-site/">NCAR first joined the testbed</a> back in 2022 as an associate site with a handful of AMD Thunder nodes, which though unique on the testbed and interesting to our users were few in number. Now, there are 40 new Compute Zen 5 nodes, each with AMD EPYC 4545P 16-Core processors, 64 GiB of memory, and 1 TB of NVMe storage — making these nodes a great option for users who need interactive fast storage for I/O-heavy workloads. Additionally, NCAR has 75 TB of object storage. Please don't be shy about using these new resources!</p>

<p><strong>Baremetal H100 Nodes at CHI@TACC.</strong> Last year, we announced <a href="https://blog.chameleoncloud.org/posts/chameleon-changelog-for-may-2025/">H100 GPUs with virtual machines</a> at KVM@TACC, but now we've added more hardware of the same type configured for baremetal on CHI@TACC, letting you run H100 experiments without going through a virtualization layer. These nodes are Dell PowerEdge XE9640 equipped with an Intel Xeon Platinum processor, 4 NVIDIA HGX H100 GPUs, 1 TB DDR5-4800 RAM, 2x 447.13 GB PCIe NVMe, and 1x 3.84 TB PCIe NVMe. For the full hardware specification, <a href="https://chameleoncloud.org/hardware/">filter by <code>gpu_h100</code> in our hardware browser</a>.</p>

<p><strong>Jetson Orins on CHI@Edge.</strong> Chameleon is an edge-to-cloud testbed where users can run edge-to-cloud experiments by either using CHI@Edge resources managed by Chameleon operators or adding their own edge resources to the testbed via BYOD. Our CHI@Edge site lets you run experiments on devices such as <a href="https://chameleoncloud.gitbook.io/chi-edge/hardware-info/device-type">Raspberry Pi 4s, NVIDIA Jetson Nanos, and NVIDIA Jetson Xavier NXs</a>. This month, we've enrolled 4 <a href="https://www.nvidia.com/en-us/autonomous-machines/embedded-systems/jetson-orin/">NVIDIA Jetson Orin</a> devices: 3 Orin Nanos (NVMe) and 1 AGX Orin. Compared to the Jetson Xavier NX, they have faster memory, 2–10x better AI performance, and come with the Ampere GPU architecture. For full details about these devices and the required software configuration, see our <a href="https://chameleoncloud.gitbook.io/chi-edge/hardware-info/device-type">device type docs</a>.</p>

<p><strong>AI Documentation Assistant (Preview).</strong> Chameleon is a large system with many capabilities — and many documentation sources, articles, and blog posts explaining how to use them — so that sometimes it is not exactly easy to find what you need. This month, we are piloting a <a href="https://ai.chameleoncloud.org/">new AI assistant</a> to help with the process of searching through these documentation sources to find the right information. Simply ask any question about Chameleon, and it answers it and provides links to the most relevant documentation pages and blog posts. This service is brand new and offered as a preview as we continue to improve the quality of answers. To give you the opportunity to give feedback we provided a built-in feedback mechanism to rate answers — please use it to help us make this service better! In the future, we are planning to include more information in the AI's knowledge base, including hardware data as well as recommendations for Trovi artifacts that will let you get started with your research faster. We hope this will make it easier for you to find information about Chameleon, but you are welcome, as always, to contact us directly with any questions via <a href="https://chameleoncloud.org/user/help/">the Help Desk</a>.</p>

<p><strong>Documentation Revamp.</strong> Speaking of documentation, this month we revamped <a href="https://chameleoncloud.readthedocs.io/en/latest/">Chameleon's Docs</a>, updating all of the information and images that were slightly out of date. We are thankful to all users who provided the feedback guiding those changes — and in particular to those of you who made it to the User Meeting this month! Please keep the feedback coming; we would like to help you get started with the system!</p>

<p>Keep an eye on our <a href="https://chameleoncloud.org/learn/webinars/">webinar calendar</a> as we announce new webinars for upcoming months.</p>
