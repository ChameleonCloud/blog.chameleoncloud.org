---
abstract: <p>Distributed storage systems are upgraded constantly, and one subtle class
  of bug — data format incompatibility, where a new version misreads data written by the
  old one — ranks among the leading causes of cloud incidents during upgrades, with
  consequences as severe as data loss and cluster-wide outages. UpFuzz, an award-winning
  open-source fuzzer from Purdue University, is the first tool built specifically to hunt
  these cross-version bugs. It has already uncovered 15 previously unknown failures in the
  latest stable releases of Cassandra, HBase, and HDFS — and its evaluation was run on
  bare metal testbed infrastructure that included Chameleon.</p>
authors:
- Ke Han
categories:
- Featured
- User Experiments
date: '2026-05-28'
featured: true
hide_image: true
image: 'https://chameleoncloud.org/media/filer_public/8e/02/8e022415-21c1-4987-bb12-f4febcc0372a/ke_han.jpeg'
related_posts:
- slug: running-artifact-evaluations-on-chameleon
  title: Running Artifact Evaluations on Chameleon
- slug: wax-optimizing-data-center-applications-with-stale-profile
  title: 'Wax: Making Stale Profiles Work for Data Center Optimization'
slug: upfuzz-fuzzing-distributed-storage-upgrade-bugs
subtitle: An NSDI '26 Community Award–winning, fully open fuzzer from Purdue uncovered
  15 previously unknown upgrade bugs in Cassandra, HBase, and HDFS
title: 'UpFuzz: Hunting the Data-Format Bugs That Break Distributed-Storage Upgrades'
---

<p>Software upgrades are supposed to be routine. In a large data center, thousands of distributed-system upgrades can happen in a single day, each one quietly swapping in new code and migrating the system's stored state from the old version's format to the new one's. Most of the time, no one notices. But when that migration goes wrong, the results can be spectacular — and a team at Purdue University has built a tool, called UpFuzz, designed specifically to catch the failures before they reach production. <strong>The work earned the Community Award at <a href="https://www.usenix.org/conference/nsdi26">NSDI '26</a>, USENIX's flagship networked-systems conference as an outstanding paper with publicly available code and data.</strong></p>

<h2>When an upgrade goes wrong</h2>

<p>The bugs UpFuzz targets are a class its authors call <em>data format incompatibility</em> (DFI) bugs. They occur when a newly upgraded version of a system reads data that the old version wrote to disk, but the format of that data — how it is structured and interpreted in memory and on storage — changed across versions in a way the upgrade logic didn't fully handle. The new version then misinterprets perfectly valid old data, and the consequences cascade: crashed clusters, corrupted records, silently lost data, and large-scale service outages.</p>

<p>This is not a niche concern. Prior research has found that data format inconsistencies account for nearly two-thirds of distributed-system upgrade failures. And the real-world track record is sobering. The paper points to a 2025 Google Cloud outage that affected roughly 1.4 million users, traced to an inconsistency in a policy data structure between old and new versions of a control service, and to the 2024 CrowdStrike incident that crashed millions of systems worldwide — also rooted in a format inconsistency surfacing during an update.</p>

<h2>Why these bugs slip through</h2>

<p>Part of what makes DFI bugs so persistent is that they are mostly discovered after release. There is surprisingly little automated testing built specifically for the upgrade <em>process</em> — most upgrade tests are written by hand and cover only a narrow set of scenarios. The closest prior work, a tool the same Purdue group built earlier (DUPTester), automated some upgrade testing by repurposing existing stress and unit tests, but inherited the limited coverage of those hand-written tests.</p>

<p>The obvious next step — fuzzing, which generates and runs huge numbers of tests to shake out edge cases — runs into a hard wall. A single upgrade operation can take tens of seconds or even minutes to complete, because the system has to flush data, shut down cleanly, reinitialize, reload configuration, and re-establish cluster membership. Traditional fuzzers depend on running enormous numbers of cheap tests quickly; when every test can carry the cost of a full upgrade, brute force becomes hopeless. The real problem is figuring out which tests, out of an effectively infinite pool, are actually worth the expense.</p>

<h2>A fuzzer that knows where to look</h2>

<p>UpFuzz's central insight is that DFI bugs come from a specific, identifiable slice of a program's state. A bug can only appear when some piece of data is written to disk by the old version, read back by the new version, and the format of that data changed between the two. The team calls this slice the <em>Transitively Persisted State</em> (TPState): the subset of program state that ends up persisted to storage — directly, or indirectly through chains of in-memory copies — and is later read after the upgrade.</p>

<p>Rather than rewarding a fuzzer for exploring new code or new states indiscriminately, which drowns instantly in the state space of a real system, UpFuzz selectively monitors these transitively persisted states, infers the data-format properties that govern how they are serialized and deserialized, and prioritizes the states whose underlying class definitions actually changed across versions. It also lets the fuzzer skip the expensive upgrade step for tests that don't look promising, concentrating its limited budget where a cross-version bug is most likely to hide. The result, according to the authors, is the first feedback-driven fuzzing engine built specifically to test cross-version data-format compatibility during distributed-storage upgrades.</p>

<p><img src="https://chameleoncloud.org/media/filer_public/7c/6d/7c6de490-f09f-47e5-a43d-06dde330f36e/upfuzz-arch.png" alt="The UpFuzz pipeline in four stages: test generation, old-version execution with a TPState analyzer inspecting persisted state, an upgrade-skip decision, and failure detection via a differential oracle" style="max-width: 100%;"></p>
<p style="text-align: center; font-size: 0.9em;"><em>The UpFuzz pipeline. It generates tests and runs them against an old-version cluster while a TPState analyzer inspects the state being persisted, decides whether each test is worth the cost of a full upgrade (skipping the unpromising ones), then upgrades and checks the new-version cluster for failures using a differential oracle, crashes, and error logs.</em></p>

<h2>What it found</h2>

<p>The team applied UpFuzz to three of the most widely deployed open-source distributed storage systems: Apache Cassandra (a peer-to-peer database), HDFS (the Hadoop distributed file system), and HBase (a master-worker database). These are mature, heavily tested systems that historically see only about one or two data-format incompatibility bugs reported per year.</p>

<p>UpFuzz found 15 previously unknown DFI bugs across them. Eight have already been confirmed by the projects' developers and three have been fixed. Six of the bugs crash the cluster outright, and four cause data loss or corruption. Notably, 7 of the 15 could only be discovered once UpFuzz's transitively-persisted-state analysis was switched on — they were invisible to a strong baseline built from conventional state-of-the-art fuzzing techniques. Against that baseline, UpFuzz reached the same incompatibility-related states roughly 4.7 times faster. Counting the additional upgrade and single-version bugs it surfaced along the way, the tool has uncovered 38 previously unknown bugs in total.</p>

<p><img src="https://chameleoncloud.org/media/filer_public/b9/45/b945ba8a-b267-40b0-846b-10c1dfebf5c3/upfuzz-results.png" alt="Three line charts for Cassandra, HDFS, and HBase plotting distinct data-format violations discovered over 24 hours, with UpFuzz's full configuration (DF+VD+S) above the DF+S and branch-coverage (BC) baselines" style="max-width: 100%;"></p>
<p style="text-align: center; font-size: 0.9em;"><em>Distinct incompatibility-related states discovered over a 24-hour run on Cassandra, HDFS, and HBase. UpFuzz's full configuration (DF+VD+S, the solid blue line) surfaces more of these states — and reaches them faster — than a conventional branch-coverage baseline (BC, the dotted green line).</em></p>

<h2>Open by design</h2>

<p>What sets UpFuzz apart for the broader community is not only what it found but how openly it was released: the fuzzing engine, the analysis, and the supporting data are all publicly available on GitHub. That openness is recognized directly by the field — UpFuzz received the NSDI '26 Community Award, which USENIX presents to outstanding papers whose code and/or dataset is made publicly available by the final paper deadline. For a research area where reproducibility is hard — the bugs are rare, the systems are large, and the experiments are long-running — a fully open, runnable artifact is a meaningful contribution in its own right. The code lives at <a href="https://github.com/zlab-purdue/upfuzz">github.com/zlab-purdue/upfuzz</a>.</p>

<h2>Built on bare metal</h2>

<p>Hunting these bugs is not a single-machine job. Each target system runs as a real multi-node cluster — a single node for Cassandra and three nodes each for HDFS and HBase in the published setup — and the evaluation packed several such clusters onto each physical machine to run tests in parallel. Because every test can trigger a full upgrade, the team ran sustained campaigns: each configuration was fuzzed for 24 hours and repeated three times, across multiple version pairs and analysis settings. That is exactly the kind of long-running, multi-node, bare metal workload that is awkward and expensive to reproduce on a shared commercial cloud, where dedicated hardware and full control of the software stack are hard to come by.</p>

<p>To run that evaluation, the authors credit Chameleon Cloud — alongside CloudLab — for providing the computing infrastructure behind the project. Bare metal testbeds like these give researchers the isolated, reconfigurable, multi-node environments that systems work of this kind depends on, and they make it possible for others to rerun the experiments on comparable hardware rather than approximating them.</p>

<p style="text-align: center;">
  <img src="https://chameleoncloud.org/media/filer_public/8e/02/8e022415-21c1-4987-bb12-f4febcc0372a/ke_han.jpeg" alt="Ke Han, lead author of UpFuzz, outdoors" style="height: 240px; border-radius: 8px;"><br>
  <em style="font-size: 0.9em;">Ke Han, the paper's lead author.</em>
</p>

<h2>Learn more</h2>

<ul>
  <li><strong>Paper:</strong> Ke Han, Sruthi P C, Yayu Wang, Yaoxu Song, Bishal Basak Papan, Junwen Yang, Pedro Fonseca, and Yongle Zhang. "UpFuzz: Detecting Data Format Incompatibility Bugs during Distributed Storage System Upgrade." In the 23rd USENIX Symposium on Networked Systems Design and Implementation (NSDI '26). <a href="https://www.usenix.org/conference/nsdi26/presentation/han">usenix.org/conference/nsdi26/presentation/han</a></li>
  <li><strong>Code:</strong> <a href="https://github.com/zlab-purdue/upfuzz">github.com/zlab-purdue/upfuzz</a></li>
  <li><strong>The team:</strong> The work comes from the labs of Yongle Zhang and Pedro Fonseca at Purdue University, with collaborators at the University of British Columbia and Meta.</li>
</ul>