---
abstract: <p><em>In this interview, Weichen Li, a PhD student from the University
  of Chicago discusses research on improving code editing through explicit transformation
  rules. EditLord breaks down the code editing process into clear, step-by-step transformations,
  significantly enhancing editing performance, robustness, and functional correctness
  compared to existing methods.</em></p>
authors:
- Weichen Li
categories:
- User Experiments
date: '2025-03-24 17:11:32+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/f4/fb/f4fbb5f3-c13e-4319-94d4-fed1d967e979/weichen_li.jpg
slug: editlord-learning-code-transformation-rules-for-code-editing
subtitle: Making code edits more effective, robust, and transparent through explicit
  transformation rules
title: 'EditLord: Learning Code Transformation Rules for Code Editing'
---

<p>Code editing is a fundamental task in software development, and its effectiveness can significantly impact the quality and reliability of software products. Traditionally, code editing has been treated as an implicit, end-to-end task, overlooking the fact that it consists of discrete, clear steps. This research introduces EditLord, a novel approach that makes these transformation steps explicit and leverages language models to learn concise editing rules from examples.</p>

<h3>Research Overview</h3>

<p>Our experiment addresses the challenge of making code editing more effective, robust and interpretable. Code editing is a foundational task in software development, where its effectiveness depends on whether it introduces desired code property changes without breaking the original functionality. Traditionally, code editing is treated as one implicit, end-to-end task, omitting the fact that code editing procedures actually consist of clear, discrete steps. Our hypothesis is that by making these transformation steps explicit and leveraging a language model to learn concise editing rules from examples, we can significantly enhance the editing process.</p>

<p><img alt="" src="https://www.chameleoncloud.org/media/filer_public/1a/26/1a262367-7b8f-4f35-b83d-f0fe50162f13/image2.png"></p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/e6/50/e650856a-a0e2-4602-882d-0ea075c9cd2a/image1.png"></p>

<p>Consider the readability improvement task: instead of rewriting the code all at once, you make specific, deliberate changes to individual statements. Similarly, EditLord extracts meta-rule sets that guide the editing process, ensuring that each step is accurate and robust. Day-to-day, this research can lead to more reliable software updates, quicker bug fixes, and improved security in critical applications. EditLord boosts editing performance by around 22.7%, enhances robustness by 58.1%, and achieves 20.2% higher functional correctness, marking a substantial leap in the quality and efficiency of software development.</p>

<p>We break code editing into clear, step-by-step transformations rather than treating it as a mysterious black box. Instead of expecting an AI to generate a completely new version of code in one go, our approach teaches the system to learn explicit transformation rules from examples of code before and after edits. Think of it as instructing a handyman to follow a detailed checklist—each step is transparent and easy to verify.</p>

<p>Our method has three main parts. First, we use a language model to analyze pairs of original and edited code to discover specific transformation rules. These rules are then refined through an iterative process that merges similar changes and prunes overly specific ones, forming a concise "meta-rule set." Second, we extract functional specifications from the code, which are simple descriptions of what the code is supposed to do, to ensure that the edits preserve its intended behaviour. Finally, we combine these learned rules and functional summaries to guide the editing process, whether by fine-tuning the model or directly prompting.</p>

<p>In our experiments, EditLord achieved an average improvement in editing performance of 22.7%, enhanced robustness by 58.1%, and improved functional correctness by 20.2% compared to existing methods.</p>

<p>With EditLord, developers can be more aware of what the language model is doing during code editing and intervene with it by introducing custom editing rules for intended changes.</p>

<h3>Experiment Implementation on Chameleon</h3>

<p>In our research, we set up and ran our performance evaluations on Chameleon. We start by selecting the appropriate hardware through the hardware catalog and verifying resource availability with the host availability browser. This ensures that our experimental environment meets our specific requirements.</p>

<p>Then, we configure the environment via command-line tools. While the GUI and Jupyter interfaces are available, we find that the command line provides a faster and more reproducible workflow for our performance evaluations.</p>

<p>For those setting up similar experiments: start with the hardware catalog and host availability browser early on to match your experimental needs with available resources, and rely on the documentation to navigate common configuration challenges.</p>

<p>We rely on several unique Chameleon features to ensure a controlled, reproducible environment and eliminate bare-metal issues. Specifically, we use bare-metal reconfiguration and custom kernel boot to establish a clean system state and access the serial console for low-level debugging. These features are essential for maintaining consistent test conditions and isolating performance metrics. Without these features, experiments would be more error-prone and less reproducible, potentially forcing us to adjust our hypothesis or design to account for additional variability.</p>

<h3>Experiment Artifacts</h3>

<p>The specific code repo we run on Chameleon: <a href="https://github.com/kleinercubs/pie">https://github.com/kleinercubs/pie</a></p>

<h3>User Interview</h3>

<p><img src="https://www.chameleoncloud.org/media/filer_public/f4/fb/f4fbb5f3-c13e-4319-94d4-fed1d967e979/weichen_li.jpg"></p>

<h4><strong>Tell us a little bit about yourself</strong></h4>

<p>I'm currently a first-year PhD student at the University of Chicago, where I focus on research in programming languages, security, software engineering, and machine learning. I hope to make impactful contributions in my fields, whether in academia or industry. Ultimately, I aim to develop innovative solutions that address key challenges in programming and security.</p>

<h4><strong>Most powerful piece of advice for students beginning research or finding a new research project?</strong></h4>

<p>Embrace curiosity and be open to uncertainty. Rather than waiting for a perfectly formed research question, we should let our interests guide us. Explore broadly, ask thoughtful questions, and push the boundaries of your research environment. Don't be discouraged by poor experimental results—these setbacks can reveal powerful insights. Engage with mentors and peers, read widely, and don't be afraid to take risks. Often, the most impactful discoveries arise from the questions that truly ignite our curiosity.</p>

<h4><strong>How do you stay motivated through a long research project?</strong></h4>

<p>I stay motivated throughout long research projects by focusing on the incremental progress and the larger impact my work can have. Even when the pace feels slow, I remind myself that each small breakthrough contributes to the overall discovery process.</p>

<h4><strong>What has been a tough moment for you either in your life or throughout your career? How did you deal with it? How did it influence your future work direction?</strong></h4>

<p>During research, encountering setbacks, e.g., a promising experiment not yielding expected results, can be tough. Instead of viewing it as a setback, I took time to analyze what went wrong and discussed the issues with my peers and mentors. This experience not only deepened my understanding but also shifted my research direction to focus on more innovative solutions, ultimately leading to new insights.</p>

<p><strong>Thank you for sharing your work with the Chameleon Community!</strong></p>