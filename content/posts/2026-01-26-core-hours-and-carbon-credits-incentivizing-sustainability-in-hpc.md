---
abstract: <p>A survey of 300+ HPC users reveals that fewer than 30% are aware of their
  energy consumption. This research introduces Energy-Based and Carbon-Based Accounting
  models that tie computing costs to environmental impact, demonstrating through real
  experiments and simulations that such incentives can dramatically reduce energy
  use while maintaining scientific productivity.</p>
authors:
- Alok Kamatar
categories:
- User Experiments
date: '2026-01-26 16:18:51+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/8e/b7/8eb711ec-33a0-4725-917d-d3cb9e6a128f/screenshot_2026-02-02_at_102652am.png
related_posts:
- slug: fair-co2-fair-attribution-for-cloud-carbon-emissions
  title: 'Fair-CO2: Fair Attribution for Cloud Carbon Emissions'
- slug: power-patterns-understanding-the-energy-dynamics-of-io-for-parallel-storage-configurations
  title: 'Power Patterns: Understanding the Energy Dynamics of I/O for Parallel Storage
    Configurations'
- slug: zeus-gpu-energy-as-a-first-class-resource-in-dnn-training
  title: 'Zeus: GPU Energy as a First-Class Resource in DNN Training'
slug: core-hours-and-carbon-credits-incentivizing-sustainability-in-hpc
subtitle: Researchers demonstrate that linking resource costs to energy consumption
  can reduce HPC energy use by 40%
title: 'Core Hours and Carbon Credits: Incentivizing Sustainability in HPC'
---

<p>High-performance computing enables groundbreaking scientific discoveries, but its environmental impact continues to grow. While HPC facilities invest heavily in renewable energy and efficient cooling, user choices—such as which machine to use or when to run jobs—can be equally important for sustainability. But do users actually consider energy efficiency in their decisions?</p>

<p>To find out, researchers collaborated to conduct the first large-scale survey of HPC users focused on energy awareness, receiving 316 responses from researchers across North America, Europe, and beyond. The results revealed a troubling disconnect: while 73% of users knew how many node-hours their jobs consumed, only 27% were aware of energy usage. Even more striking, when ranking factors that influence machine selection, energy efficiency came in last—well behind hardware availability, queue times, and performance.</p>

<p>This gap between provider sustainability efforts and user awareness suggested a fundamental problem with current accounting methods. By charging users based only on time (node-hours or core-hours), we provide no incentive to prioritize energy efficiency.</p>

<h2>A New Accounting Model</h2>

<p>To address this, researchers developed two impact-based accounting models:</p>

<ul>
	<li><strong>Energy-Based Accounting (EBA):</strong> Charges users for the energy their jobs consume rather than time spent computing</li>
	<li><strong>Carbon-Based Accounting (CBA):</strong> Incorporates both operational carbon from electricity generation and a portion of the machine's embodied carbon</li>
</ul>

<p>Under these models, users might receive an allocation of 10 kg CO2e instead of 100 node-hours, enabling them to compare the carbon footprint of running a computation on different machines and choose accordingly.</p>

<h2>Testing on Chameleon</h2>

<p>To evaluate these accounting models, researchers built green-ACCESS, a Function-as-a-Service platform on top of HPC infrastructure using Globus Compute. Chameleon Cloud's bare-metal access and heterogeneous hardware provided the ideal testbed for measuring real energy consumption across different systems.</p>

<p>Running a Cholesky decomposition benchmark on four different CPU systems revealed unexpected trade-offs. The Cascade Lake machine delivered the fastest runtime but consumed more than twice the energy of an AMD Zen3 system. Under traditional time-based accounting, Cascade Lake appeared cheapest because it was fastest. But under EBA, Zen3 had lower cost despite slightly longer runtime.</p>

<p>Similar patterns emerged with GPUs. Across three generations of NVIDIA GPUs (P100, V100, A100), newer hardware provided better performance but consumed significantly more energy—the A100 ran 6% faster than the V100 but used 60% more energy. EBA and CBA naturally balanced these trade-offs, steering users toward older, more efficient hardware when performance gains didn't justify the energy cost.</p>

<h2>Large-Scale Simulations</h2>

<p>Using a published dataset of 71,190 HPC jobs with measured energy consumption, researchers simulated how different accounting methods would affect real workloads. Users optimizing for energy efficiency under EBA completed 28% more work than performance-focused users with the same allocation, while consuming 40% less energy overall.</p>

<p>With CBA, researchers incorporated real carbon intensity data from electricity grids. As grid carbon intensity varied throughout the day with renewable energy availability, the cheapest machine for running a job shifted accordingly. This naturally incentivized users to align their computations with periods of renewable energy generation—a form of carbon-aware scheduling that emerged organically from the accounting model.</p>

<h2>Does It Change Real Behavior?</h2>

<p>To test whether impact-based accounting actually influences human behavior, researchers created a web-based game simulating HPC resource selection decisions. Ninety participants played under three conditions: traditional time-based costs, time-based costs with energy information displayed, and EBA.</p>

<p>Simply showing energy information had no effect—participants consumed the same amount of energy as the control group. However, when cost was tied to energy consumption through EBA, participants used 40% less energy on average. They didn't avoid energy-intensive jobs, but consistently selected more efficient machines to run them.</p>

<p>This validated the core hypothesis: information alone doesn't change behavior, but linking environmental impact to cost creates powerful incentives for sustainability.</p>

<h2>Implications</h2>

<p>This work demonstrates that HPC sustainability requires proper incentive structures. Current accounting methods inadvertently encourage inefficient behavior by making faster machines appear cheaper, even when they consume significantly more energy.</p>

<p>Impact-based accounting offers a path forward by:</p>

<ul>
	<li>Incentivizing selection of more efficient resources</li>
	<li>Rewarding code optimization for energy efficiency</li>
	<li>Extending the useful life of existing machines</li>
	<li>Aligning computing demand with renewable energy availability</li>
</ul>

<p>All code, data, and experimental artifacts are openly available on GitHub, including the green-ACCESS platform, simulation tools, and anonymized survey responses.</p>

<h2>Looking Forward</h2>

<p>Technical solutions like efficient hardware and renewable energy are essential for sustainable HPC, but they're not sufficient on their own. By aligning user incentives with sustainability goals through impact-based accounting, we can harness the entire community's creativity to drive meaningful reductions in energy consumption and carbon emissions.</p>

<p>The path to sustainable HPC requires providers and users to work together. Impact-based accounting provides a mechanism to make that collaboration not just possible, but natural.</p>

<hr>
<p><strong>Publication:</strong> This work was published at SC '25: <em>Core Hours and Carbon Credits: Incentivizing Sustainability in HPC</em>. DOI: <a href="https://doi.org/10.1145/3712285.3759858">10.1145/3712285.3759858</a></p>

<p><strong>Code &amp; Data:</strong> <a href="https://github.com/AK2000/core-hours-artifact">https://github.com/AK2000/core-hours-artifact</a></p>