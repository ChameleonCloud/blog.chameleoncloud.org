---
abstract: "<p>In this month's user experiment blog we get a fascinating insight into\
  \ how much power training deep neural networks (DNNs) consumes \u2013 and how to\
  \ make it less. The authors\u2019 discuss research presented as part of their NSDI\
  \ \u201923 paper, describe how they structured their experiments on Chameleon, and\
  \ explain why bare metal resources are essential for power management research.\_\
  </p>"
authors:
- Jae-Won Chung
categories:
- User Experiments
date: '2022-11-22 16:53:40+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/e8/37/e83761ab-5495-4b77-b1f3-7b4f4e175111/zeus.png
related_posts: []
slug: zeus-gpu-energy-as-a-first-class-resource-in-dnn-training
subtitle: ''
title: 'Zeus: GPU Energy as a First-Class Resource in DNN Training'
---

<p dir="ltr"><b id="docs-internal-guid-4a040cba-7fff-951f-4553-5eccb0f1d697">What is the central challenge/hypothesis your experiment investigates?</b></p>

<p dir="ltr">In recent years, Deep Neural Networks (DNNs) have become one of the most popular methods of implementing Artificial Intelligence (AI). The surge in DNNs was possible in large part due to a special type of hardware called GPU, traditionally built for graphics processing like gaming, but turning out to be very effective for the specific type of computation needed for training DNNs. Thus, to run DNN training, IT companies built large clusters of tens of thousands of GPUs, and the cluster is only getting larger.</p>

<p>What’s important is that GPUs are power-hungry hardware. They consume <a href="https://arxiv.org/abs/2206.05229">around 70% of the energy of the entire computer when training DNNs</a>. At extreme scales, <a href="https://arxiv.org/abs/2104.10350">training a large DNN called GPT-3 just once</a> consumes<a href="https://www.eia.gov/tools/faqs/faq.php?id=97&amp;t=3"> electricity that can supply an average US household for 120 years</a>. This might be fine if DNN training is a one-time cost,<a href="https://ieeexplore.ieee.org/document/8327042"> but actually DNNs have to be re-trained, as frequently as every hour, to incorporate new data flowing in from users</a>.</p>

<p>Hence we ask the question: <em>How can we use less energy when training DNNs on GPUs?</em></p>

<p><b id="docs-internal-guid-95bd1f6b-7fff-4c10-4539-acaf84ab85ee">How is your research addressing this challenge? </b></p>

<p>The first step of optimizing something (GPU energy in our case) would be to understand how it behaves when we change things. We decided that the most important knobs we have are the <em>batch size</em> used for DNN training and the <em>power limit </em>configuration of the GPU, both of which can be controlled with pure-software.</p>

<p><b id="docs-internal-guid-39deb6d8-7fff-f7a3-efd3-ccd9211559ab"><img height="233" src="https://lh3.googleusercontent.com/a9-7zfsBiJDIJxQBTbp57yvyhTPucSrgz60M-ksqX57IjirOazhuK0yGaIYooD6u7CZI6xTrtLWm3edoE6OfMXsHNFh2dC9o9TWot1oKcyQV9FLCFst9wz9a6ayL_5XhIDGlAbALlvfpP78BFnGLuDHnkHgvgUVljREXg84-MddqVEnOZZ47zgf-Amr6Sw" width="280"></b><b id="docs-internal-guid-0f561478-7fff-24df-9649-cac1bb7eb363"><img height="241" src="https://lh5.googleusercontent.com/YcFjpkkc1DYdtv3lGoaoygE137u3OuH77aSDttQrSC8U4LlDmnE-f1FQSy9Zs4HXiQK8iMwg9jSHZnkDN58MASi-c1Ie5FBo5kDqb1HQBOmXAJA_Hm103kylJuWpD0Hxcwx_1TAVBYjHnkKoEO3rwRHVpuWafRYa9wuVkcV82C2btGe-HxS8ORbGsBLYeA" width="292"></b></p>

<p> </p>

<p>We swept all possible combinations of batch size and power limit, and found that there is a tradeoff between training time and energy consumption. The figure above shows a clear Pareto frontier of efficient training time and energy consumption pairs, each resulting from an efficient batch size and power limit pair.</p>

<p>Based on this understanding, we designed Zeus, an energy optimization framework for DNN training. Given an arbitrary DNN training job specification, Zeus can find the optimal batch size and power limit configuration that lies on the Pareto frontier<br>
 </p>

<p>Zeus has two major components. First, the <em>Just-in-Time power profiler</em> transparently observes the power consumption of a DNN training job and figures out the optimal power limit while training is running. Second, the <em>Multi-Armed Bandit </em>module searches for the optimal batch size by observing and learning from the energy and time consumption of running training with certain batch sizes. Its goal is to figure out the optimal batch size without incurring too much cost while exploring, which is achieved by our modified version of the Thompson Sampling policy.</p>

<p style="text-align: center;"><b id="docs-internal-guid-bb981312-7fff-7797-5eff-1c053a873ba5"><img height="328" src="https://lh6.googleusercontent.com/Jslk_f9zdksujTL98DhKNlGHHiqiBFfPwg9RNsaE-R_1e9mVUbD8yIYgAMhAjYRxrzhw7mS-XXfaV2EXVhoplJcJ5RAqQeDKES2NH8dPoDZzo8TWUQm_1m9_NgqaNzeWi1DnYT54rHJsezFMajshNfyM4DWU-rIGLHzFpr1G5gZ1JREp3L1gQMvC30i40A" width="310"></b></p>

<p>With all this, Zeus is able to cut down the energy consumption of DNN training by at least 15.3% and as much as 75.8%. Moreover, Zeus allows users to express their preferences of how much training time they’re willing to trade off for energy savings with a single number.</p>

<p><strong>How do you structure your experiments on Chameleon?</strong></p>

<p>Our project requires us to run the same workload on many different types of GPUs to show that our solution is general across GPU generations. Thankfully Chameleon Cloud offers many types of GPUs: NVIDIA A100, V100, P100, RTX6000, K80, M40, etc. Moreover, we can use the same operating system image (specifically we used the Ubuntu 20.04 CUDA 11 image) to create almost identical environments across machines with many different GPU types.</p>

<p>Now that we have the hardware, there is one special software I wrote to conveniently run hundreds of DNN training commands automatically across many machines over SSH. That software is <a href="https://github.com/jaywonchung/pegasus">Pegasus</a>. Pegasus is a multi-node SSH command runner written in Rust that is well suited for any cloud service that provides simple SSH access to nodes. It allows you to 1) bootstrap multiple nodes at the same time by running the same sequence of commands, and 2) drain a queue of commands using a set of SSH nodes.</p>

<p><strong>What features of the testbed do you need in order to implement your experiment?</strong></p>

<p>Getting bare metal machines is a hard requirement for our experiments, because we are interested in the throughput and power consumption of GPUs. Any virtualization in between will influence the numbers in an undesirable way. Especially considering the diversity of our GPU type requirement, Chameleon Cloud was an integral part of conducting our experiments.</p>

<p><strong>Can you point us to artifacts connected with your experiment that would be of interest to our readership?</strong></p>

<p>Zeus was accepted to appear at the 20th USENIX Symposium on Networked Systems Design and Implementation (NSDI ’23). Zeus is completely open source, together with all the training and power consumption trace data we collected.</p>

<ul>
	<li>Paper: https://arxiv.org/abs/2208.06102</li>
	<li>Website: https://ml.energy/zeus</li>
	<li>Open source repository: https://github.com/SymbioticLab/Zeus</li>
</ul>

<p><b id="docs-internal-guid-b53b555f-7fff-522c-7436-0eb518e48291"><img height="190" src="https://lh5.googleusercontent.com/h_7gLwBTqTr8UtCFNtMiPdCtusa7raohIKkQy35X5JTAXQKeCyIGg3aFe3IRWn-zdbLi3bWUErSy6FZpriGis4Npskg6J4PXZ4bpezu0CsuCO2u7Gz-GVRyT9sY-Qr141KRs-8pbmXuxr0wkFLCauzkBm909SMncCWtS-adRQktBMqiXdT8EmN_1_h3NmQ" width="190"></b><b id="docs-internal-guid-3d512303-7fff-6e59-3682-9056b31e752b"><img height="190" src="https://lh4.googleusercontent.com/IYJCwyWhp_-YuXNmd2fnCfCxMQ5kBxMKDAcR073F75x34uvV6NfKS4Bf2-s5Xbz5uq1OpULTKKDFryzPx92-yoYknwj6qR9SWMFbR4D1Wp9uM96TC_vnjOOzWO6xQ88iSF8e5Rc9JCxCVBVOfEq4zoSUw8EHBSD9iIMW4pC5avcdTC14EhEHijqs_sRhAg" width="190"></b><b id="docs-internal-guid-cf3fc2f1-7fff-8b2e-1ab2-79eec941fc5b"><img height="190" src="https://lh3.googleusercontent.com/oykE7FT4SkwTSrvzdlN4T5rN0ahpket8fRHWarl8Cq0d_fKEzlo-YbvacWuXPinfxk6BVU_e5jSr01FFmyeq9TRW5HuTpdIY-_qSimLkYQ0_sYg9A0Lll2ITaZv7gB5wdzuIcOjJn9REihwQQR4SVyWB7cscFwoVrfZ3r86XNZE8QtnOvJC9z6uK1TjBpQ" width="190"></b></p>

<p><em>Left to right: Jie You, Jae-Won Chung, and Mosharaf Chowdhury</em></p>

<p>Introducing the Zeus team, part of <a href="https://symbioticlab.org/">SymbioticLab</a> in the University of Michigan!</p>

<p>Advised by associate professor Mosharaf Chowdhury, Jie and Jae-Won contributed equally to the publication of Zeus. Jie, who recently graduated as a PhD, is currently at Meta as a research scientist. Jae-Won (the writer of this blog post) is a second year PhD student interested in the intersection of deep learning and software systems. We are also leading the <a href="https://ml.energy/">ML energy initiative</a>, where Zeus is the first project under it.</p>

<p><strong>Most powerful piece of advice for students beginning research or finding a new research project?</strong></p>

<p>It doesn’t work until it works. Believe in what you do. And somehow if you find yourself not believing in what you’re doing (e.g. “Ugh, I don’t think this thing will ever work”), figure out why you’re feeling like that and try to resolve that issue.</p>

<p><strong>How do you stay motivated through a long research project?</strong></p>

<p>When things are going well, you don’t need to do anything to stay motivated. On the other hand, when you’re stuck, I think remembering the time when things went well and believing that you’ll make a breakthrough are important. Also, I always ask myself whether what I’m doing is fun and meaningful, and make sure the answer is always yes.</p>

<p><strong>Why did you choose this direction of research?</strong></p>

<p>My research experience begins with deep learning, not systems. But as I worked on deep learning, I realized that deep learning research is usually bottlenecked by systems, not how fast a researcher can generate ideas. That’s how I was motivated to delve into systems support for deep learning. I believe my experience in deep learning in turn helped a lot in making MLSys papers interesting and practical.</p>

<p>I dived into energy after I came to Michigan, which was something frequently optimized in the perspective of designing better hardware, but scarcely so in designing software. I believe this is an important topic because people already bought their hardware for deep learning (GPUs), and they’re not going to throw them away to replace them with more energy efficient hardware. We need a solution that is energy efficient on existing hardware, but flexible enough to be deployed without requiring significant modifications to any existing software stack.</p>

<p> </p>