---
abstract: <p>In this study, Chuanyu Xue tackles the complex challenge of optimizing
  Time-Sensitive Networking (TSN) for real-world applications. Using Chameleon's powerful
  computing resources, he conducts a comprehensive evaluation of 17 scheduling algorithms
  across 38,400 problem instances. This research not only sheds light on the strengths
  and weaknesses of various TSN scheduling methods but also demonstrates how large-scale
  experimentation can drive advancements in network optimization. Readers will gain
  insights from Xue's journey, including key findings, implementation challenges,
  and valuable tips for leveraging Chameleon in their own research.</p>
authors:
- Chuanyu Xue
categories:
- User Experiments
date: '2024-06-25 22:08:34+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/a8/82/a882fe3f-eb26-4b47-9ba5-ad1c4380df27/image5.png
slug: real-time-scheduling-for-time-sensitive-networking-a-systematic-review-and-experimental-study
subtitle: Optimizing Network Performance with Chameleon's Computing Power
title: 'Real-time Scheduling for Time-Sensitive Networking: A Systematic Review and
  Experimental Study'
---

<p>Imagine a world where every device in your home required its own unique network to communicate. Your living room would be a tangled mess of wires, and the cost of maintaining these separate networks would be astronomical.</p>

<p> </p>

<div style="display: flex;"><img height="auto" src="https://www.chameleoncloud.org/media/filer_public/e1/3f/e13f8bed-f121-44a4-8b58-b34fe2c0fbee/image3.jpg" width="50%"> <img height="auto" src="https://www.chameleoncloud.org/media/filer_public/c0/34/c03456a5-39e2-4a62-a2b2-1a07767fd64e/image1.jpg" width="50%"></div>

<p> </p>

<p>This scenario reflects the challenge faced by many industries today, where different types of communication, each with their own safety requirements, demand separate networks. For example, sensor data might use serial communication, motion control relies on CAN-bus, high-resolution video cameras require Ethernet, and safety operations need yet another network. While this approach ensures safety and reliability, it also significantly increases system complexity and cost, making maintenance a nightmare. If you've ever seen the communication system within an aircraft at NASA, you'll understand the scale of the problem—countless wires for each subsystem, all in the name of safety.</p>

<p> </p>

<p><img height="auto" src="https://www.chameleoncloud.org/media/filer_public/a8/82/a882fe3f-eb26-4b47-9ba5-ad1c4380df27/image5.png" width="100%"></p>

<p> </p>

<p>To address this issue, Time-Sensitive Networking (TSN) was developed. TSN is a set of standards built upon Ethernet, developed by the IEEE 802.1 working group to address the challenges of mixed critical communication within a single network. It defines traffic shaping and scheduling techniques to support different levels of communication, ensuring that data with varying importance and timing requirements can coexist on the same network without causing congestion or delays. TSN also supports features like network-wide synchronization, stream reservation, and redundancy for uninterrupted communication. However, configuring TSN networks for specific use cases remains a challenge. This is where my research comes in, aiming to create a benchmark for systematically understanding and comparing existing TSN scheduling methods.</p>

<h2>Research Overview:</h2>

<p>My study makes three key contributions. First, I propose a model-based categorization to compare approaches used by each scheduling method. Second, I set up a physical testbed for hardware validation. Finally, I create a comprehensive benchmark considering relevance, fairness, and reproducibility. For this last part, I rely on Chameleon to conduct large-scale experiments on online computing platforms.</p>

<p> </p>

<p><img height="auto" src="https://www.chameleoncloud.org/media/filer_public/b9/eb/b9eb0b27-d1d6-414e-951b-1335e1599913/image2.jpg" width="100%"><br>
<small>High-level preview of the large-scale experiment results based on Chameleon</small></p>

<h4><strong>Key Findings</strong>:</h4>

<p>Using Chameleon, I conducted comprehensive evaluation experiments on 17 scheduling algorithms across 38,400 problem instances with two evaluation metrics. I'll discuss two major findings here, while more details can be found in my paper.</p>

<p>First, using different evaluation metrics can yield inconsistent comparison results, suggesting the need for diverse metrics to better understand the pros and cons of algorithms. Second, schedulability varies under different settings, even when using the same evaluation metric, highlighting the importance of comprehensive experiment settings to avoid bias. These findings should help the community better understand existing TSN scheduling methods and provide insights for future development.</p>

<h4><strong>Experiment Implementation on Chameleon</strong>:</h4>

<p>My experiments involve solving optimization problems using third-party mathematical solvers and self-implemented algorithms in Python. These tasks are CPU and memory-intensive, and I faced three main challenges during implementation.</p>

<p>The first challenge was managing many computing servers effectively. I allocated 16 compute_zen3 nodes, each with 2 AMD EPYC® CPUs (64 cores per CPU, 2.45 GHz) and 256 GB DDR4 memory. I used the bare metal model and SSH for connections. A useful tip I discovered is to configure a single node, save its system image with the cc-snapshot utility, and then boot other nodes using this image. For code synchronization, I used GitHub to pull the latest code to the Chameleon nodes. Another tip is configuring the same RSA key on different nodes allows for a single SSH key configuration on GitHub.</p>

<p>The second challenge was conducting experiments efficiently. With 17 scheduling methods and 38,400 problem instances, I needed to run over 650,000 experiments. To reduce runtime, I developed a strategy for parallel execution on multi-core processors using Python's multiprocessing library. I employed the longest-processing-time-first strategy within single nodes and balanced workload across multiple nodes based on estimated runtimes.</p>

<p>The final challenge was collecting results. I used SSH to download data at more than 1Gb speed, thanks to Chameleon's high-speed network. A useful tip is to use a script to download results in real-time instead of waiting for the experiment to finish, preventing data loss due to expired leases.</p>

<h4><strong>Chameleon Features Utilized</strong>:</h4>

<p>The features of Chameleon crucial for my experiment include large amounts of computational resources with consistent node performance, the bare-metal model for customized resource management, SSH that supports full speed data exchange, and custom kernel boot for convenient configuration. The bare-metal reconfiguration was particularly useful as it allowed me to have full control over the environment.</p>

<p>If Chameleon wasn't available, it would have significantly impacted my experiment. The scale of computational resources and the flexibility to configure them according to my needs would be hard to find elsewhere. It might have been possible to carry out the experiment on a smaller scale, but it would have been much harder and time-consuming, potentially affecting the comprehensiveness of my results.</p>

<h2>Experiment Artifacts:</h2>

<p>For those interested in delving deeper into my research, you can find my paper titled "<a href="https://arxiv.org/abs/2305.16772">Real-Time Scheduling for 802.1Qbv Time-Sensitive Networking (TSN): A Systematic Review and Experimental Study</a>" on arXiv. The source code for my project is available on GitHub under the repository name "<a href="https://github.com/ChuanyuXue/tsnkit">tsnkit: A scheduling and benchmark toolkit for Time-Sensitive Networking in Python</a>".</p>

<h2>User Interview</h2>

<h3>About Me:</h3>

<p>I'm a fifth-year PhD student at the University of Connecticut, working in the cyber-physical lab. My research focuses on real-time systems and their applications in time-sensitive networking. In the future, I want to find an R&amp;D job position about computer systems in industry. I primarily use C/C++, Python, and GoLang for my work. Additionally, I'm independently developing iOS/macOS applications using SwiftUI.</p>

<p>In my free time, I enjoy reading, cycling, veggie planting, and coffee brewing. Here's an interesting tidbit about me: I was previously an independent musician in China, where my music earned over 247k listens online!</p>

<h3>Advice for Aspiring Researchers:</h3>

<p>If I could offer one piece of advice to students beginning research, it would be this: find a research style that you enjoy. Computer science research allows for different approaches, from solving problems through real implementation to working with mathematical abstractions or conducting experiment-based research. Each style has its own advantages and is suited to solving different problems. The important thing is to discover which style you are most interested in and better suited for, and then dedicate time to learning and working in that area.</p>

<h3>Staying Motivated:</h3>

<p>To me, the most helpful insight for staying motivated is to recognize that PhD progress is more like an area (integral) than a height. If we plot our progress, the horizontal axis represents time, and the vertical axis represents our progress at each moment. The total progress we make isn't determined by where we are right now, but by the area covered under the entire line segment.</p>

<p>When we feel frustrated, we should remember that we can't measure our entire Ph.D. life by our current state. It depends on whether we have consistent reading, coding, writing, and thinking over the long term. This perspective helps me stay motivated even during challenging times, knowing that consistent effort over time is what truly matters.</p>

<p>In conclusion, my research on TSN scheduling methods, facilitated by the powerful resources of Chameleon, has provided valuable insights into the field. It's my hope that this work will contribute to more efficient and reliable network configurations in various industries, potentially reducing the complexity and cost of communication systems. As I continue my journey in computer science research, I look forward to tackling more challenges and making further contributions to this exciting field.</p>

<p><strong>Thank you for sharing your knowledge with the Chameleon community!</strong></p>