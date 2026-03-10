---
abstract: "<p>High-resolution Vision-Language Models (VLMs) offer impressive accuracy\
  \ but come with significant computational costs\u2014processing thousands of tokens\
  \ per image can consume 5GB of GPU memory and add 15 seconds of latency. The HiRED\
  \ (High-Resolution Early Dropping) framework addresses this challenge by intelligently\
  \ selecting only the most informative visual tokens based on attention patterns.\
  \ By keeping just 20% of tokens, researchers achieved a 4.7\xD7 throughput increase\
  \ and 78% latency reduction while maintaining accuracy across vision tasks. This\
  \ research, conducted on Chameleon's infrastructure using RTX 6000 and A100 GPUs,\
  \ demonstrates how thoughtful optimization can make advanced AI more accessible\
  \ and affordable.</p>"
authors:
- Kazi Hasan Ibn Arif
categories:
- User Experiments
date: '2025-04-29 20:04:03+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/54/15/541526d6-c898-44c8-9d0a-1e6b5073eede/content-diagram.png
slug: faster-multimodal-ai-lower-gpu-costs
subtitle: 'HiRED: Cutting Inference Costs for Vision-Language Models Through Intelligent
  Token Selection'
title: Faster Multimodal AI, Lower GPU Costs
---

<p><big>By Hasan Kazi Ibn Arif &amp; JinYi Yoon</big></p>

<p>Generative AI models are significantly larger (&gt;1000x) than traditional predictive AI, presenting new computational challenges. In this study, we focus on Vision-Language Models (VLMs) -- models that understand and process both text and image information. Such Generative AI models can reason over image-text to generate a response. However, they are costly to deploy. For example, a multimodal model with 7B parameters needs around 14GB of GPU memory only for the model weights, and additional GPU memory is required for intermediate representations, called tokens, during inference—the more tokens, the higher the processing time, GPU cycles, and memory usage. In VLMs, representing a single high-resolution image often requires over 2,000 tokens, consuming more than 5GB of memory. This heavy workload makes it difficult to run on commodity GPUs and increases costs. Our research aims to reduce the number of tokens needed to represent an image in VLMs, without losing important visual details. By reducing token usage, we can speed up inference, save GPU memory, and make the process more efficient. This work focuses on finding ways to optimize token representation in VLMs, offering a potential solution to these computational challenges and lowering the cost of deploying advanced AI systems.</p>

<h3>Research Overview</h3>

<p>Our approach is simple: we drop visual tokens that are not important, reducing the number of tokens processed during inference. However, identifying which tokens are important is nontrivial, especially with high-resolution images, where we need to account for how each cropped image part contributes, as shown in the figure below.</p>

<p><img alt="" src="https://www.chameleoncloud.org/media/filer_public/54/15/541526d6-c898-44c8-9d0a-1e6b5073eede/content-diagram.png"> </p>

<p>In high-resolution VLMs, the input image is cropped into sub-images, and each sub-image is encoded separately. We also provide a downsampled full image to capture the entire context, as we cannot fit the full image into the Vision Encoder at once. These representations are then transformed into visual tokens, which are processed by the Large Language Model (LLM). An image in LLaVA (a popular VLM) typically results in 576 tokens per sub-image. So, an input image with 1 full image and 4 sub-images results in 2,880 tokens (576 x 5). That’s a lot to process! For instance, these additional 2,000 tokens can consume 5GB of GPU memory and add around 15 seconds of latency on a Tesla P40. This directly impacts GPU costs, as more time and GPU cycles are required for each inference. From the user’s perspective, it results in higher latency and a worse experience. This is where our research steps in. Do we really need all these tokens to represent the image? To answer this, we calculate the attention weights these visual tokens receive in the LLM. Attention weights are commonly used to determine the importance of each token. By focusing on the most important tokens, we can reduce the number of tokens while maintaining the image’s essential information. This helps speed up inference, saves GPU memory, and improves user experience. Implementing such an approach shows impressive performance improvements while maintaining accurancy. When using just 20% of the visual tokens on LLaVA, our system achieves a 4.7× increase in token generation throughput (2.30 vs. 0.49 tokens/sec), reduces response latency by 78% (4.21 vs. 19.49 seconds), and saves 14% of GPU memory (13.76 vs. 16.04 GB) for single inference on an NVIDIA TESLA P40.</p>

<h3>Experiment Implementation on Chameleon</h3>

<p>We started by analyzing the attention weights of various images from popular visual QA benchmarks like ScienceQA, TextVQA, and VQAv2. Chameleon’s infrastructure played a key role in supporting this process. We primarily used the RTX 6000 GPUs from the CHI@UC cluster for our experiments due to their longer availability, and the A100 GPUs for running benchmarks with different setups. To manage GPU usage, we regularly checked the host calendar to see which nodes were available. This feature was extremely helpful in planning our experiments, especially when we needed the A100 GPUs. We also found Chameleon’s documentation well-written and easy to follow, which made setting up experiments much smoother. Another feature we found useful was the floating IP address, which provided public access to our virtual machine and allowed for easy reassignment. For anyone looking to run similar experiments, I’d recommend taking advantage of Chameleon’s hardware catalog, the availability browser, and the floating IP system to streamline their setup and planning process. Another valuable feature was the ability to run Jupyter Notebooks directly in the cloud. This interface allowed us to prototype, explore, and document the entire experimental process seamlessly. The integration of rich text, code execution, and visualizations in the JupyterLab environment was especially useful for presenting and analyzing our results and artifacts.</p>

<h3>Experiment Artifacts</h3>

<p>Our paper is available in the AAAI 2025 proceedings: <a href="https://ojs.aaai.org/index.php/AAAI/article/view/32171">HiRED: Attention-Guided Token Dropping for Efficient Inference of High-Resolution Vision-Language Models</a>. We’ve also created a demo video explaining the experiment, which can be found on YouTube: <a href="https://www.youtube.com/watch?v=7ND4b64BgtI">Watch it here</a>. Additionally, the code for our HiRED framework is open-sourced on GitHub: <a href="https://github.com/hasanar1f/HiRED">Visit the repository</a>. These resources will allow others to explore and replicate our experiment.</p>

<h3>User Interview</h3>

<p><strong>Tell us a little bit about yourself</strong></p>

<p><img alt="" src="https://www.chameleoncloud.org/media/filer_public/8e/43/8e434710-86ae-4fc8-a323-8ff837ec0b44/hasan.jpg"> </p>

<p>(Hasan) I am currently a PhD student at Virginia Tech, where I focus on optimizing generative (Hasan) AI models to address computational challenges. My research aims to make generative AI services more affordable and efficient, specifically in areas like algorithm-system co-design, parallelization, Key-Value (KV) cache optimization, and sparse self-attention. Previously, I obtained my bachelor’s in Computer Science from Bangladesh University of Engineering and Technology. Afterward, I worked as an ML engineer at IQVIA, where I helped scale their Next-Best-Action recommendation model for production use. Looking ahead, I aspire to become a research scientist in the industry, focusing on making generative AI more accessible and affordable. I hope to bring real-world change through my work, helping as many people as possible by advancing AI technologies. Outside of my research, I enjoy long drives as a way to unwind and find inspiration. </p>

<p><img alt="" src="https://www.chameleoncloud.org/media/filer_public/90/b2/90b28b49-e6f7-4e62-b070-f24463ee35a0/yoon.jpg"> (JinYi) I am a Presidential Postdoctoral Fellow in the Department of Computer Science at Virginia Tech. I received all of my B.S., M.S., and Ph.D. degrees from Ewha Womans University, Seoul, South Korea. I have broad interests in the intersection of edge computing and AI. Here, edge computing is to process the computing on edge devices such as smartphones, laptops, or desktops near the users. So, I am interested in Edge for AI (how can edge networks or devices support AI) and AI for edge (how can we use AI in edge networks). I have a strong will to become a researcher and educator, particularly in fostering the next generation of women engineers at my future institution in Korea. Beyond the work, I love traveling, especially after submitting my paper! I really deeply dive into my work, and once it’s done, I like to visit somewhere new. I also enjoy having coffee outside when the sun is shining to refresh while working.</p>

<p><strong>Most powerful piece of advice for students beginning research or finding a new research project</strong></p>

<p>(Hasan) The most powerful piece of advice I can give to someone who’s starting research is: Start by diving into the work that excites you, and don’t be afraid to explore. Read papers, follow research blogs, and try reproducing results. You’d be surprised how many interesting challenges pop up when you try to recreate what others have done. For me, this process of diving in and experimenting is key—it helps uncover hidden problems and sparks new ideas. But here’s the catch: don’t just solve a problem for the sake of solving it. Ask yourself, How important is this problem? Does it matter? Will people care about this solution? These questions will guide you toward research that’s not only novel but also impactful.</p>

<p>(JinYi) Know what you are interested in. You are the one who leads the project, thinks a lot, and spends the most time. So, it should be interesting to you.</p>

<p><strong>Why did you choose this direction of research?</strong></p>

<p>(Hasan) I was truly fascinated by the potential of generative AI, and I felt a strong need to make these technologies more accessible and affordable. I see this as a way to help more people, enabling advancements that can positively impact daily life in various fields, from healthcare to entertainment.</p>

<p>(JinYi) I am very interested in solving real-world problems. I believe that most of you agree that AI is very promising. However, not many people are thinking about how to deploy and use them in practice. AI is not some abstract or virtual thing. The system should exist somewhere, and you are accessing it to use. And how do we access them? Most likely through our smartphones, laptops, or desktops. So, how to connect your devices–called edge devices–with those systems is very important.</p>

<p><strong>What has been a tough moment for you either in your life or throughout your career? How did you deal with it? How did it influence your future work direction?</strong></p>

<p>(Hasan) Landing my dream job right after completing my bachelor’s was a huge accomplishment, but shortly after, I had to leave it to start grad school. It was tough, especially as I had to make the difficult decision between diving into a career in GenAI and furthering my academic pursuits. But looking back, I’ve realized that pursuing grad school was the best choice for my long-term goals, allowing me to make a broader impact in the field.</p>

<p>(JinYi) Just right after starting my PhD. It was very stressful for me at that time. Although I spent a lot of time on research, there was no progress or outcome at all over one year. I thought my decision to start a PhD was wrong and didn’t know what to do. I cannot escape from thinking more and more negatively, and the situation becomes worse and worse. Honestly, there were no solutions. I am the person who is motivated by outcomes. So, I just endure and endure, struggle and struggle until I get some good news. I can say my solution was just to keep going. If I gave up there, I couldn’t be here. I couldn’t hope for my dream. I would live a totally different life then. From this experience, I believe now there are so many things that do not go as expected. However, let us just keep going forward persistently. One more thing–Good luck, all!</p>

<p><strong>Thank you for sharing your knowledge with the Chameleon community!</strong></p>