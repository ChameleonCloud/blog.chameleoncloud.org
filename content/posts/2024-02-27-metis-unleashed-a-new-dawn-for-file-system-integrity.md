---
abstract: "<p>File systems are a fundamental part of computer systems, which organize\
  \ and protect the files and data on assorted devices, including computers, smartphones,\
  \ and enterprise servers.\_Due to its crucial role, vulnerabilities and bugs in\
  \ the file system can lead to severe consequences such as data loss and system crashes.\_\
  After decades of development, file systems have become increasingly complex, yet\
  \ bugs continue to emerge.\_Meanwhile, many new file systems are invented to support\
  \ new hardware or features, often without undergoing comprehensive testing. To address\
  \ these gaps, we develop a checking framework (Metis) that can thoroughly and efficiently\
  \ test file systems and is easy to apply to a wide range of file systems. Metis\
  \ helps developers and users identify file system bugs and offers directions for\
  \ reproducing and fixing them.</p>"
authors:
- Yifei Liu
categories:
- User Experiments
date: '2024-02-27 18:42:47+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/83/63/83633785-178a-43a5-8e5f-287ffd60f5b7/author_image.jpg
related_posts:
- slug: chameleon-is-coming-to-fast-2024
  title: Chameleon Is Coming to FAST 2024
- slug: chameleon-at-fast
  title: Chameleon at FAST
- slug: reproducing-solid-state-drive-simulator-research-results-chameleon
  title: Reproducing Solid State Drive Simulator Research Results on Chameleon
slug: metis-unleashed-a-new-dawn-for-file-system-integrity
subtitle: ''
title: 'Metis Unleashed: A New Dawn for File System Integrity'
---

<p>File systems are a fundamental part of computer systems, which organize and protect the files and data on assorted devices, including computers, smartphones, and enterprise servers. Due to its crucial role, vulnerabilities and bugs in the file system can lead to severe consequences such as data loss and system crashes. After decades of development, file systems have become increasingly complex, yet bugs continue to emerge. Meanwhile, many new file systems are invented to support new hardware or features, often without undergoing comprehensive testing. Given these circumstances, there is a need for a model-checking framework that can thoroughly and efficiently test file systems and is easy to apply to a wide range of file systems. Research is needed to determine the appropriate framework, implementation, and tools to facilitate robust file-system checking.</p>

<h1>Our Research Findings</h1>

<p><img height="auto" src="https://chameleoncloud.org/media/filer_public/b1/c7/b1c7c867-0a35-4b85-9e45-9fa50fe83156/metis-diagram.png" width="100%"></p>

<p><strong>Figure 1</strong>: Diagram showing the architecture of the Metis framework</p>

<p>To address these gaps in file-system reliability, we developed a file system checking framework called <a href="http://github.com/sbu-fsl/Metis">Metis</a>, named after the <a href="https://en.wikipedia.org/wiki/Metis_(mythology)">Titaness in Greek mythology</a>. Metis helps developers and users identify file system bugs and offers directions for reproducing and fixing them, thereby enhancing reliability. Our approach combines two classic techniques—model checking and differential testing—to test file systems while enabling optimization beyond traditional procedure. Metis’s architecture is shown in the <strong>Figure 1</strong> above. The “input driver” (1) in the architecture generates test cases containing a sequence of operations that execute on the 1) “File System Under Test” and 2) “Reference File System.” The Reference File System acts as a standard for the File System Under Test. If there is a discrepancy between these file systems’ behaviors, our framework flags it as a potential bug. The architecture also provides an "event logger" (4) to monitor the checking process and an "optimized replayer" (5) to help reproduce found bugs.</p>

<p>Our objective with the Metis framework is to comprehensively explore the different states of file systems, where “state” encompasses the file system’s content, status, and context. File systems are intricate and possess a vast state space. Therefore, Metis has a "state explorer" (2) designed to focus on only “interesting” states, avoid duplicates, and effectively cover numerous corner cases. We also developed a new file system, <a href="http://github.com/sbu-fsl/RefFS">RefFS</a>, as a model of an efficient and reliable reference file system. We thoroughly checked RefFS to ensure it is trustworthy enough to represent correct file system behaviors.</p>

<p>With Metis and RefFS, we have already detected 15 bugs in nine file systems and are continuing to check more file systems to improve their reliability and stability. We open-sourced our research artifacts, hoping that people will use our work to test their file systems and enhance the reliability of modern storage stacks. In the long run, we aim to generalize our framework for testing more software systems, such as databases and network systems.</p>

<h1>Running the Experiment on Chameleon</h1>

<p>Our experiments were CPU- and memory-intensive and required several interconnected machines working in unison to address a large problem collaboratively. Chameleon offers a broad spectrum of hardware and many useful features, which aided in locating, acquiring, and configuring the most suitable computing resources that we needed.</p>

<p>We tested Metis on Chameleon with Ubuntu 22.04 and Ubuntu 20.04 with the following Linux kernel versions: 5.4.0, 5.15.0, 5.19.7, 6.0.6, 6.2.12, 6.3.0, or 6.6.1. We used Chameleon’s <a href="https://chameleoncloud.org/hardware/">hardware catalog</a> and <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/reservations.html">host availability browser</a> to determine the required hardware's availability. We then reserved the hardware via the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/gui.html">Chameleon GUI</a>, which provides a user-friendly interface for visualizing the status of other hosts. This feature simplified the task of prioritizing our experiments, because varying experiments required distinct hardware specifications. Next, we created the bare-metal instances associated with a floating IP and our favorite disk image. In addition to various hardware options, Chameleon also offers a wide range of <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images.html">images</a> and appliances and even allows users to use their own <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images.html#the-cc-snapshot-utility">snapshotted images</a>. This feature substantially simplified the process of transitioning between different experimental environments. Finally, we conducted experiments on the instances and collected extensive results and data, which you can regenerate yourself with our artifacts linked below.</p>

<p>Our experiment benefited from a variety of assorted features on Chameleon, mainly <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/baremetal.html">bare-metal reconfiguration</a> and <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images.html#the-cc-snapshot-utility">snapshot utilities</a>. Checking different file systems in this experiment called for varied system settings. Given the easy-to-use bare-metal reconfiguration, we could flexibly tailor hardware and test environments. If this feature had not been available, we would have had to set up a exclusive machine for a single or just a few file systems, which would have negatively impacted the efficiency of performing experiments with multiple file systems. The snapshot utility was also indispensable for our experiments testing the kernel file system, which included kernel hacking and debugging. There was a risk that these experiments would crash the system or cause it to become unbootable. The snapshot utility allowed us to take and revert to a snapshot as required. This capability was crucial for preserving experimental progress and vital data during high-risk experiments on the cloud.</p>

<h1>Experiment Artifacts</h1>

<p>Our artifacts demonstrate and evaluate the functionalities presented in our USENIX FAST 2024 paper, titled “Metis: File System Model Checking via Versatile Input and State Exploration.” The paper and accompanying presentation slides will be available at <a href="https://www.usenix.org/conference/fast24/presentation/liu-yifei">https://www.usenix.org/conference/fast24/presentation/liu-yifei</a> after the conference. Our artifacts have been evaluated by the FAST 2024 Artifact Evaluation Committee and assigned all 3 badges: Artifacts Available, Artifacts Functional, and Results Reproduced. We have made all the artifacts publicly available on GitHub and packaged the Metis artifact via Chameleon's Trovi service and Zenodo.</p>

<p>These artifacts generate one or multiple verifiers (or VTs) to run two file systems concurrently, and all the file system operations, file system states, and detected discrepancies are recorded in Metis logs. Any discrepancy is considered as a potential bug. Users can use these logs and saved file system images to confirm and reproduce file system bugs detected by Metis.</p>

<p><strong>GitHub repositories</strong>:<br>
<a href="https://github.com/sbu-fsl/Metis">Metis</a><br>
<a href="https://github.com/sbu-fsl/RefFS">RefFS</a></p>

<p><strong>Chameleon Trovi</strong>: <a href="https://www.chameleoncloud.org/experiment/share/9bf607e5-038c-4b15-bf29-12d5c07e86b2">https://www.chameleoncloud.org/experiment/share/9bf607e5-038c-4b15-bf29-12d5c07e86b2</a></p>

<p><strong>Zenodo</strong>: <a href="https://zenodo.org/records/10537199">https://zenodo.org/records/10537199</a></p>

<h1>User Interview</h1>

<p><img height="auto" src="https://chameleoncloud.org/media/filer_public/83/63/83633785-178a-43a5-8e5f-287ffd60f5b7/author_image.jpg" width="50%"></p>

<p><strong>Tell us a little bit about yourself.</strong></p>

<p>I am Yifei Liu, a fifth-year Ph.D. student in computer science at Stony Brook University. I am advised by Prof. Erez Zadok in the File Systems and Storage Lab (FSL). I also work closely with a few other illustrious researchers, such as Dr. Gerard Holzmann (Nimble Research), Prof. Geoff Kuenning (Harvey Mudd College), and Prof. Scott Smolka (Stony Brook University). My research topics mainly lie in file system model checking, testing, and verification. I am interested in everything about computer storage, including file systems, caching, storage devices, and cloud storage. My hope and career goal is to enhance the existing storage infrastructure by boosting its performance, reliability, and intelligence. I enjoy reading, hiking, skating, and skiing when I am free.</p>

<p><strong>Most powerful piece of advice for students beginning research or finding a new research project?</strong></p>

<p>My advice is that when finding or starting a research project, the first question to ask should be, “Is this an important problem?”, rather than, “Is this an easy problem?” When tackling important problems, even if they are difficult, your efforts and curiosity will eventually lead to something significant.</p>

<p><strong>How do you stay motivated through a long research project?</strong></p>

<p>Computer system research can be time-consuming and struggling. I am grateful to work in a supportive team. My advisor demonstrates great patience and gives me plenty of advice whenever I encounter challenges in the research project. Engaging in conversations with people, including professors, students, and industry professionals, is helpful in broadening my research scope and keeping me motivated. Moreover, in a long research project, it's important to value small achievements, as they contribute to boosting your confidence and fortitude in addressing challenges along the journey.</p>

<p><strong>Are there any researchers you admire?</strong></p>

<p>I really admire Samuel C. C. Ting, an MIT Physics Professor and Nobel Laureate, for his diligence, perseverance, curiosity, and pragmatism in scientific research. He has devoted his career to experimental physics, working on incredibly meaningful but complex experiments, some of which are as challenging as “finding a needle in a haystack.” His advice to young researchers is to recognize the importance of experimental work. I am fond of his quote, “In reality, a theory in natural science cannot be without experimental foundations.” Even though my field is not physics, he is a role model and inspiration to me, underscoring the crucial importance of experimentation in my own research.</p>

<p><strong>Thank you for sharing your knowledge with the Chameleon community!</strong></p>

<p> </p>