---
abstract: <p>MCP-enabled computer-use agents are proliferating faster than our ability
  to evaluate them — and most existing benchmarks depend on commercial APIs that get
  deprecated without notice. OpenMCP is an open-source, fully self-hosted benchmarking
  harness built by NYU researchers that lets anyone reproducibly evaluate MCP agents
  across diverse hardware, from H100 datacenter GPUs to a Raspberry Pi 5 at the edge.</p>
authors:
- Agustin Leon
- Anup Raj Niroula
categories:
- Featured
- User Experiments
date: '2026-04-26'
featured: true
hide_image: false
image: https://chameleoncloud.org/media/filer_public/22/e3/22e357af-c8fa-432e-8338-2a775cef9c13/openmcp_pic2.png
related_posts:
- slug: wax-optimizing-data-center-applications-with-stale-profile
  title: 'Wax: Making Stale Profiles Work for Data Center Optimization'
- slug: running-artifact-evaluations-on-chameleon
  title: Running Artifact Evaluations on Chameleon
- slug: a-holistic-approach-to-teaching-cloud-computing
  title: A Holistic Approach to Teaching Cloud Computing
slug: openmcp-reproducible-benchmarking-mcp-agents
subtitle: How two NYU master's students built a self-hosted, hardware-diverse evaluation
  framework for the fast-growing MCP ecosystem
title: 'OpenMCP: A Reproducible Benchmarking Harness for Evaluating Computer-Use Agents on Chameleon'
---

<p><em>Agustin Leon and Anup Raj Niroula, New York University</em></p>

<hr>

<h2>What is the central challenge your experiment investigates?</h2>

<p>Computer-use agents are language model programs that operate a computer through the same channels a person does: controlling a cursor, typing into applications, and calling tools. Think of it like an assistant that can organize your Notion notes, update a GitHub issue, or manage your calendar without needing step-by-step instruction. Through <a href="https://www.anthropic.com/news/model-context-protocol">Model Context Protocol (MCP)</a>, an open standard released in late 2024, agents can perform actions with specific applications in a consistent way. Adoption of MCP has been rapid: by the end of 2025, PulseMCP, a popular directory of MCP servers, had already <a href="https://www.pulsemcp.com/statistics">tracked over 15 million downloads</a> and more than 6,000 MCP servers.</p>

<p>This ecosystem is growing faster than our ability to evaluate it, and we still do not have solid answers to basic questions such as how different agent designs compare, which tasks are hardest, or where agents tend to fail. Answering those questions depends on benchmarks that are rigorous and reproducible, and this is where the current generation of MCP benchmarks falls short. Most of them rely on commercial language models accessed through external APIs. Those models get deprecated, their behavior can change without notice, and when that happens, benchmark results become impossible to reproduce. We set out to build a benchmark that avoids these problems.</p>

<hr>

<h2>How is your research addressing this challenge?</h2>

<p>OpenMCP is our contribution: an open-source, fully self-hosted benchmarking harness for MCP-enabled computer-use agents. It follows a "Bring Your Own" principle, where researchers bring their own models, tasks, MCP servers, and infrastructure, and the harness handles scheduling, isolation, evaluation, and telemetry.</p>

<p>Evaluating a computer-use agent is a multi-part problem. It requires infrastructure to run the language model powering the agent, an evaluator to determine whether a task was actually completed, a task suite worth running, and a place for the agent to operate: typically a virtual desktop with real applications installed and MCP servers exposed. OpenMCP brings these pieces together behind a single configuration file. Additionally, by building on a self-hosted model, we are able to overcome the challenge of non-reproducibility of previous benchmarks. Future OpenMCP users will be able to reproduce our experiments and compare their own results in a reliable way, without worrying about models changing or being deprecated without warning.</p>

<p><img src="/img/openmcp-blog-image.png" alt="OpenMCP architecture diagram showing the Plan-Act-Observe agent loop, task suite, containerized playground, and evaluator components" style="max-width: 100%;"></p>

<p>The architecture has four components. The agent itself implements a Plan-Act-Observe loop: it queries a locally served language model to decide on an action, executes that action against the environment, observes the result, and repeats — with actions falling into one of three categories (MCP tool calls, GUI operations on the virtual desktop, or shell commands). The agent acts on a task suite, a set of concrete instructions like creating a note in Obsidian, changing the tab size in VS Code, or committing a change from a Git workspace, each paired with verifiable key steps and a handler script that defines success.</p>

<p>All of this activity happens inside a playground: a containerized Ubuntu environment with the target applications installed and the MCP servers wired in. An evaluator oversees the whole process — it runs the agent, detects task completion through deterministic checks tied to internal application events, classifies failures into categories (planning loops, hallucinated tool calls, partial completions, timeouts), and collects infrastructure telemetry along the way, including GPU utilization, memory, power draw, and total energy per task.</p>

<hr>

<h2>How do you build your experiment on Chameleon?</h2>

<div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%; margin-bottom: 1.5em;">
  <iframe
    src="https://www.youtube.com/embed/CBL8B3-d3IU?start=2"
    title="OpenMCP demo — Chameleon User Meeting 2026"
    frameborder="0"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
    allowfullscreen
    style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;">
  </iframe>
</div>

<p>OpenMCP is fully containerized. Once an instance is provisioned, a complete experiment launches from a single configuration file with a handful of commands, and the whole setup is published as a <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/31fc62a4-1996-4719-957e-4c1b4e47b1b6">Trovi artifact</a> so the environment can be reproduced on Chameleon without manual reconstruction.</p>

<p>Running experiments is a straightforward process. Once the instance is provisioned, users modify one single configuration file, where they define the parameters for their experiments — selecting models, applications, agent runtime types (what the agent is allowed to do), and timeout limits, among others. Once the configuration file is ready, OpenMCP automatically brings up the necessary services according to the user's specifications and starts the experiment. During the experiment, OpenMCP collects rich data for each task: metadata, metrics, raw events (the steps taken by the agent), and GPU hardware telemetry. Users can access this data as structured JSON files, ready to be processed for analysis.</p>

<p>Our experiments ran primarily on <a href="https://kvm.tacc.chameleoncloud.org">KVM@TACC</a> and <a href="https://chi.tacc.chameleoncloud.org">CHI@TACC</a>, with edge runs on <a href="https://chi.edge.chameleoncloud.org">CHI@Edge</a> using a Raspberry Pi 5. On the KVM side we relied heavily on <a href="https://kvm.tacc.chameleoncloud.org/project/volumes/">volume storage</a> to keep a persistent development environment across sessions, which turned out to be essential over the six months the project lasted. Chameleon's reservation model also helped: knowing the hardware availability allowed us to schedule long experiment runs without guesswork.</p>

<hr>

<h2>What features of the testbed did you need in order to implement your experiment?</h2>

<p>Three features of Chameleon were central to this project. The first was hardware diversity: we ran experiments on H100, RTX 6000, P100, V100, a CPU-only host, and a Raspberry Pi 5 at the edge. The ability to evaluate the same agent across that range — from a high-end datacenter GPU down to an edge device — is not something we have found elsewhere, and it made direct cross-hardware comparisons of energy, latency, and task success possible under identical task definitions. The second was easy provisioning through <a href="https://trovi.chameleoncloud.org/dashboard">Trovi</a>: packaging the full environment as an artifact keeps the barrier to reproduction low, so a user can clone it and be running the same experiments we did shortly after, without rebuilding the setup by hand.</p>

<p>The third, and the one that shaped our day-to-day workflow the most, was the KVM@TACC H100 instances. They provision in a few minutes, compared to roughly 30 minutes for baremetal, and they support persistent volume storage — which is critical for long-running development where rebuilding the environment repeatedly is not practical, and taking snapshots is not feasible. Their attached storage is also sufficient to work with very large models, including the Qwen3-VL 235B variant we benchmarked. Without Chameleon, a project of this shape would have been significantly harder to execute: direct bare metal access and reproducibility guarantees are difficult to obtain in commercial clouds, and the cost at this scale would likely have been prohibitive.</p>

<hr>

<h2>Can you point us to artifacts connected with your experiment?</h2>

<p>Everything from the project is openly available, including artifacts, codebase, and data.</p>

<ul>
  <li><strong>Trovi artifact:</strong> <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/31fc62a4-1996-4719-957e-4c1b4e47b1b6">https://trovi.chameleoncloud.org/dashboard/artifacts/31fc62a4-1996-4719-957e-4c1b4e47b1b6</a></li>
  <li><strong>OpenMCP codebase:</strong> <a href="https://github.com/AguLeon/OpenMCP">https://github.com/AguLeon/OpenMCP</a></li>
  <li><strong>Chameleon User Meeting 2026 slides:</strong> <a href="https://docs.google.com/presentation/d/1nqtelJHctmnP14360qowXBY6zpfdqBFxY6aXLzmaUQ0/edit?usp=sharing">https://docs.google.com/presentation/d/1nqtelJHctmnP14360qowXBY6zpfdqBFxY6aXLzmaUQ0/edit?usp=sharing</a></li>
  <li><strong>Upcoming EuroMLSys publication:</strong> <em>Agustin Leon, Anup Raj Niroula, and Fraida Fund. 2026. OpenMCP: an open-source self-hosted benchmarking harness for MCP-enabled computer use agents. In The 6th Workshop on Machine Learning and Systems (EuroMLSys '26), April 27–30, 2026, Edinburgh, Scotland UK. ACM, New York, NY, USA, 10 pages. <a href="https://doi.org/10.1145/3805621.3807649">https://doi.org/10.1145/3805621.3807649</a></em></li>
</ul>

<hr>

<h2>Tell us a little bit about yourselves</h2>

<p>
  <img src="https://chameleoncloud.org/media/filer_public/22/e3/22e357af-c8fa-432e-8338-2a775cef9c13/openmcp_pic2.png" alt="Photo of Agustin Leon and Anup Niroula Presenting at the Chameleon User Meeting in Boulder, CO on April 15." style="height: 150px; border-radius: 50%; margin-right: 16px; vertical-align: middle;">
</p>

<p>We are both Computer Engineering master's students at NYU. Our research interests focus on machine-learning systems, and particularly on the space between "lab ML" — where the model is the only variable that matters — and production ML pipelines that have to be reliable, efficient, and deployable in real settings. Outside of research, we enjoy hiking in the outdoors, and discovering new streets and alleys around New York City.</p>

<hr>

<h2>Most powerful piece of advice for students beginning research?</h2>

<p>It doesn't need to be pretty. It needs to work. When you're starting research, it's easy to fall into the perfectionist trap of trying to make code, ideas, and notes flawless from the start. That mentality tends to get you stuck and slows progress. Focus on getting something — anything — done, even if it isn't pretty. Research is an iterative process. You will always have opportunities to reflect, refine, and improve your work along the way. Progress matters more than polish at the start.</p>

<hr>

<h2>How do you stay motivated through a long research project?</h2>

<p>Staying consistently motivated across a long project is not really possible, at least not in our experience. What matters is to keep moving when motivation is low. If you feel stuck in a rut, take a break, get some fresh air. Coming back with a clear mind often makes a problem look smaller than it did before, and we have lost count of the number of times a short pause has helped us work through something that seemed impossible an hour earlier.</p>

<p>Then try again. And again. If you focus on the next step and stay consistent, you will make progress, and one day, before you realize it, the project will be done. The satisfaction at the end is hard to match. "Just keep swimming."</p>
