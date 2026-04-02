---
abstract: <p>Data centers waste enormous performance potential because software evolves
  faster than profiles can be collected. Wax, developed by Tawhid Bhuiyan and colleagues
  at Columbia University, uses source code and debug information to recover 65–93%
  of fresh-profile performance gains from stale profiles—outperforming the state of
  the art by up to 7.86 percentage points across five real-world data center applications.</p>
authors:
- slug: tawhid-bhuiyan
  name: Tawhid Bhuiyan
categories:
- User Experiments
date: '2026-03-30'
featured: true
hide_image: false
image: https://chameleoncloud.org/media/filer_public/bf/5b/bf5b5989-81e0-463b-967b-c4037760eed0/wax-banner.png
related_posts:
- slug: core-hours-and-carbon-credits-incentivizing-sustainability-in-hpc
  title: 'Core Hours and Carbon Credits: Incentivizing Sustainability in HPC'
- slug: tigon-a-distributed-database-for-a-cxl-pod
  title: 'Tigon: A Distributed Database for a CXL Pod'
- slug: netprompt-ai-powered-network-policy-management-for-programmable-networks
  title: 'NetPrompt: AI-Powered Network Policy Management for Programmable Networks'
slug: wax-optimizing-data-center-applications-with-stale-profile
subtitle: Leveraging source code and debug information to unlock up to 93% of fresh-profile
  performance gains
title: 'Wax: Making Stale Profiles Work for Data Center Optimization'
---

<p>Every time you run a search query, stream a video, or send a message, a data center somewhere is burning energy to make it happen. Keeping those data centers fast and efficient is a constant engineering challenge—and one of the most powerful tools available is <em>profile-guided optimization</em> (PGO): using data about how an application actually runs to reorganize its binary code for better performance.</p>

<p>The catch? Profiling takes time, and software doesn't stand still. By the time engineers have collected a useful profile and applied it to their code, they're often already shipping the next version of the software. According to recent work from Google and Meta, <strong>70–92% of profile samples can become stale within a week</strong> of a new release—meaning they no longer accurately map to the code they were meant to optimize. The result is a significant, persistent performance gap in some of the most critical software on the planet.</p>

<p>Tawhid Bhuiyan, a Ph.D. student at Columbia University working with Professor Tanvir Ahmed Khan, set out to close that gap. The result is <strong>Wax</strong>, a novel technique that recovers the vast majority of performance benefits from stale profiles—without needing to re-profile the fresh binary.</p>

<h2>Why Stale Profiles Are So Hard to Use</h2>

<p>Profile-guided optimizers like BOLT work by identifying "hot" functions and basic blocks—the parts of the code executed most frequently—and packing them together in memory. This shrinks the code footprint, reduces instruction cache and TLB misses, and can deliver end-to-end speedups of several percent, worth millions of dollars at data center scale.</p>

<p>But to use a stale profile on a fresh binary, you first have to figure out which parts of the old binary correspond to which parts of the new one. This <em>mapping</em> problem turns out to be surprisingly difficult.</p>

<p>Existing approaches tackle it at the binary level, comparing function names and hashing basic-block instruction sequences. The trouble is that C++ binaries are messy. Function names—or "mangled names"—encode namespaces, parameters, and compiler-generated suffixes, all of which can change between versions even for logically identical functions. And basic-block hashes break the moment a single instruction is added, removed, or reordered, which happens constantly as developers fix bugs and add features. The state of the art leaves up to 33.9% of function samples and 34.8% of basic-block samples unmapped—and those unmapped samples represent lost performance potential.</p>

<h2>A Different Approach: Look at the Source</h2>

<p>Wax's key insight is that the binary isn't the only available source of truth. Data center optimization pipelines already generate and store <em>debug information</em> alongside binaries—metadata that links binary instructions back to the source files and line numbers that produced them. And the source code itself is always available. Why not use both?</p>

<p>Wax works in three coordinated steps:</p>

<ul>
	<li><strong>Source Mapping:</strong> Wax first maps source files from the stale version to the fresh version, then maps individual source lines by comparing their content—exact matches first, then fuzzy matching using Levenshtein similarity for lines that changed slightly.</li>
	<li><strong>Function Mapping:</strong> Using the source file mappings as anchors, Wax compares function names component by component—namespace, basename, parameters, and compiler suffix—rather than treating the mangled name as a single opaque string. This allows Wax to correctly match functions whose names changed in predictable ways across versions.</li>
	<li><strong>Basic-block Mapping:</strong> Rather than hashing entire basic blocks, Wax partitions assembly instructions by their mapped source locations. Within each partition, it maps instructions by comparing opcodes and operands, then aggregates those instruction mappings into basic-block mappings using similarity scores and control-flow neighbors as tiebreakers.</li>
</ul>

<p>The result is a much more robust mapping that survives the kinds of source-level changes that defeat binary-only approaches.</p>

<h2>Testing on Chameleon</h2>

<p>To evaluate Wax rigorously, the team needed server-class hardware with support for Intel's Last Branch Record (LBR) profiling technology—the same mechanism used by companies like Google and Meta for continuous production profiling. Chameleon's bare-metal nodes at TACC, specifically machines with Intel Icelake Platinum 8380 CPUs, provided exactly that environment.</p>

<p>The experiments spanned five widely-used open-source applications with large code footprints: <strong>gcc, clang, mysql, postgresql, and mongodb</strong>. For each application, the team compiled a "stale" version and a "fresh" version, collected LBR profiles from both, and used BOLT to optimize the fresh binary under three conditions: with its own fresh profile (the theoretical best case), with the stale profile mapped by the prior state-of-the-art technique, and with the stale profile mapped by Wax. Each experiment was run at least five times to ensure statistical reliability.</p>

<h2>Results</h2>

<p>The numbers tell a clear story. Optimizing with fresh profiles delivers speedups ranging from 7.64% (postgres) to 38.45% (mongodb). The prior state of the art captures only a fraction of those gains when using stale profiles. Wax does substantially better:</p>

<ul>
	<li><strong>gcc:</strong> 8.72% speedup with Wax vs. 3.90% with prior work (fresh profile: 11.72%)</li>
	<li><strong>clang:</strong> 18.21% vs. 15.98% (fresh: 19.63%)</li>
	<li><strong>mysql:</strong> 26.46% vs. 18.60% (fresh: 32.63%)</li>
	<li><strong>postgres:</strong> 5.76% vs. 4.56% (fresh: 7.64%)</li>
	<li><strong>mongodb:</strong> 24.89% vs. 17.81% (fresh: 38.45%)</li>
</ul>

<p>Across all five applications, Wax achieves <strong>65–93% of the speedup that a fresh profile would deliver</strong>, and outperforms the prior state of the art by 1.20–7.86 percentage points. The improvements carry through to microarchitectural cache miss rates as well: Wax reduces L1 and L2 instruction cache misses, iTLB misses, and branch target buffer misses more effectively than any prior technique.</p>

<p>The results hold up across diverse workloads and across both minor and major version gaps. When the researchers tested Wax against eight different MySQL query types, it consistently outperformed the prior state of the art for every single workload. And as profile staleness increased with wider version gaps, Wax's advantage grew larger—exactly the behavior you'd want in a real deployment environment where software evolves rapidly.</p>

<p>As a final stress test, the team compared Wax against OCOLOS, an online system that sidesteps the staleness problem entirely by profiling and optimizing a running binary in real time—meaning it uses a fresh profile by definition. Wax, operating offline with a stale profile, still outperformed OCOLOS even after OCOLOS finished its optimization pass. The reason: OCOLOS leaves function pointers pointing to unoptimized code, a limitation that Wax doesn't share.</p>

<h2>Looking Forward</h2>

<p>Wax is implemented in roughly 2,240 lines of Python and integrates cleanly into standard PGO pipelines. It requires only the debug information that optimization systems like AutoFDO already generate and retain—no new instrumentation, no changes to the profiling infrastructure. The team has also demonstrated that Wax's approach extends beyond BOLT: applying the same mapping technique to Propeller, Google's re-linking optimizer, produced a 6.44% speedup for clang compared to 5.38% with the prior state of the art.</p>

<p>Profile staleness is an unavoidable feature of fast-moving software development. Wax demonstrates that it doesn't have to be a performance ceiling.</p>

<hr>

<p><strong>Publication:</strong> This work was published at ASPLOS '26: <em>Wax: Optimizing Data Center Applications With Stale Profile</em>. DOI: <a href="https://doi.org/10.1145/3779212.3790248">10.1145/3779212.3790248</a></p>

<p><strong>Code:</strong> <a href="https://github.com/ice-rlab/wax">https://github.com/ice-rlab/wax</a></p>

<hr>

<h3>About the Author</h3>

<p>Tawhid Bhuiyan is a Ph.D. student at Columbia University, advised by Professor Tanvir Ahmed Khan. His research focuses on profile-guided optimization, microarchitectural efficiency, and compiler systems for data center applications. For more details, visit his <a href="https://takhandipu.github.io/">homepage</a>.</p>