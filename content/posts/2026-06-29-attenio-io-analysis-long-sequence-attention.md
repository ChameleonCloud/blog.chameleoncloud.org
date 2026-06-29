---
abstract: <p>Modern AI systems are often limited not only by how much computation they
  perform, but also by how much data they need to move. AttenIO, developed by Xiaoyang
  Lu at Illinois Institute of Technology, is an I/O-driven accelerator for exact long-sequence
  self-attention that achieves up to 3.4× speedup over FlashAttention-2 by applying
  principled I/O analysis to minimize data movement across the memory hierarchy.</p>
authors:
- Xiaoyang Lu
categories:
- User Experiments
- Featured
date: '2026-06-29'
featured: true
hide_image: false
image: 'https://chameleoncloud.org/media/filer_public/70/69/7069d921-a5bd-49eb-ad01-04a5fefed628/presenting.jpg'
related_posts:
- slug: wax-optimizing-data-center-applications-with-stale-profile
  title: 'Wax: Making Stale Profiles Work for Data Center Optimization'
- slug: baremetal-h100s
  title: Baremetal H100 nodes on Chameleon
- slug: running-artifact-evaluations-on-chameleon
  title: Running Artifact Evaluations on Chameleon
slug: attenio-io-analysis-long-sequence-attention
subtitle: An I/O-driven accelerator that achieves up to 3.4× speedup over FlashAttention-2
  by minimizing data movement in long-sequence self-attention
title: 'I/O Analysis is All You Need: An I/O Analysis for Long-Sequence Attention'
---

<p>Modern AI systems are often limited not only by how much computation they perform, but also by how much data they need to move. Moving data — or I/O — between large off-chip memory and small on-chip memory can be expensive, and this cost becomes especially important for data-intensive AI workloads. Xiaoyang Lu, a Research Assistant Professor at Illinois Institute of Technology, has been investigating how to attack this problem at its root, applying I/O analysis to design hardware that minimizes data movement rather than simply maximizing compute throughput.</p>

<h2>The I/O bottleneck in modern AI</h2>

<p>The specific target of Lu's work is long-sequence self-attention — a core operation behind large language models. As input becomes longer, exact self-attention needs to compare many more token pairs, creating massive data movement across the memory hierarchy. This slows down the model, especially during the prefilling stage, when the model reads the full input before generating the first output token.</p>

<p>Lu's hypothesis is that long-sequence attention should be optimized from an I/O perspective. Instead of only asking how to compute attention faster, the key question becomes: what is the minimum amount of data movement required, and how can a system approach that limit? If successful, this can reduce the latency of long-context AI applications and make exact long-sequence inference more efficient.</p>

<h2>AttenIO: I/O-guided hardware design</h2>

<p>The answer to that question is AttenIO, an I/O-driven accelerator for exact long-sequence self-attention. The key idea is to use I/O analysis to guide system design, rather than relying on heuristic tuning. The approach begins with an analysis of the I/O lower bound of tall-and-skinny matrix multiplication, which captures the dominant data movement pattern in long-sequence attention. This analysis determines how to choose tiling sizes and scheduling strategies under limited on-chip memory, so that the accelerator can maximize data reuse and minimize data movement between off-chip and on-chip memory.</p>

<p>Based on this I/O analysis, AttenIO introduces three main optimizations. First, it uses an I/O-optimal dataflow to schedule the attention computation and reduce unnecessary I/O operations. Second, it applies three-level fine-grained communication-computation overlapping, so that remaining data movement latency can be hidden behind useful computation instead of becoming exposed stall time. Third, it reorganizes online softmax into parallel execution patterns, improving the efficiency of a key operation in exact attention. The architecture brings together AttenIO's controller, on-chip cache, processing-element array, exponential unit, and key/value buffer to realize these optimizations in practice.</p>

<p><img src="https://chameleoncloud.org/media/filer_public/6e/2d/6e2d30ca-3a39-48af-b7f8-84dbafbd9780/paper_graphic.png" alt="Performance comparison of AttenIO against state-of-the-art GPU implementations" style="max-width: 100%;"></p>
<p style="text-align: center; font-size: 0.9em;"><em>Performance comparison of AttenIO against state-of-the-art GPU implementations.</em></p>

<p>The performance results are substantial. AttenIO substantially outperforms GPU-optimized FlashAttention implementations, achieving up to 3.4× speedup over FlashAttention-2 and up to 3.0× over FlashAttention-3 in the evaluated configuration. Overall, AttenIO demonstrates how hardware-aware I/O analysis can provide a principled foundation for optimizing high-performance systems.</p>

<h2>Building and running experiments on Chameleon</h2>

<p>Lu built and ran the AttenIO simulation on Chameleon using compute nodes as the main experimental environment. After allocating the required resources, he accessed the nodes through the command line, configured the software stack, built the simulator, and ran the evaluation scripts from the terminal. This workflow proved well-suited to the demands of the project: architecture and systems experiments often require careful control over compilation, simulator configuration, runtime parameters, and output collection. Chameleon's documentation was clear and helpful for setting up the environment and managing the experiment workflow.</p>

<p>The most important Chameleon feature for this experiment was the flexibility to configure the compute environment for systems-level evaluation. This flexibility matters because architecture simulations often depend on specific compiler settings, runtime configurations, and system environments that are difficult to reproduce on shared cloud infrastructure. Without access to a bare-metal testbed like Chameleon, the experiment would still be possible in principle, but it would be harder to set up a clean, controlled, and reproducible environment for running and managing the simulations.</p>

<h2>Learn more</h2>

<ul>
  <li><strong>Paper:</strong> <a href="https://dl.acm.org/doi/10.1145/3779212.3790174">https://dl.acm.org/doi/10.1145/3779212.3790174</a></li>
  <li><strong>Project page:</strong> <a href="https://xiaoyang-lu.github.io/publications/ASPLOS2026">https://xiaoyang-lu.github.io/publications/ASPLOS2026</a></li>
  <li><strong>Slides:</strong> <a href="https://xiaoyang-lu.github.io/files/ASPLOS2026/ASPLOS2026_slides.pdf">https://xiaoyang-lu.github.io/files/ASPLOS2026/ASPLOS2026_slides.pdf</a></li>
  <li><strong>Poster:</strong> <a href="https://xiaoyang-lu.github.io/files/ASPLOS2026/ASPLOS2026_poster.pdf">https://xiaoyang-lu.github.io/files/ASPLOS2026/ASPLOS2026_poster.pdf</a></li>
</ul>

<hr>

<p><strong>Tell us a little bit about yourself</strong></p>

<p>I am a Research Assistant Professor in the Department of Computer Science at Illinois Institute of Technology. My research focuses on computer architecture and high-performance computing, especially data movement, memory hierarchy optimization, I/O analysis, and efficient AI systems. At this stage of my career, I hope to continue developing data-centric system designs for data-intensive workloads, including data movement analysis, data access optimization, and memory-centric architecture. Outside research, I enjoy discussing new ideas with students and collaborators, following emerging technology trends.</p>

<p style="text-align: center;">
  <img src="https://chameleoncloud.org/media/filer_public/26/0d/260db004-1c26-404c-91c9-f68bc1c104db/lu_headshot.png" alt="Xiaoyang Lu" style="height: 240px; border-radius: 8px;">
</p>

<p><strong>How do you stay motivated through a long research project?</strong></p>

<p>I stay motivated by returning to the core problem behind the project. Long research projects often involve many uncertain stages: the first idea may not work, experiments may need to be redesigned, and the story may take time to become clear. For me, it helps to keep asking whether the problem is real, important, and worth solving. If the answer is yes, then the difficulties become part of the process rather than a reason to stop.</p>

<p><strong>Why did you choose this direction of research?</strong></p>

<p>I chose this direction because modern computing is increasingly limited by data movement and data access. Many data-intensive applications today, from scientific computing to large language models, are not bottlenecked only by arithmetic operations, but by how efficiently data can be accessed, moved, and reused. This makes data-centric system design an important research direction. I am especially interested in building systems where the architecture, dataflow, and memory hierarchy are designed together from a data-centric view to address this fundamental research problem.</p>

<p>Thank you for sharing your knowledge with the Chameleon community!</p>
