---
abstract: <p>Martin Putra, a 4th year PhD student at the University of Chicago, shares
  how he used Chameleon to build and test a scalable benchmarking tool for genomics
  workflows, uncovering insights that could lead to more efficient resource management
  for these computationally intensive tasks.</p>
authors:
- Martin Putra
categories:
- User Experiments
date: '2024-08-27 03:02:03+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/8e/71/8e71e005-918a-435a-a0d8-0edf882371f5/martin_putra.jpg
related_posts:
- slug: rethinking-memory-management-for-multi-tiered-systems
  title: Rethinking Memory Management for Multi-Tiered Systems
- slug: real-time-scheduling-for-time-sensitive-networking-a-systematic-review-and-experimental-study
  title: 'Real-time Scheduling for Time-Sensitive Networking: A Systematic Review
    and Experimental Study'
- slug: optimizing-production-ml-inference-for-accuracy-and-cost-efficiency
  title: Optimizing Production ML Inference for Accuracy and Cost Efficiency
slug: towards-characterizing-genomics-workload-performance-at-scale
subtitle: Leveraging Chameleon's Bare Metal Resources to Benchmark Genomics Workflows
title: Towards Characterizing Genomics Workload Performance at Scale
---

<p>Genomics data analysis has potential to empower precision medicine by accelerating the generation of insights from large and diverse amounts of samples. For example, the analysis results can help physicians to predict the existence of cancer at an early stage, and also tailor treatment based on a patient's genetic information. Oncologists and public health specialists working with population-wide genomics data can infer the most common mutation among people in a certain geographic area, and thus guide the design of healthcare systems and policy for that area.</p>

<p>All these efforts benefit from the large amounts of samples, yet from a computational perspective, such analysis is very challenging at least for two reasons: 1.) the massive size of input data, and 2.) the diverse characteristics of genomics applications. This leads to many interesting problems in subareas of workload characterization, performance modeling, scheduling, and reliability to name a few.</p>

<h3>Research Overview</h3>

<p>One of the problems we are working on right now is the performance characterization of genomics workflows. Genomics workflows are often composed of independent applications with diverse characteristics: they can be I/O bound, compute-bound, memory-bound, or a mix of all. An intimate understanding of such characteristics, especially when the workflows are executed at large scale, is crucial to design effective scheduling &amp; resource management techniques.</p>

<p>To this end, we attempt to build a scalable benchmarking tool that is representative of the scale of a real production system. The underlying intuition is that most of the problems we face happen due to scale, thus all insights we use to solve the problems should also be based on data collected at similar scale, lest our solutions might be misguided. We have built a prototype which enables us to run a genomics workflow using open-source inputs and capture the runtime resource utilization (i.e., CPU, memory, and I/O) of each individual application. Below we show the CPU utilization pattern of 9 longest applications used by a popular genomics workflow.</p>

<div style=""><img alt="Description of image 1" src="https://chameleoncloud.org/media/filer_public/df/48/df48b957-7e22-4fd1-b130-a83c3ab0469e/image1.png" style="width: 100%; height: auto; border-radius: 4px;"> <img alt="Description of image 2" src="https://chameleoncloud.org/media/filer_public/16/eb/16eb2b85-e652-4df9-9b47-e60ea25e74b2/image2.png" style="width: 100%; height: auto; border-radius: 4px;"> <img alt="Description of image 3" src="https://chameleoncloud.org/media/filer_public/9e/c5/9ec569c1-c7bc-43a6-b211-c83ca86e4277/image3.png" style="width: 100%; height: auto; border-radius: 4px;"> <img alt="Description of image 4" src="https://chameleoncloud.org/media/filer_public/fe/95/fe956f94-f48e-46c1-9207-4c4b1f3b8ff6/image4.png" style="width: 100%; height: auto; border-radius: 4px;"> <img alt="Description of image 5" src="https://chameleoncloud.org/media/filer_public/51/33/51338735-af94-4d2f-bc22-eab09099fe3d/image6.png" style="width: 100%; height: auto; border-radius: 4px;"> <img alt="Description of image 6" src="https://chameleoncloud.org/media/filer_public/f6/0b/f60bb160-19fe-46e4-a3ef-2c8d5afaa4eb/image7.png" style="width: 100%; height: auto; border-radius: 4px;"> <img alt="Description of image 7" src="https://chameleoncloud.org/media/filer_public/c9/cb/c9cb1831-7cc8-494c-9ffb-9589a34e6800/image8.png" style="width: 100%; height: auto; border-radius: 4px;"> <img alt="Description of image 8" src="https://chameleoncloud.org/media/filer_public/ee/f8/eef8857f-e66e-4dc2-b842-16e0567f1618/image9.png" style="width: 100%; height: auto; border-radius: 4px;"> <img alt="Description of image 9" src="https://chameleoncloud.org/media/filer_public/2f/b6/2fb65698-0c87-4b93-abaa-a7c546c2e756/image10.png" style="width: 100%; height: auto; border-radius: 4px;"></div>

<p><small><strong>Figure 1.</strong> CPU Utilization Patterns. Each subfigure shows the CPU utilization pattern for 9 applications used in a popular genomics workflow. Their dynamicity suggests opportunities to reclaim compute resources at a fine-grained level. x-axis: time since application starts (seconds), y-axis: amount of cores used x 100%.</small></p>

<p>These initial results provided us with an interesting observation: even for highly parallelizable applications which we thought will completely saturate a machine's CPU resources, their utilization patterns are dynamics (there are recurring up and lows) due to interleaving I/Os operations, and there are resource reclamation opportunities at a fine-grained level. We build upon this observation and devise a resource reclamation technique specifically tailored for these genomics applications. This is one example of how the data generated by our benchmarking tool can guide the design of novel systems support.</p>

<h3>Running the Experiment on Chameleon</h3>

<p>As we aim to build a benchmarking tool that can characterize performance at scale, it is imperative to also have an infrastructure &amp; enough computational resources to execute the workload at scale. We found Chameleon immensely helpful in this regard. Our tool is designed to run on a cluster, thus we need multiple machines that can easily communicate with each other. We also need a large amount of storage to stage the genomics workflow inputs, which can easily reach tens of GBs per sample. We use the hardware catalog extensively to choose appropriate node types with enough CPU, memory, storage, and I/O bandwidth. We also use Chameleon's CLI to automate a big part of our infrastructure setup.</p>

<p>We are especially fond of Chameleon's bare metal capabilities. It is known that there are performance variations between execution on bare metal vs virtualized environments. By characterizing performance on bare metal and VMs separately, the data we generate becomes richer, and we have solid grounds to claim how certain applications will perform given certain hardwares. Chameleon's object store, with PBs capacity, allows us to store large input files easily. We imagine setting up data storage would be much more difficult without this feature.</p>

<p>We plan to open-source our benchmarking tool once it is ready. Please stay tuned!</p>

<h3>User Interview</h3>

<p><img src="https://chameleoncloud.org/media/filer_public/8e/71/8e71e005-918a-435a-a0d8-0edf882371f5/martin_putra.jpg" width="80%"></p>

<p><strong>Tell us a little bit about yourself</strong></p>

<p>I am a 4th year Computer Science PhD student at the University of Chicago. My previous works were on storage systems reliability; this continues to interest me, but I'm currently focused on designing and building novel systems support for large-scale genomics data processing. I think I stumbled upon a subfield with lots of interesting &amp; potentially impactful problems. If possible, I would like to continue a similar line of work, preferably in academia. Outside of work you might find me in museums, orchestras, or simply reading a book in open space.</p>

<p><strong>Most powerful piece of advice for students beginning research or finding a new research project?</strong></p>

<p>Believe in the process! Keep on doing the good habits. You will be surprised by how far you walked.</p>

<p><strong>How do you stay motivated through a long research project?</strong></p>

<p>I often try to imagine how my work would fit in the 'bigger picture'. This gives me the reassurance that what I'm doing is indeed meaningful, although it's probably small, and each day is filled with failed experiments (alas). I also try to cherish the small wins – any improvement, however small, might be a sign that we're in the right direction. Keep pushing!</p>

<p><strong>Are there any researchers you admire? Can you describe why?</strong></p>

<p>There are people whom I think are very bold &amp; visionary in their works. They believe that the field is moving / should move towards a certain direction, they anticipate the challenges, then their works 'ease' the way for the whole community to move forward. I think it's a very admirable way of doing science.</p>

<p><strong>Thank you for sharing your knowledge with the Chameleon community!</strong></p>