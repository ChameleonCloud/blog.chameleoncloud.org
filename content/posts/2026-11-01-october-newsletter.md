---
abstract: '<p>Lots of good news this month: meet with Chameleon at SC and hear about
  our new venture into AI-augmented experiment design, fantastic new artifacts on Trovi
  created by our users that could give you a serious leg up with your experimentation,
  lots of new features and improvements on the system, and insights into what’s trending
  on Chameleon…</p>'
authors: []
categories:
- Chameleon Changelog
- Featured
date: '2026-11-01'
featured: true
hide_image: true
image: 'https://chameleoncloud.org/media/filer_public/3e/a5/3ea5c5e0-7937-4511-b064-8548a8e6751b/falco-negenman-3ip7w74bupc-unsplash.jpg'
related_posts:
- slug: chameleon-newsletter-changelog-september-2026
  title: Chameleon Newsletter & Changelog September 2026
- slug: chameleon-newsletter-changelog-august-2026
  title: Chameleon Newsletter & Changelog August 2026
- slug: chameleon-newsletter-changelog-july-2026
  title: Chameleon Newsletter & Changelog July 2026
slug: chameleon-newsletter-changelog-october-2026
subtitle: 'Welcome to the Chameleon October 2026 Newsletter!'
title: 'Chameleon Newsletter & Changelog October 2026'
---

<p><img src="https://chameleoncloud.org/media/filer_public/3e/a5/3ea5c5e0-7937-4511-b064-8548a8e6751b/falco-negenman-3ip7w74bupc-unsplash.jpg" alt="Chameleon Newsletter &amp; Changelog October 2026" width="50%"></p>

Lots of good news this month: meet with Chameleon at SC and hear about our new venture into AI-augmented experiment design, fantastic new artifacts on Trovi created by our users that could give you a serious leg up with your experimentation, lots of new features and improvements on the system, and insights into what’s trending on Chameleon…

## Chameleon at SC26

Calling all Chameleon users and collaborators coming to SC26 in our home town of Chicago! If you are using Chameleon or would like to collaborate with us, please give us a shout – we’d love to meet you all! Quite apart from any scheduled meeting we’d like to invite everybody to the following events:

First, as many of you know we have been experimenting with using AI to help design experiments on Chameleon or other scientific clouds. [Our paper](https://chameleoncloud.org/media/filer_public/80/00/80008265-55c6-47ef-b99f-3338cac63a26/envagent_sc_workshop_2026_11.pdf) presenting preliminary results will be presented at the [AI4S: 8th Workshop on Artificial Intelligence and Machine Learning for Scientific Applications](https://ai4s.github.io) SC26 workshop on Sunday, November 15, 2026 (10:30am - 10:50am CST) in Room W183a.

Second, for those of you who are also coming to the [OpenInfra Day](https://openinfra-day-northamerica-2026.sessionize.com/schedule/day/20261117), on Tuesday November 17, 2026 in Marriott Marquis in Chicago, running in parallel with SC26, Chameleon Infrastructure Lead Mike Sherman will take the mike for a spell during the keynote to talk about the work we are doing with OpenStack – including the AI-assisted design of computational experiments above. The keynote will take place 8:00-8:40AM – so this is really a snooze you lose situation…

## New Trovi Artifacts in October

Before we tell you about all the wonderful new capabilities the Chameleon team added to the testbed, we’d like to highlight new interesting contributions from our users who published new artifacts on Trovi. These artifacts represent results from papers, educational content, or simply experiment patterns, i.e., “experiment foundations” that allow you to get started with your experimentation faster.

In October, our users contributed the following new Trovi artifacts:

- “[Reproducing Cloud Local Storage Evolution & LATTE (USENIX FAST '26)](https://trovi.chameleoncloud.org/dashboard/artifacts/901a7ac5-207e-41c9-aeeb-816e3de71e3b)” by Yizreel Schwartz Sipahutar at Institut Teknologi Del reproduces and extends the foundational cloud storage findings from the paper: “Here, There and Everywhere: The Past, the Present and the Future of Local Storage in Cloud", published by Alibaba Group and Shanghai Jiao Tong University
- “[Single node experiment pattern: CPU LLM Inference Scaling with llama.cpp](https://trovi.chameleoncloud.org/dashboard/artifacts/a07ec407-8366-43d3-ac07-3749137bf450)” from our very own Mark Powers benchmarks CPU-only large language model inference on a single Chameleon instance (bare metal or virtual) and provides a good foundation for your experimentation. This artifact is supported by the Chameleon team as attested by the Chameleon logo badge.
- “[Reproducible pgchecker MPI Experiment on Chameleon](https://trovi.chameleoncloud.org/dashboard/artifacts/dd253a2b-71d8-48e9-b6ff-cc874159583a)” from Christian Pirngruber at TU Wien runs a reproducible pgchecker MPI Experiment on Chameleon and can also be used as foundation for new experiments.
- “[MINCER](https://trovi.chameleoncloud.org/dashboard/artifacts/33ee6b66-1583-4e96-893f-711776420a6e)” by Jhonny Gonzalez and team from the University of Texas at El Paso automates the setup and monitoring of experiments using Docker containers that include performance measurement tools like PAPI (Performance Application Programming Interface) – it looks like a great experiment pattern that can help you create many new experiments!
- “[CacheBlend Reproduction](https://trovi.chameleoncloud.org/dashboard/artifacts/cff1acd4-f39f-4142-b3dd-bc5a691cb11c)” by Jack Huber at the University of Chicago (submitted on Halloween, must be scary!) configures a GPU instance to run the CacheBlend tests (see artifact content) and present the results of those tests.

In other words, plenty of new content to check out courtesy of our users – happy experimenting!

## Artifacts from PACT’26

And in addition to that – two results at the [PACT’26 Artifact Evaluation](https://pact2026.github.io/ae/) were awarded the Chameleon Reproducibility Challenge Award at the conference which took place last month. Both are available as Trovi artifacts – check them out!

[Splyce](https://trovi.chameleoncloud.org/dashboard/artifacts/4ad43ccf-564d-450a-abf2-25a99d5d3d70), authored by Kabilan Mahathevan, Poorna Gunathilaka, and Kirshanthan Sundararajah from Virginia Tech, demonstrates that by converting unpredictable control-flow into a predictable data stream, compiler-driven speculation can effectively reconcile the memory efficiency of compressed storage with the execution-unit throughput of modern superscalar architectures. Reproducing Splyce's results requires bare-metal hardware and a carefully configured experimental environment. Chameleon's Jupyter workflow makes it easier to run experiments and visualize and compare results presented at PACT'26.

[SALT](https://trovi.chameleoncloud.org/dashboard/artifacts/fa2befc9-24de-442a-9fde-2141e0502eab), authored by Yanghui Wu, Yifan Zhu, Yekai Pan, Chen Ding from University of Rochester, introduces a symbolic analysis framework that characterizes memory reuse and predicts cache misses in loop programs with rectangular iteration spaces and symbolic parameters such as problem dimensions and tile sizes. This Chameleon/Trovi artifact packages the MLIR-based implementation, benchmarks, and evaluation workflows for reproducing the experimental results presented at PACT 2026.

Congratulations to all artifact authors!

## Changelog

**Artifact verification.** Trovi is Chameleon’s sharing portal, allowing users to share digital artifacts with the community and track metrics of how many users use your artifact. This month, we’ve added a new metric: verifications. Users who run your artifact can report whether the artifact worked as expected. We hope that this metric not only helps you find working artifacts as a user, but also will help artifact authors create reliable and robust artifacts. For more information, [see our documentation](https://chameleoncloud.readthedocs.io/en/latest/technical/experiments/browsing_artifacts.html#verifying-artifacts).

**Comment notifications.** Last month, we enabled you to [leave comments on Trovi artifacts](https://chameleoncloud.readthedocs.io/en/latest/technical/experiments/browsing_artifacts.html#commenting-on-artifacts), allowing you to leave feedback, ask questions, or discuss experiments with other users. This month we improved comments by adding email notifications. When someone adds a comment to your artifact, or replies to a comment you’ve made, you’ll now be notified via email. If you would prefer less email, you can also edit your Trovi profile to turn off comment notifications entirely.

**Overhauled Trovi UI.** And if that was not enough, we’ve also improved the Trovi UI based on your feedback. The biggest change you’ll notice is the reorganized [artifact editing page](https://chameleoncloud.readthedocs.io/en/latest/technical/experiments/packaging_artifacts.html#editing-artifacts). Now, items are grouped together into more logical sections, making it much easier to find what you need. We’ve added a new metric tracking recent accesses, which only counts the number of accesses for an artifact in the last 90 days. This makes it easier to find “trending” artifacts. Additionally, we've optimized the API so that loading artifacts should be much faster when searching or listing all artifacts.

**Persistent Volumes for CHI@TACC VMs.** Back in August, we announced that you could now launch both bare metal and VM instances from the same interface at CHI@TACC. This month, we’ve updated CHI@TACC so you can attach [persistent volumes](https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_volumes.html) to your VM instances. By default, the disk in your VM is ephemeral and lost when the instance is deleted. If you attach a persistent volume to your instance, you can instead keep it around between instances, ensuring that if your lease expires you don’t lose anything important! In January, we’ll be shutting down KVM@TACC, so now that you can, be sure to migrate your volume data to CHI@TACC soon! If you want to learn more about how unifying bare metal and virtualized instances in one interface can help your experimentation, [read our latest blog](https://blog.chameleoncloud.org/posts/mix-and-match-combining-bare-metal-and-virtualized-instances/) on this topic.

**Improved CHI@Edge methods in python-chi.** Our edge testbed, CHI@Edge, lets you experiment with devices like raspberry pis and jetson nanos, all orchestrated via our python-chi library. This month, we’ve improved the methods for downloading and uploading files, and executing commands in your container. We’ve fixed all of these methods so that they work with large files or long-running commands. Previously, this would only work if your command exited within 5 seconds, or your file upload/download finished within one minute. Additionally, we improved how upload and download handle single files and directories. For more information, [see our documentation](https://python-chi.readthedocs.io/en/latest/modules/container.html#chi.container.Container.download).

**Storage Limits.** This month, we are introducing limits to our [object store](https://chameleoncloud.readthedocs.io/en/latest/technical/swift/index.html) usage. The object store is one the few resources on Chameleon that isn’t provisioned via a lease and where your usage is not time bounded – yet. To keep it as flexible as possible for as long as possible we have to ensure that no project is using more than their fair share of storage and therefore limiting individual project usage to 1TB. If you need an exception to this limit, or any of our limits, please feel free to [reach out via the help desk](https://chameleoncloud.org/user/help/).

**Image updates.** We wanted to give you notice that some of our [operating system images](https://chameleoncloud.readthedocs.io/en/latest/technical/images/index.html) are coming to the testbed in the upcoming months. Ubuntu 22.04 and Centos9-Stream are both going end-of-life in April 2027, and so we will no longer support our CC variants after this date. We recommend that you start using the newer versions of these operating systems instead. If you need to use these older, less secure images, we recommend you set it up [behind a bastion host](https://trovi.chameleoncloud.org/dashboard/artifacts/8e893a1e-4833-4a6b-b596-d046f12018ba). Additionally, our Ubuntu 26 + CUDA image will soon stop working on our p100, v100, m40, and k80 GPUs, since these boards do not support CUDA 13.

## Trending on Chameleon…

And lastly, to see what’s popular on the platform you only have to go to Chameleon Trovi and sort according to “trending” which translates into the number of accesses in the last 90 days.

So what’s trending now? Seven out of ten top artifacts on the list are part of Professor Fraida Fund’s acclaimed operational ML class at NYU – apparently this is the job everybody wants these days! The artifacts connected with this [class](https://teaching-on-testbeds.github.io/mlops-chi/) form what amounts to a digital textbook that covers topics from Chameleon basics, through cloud computing and storage, to ML-specific topics such as model training and ML-ops pipeline. The individual segments can be used standalone or as part of a class – no wonder they are popular!

With so much attention given to just one class, an even more interesting question perhaps is: what are the other three artifacts in the top ten? It looks like they are artifacts submitted through reproducibility initiatives and an experiment pattern, i.e., a base experiment that provides a foundation for a set of many experiments. In the former category we have SC26 AD/AE for "[Communication Avoiding Parallel Sketching via Sparse Subspace Embeddings](https://trovi.chameleoncloud.org/dashboard/artifacts/bcffce09-cb02-4ba1-8e92-1f30a13f96da)" from Johannes Laute at Paul Scherrer Institut – in #4 and [Splyce](https://trovi.chameleoncloud.org/dashboard/artifacts/4ad43ccf-564d-450a-abf2-25a99d5d3d70) by Kabilan Mahathevan which won the Chameleon reproducibility award at PACT’26 (see above) – in #6. Lastly, the “[Jupyter + OpenCode environment](https://trovi.chameleoncloud.org/dashboard/artifacts/d0cb594d-dd07-436f-85bd-50b09d9b7230)” experiment pattern from Professor Fraida Fund at NYU again launches a ready-to-use remote development environment on KVM@TACC, with JupyterLab and OpenCode accessible through a floating IP.

In other words – a class, reproducible artifacts from Artifact Evaluations (AE) at recent conferences, and an experiment pattern have recently been the most popular!
