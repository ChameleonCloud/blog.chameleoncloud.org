---
abstract: '<p><span id="docs-internal-guid-d4e6845c-7fff-5c0e-2b81-86f59c31c4ab" style="font-size:
  11pt; font-family: Arial,sans-serif; color: #000000; background-color: transparent;
  font-weight: 400; font-style: normal; font-variant: normal; text-decoration: none;
  vertical-align: baseline; white-space: pre; white-space: pre-wrap;">In 2021, we
  introduced </span><a href="https://www.chameleoncloud.org/experiment/chiedge/" style="text-decoration:
  none;"><span style="">CHI@Edge</span></a><span style="font-size: 11pt; font-family:
  Arial,sans-serif; color: #000000; background-color: transparent; font-weight: 400;
  font-style: normal; font-variant: normal; text-decoration: none; vertical-align:
  baseline; white-space: pre; white-space: pre-wrap;">, a cutting-edge testbed tailored
  to the dynamic needs of edge computing and IoT research. Our initial offerings included
  a robust selection of devices like Raspberry Pi 4s, Nvidia Jetson Nanos, and Jetson
  Xaviers, tailored for high-performance yet low-power edge computing tasks. Today,
  we''re thrilled to announce the transition of CHI@Edge from a widely embraced preview
  to its official full production phase.</span></p>'
authors:
- Soufiane Jounaid
categories:
- Tips and Tricks
date: '2024-04-15 17:33:11+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/d5/63/d5635bf0-774e-4a87-be06-73abf9d45524/chiedge_logo_resized.jpg
slug: chiedge-transitioning-from-successful-preview-to-full-production
subtitle: Unlock the power of edge computing with CHI@Edge - In production now!
title: 'CHI@Edge: Transitioning from Successful Preview to Full Production'
---

<p><img height="auto" src="https://chameleoncloud.org/media/filer_public/d5/63/d5635bf0-774e-4a87-be06-73abf9d45524/chiedge_logo_resized.jpg" width="50%"></p>

<p>In 2021, we introduced <a href="https://www.chameleoncloud.org/experiment/chiedge/">CHI@Edge</a>, a cutting-edge testbed tailored to the dynamic needs of edge computing and IoT research. Our initial offerings included a robust selection of devices like Raspberry Pi 4s, Nvidia Jetson Nanos, and Jetson Xaviers, tailored for high-performance yet low-power edge computing tasks. Today, we're thrilled to announce the transition of CHI@Edge from a widely embraced preview to its official full production phase.</p>

<p><strong>Reflecting on CHI@Edge’s Journey:</strong> Since its preview, CHI@Edge has facilitated a wide array of impactful projects and emerged as a cornerstone for innovative research and education in edge computing. Our <a href="https://www.chameleoncloud.org/blog/2022/04/26/conducting-research-on-the-edge-chiedge/">initial blog post</a> outlined the vision and potential of CHI@Edge, which has since been realized through various high-profile projects and collaborations.</p>

<p>Highlights include the deployment of <a href="https://chameleoncloud.org/blog/2022/12/19/driving-autonomous-cars-from-edge-to-cloud-with-chiedge/">autonomous vehicles for educational purposes</a> (see <strong>Figure 1</strong>) and foundational work in real-time data processing for environmental research, as showcased in projects like "<a href="https://www.chameleoncloud.org/blog/2022/04/18/one-fish-two-fish-choosing-optimal-edge-topologies-for-real-time-autonomous-fish-surveys/">One Fish, Two Fish: Choosing Optimal Edge Topologies for Real-Time Autonomous Fish Surveys</a>."</p>

<p><img height="auto" src="https://chameleoncloud.org/media/filer_public/b8/c7/b8c7c1c6-8567-46da-9c77-cae58314b111/autonomous_vehicles_chi-edge.png" width="80%"></p>

<p><small><strong>Figure 1</strong>: Researchers have created a streamlined training system using autonomous vehicles on reconfigurable tracks, enhanced by CHI@Edge integration. This setup allows vehicles, equipped with sensors and Raspberry Pi, to be reserved and operated remotely via a Jupyter notebook. The notebook enables direct data transfer to and from the Chameleon testbed, forming a closed-loop system for rapid data collection, model refinement, and deployment, facilitating continuous experimentation and learning.</small></p>

<p><strong>What’s New in Full Production?</strong> As CHI@Edge enters full production, we're introducing an array of enhancements to improve user experience and expand capabilities:</p>

<ul>
	<li><strong>Enhanced Reliability and Usability:</strong> System-wide updates have been implemented to ensure smoother operations and better user experience.</li>
	<li><strong>Advanced GPU Support:</strong> Full support for the Nvidia container runtime platform is now available, complete with detailed tutorials (see below) to utilize GPU-accelerated containers effectively on Nvidia devices.
	<ul>
		<li>AI at the Edge is crucial for real-time, privacy-preserving, efficient processing on devices. AI applications are increasingly incorporating the use of sensors and actuators in our everyday environments; hence the need for low-latency, reliable, and energy-efficient processing on the edge.</li>
		<li>We recognize the need for advancement in edge AI/ML research in our community, so we first staffed our cluster with Nvidia’s Jetson Nanos and Xaviers; with this feature, we facilitate the orchestration of a full-featured development environment for GPU workloads, reaffirming our intent to continuously support and expand this use case in CHI@Edge.</li>
	</ul>
	</li>
	<li><strong>Hardware Resource Discovery:</strong> A brand-new <a href="https://www.chameleoncloud.org/edge/hardware/">hardware resource discovery page</a> that shows up-to-date information about the current edge devices hosted on the platform.
	<ul>
		<li>Many of our users have expressed interest in a full-fledged, up-to-date hardware catalog for CHI@Edge to facilitate the orchestration of repeatable experiments.</li>
		<li>Thanks to the new hardware discovery feature, users can more easily choose which devices to reserve and learn more about the current state of devices. We will continue improving hardware discovery with more information about our hardware.</li>
	</ul>
	</li>
	<li><strong>New Device and Peripheral Support:</strong> We're excited to announce upcoming support for Google Coral and Nvidia Jetson AGX Orin development boards, alongside advanced peripherals integration, including high-performance cameras and sensors.</li>
	<li><strong>New Support Channels</strong>: As part of our efforts to better support our users, CHI@Edge support will officially move from the <a href="https://bit.ly/3gryNUg">Google mailing list</a> to our dedicated <a href="https://chameleoncloud.org/user/help/">help desk</a>. This change will facilitate faster and more personalized assistance to our community.</li>
</ul>

<p><strong>To see how CHI@Edge can facilitate your edge computing research and projects, visit our <a href="https://www.chameleoncloud.org/experiment/share/ae64bc9b-8315-41dc-96ec-abd86259ba3f">Tutorial on CHI@Edge</a> for detailed examples and use cases</strong> (see <strong>Figure 2</strong>). We have also updated our <a href="https://chameleoncloud.gitbook.io/chi-edge/getting-started">CHI@Edge documentation</a> to further assist users with their CHI@Edge projects.</p>

<p><img height="auto" src="https://chameleoncloud.org/media/filer_public/78/d1/78d1053f-bd76-49c3-bd29-960536dee14d/image1.png" width="80%"></p>

<p><small><strong>Figure 2:</strong> You can run the interactive CHI@Edge tutorial through our <a href="http://chameleoncloud.org/experiment/share">Trovi service</a> to learn about the most important CHI@Edge features.</small></p>

<p>The above tutorial offers a comprehensive guide to using the CHI@Edge platform. It begins by walking you through the process of launching your first container on the platform, providing a foundational understanding of how to initiate and manage edge computing tasks. You will learn how to interact directly with your container, adjusting settings and configurations as needed for your specific project. The tutorial also covers how to assign a public IP to your container, enabling external access and connectivity—crucial for remote monitoring and control.</p>

<p><img src="https://chameleoncloud.org/media/filer_public/e8/aa/e8aa5e6b-8e2a-4b0b-b1e0-d88502d76448/image4.png"></p>

<p><small><strong>Figure 3:</strong> The experiment topology. The Publisher and MQTT Server are both running as Docker containers on a Raspberry Pi.</small></p>

<p>Further, you'll explore the practical aspects of uploading and downloading data to and from your containers, an essential skill for managing inputs and outputs in your experiments. A full experiment using MQTT is demonstrated, showcasing how to implement this lightweight messaging protocol for IoT, which is pivotal for data communication between devices (see <strong>Figure 3</strong>). Finally, the tutorial culminates with an advanced section on training a neural network using CUDA and PyTorch on an Nvidia Jetson Nano. This part highlights how to leverage the powerful GPU capabilities of the platform for intensive computational tasks such as deep learning, providing you with the tools to conduct cutting-edge research in neural networks and machine learning on edge devices.</p>

<p><strong>Looking Ahead:</strong> The transition to full production is just another step in our journey. We are committed to continuous improvement, with plans to enhance device integration further and develop interactive features to streamline the development process on edge containers.</p>

<p>Stay tuned for future updates and our upcoming tips&amp;tricks series, designed to help users maximize the potential of CHI@Edge. As we celebrate this milestone, we invite both new and current users to explore the expanded capabilities of our platform. Whether you're a researcher, educator, or innovator, CHI@Edge is designed to support your projects with state-of-the-art technology and an ever-evolving suite of tools.</p>