---
abstract: <p>Recently, we have added new features to Trovi, extending it into a social
  site where you can engage with other users beyond a simple repository of data, with
  comments, verifications, and new metrics. These new features let you participate
  in Trovi in new ways, not just creating new artifacts.</p>
authors:
- Mark Powers
categories:
- Tips and Tricks
- Featured
date: '2026-11-23'
featured: true
hide_image: false
image:
related_posts:
- slug: from-github-to-publication-using-trovi-effectively
  title: 'From GitHub to Publication: Using Trovi Effectively'
- slug: bringing-external-reproducibility-artifacts-into-trovi
  title: Bringing External Reproducibility Artifacts Into Trovi
slug: more-than-a-repository-new-ways-to-engage-on-trovi
title: 'More Than a Repository: New Ways to Engage on Trovi'
---

Trovi is Chameleon’s repository of digital artifacts, letting users share things like reproducible experiments, tutorials, and educational courses. It is also a great place to get started with the testbed: chances are somebody has already run a similar experiment or taught a class on a similar topic – so rather than develop content from scratch you can “stand on the shoulders of giants” – though please always remember to acknowledge them if you choose to use or extend their work. To date, users have contributed 495 artifacts, ranging from experiment patterns, educational content, to reproducible experiments capturing influential results.

Recently, we have added new features to Trovi, extending it into a social site where you can engage with other users beyond a simple repository of data, with comments, verifications, and new metrics. These new features let you participate in Trovi in new ways, not just creating new artifacts.

## Comments

First, we have comments for artifacts. If you are signed in to the dashboard, you can leave comments on an artifact to share feedback or ask questions. For example, if you try to run an artifact but the node type that the author used is not available at that moment, you could instead swap to a different type, and leave a comment on how this worked. This may be helpful to both the author and other researchers who come along and run the experiment later. You can also leave threaded replies to comments, so that you can have full discussions or answer questions.

You will receive an email if someone leaves a comment on your artifact or replies to your comment. You can disable these notifications in the dashboard settings. You also can edit or delete your own comments. Authors and managers can manage comments on artifacts they own by flagging specific comments, or turning off comments entirely.

## Verification

Another new way to interact with artifacts is via [artifact verification](https://chameleoncloud.readthedocs.io/en/latest/technical/experiments/browsing_artifacts.html#verifying-artifacts). Beyond just launching an artifact, verification is a way to provide structured feedback about an artifact. A successful verification indicates that someone was able to run an artifact and to produce the expected result, while a failure to verify indicates that the artifact did not work as expected.

You can only report a verification after launching the artifact at least once. If you are reporting a failure to verify, please be sure to leave feedback to the author via a comment. We show the total number of successes and failures in the artifact list. We provide a “best-effort” check that a user has launched an artifact, without a guarantee that they executed the entire artifact. For more information, [see our documentation](https://chameleoncloud.readthedocs.io/en/latest/technical/experiments/browsing_artifacts.html#verifying-artifacts).

## Recent Metrics

We’ve added new metrics so that artifacts that users are engaging with are easier to find. Previously, you could sort to find artifacts created or updated recently, or sort to find artifacts that are popular. The former meant that you often found things that didn’t necessarily work, or were a work in progress. The latter meant you found artifacts used by classes, where a large number of students were launching them, and so this list rarely changed. Now, you can sort by the 90-day access count, which shows how many times users have launched an artifact only within the last 90 days. Using this metric, you may still prominently see artifacts from active classes, but you should also see artifacts from current conferences. For example, at the time of this post, you will see artifacts from SC '26 and PACT '26, two conferences from this fall.

- [SC26 AD/AE for "Communication Avoiding Parallel Sketching via Sparse Subspace Embeddings"](https://trovi.chameleoncloud.org/dashboard/artifacts/bcffce09-cb02-4ba1-8e92-1f30a13f96da)
- [Computational Artifact - Understanding Reliability Bottlenecks in LLM Agents for HPC I/O Telemetry Analysis](https://trovi.chameleoncloud.org/dashboard/artifacts/5adfe437-b7df-4866-b21d-030fbe9568f8)
- [Artifact for "SALT: Symbolic Analysis of Loop Tiling"](https://trovi.chameleoncloud.org/dashboard/artifacts/fa2befc9-24de-442a-9fde-2141e0502eab)
- [Splyce: SIMD Vectorization of Sparse Coiteration](https://trovi.chameleoncloud.org/dashboard/artifacts/4ad43ccf-564d-450a-abf2-25a99d5d3d70)

## Trovi on the Horizon

We aren’t yet done adding new features to Trovi. Soon we are planning on supporting a more general type of artifacts, beyond ones orchestrated via Jupyter notebooks, and we are looking to show the lineage of artifacts, so that you can see users “fork” an artifact to create new ones. Additionally, if you have any feedback or suggestions on the current Trovi features, we’d love to hear from you, as always, via [the help desk](https://chameleoncloud.org/user/help/).
