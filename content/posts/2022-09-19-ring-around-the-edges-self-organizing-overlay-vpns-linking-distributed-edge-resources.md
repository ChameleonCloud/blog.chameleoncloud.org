---
abstract: <p>Learn how to use <a href="https://edgevpn.io">EdgeVPN.io</a> to easily
  create Virtual Private Networks (VPNs) and run unmodified middleware and applications
  across edge and cloud computing resources across networks with different firewalls
  and NATs (Network Address Translators).</p>
authors:
- Renato Figueiredo
categories:
- User Experiments
date: '2022-09-19 20:26:47+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/53/24/53245518-f9ba-48df-bcda-dd84f5089f22/class.jpg
related_posts:
- slug: conducting-research-on-the-edge-chiedge
  title: 'Conducting Research on the Edge: CHI@Edge'
slug: ring-around-the-edges-self-organizing-overlay-vpns-linking-distributed-edge-resources
subtitle: ''
title: 'Ring around the edges: self-organizing overlay VPNs linking distributed edge
  resources'
---

<p style="text-align: center;"><b id="docs-internal-guid-3c8f57ad-7fff-9f2d-055a-8d5ff5ff689f"><img src="https://chameleoncloud.org/media/filer_public/53/24/53245518-f9ba-48df-bcda-dd84f5089f22/class.jpg" style="width: 512px; height: 397px;"></b></p>

<p dir="ltr"><b id="docs-internal-guid-7ddf8a15-7fff-0127-6e2f-5956010c4f44">What is the central challenge/hypothesis your experiment investigates?</b></p>

<p dir="ltr">Edge computing creates opportunities for new applications that can, in real-time, process data close to where it is produced and used by Internet-of-Things (IoT) sensors and actuators. Emerging applications in smart cities, agriculture, transportation, and safety, among other domains, stand to benefit from processing near data and improved privacy, e.g., by running Artificial Intelligence (AI) algorithms on edge devices distributed near cameras instead of remote cloud servers. However, unlike cloud computing data centers, where servers are co-located in the same managed networks, edge devices can be deployed across various sites, in different networks, where each is administered independently. This is a challenge that significant hinders the ability of edge applications to scale across multiple edge providers because applications generally expect bi-directional network connectivity among all participants' nodes - an assumption that is broken when nodes are behind NATs and firewalls.. Our project investigates this central challenge, and we hypothesize that software-based virtual networks that overlay a self-organizing ring-like topology can recover symmetry in communication for edge applications, despite the underlying Internet asymmetry due to NATs and firewalls.<br>
 </p>

<p dir="ltr"><b id="docs-internal-guid-7f7d4087-7fff-d30c-a62e-2c09dc35c655">How is your research addressing this challenge? </b></p>

<p dir="ltr">Our approach builds on techniques used in different computer systems but have not been previously integrated: 1) software-defined networking, 2) network overlays using tunnels, 3) the Symphony decentralized structured peer-to-peer algorithm to form scalable topologies and routing, and 4) peer-to-peer NAT traversal. Together, the resulting system can (1) self-organize a topology and efficiently route virtual network messages as peers dynamically join and leave the network, (2) create and expose virtual network IP addresses to edge applications that are decoupled from their physical IP addresses, and (3) enforce private communications among peers using encryption. The resulting system is a software program that runs on each edge device and acts as a peer that allows messages to be inserted, routed, and delivered across the network completely transparently to the edge applications. In other words, edge developers can run their applications as if in a local network when it is distributed across multiple providers on the Internet. While this approach directly impacts edge developers and practitioners, it can indirectly improve people’s day-to-day lives by enabling new edge computing applications that users seamlessly benefit from through their mobile devices, vehicles, and smart cities - applications that might otherwise be too complex or expensive to deploy, scale, and maintain without the availability of a virtual network. In particular, our research addresses challenges that arise when unpredictable events occur, and emergency response is needed by quickly standing up virtual networks spanning edge and cloud devices of emergency responders and coordinators.</p>

<p dir="ltr"><b id="docs-internal-guid-53402393-7fff-7597-33d5-efce1111bbc0">How do you structure your experiment on Chameleon? </b></p>

<p dir="ltr">The Chameleon experiment was to demonstrate the ability of EdgeVPN to create virtual networks on demand across multiple cloud and edge sites. A total of 22 nodes were deployed, distributed across: Chameleon cloud (arm64 bare metal), Oracle Cloud (VMs),  Nara Institute of Science and Technology (NAIST, Japan), and different residential Internet Service Providers (ISPs) in Florida, Pennsylvania, Texas and Osaka/Japan (Raspberry Pi 4s). Despite these devices being deployed in different edge networks (and behind NATs), EdgeVPN logically aggregated them in the same virtual network and allowed us to deploy unmodified software for containerized cluster orchestration (Kubernetes with the Flannel network). The images below show the overlay’s outer “ring” logically connecting all devices into a virtual network - with “shortcut” links going across for scalable routing. Each node in the first image represents a node running EdgeVPN software, while each link represents a private tunnel that can traverse NATs and firewalls over the Internet. The second image shows a snapshot of Kubernetes running unmodified across all nodes.</p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-3c8f57ad-7fff-9f2d-055a-8d5ff5ff689f"><img alt="The EdgeVPN network" src="https://chameleoncloud.org/media/filer_public/42/8d/428d67c9-8e7c-4f56-8971-8fc84c8cddae/network.png" style="width: 512px; height: 503px;"></b></p>

<p style="color: rgb(170, 170, 170); font-style: italic; text-align: center;">Figure 1: Each node represents a node running EdgeVPN software, while each link represents a private tunnel that can traverse NATs and firewalls over the internet.</p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-3c8f57ad-7fff-9f2d-055a-8d5ff5ff689f"><img alt="A snapshot of kubernetes running unmodified across all nodes" src="https://chameleoncloud.org/media/filer_public/52/c2/52c2867e-41a7-4aee-bcbb-d564cb41f591/kubectl.png" style="width: 512px; height: 430px;"></b></p>

<p style="color: rgb(170, 170, 170); font-style: italic; text-align: center;">Figure 1: A snapshot of Kubernetes running unmodified across all nodes.</p>

<p dir="ltr"><b id="docs-internal-guid-d020a9bd-7fff-0a53-aff0-919752caca30">What features of the testbed do you need in order to implement your experiment? </b></p>

<p dir="ltr">Deployment on Chameleon only required the selection of Ubuntu base images, interactive access to the console (using either the Web interface console, or SSH), and by following the steps to deploy the EdgeVPN software (available for arm64 and x86) from a Debian package. We used bare metal reconfigurable ARM nodes at NCAR, since our goal was to create a single-architecture but distributed Kubernetes cluster including Raspberry Pi 4 nodes. The resulting system was a heterogeneous cluster with bare-metal ARM nodes at Chameleon connected to a distributed set of Raspberry Pi 4 ARM nodes. Any Chameleon user interested in experiments that include multiple edge and cloud nodes can use the software by following the quick start steps described in the EdgeVPN website.</p>

<p dir="ltr"><b id="docs-internal-guid-3b41ad8a-7fff-51a9-7330-2d085b9046f8">Can you point us to artifacts connected with your experiment that would be of interest to our readership? </b></p>

<p dir="ltr">You can use the EdgeVPN software for your own cross-edge experiments with Chameleon and beyond! To get started, visit <a href="https://edgevpn.io">https://edgevpn.io</a> for more information on deploying your own edge virtual networks. Documentation, video demonstrations, and downloadable software are all available from the EdgeVPN website. Also, feel free to contact the authors if you have any questions or interest in collaborations!</p>

<p dir="ltr"><b id="docs-internal-guid-a004d42a-7fff-0164-6ab0-0e862ae75ae9">Most powerful piece of advice for students beginning research or finding a new research project?</b></p>

<p dir="ltr">Bring purpose to your research, and aim to find problems that bring you joy in solving, and a positive impact on society </p>

<p dir="ltr"><b id="docs-internal-guid-dc1cc5eb-7fff-744a-d1e1-3108102a2c7c">How do you stay motivated through a long research project?</b></p>

<p dir="ltr">I find that exploring collaborations with researchers in other domains - for instance, I work now with ecologists and biologists - helps me step out of the computer systems bubble and stay motivated to do research that has tangible impact</p>

<p dir="ltr"><b id="docs-internal-guid-aabb86af-7fff-c95f-1f98-17096bfb781c">Are there any researchers you admire? Can you describe why?</b></p>

<p dir="ltr">One that comes to mind is Carl Sagan. He was a champion of humanism and his impact went much beyond innovations in space exploration, but also in bringing the beauty of the universe and science to the broader public through programs like Cosmos - which motivated me to pursue science as a kid.</p>

<p dir="ltr"><b id="docs-internal-guid-0933b988-7fff-2acf-b595-3140c1e5b7ed">Why did you choose this direction of research?</b></p>

<p dir="ltr">I’ve always been fascinated at the power of virtualization and the potential that “any problem in computer science can be solved by another level of indirection.”, a quote attributed to Roger Needham (who attributed it to David Wheeler). I’ve also been fascinated by the elegant power of self-organizing peer-to-peer networks in dealing with complexities that arise when systems need to scale and deal with dynamic events including failures. I chose this direction of research as it brought these two thrusts together to solve an important practical problem with applications in edge computing.</p>

<p dir="ltr"><b id="docs-internal-guid-512fa847-7fff-7ae8-3638-39b3553fec00">Author profile</b></p>

<p dir="ltr"><b id="docs-internal-guid-3c8f57ad-7fff-9f2d-055a-8d5ff5ff689f"><img alt="Renato Figueiredo" src="https://chameleoncloud.org/media/filer_public/e7/62/e76209e3-d7c0-407e-84c5-e03c55cf98f9/author.jpg" style="width: 384px; height: 512px;"></b></p>

<p dir="ltr">My name is Renato Figueiredo and I am a Professor in the ECE Department at the University of Florida and lead PI of the EdgeVPN project. My interests are in computer systems, in particular in the application of virtualization in distributed systems, and networking. One of my aspirations is to contribute with open-source software that can be widely adopted by the computer systems community and the public at large to solve problems and advance the state of the art. My hobbies include photography and digital editing. <br>
LinkedIn: <a href="https://linkedin.com/in/renato-figueiredo-93b2742">linkedin.com/in/renato-figueiredo-93b2742</a></p>

<p dir="ltr"><b id="docs-internal-guid-3c8f57ad-7fff-9f2d-055a-8d5ff5ff689f"><img alt="Kensworth Subratie" src="https://chameleoncloud.org/media/filer_public/f3/4e/f34e2e09-7743-4b19-83b9-a5494ee40b29/kensworth.png" style="width: 183px; height: 203px;"></b></p>

<p dir="ltr">I am Kensworth Subratie, a postdoctoral researcher at the University of FL and a contributor to the research, design, and development of EdgeVPNio. My research interests are concurrent, distributed, and P2P systems, network virtualization, and software system design. <br>
LinkedIn: <a href="https://linkedin.com/in/ken-subratie/">linkedin.com/in/ken-subratie/</a></p>

<p dir="ltr"> </p>