---
abstract: "<p>Today's Tips&amp;Tricks blog spotlights one of the Chameleon Associate\
  \ Sites: the\_Electronic Visualization Laboratory\_(EVL) at the University of Illinois\
  \ Chicago. Learn about the hardware availability at the site, the motivation behind\
  \ creating it, and some hands on insights gained in the process of deploying CHI\
  \ in a Box on the site!</p>"
authors:
- Lance Long
categories:
- Tips and Tricks
date: '2022-11-29 02:58:26+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/60/e5/60e58a64-abf8-45c4-b51e-7c92c27288b2/continuum.png
related_posts: []
slug: haswells-are-back-an-interview-with-the-uic-associate-site
subtitle: ''
title: 'Haswells are Back: an Interview with the UIC Associate Site'
---

<p>Last year we announced the <a href="https://www.chameleoncloud.org/blog/2021/05/03/chameleon-legacy-hardware/">Chameleon Legacy Hardware program</a> – today we bring you an interview with  Lance Long of EVL@UIC, who was one of the receipients of the program. More information about the EVL Chameleon site and the challenges of its construction can be found in the <a href="https://www.chameleoncloud.org/media/filer_public/00/fb/00fb4562-d381-4e7e-b642-bab7268d5321/pearc22-chi-in-a-box.pdf">PEARC'22 paper</a>.   </p>

<p><strong>CHI:</strong> Lance, welcome to the Chameleon family and congratulations on setting up your Chameleon Associate Site! We’d love to hear about your experiences with the process, the experiments you support, and the plans you have for the types of resources that you would like to make available for science. Can you please tell us first about your institution and the research groups it supports ? </p>

<p><strong>Lance: </strong>The <a href="https://www.evl.uic.edu">Electronic Visualization Laboratory (EVL)</a> is an interdisciplinary research laboratory in the UIC College of Engineering’s Computer Science department. EVL specializes in collaborative visualization, virtual reality, visual data science, and advanced ML/AI computing and networking infrastructure.</p>

<p> </p>

<p><strong>CHI:</strong> What hardware does your site offer to Chameleon users? </p>

<p><strong>Lance: </strong>The EVL at the University of Illinois Chicago site provides 8 Haswell nodes retired from Texas Advanced Computing Center (TACC) with additional nodes ready to come online pending a master node OS upgrade. The EVL site can be accessed with an existing Chameleon Account, Projects, and Allocations. Each node is equipped with 24 cores (48 threads), 128 GB of RAM, 2x 1G network connections, and a 250GB hard drive. Hardware details and availability can be reviewed on the hardware discovery page.</p>

<p>In addition to contributing resources to Chameleon, researchers at UIC area also its users. Practical AI applications are increasingly relying on complex deep learning models and large datasets. The communication phase is often the performance bottleneck of the applications and prevents linear scale-out of systems. Approaches to improve the communication efficiency are in research at UIC with experiments run on interconnected GPU nodes to calculate baseline performance metrics. Chameleon is an open testbed that can provide the hardware required for this distributed training research. Dedicated computing resources such as GPUs interconnected with a fast network are required to run the benchmarks. The performance bottleneck of the communication phase shows itself best when enough worker nodes equipped with GPUs are dispersed in a network. Chameleon resources across multiple sites are a good fit for this type of research.<br>
 </p>

<p><strong>CHI:</strong> Why did it make sense for EVL and IIT  to become a Chameleon Associate Sites? </p>

<p><strong>Lance:</strong> The UIC research community utilizes a broad range of innovative cyberinfrastructure services. EVL has a 100Gbps network path to the StarLight International/National Communications Exchange Facility. StarLight, designed by researchers, for researchers, is an open exchange facility that provides connectivity among multiple key science sites – nationally, internationally, regionally, and locally. EVL was also a founding member of the Global Research Platform (GRP), an international scientific collaboration aimed to create one-of-a-kind advanced ubiquitous services that integrate resources around the globe. EVL has substantial computing facilities consisting of bare metal clusters supporting NSF (MRI) instruments, including COMPasS DLV,  NSF MRI #CNS-18282, a composable infrastructure instrument supporting GPU containers and virtual machines for machine learning and real-time visualization. This system supports computing requirements for several UIC College of Engineering faculty and complements campus production resources, as well as Federally-funded community computational resources. Additionally, EVL hosts resources for the National Research Platform (NRP) Nautilus Hypercluster, providing 300GB Ceph storage, 128 CPU cores and 21 GPUs. EVL provides access to these cloud systems along with providing campus data transfer resources, network time services and a perfSONAR network measurement system. Over the years, EVL has had much success distributing (open-source) and commercializing its visualization and virtual-reality hardware and software systems, and building and supporting user communities on a global scale. EVL’s history of maintaining large instruments and participating in national and global research testbeds provides an ideal location for a Chameleon Associate site.</p>

<p><strong>CHI: </strong>Tell us about your journey – what did setting up an Associate Site involve on a practical level, what challenges did you encounter, and how did you overcome them?</p>

<p><strong>Lance: </strong>In 2021, EVL began a collaboration with the Chameleon project and took delivery of 21 P1 Haswell nodes from TACC’s (Texas Advanced Computing Center) original Chameleon allocation. The shipment included a rack with these nodes and additional nodes for Northwestern University’s iCAIR. The rack arrived damaged and required the nodes to be transferred. The original fiber interconnections and switch were not included in the shipment. A copper ethernet switch was deployed utilizing the available onboard 1GbE connections on the nodes. The CHI-in-a-box site at EVL was deployed by an undergraduate student who had experience working on several EVL compute clusters, and most recently deployed EVL’s NSF-funded COMPaaS system. Our OpenStack experience was limited to understanding the fundamental vocabulary of the platform. CHI-in-a-box’s complex network structure, fundamental to the operation of the system, required intensive troubleshooting to verify behaviors across many components and, at times, produced misleading network status logs. Significant help from Chameleon’s support team was required to get the site fully deployed. While the site is fully deployed and operational, there is still effort to be completed on transitioning to a new master node and enabling more advanced features. </p>

<p><strong>CHI:</strong> Regarding the CHI configuration process itself: how do you compare setting up a CHI site to working with other academic infrastructure? </p>

<p><strong>Lance:</strong> CHI-in-a-box’s complex network structure, fundamental to the operation of the system, required intensive troubleshooting to verify behaviors across many components. At the same time, the CHI-in-a-box network is significantly simpler to understand when compared to our experience with Kubernetes, which creates many more virtual interfaces and opaque networks. </p>

<p>Cluster state management posed some difficulty as, at times, different services held competing cluster state data. Chameleon’s support team helped significantly to synchronize the different services, however, there remained times where a forced state resynchronization and manual changes to state data were required. This leaves room for improvement compared to Kubernetes, as Kubernetes can seamlessly recognize most changes in cluster state, rarely requiring manual intervention. Kubernetes is a containerization and orchestration tool, OpenStack is a cloud service tool, so comparisons between them are limited as they address a different group of users and workloads. </p>

<p>Overall, we found the deployment of CHI-in-a-box seamless and impressive in its scope, providing a more robust cluster infrastructure system than our experience with Kubernetes and MAAS.io. As expanded documentation and troubleshooting guides become available, the CHI-in-a-box deployment process will be faster and more hands free when compared to other “shrinkwrapped” bare metal infrastructures.<br>
<br>
<strong>CHI: </strong>How did you like working with the Chameleon operations team?</p>

<p><strong>Lance: </strong>The Chameleon operations team are friendly and readily available to answer questions. Management of the system has been learned entirely through the help of the team and their resourcefulness to resolve issues. They were crucial to successful deployment of the site and its continued maintenance.<br>
 </p>

<p><strong>CHI: </strong>What advice would you give to others wanting to configure Chameleon Associate sites?</p>

<p><strong>Lance: </strong>Strong systems knowledge, experience in infrastructure deployments would be beneficial. The CHI-in-a-box site at EVL was deployed by an undergraduate student who previously only had experience working on various EVL compute clusters. <br>
 </p>

<p><strong>CHI: </strong>Tell us a little bit about yourselves and your hopes, dreams, and aspirations for research infrastructure. </p>

<p><strong>Lance: </strong>Cyberinfrastructure includes multiple technologies to support advanced research across engineering and related fields, including expertise to support the researchers and their work in data science, artificial intelligence / machine learning / deep learning, and visualization. We design and develop novel instrumentation, innovative spaces and applications with faculty, graduate and undergraduate students and staff. This includes deploying technologies such as Jupyter notebooks to control composable infrastructure enabling researchers to tailor resources of a machine. We also participate in interdisciplinary exchanges with collaborators and demonstrations by maintaining infrastructure testbeds with external collaborators (i.e. Starlight, Chameleon, NRP) and engage with industry in research and commercialization. <br>
 </p>

<p> </p>