---
abstract: "<p>Learn all about CHI@Edge, Chameleon's edge computing testbed, how to\
  \ interact with CHI@Edge devices, research projects that came out of our early preview\
  \ and how to enroll your own device on CHI@Edge! Check out the post for links to\_\
  an interactive user guide on Trovi, a YouTube video, and how to join the CHI@Edge\
  \ Google Group to stay up to date with the latest news!</p>"
authors:
- Jason Anderson
categories:
- Tips and Tricks
date: '2022-04-26 18:35:34+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/2c/75/2c753a18-8b29-47f1-8573-e02e55b749e7/screen_shot_2022-04-26_at_73509_pm.png
slug: conducting-research-on-the-edge-chiedge
subtitle: ''
title: 'Conducting Research on the Edge: CHI@Edge'
---

<p dir="ltr">Chameleon is always chasing the frontier of research, a task made all the more difficult by the various directions the frontier is spreading. One such interesting area is edge computing and IoT. That's why, last year, we worked to build a new testbed tailoring to the needs of research on the edge—we call it <a href="https://www.chameleoncloud.org/experiment/chiedge/">CHI@Edge</a>!</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-cb59c2c6-7fff-37bd-2461-2804cd453fb5">What's in a name?</b></p>

<p>First, it's important to define what we mean by "edge," as the terminology is still evolving and there are many interpretations of what an edge device is. CHI@Edge currently is built for what we call "fat" devices: single-board computers with relatively high processing capabilities, yet low power consumption and form factor. This is in our estimation the category of devices most widely deployed at the edge today. The CHI@Edge testbed has support for Raspberry Pis, as well as Jetson Nano and Jetson Xavier devices.</p>

<p> </p>

<p dir="ltr">As a user interested in edge research, you can make leases for exclusive use of one or more of these devices. You can then launch application containers directly on the device via a web, <a href="https://python-chi.readthedocs.io/en/latest/">Python</a>, or command line interface. Any containers you launch are internally networked and addressable, allowing you to create many different network topologies across a large physical area. You can also use a <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/networks/networks_basic.html#floating-ip-addresses">Floating IP</a> to allow public connectivity to a container from the internet. Most aspects of the container can be controlled by you, such as the image, execution environment, command string, even mounted configuration files or Linux devices. With these building blocks, you can express a wide variety of edge and IoT experiments.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-cb59c2c6-7fff-37bd-2461-2804cd453fb5">CHI@Edge Preview</b></p>

<p dir="ltr">Last summer <a href="https://www.chameleoncloud.org/blog/2021/06/01/chameleon-changelog-may-2021/">we released an early preview of CHI@Edge</a>, which was immediately popular and used by many projects, culminating in a <a href="https://www.chameleoncloud.org/blog/2021/12/23/chiedge-community-workshop-report/">community workshop on edge to cloud experimentation</a>. Researchers used CHI@Edge to <a href="https://www.chameleoncloud.org/blog/2021/12/21/pegasus-at-the-edge/">profile workloads across different device types</a>, <a href="https://www.chameleoncloud.org/blog/2022/04/18/one-fish-two-fish-choosing-optimal-edge-topologies-for-real-time-autonomous-fish-surveys/">deploy code for autonomous aquatic vehicles tasked with surveying fish populations</a>, and <a href="https://www.chameleoncloud.org/blog/2022/02/21/chiedge-as-a-baseline-for-ara-wireless-living-lab/">create the foundation for a new wireless testbed</a>.</p>

<p> </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-cb59c2c6-7fff-37bd-2461-2804cd453fb5"><img height="353" src="https://lh3.googleusercontent.com/2n2YEkLINoLwgePvcKJ-eultfnCx89hC1DtxAek_smdMSTJiWKavxEGx-Mt1F5kDXBGXqMlrtOvDYCYu65ivMW0MGLjZj8586oC3yJhzCMPs9cVl6LixrGwTgGfPCZdsL0CG-ymv" width="624"></b></p>

<p dir="ltr" style="text-align: center;">Counting fish with object detection models deployed at the edge. <a href="https://bit.ly/3JPYz0Z">Read the blog about this project</a>!</p>

<p> </p>

<p dir="ltr">In general, we noticed several patterns. Researchers often wanted to collect data at the edge, with a variety of local sensors or other connected peripherals. That data may be processed on the device, or sent to the cloud (a significant number of questions arise on when it's worthwhile to pay the network cost in this arrangement.) The availability of GPUs or other accelerators on the edge introduces even more research opportunities as to local processing and decision-making. Increasingly, it became clear that we as testbed operators would not be able to provide enough hardware in enough places to properly serve the research community by ourselves. Therefore, it was paramount that, in an edge environment, we allow our users to bring their own devices, using CHI@Edge to manage the complexity around provisioning and access management.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-cb59c2c6-7fff-37bd-2461-2804cd453fb5">Bring Your Own Device</b></p>

<p dir="ltr">Enrolling a device you already control to CHI@Edge comes with several benefits:</p>

<ul>
	<li dir="ltr">
	<p dir="ltr">You can manage your device with powerful yet friendly interfaces, without compromising on ownership—you can keep your device exclusive to you and your collaborators.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">You avoid solving problems of application provisioning and network connectivity through firewalls or NATs.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">You can temporarily share access to the device with others, for example during digital artifact review.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">You can use one set of interfaces to instrument both the cloud and the edge, making it much simpler to perform such experiments.</p>
	</li>
</ul>

<p> </p>

<p dir="ltr">For example, one of our users teaches a class on self-driving cars (read more in the <a href="https://chameleoncloud.org/chiedge-community-workshop/">workshop report</a>). He created several custom car rigs, consisting of a modified RC car and front-facing camera integrated with a Raspberry Pi. Each car's Pi was enrolled in CHI@Edge. The instructor did not need to set up any special networking for the cars except allowing them access to a WiFi network. The cars could only be reserved by students, who could then use a Jupyter Notebook to deploy new code to the cars and remotely start their test runs. Detailed race data could be saved or uploaded to the cloud after each run. Students could experiment with training the model on Chameleon's bare metal testbed, which has much more powerful GPUs. CHI@Edge made it easier for the instructor to introduce students to the important parts of the class, as the testbed handled complexities around networking the cars to a control plane, managing the lifecycle of code deployed to the car, and remote access and Jupyter integration.</p>

<p> </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-cb59c2c6-7fff-37bd-2461-2804cd453fb5"><img height="294" src="https://lh6.googleusercontent.com/p0BFggLAPwceZHl3rh90bCgmG-iu79L4K0SBKsbgNALhFORF982TPgpGOW-C45HKneMKqCvAwywgqfhflxWN2fkgQUgdB4sv07SCv9A9zCZoHo0Cwi-89IhR2NYGjGPfehtv2Nt0" width="400"></b></p>

<p> </p>

<p dir="ltr">Adding a device you already own to the testbed is easy with the <a href="https://chameleoncloud.gitbook.io/chi-edge/device-enrollment/edge-sdk">CHI@Edge SDK</a>, which you can install via Pip, the Python package manager. The SDK comes with a simple CLI tool that lets you manage any devices you've enrolled. You can see all your devices and their status, and get more details about a particular device's state, but most importantly can enroll new devices. Device enrollment consists of downloading a supported base image, "baking" it with device-specific information generated by the SDK, and then flashing the image onto an SD card and inserting it into your target device–that's it! Once the device powers on, it will self-register and appear in the CHI@Edge web interface, at which point you can reserve it via any supported testbed interface and use it just like any of the Chameleon-provided devices. You can connect various peripherals to your device to add, e.g., additional USB storage, camera or GPIO or serial interface. It's also possible to allow access to local networks the device is connected to, if you wish. Many things are possible and we're still exploring use cases with our edge community.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-cb59c2c6-7fff-37bd-2461-2804cd453fb5">Getting Started</b></p>

<p>You can get started with CHI@Edge immediately by making a reservation for any of the devices installed and maintained by the Chameleon team. These include numerous Raspberry Pis, Jetson Nanos and Xaviers (with GPUs.) Some of these devices have additional capabilities, like an attached camera. If you already have a compatible device, use the CHI@Edge SDK to enroll it and start taking advantage of the testbed platform!</p>

<p> </p>

<ul>
	<li dir="ltr">
	<p dir="ltr">To see an example of a full edge-to-cloud experiment setup, expressed as a Jupyter Notebook, refer to our <a href="https://www.chameleoncloud.org/experiment/share/37991779-fd7b-4ab0-8d6f-e726a9204946">Edge-to-Cloud User Guide</a> on Trovi.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Check out a <a href="https://youtu.be/k5fUqdeQRs8">screencast</a> we put together, which describes the edge testbed and also covers device enrollment.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">To learn more about CHI@Edge and see what others are doing on the testbed, check out our <a href="https://groups.google.com/g/chameleon-edge-users">Google Group</a>—we announce new platform features and changes there, as well as answer questions and solicit feedback. Help us shape the testbed to make your research possible!</p>
	</li>
</ul>