---
abstract: '<div class="flex flex-grow flex-col max-w-full">

  <div class="min-h-[20px] text-message flex flex-col items-start gap-3 whitespace-pre-wrap
  break-words [.text-message+&amp;]:mt-5 overflow-x-auto" data-message-author-role="assistant"
  data-message-id="e488b453-b5cf-419a-8043-931f8f1b43ba">

  <div class="markdown prose w-full break-words dark:prose-invert dark">

  <p>In this user experiment blog, Akash Kundu details his experience using Chameleon
  to replicate a GPT from scratch on a corpus of Shakespeare texts. Using Chameleon
  Cloud, he highlights the ease and impact of training generative pre-trained transformers
  (GPTs), aiming to democratize access to this technology and highlight the importance
  of reproducible experiments.</p>

  </div>

  </div>

  </div>'
authors:
- Akash Kundu
categories:
- User Experiments
date: '2024-01-24 20:51:34+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/1e/40/1e401d69-d2ce-470d-b875-46b583b8d987/akash_kundu.jpg
related_posts:
- slug: reproduce-rerun-repeat-the-fun-way-to-learn-machine-learning
  title: 'Reproduce, Rerun, Repeat: The Fun Way to Learn Machine Learning!'
- slug: automated-fast-flux-detection-using-machine-learning-and-genetic-algorithms
  title: Automated Fast-flux Detection using Machine Learning and Genetic Algorithms
- slug: announcing-virtual-reproducibility-hackathon-december-15th-2023-hold-the-date
  title: "Announcing Virtual Reproducibility Hackathon \u2013 December 15th, 2023\
    \ \u2013 HOLD THE DATE"
slug: training-your-own-gpt-from-scratch
subtitle: An experiment reproducing NanoGPT and lessons learned
title: How to Train a GPT From Scratch
---

<p>In the realm of artificial intelligence, we hear a lot about AI-powered Large Language Models (LLMs) like ChatGPT, Bard, Gemini, and others. Many of these models rely on a technology called Generative Pretrained Transformers (GPTs). GPTs are a type of LLM that use deep learning to produce natural language texts based on a given input. A user of the GPT will feed the model with input (like a sentence of text). The GPT then generates text based on information extracted from publicly available datasets. These GPTs can process a wide range of text inputs from long-form paragraphs and code to creative writing. They provide insights, analysis, and summaries based on the input given. <strong>Figure 1 </strong>shows the architecture of a GPT.</p>

<p><img height="auto" src="https://chameleoncloud.org/media/filer_public/87/a8/87a8c7ac-8bc9-4a7e-9c60-b4c304df161a/transformer_architecture.png" width="50%"></p>

<p><strong>Figure 1</strong>: Transformer Architecture</p>

<p>My <a href="https://chameleoncloud.org/experiment/share/130b1066-2687-458d-9b2e-8c3014333069">Chameleon experiment</a>, which I prepared during my participation in <a href="https://chameleoncloud.org/blog/2023/11/13/announcing-virtual-reproducibility-hackathon-december-15th-2023-hold-the-date/">Chameleon's Virtual Reproducibility Hackathon in Dec. 2023</a>, aims to reproduce the results of <a href="https://github.com/karpathy/nanoGPT">NanoGPT</a>, an analysis by Andrej Karpathy to train a character-level GPT from scratch on the works of Shakespeare. The code is simple and easy to understand. In my experiment, I fine-tune the gpt2-xl model on the same Shakespeare dataset using 1 Nvidia A100 GPU on Chameleon Cloud and visualize the results in a Jupyter Notebook.</p>

<h2>Research Overview</h2>

<p>The aim of my experiment is to help people to get their feet wet in GPTs. Training a GPT is highly resource-intensive, which unforutnately deprives most enthusiasts of the opportunity ever to try such a project. Thanks to the resources that Chameleon offers, this barrier to working with GPTs can be overcome. My reproduction of NanoGPT and the results I obtain highlight the importanance of reproducibility in research and will hopefully help researchers better understand the existing work. NanoGPT is the simplest version of a GPT that helps us understand the foundation of the current LLMs.</p>

<p>In my experiment, I followed the methodology of Andrej Karpathy’s NanoGPT and achieved similar results. I was careful to ensure that the experiments were as similar as possible. Hence, for the gpt2-xl fine-tuning experiment, I utilized 1 A100 as specified in Karpathy's analysis. Karpathy had taken into consideration that most users may not have access to GPUs, hence he also published a CPU-based version of the project, which I also reproduced. <strong>Changing the parameters of the model significantly improved the loss during the CPU-version of the experiment from 1.88 (in the actual experiment) to 1.54</strong>.</p>

<p>My hope is that researchers can build on my replication of NanoGPT. For example, researchers could try to reproduce the results, change the parameters for themselves (to possibly improve the model), or also use their own dataset to train their model or fine-tune any version of gpt2 (small, medium, large, xl) and do a comparative analysis. They could even try to extend the work by using 8 A100s to pre-train GPT2 with OpenWebText (which is the closest representation of what GPT2 was trained upon) and compare the results with actual GPT2’s reported results. For seasoned researchers, trying out and adding Fully Sharded Data Parallel (FSDP) instead of Direct Data Parallel (DDP) could be an interesting experiment as well.</p>

<h2>Running the Experiment</h2>

<p>I developed a <a href="https://chameleoncloud.org/experiment/share/130b1066-2687-458d-9b2e-8c3014333069">Jupyter Notebook</a> to replicate the experiment, which I shared as a packaged artifact on the <a href="https://www.chameleoncloud.org/experiment/share">Chameleon Trovi</a> service. (Trovi is a service for packaging and sharing experiment artifacts that use Chameleon hardware. You can also apply for special badges to highlight your work on the service. For example, I received a <a href="https://repeto.cs.uchicago.edu/resources/about-trovi-repeto-badge/">REPETO reproducibility badge</a> for my artifact. See the <a href="https://repeto.cs.uchicago.edu/">REPETO website</a> for more information about how to obtain this badge.) I encourage readers to try running my notebook analysis and explore changing different parameters or even running the experiment on other hardware types. <strong>Figure 2</strong> shows a screenshot from the notebook.</p>

<p><img height="auto" src="https://chameleoncloud.org/media/filer_public/7d/09/7d094a01-bc69-4637-99ea-20b97af64d83/nanogpt_replication_jupyter_notebook_screenshot.png" width="100%"></p>

<p><strong>Figure 2</strong>: Demonstrating the experiment artifact that I created to replicate the NanoGPT analysis.</p>

<p>Simply running all the cells of my notebooks should be enough to replicate the experiment. Reserving a bare-metal node that has 1 A100 GPU is required. You can check node availability for this GPU on Chameleon Cloud's <a href="https://chameleoncloud.org/hardware/">hardware catalog</a>. I also tried to reproduce the results of gpt2 with a compute_liqid node from CHI@TACC, which I wanted to reconfigure to an 8xA100 cluster. I have previously worked with Google Colab but Colab's hosted runtime has caused me issues in the past. I didn’t have to face these issues with Chameleon Cloud.</p>

<p><a href="https://github.com/karpathy/nanoGPT">NanoGPT Github Repository</a></p>

<p><a href="https://chameleoncloud.org/experiment/share/130b1066-2687-458d-9b2e-8c3014333069">Chameleon Trovi Artifact</a></p>

<h2>User Interview</h2>

<p><strong>Chameleon: Tell us a bit about yourself!</strong></p>

<p>I am Akash Kundu, a second-year CS undergraduate from Heritage Institute of Technology, Kolkata, India. I am currently an AI Research Fellow at Apart Research, where I am co-authoring a paper on cross-lingual robustness of alignment techniques and evaluations on state-of-the-art large language models. I like to look at data and generate insights out of it. When I am not researching/building ML models/studying for my classes, you can find me singing and playing my guitar. I aim to be an Alignment Researcher who figures out the flaws in AI systems and aligns AI towards the right goals to make them safer for the community.</p>

<p><img height="auto" src="https://chameleoncloud.org/media/filer_public/1e/40/1e401d69-d2ce-470d-b875-46b583b8d987/akash_kundu.jpg" width="70%"></p>

<p>(A picture of me teaching a tech session as the Google Developers Students’ Club AI/ML Lead at my institute.)</p>

<p><strong>Chameleon: What is the most powerful piece of advice you have for students beginning research or finding a new research project?</strong></p>

<p>"Good things take time. Trust the Process."</p>

<p>Research is not a sprint, it’s a marathon. I would like to share one of my favourite tweets from Andrej Karpathy.</p>

<p>“How to become expert at a thing:<br>
1) iteratively take on concrete projects and accomplish them depth wise, learning “on demand” (ie don’t learn bottom up breadth wise)<br>
2) teach/summarize everything you learn in your own words<br>
3) only compare yourself to younger you, never to others”</p>

<p><strong>Chameleon: Are there any researchers whom you admire? Why?</strong></p>

<p>If it’s not already evident from my blog post, I really admire (you guessed it) Andrej Karpathy. This man had a lot of impact on the whole ML community and he has shared his knowledge with the world openly as well which is very inspiring. I have learned a lot from his CS231n Stanford Course on Deep Learning that he has publicly shared on his youtube channel. He took the time to be the human benchmark for ImageNet to prove that neural networks can work better than humans in certain instances which was very fun to know about.</p>

<p>In the Alignment Space, there is Neel Nanda who has done a lot of work in the field of Mechanistic Interpretability and has tried extremely hard to provide roadmaps and resources for people who want to get started with Mechanistic Interpretability.</p>

<p>Research should take us forward and help the whole community. The amount of time that these people have put in to educate and also create an impact in the field inspires me and I would love to be a researcher who’s known for his work (someday).</p>

<p><strong>Chameleon: Why did you choose this direction of research?</strong></p>

<p>The amount of people who should care about AI Safety and work in the field of AI Alignment is 1000x lower than it should be. The growth of AI is exponential and we need more and more people to understand the models deeply before scaling them to avoid deceptively trained models or scalable oversights. This field is in its infancy and I feel that I could create a lot of impact by getting into this field.</p>

<p><strong>Chameleon: Have you ever been in a situation where you couldn’t do an experiment that you wanted to do? What prevented you from doing it?</strong></p>

<p>I have wanted to conduct a lot of experiments but have left them after calculating the GPU costs. Reproducing NanoGPT was one of them which was finally done (thanks to Chameleon!). Currently, I have a plan to educate people in my college about stable diffusion to generate images and show them how to fine-tune SDXL. I plan to get started on this right after my semester ends!</p>

<p><strong>Chameleon: Thank you for sharing your knowledge with the Chameleon community!</strong></p>