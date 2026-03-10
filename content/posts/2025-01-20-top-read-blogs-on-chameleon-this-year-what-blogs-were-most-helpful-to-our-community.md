---
abstract: <p>Last year was remarkable for our blog, with over <strong>10,000 views
  and 5,700 active users</strong>. As we kick off this year's tips and tricks series,
  we wanted to highlight the "evergreen" advice that our community returns to time
  and again. In this roundup, you'll find our most impactful insights - the strategies
  and solutions that have stood the test of time - each with a brief description and
  a direct link to the full article. Let's start the year by building on what works!</p>
authors:
- Marc Richardson
categories:
- Tips and Tricks
date: '2025-01-20 18:57:32+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/bb/37/bb379255-923c-4308-8e9b-a39bee006e7d/chameleon_light_bulb.jpg
slug: top-read-blogs-on-chameleon-this-year-what-blogs-were-most-helpful-to-our-community
subtitle: Read about which Tips&Tricks blogs were most helpful to our community
title: Top Blogs on Chameleon Last Year (2024)
---

<p>Last year was remarkable for our blog, with over <strong>10,000 views and 5,700 active users</strong> engaging with our content. As we kick off this year's tips and tricks series, we wanted to highlight the "evergreen" advice that our community returns to time and again. In this roundup, you'll find our most impactful insights - the strategies and solutions that have stood the test of time - each with a brief description and a direct link to the full article. While Chameleon remains committed to innovation and continually enhancing our testbed for the community, there's tremendous value in revisiting the wisdom that has risen to the top. Consider this your curated collection of Chameleon classics - the cream of the crop from our knowledge base that continues to serve developers just as effectively today as when first published. Let's start the year by building on what works!</p>

<h2>Power Measurement and Management on Chameleon (360 Views - June 2024)</h2>

<p><img alt="" src="https://www.chameleoncloud.org/media/filer_public/56/a2/56a23811-f1ea-4a7d-9edd-3b7aa4fe3fe0/power_grafana.png"></p>

<p>Understanding power consumption is increasingly important for researchers focused on energy efficiency and sustainable computing. This popular blog post explores various methods to measure power usage on Chameleon nodes, from system-level measurements using the baseboard management controller (BMC) to detailed CPU power information via Intel's RAPL framework.</p>

<p>You'll learn how to install and use tools like <code>freeipmi-tools</code> for system-wide power statistics, <code>perf</code> for simple CPU energy measurements, and <code>scaphandre</code> for comprehensive per-process power tracking. The guide even covers setting up monitoring dashboards with Grafana for long-term data collection and visualization.</p>

<p>Whether you're optimizing algorithms for energy efficiency or comparing hardware power consumption across different workloads, this guide provides essential techniques to incorporate power metrics into your research.</p>

<p><a href="https://chameleoncloud.org/blog/2024/06/18/power-measurement-and-management-on-chameleon/">Read the full blog about Power Measurement and Management</a></p>

<h2>Best Practices For Secure Experiments (291 Views - June 2022)</h2>

<p>Security breaches can derail your experiments and waste valuable research time. This consistently popular blog offers practical advice to protect your Chameleon instances from unauthorized access and exploitation.</p>

<p>The post outlines essential security practices including changing default passwords, preserving built-in firewall rules, using bastion hosts for sensitive experiments, minimizing exposure of internet-facing services, and properly configuring web service bindings. These straightforward precautions can prevent the frustrating experience of having your experiment terminated due to security issues.</p>

<p>Following these security best practices not only protects your own research but also helps maintain the integrity of the Chameleon testbed for the entire community.</p>

<p><a href="https://chameleoncloud.org/blog/2021/06/28/best-practices-making-your-experiments-secure/">Read the full blog about Secure Experiments</a></p>

<h2>Composable Hardware on Chameleon NOW! (265 Views - Aug. 2024)</h2>

<p><img alt="" src="https://chameleoncloud.org/media/filer_public/41/d1/41d19d38-67ef-4ca1-a310-173ef8cd0c7b/tacc-hardware.png"></p>

<p>One of our most exciting recent features is Chameleon's composable hardware, which provides unprecedented flexibility in configuring experimental environments. This blog introduces the GigaIO systems available at both CHI@UC and CHI@TACC, consisting of bare metal nodes, accelerators, and a configurable PCIe backplane.</p>

<p>The post explains how this infrastructure allows for dynamic resource configurations that weren't previously possible, like connecting up to 8 A100 GPUs to a single node or creating custom combinations to maximize hardware utilization. The guide covers the underlying PCIe fabric technology, configuration options, and the process for reserving and utilizing these specialized resources.</p>

<p>For researchers working on GPU-intensive applications, distributed computing, or novel hardware architectures, this blog provides essential information about accessing and leveraging Chameleon's cutting-edge composable systems.</p>

<p><a href="https://chameleoncloud.org/blog/2024/08/19/composible-hardware-on-chameleon-now/">Read the full blog about Composable Hardware</a></p>

<h2>Data Storage, Management, and Sharing on Chameleon (154 Views - Oct. 2022)</h2>

<p><img alt="" src="https://chameleoncloud.org/media/filer_public/99/11/99118e34-aceb-469b-bb55-586edce34d05/chameleon-storage.png"></p>

<p>Effective data management is crucial for successful experiments, and this comprehensive guide helps you navigate Chameleon's diverse storage options. The blog breaks down ephemeral storage, object storage, block storage, and file-based storage, explaining the ideal use cases for each approach.</p>

<p>You'll learn when to use ephemeral storage for temporary data, how object storage provides access without requiring an active instance, the benefits of block storage for KVM environments, and how the shared file system offers collaborative capabilities. The guide also covers practical tools like <code>cc-snapshot</code> and <code>cc-cloudfuse</code> to streamline your data management workflows.</p>

<p>The post includes links to additional resources, including Jupyter notebook tutorials and video demonstrations, making it a valuable reference for researchers working with large datasets or collaborating across teams.</p>

<p><a href="https://chameleoncloud.org/blog/2022/10/26/data-storage-management-and-sharing-on-chameleon/">Read the full blog about Data Storage, Management, and Sharing</a></p>

<h2>Understanding the New FABRIC Layer 3 Connection (103 Views - Mar. 2024)</h2>

<p><img alt="" src="https://chameleoncloud.org/media/filer_public/28/fe/28fe7fbc-8c87-4df2-b11a-e95387168c33/fabnet-diagram.png"></p>

<p>Multi-site experiments took a significant step forward with Chameleon's FABRIC Layer 3 connection. This blog explains how this integration between Chameleon and the FABRIC testbed enables more powerful, flexible networking options for distributed experiments.</p>

<p>The post details how researchers can leverage the shared network at both CHI@UC and CHI@TACC sites to route to FABRIC resources without custom Layer 2 stitching. Even users not directly using FABRIC can benefit from the improved connectivity between Chameleon sites, with lower latency and higher bandwidth (up to 25Gb/s per flow) compared to routing via public IPs.</p>

<p>With step-by-step instructions for identifying the Fabnet network, launching servers on fabnet, and verifying network paths, this guide simplifies the process of creating sophisticated multi-site experimental environments.</p>

<p><a href="https://www.chameleoncloud.org/blog/2024/03/18/tips-and-tricks-understanding-the-fabric-layer-3-connection/">Read the full blog about FABRIC Layer 3 Connection</a></p>

<h2>Looking Forward</h2>

<p>These popular blog posts represent just a sampling of the knowledge available in our growing library of tips, tricks, and guides. Each addresses fundamental aspects of conducting successful research on Chameleon, from security and data management to advanced hardware capabilities and power measurement.</p>

<p>As we continue to enhance the Chameleon testbed with new features and capabilities, we encourage you to explore these resources and look forward to sharing more insights in the coming year. Have you found other blog posts particularly helpful in your research? Or do you have suggestions for topics you'd like us to cover? Let us know in the Forum or reach out to our support team!</p>

<p>Happy experimenting!</p>