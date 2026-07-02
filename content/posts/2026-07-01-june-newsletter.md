---
abstract: <p>This month we're reminding you not to miss out on limited-time Ponte
  Vecchio (Intel GPU) nodes and the plentiful hardware available at CHI@NCAR, previewing
  a redesigned Resource Discovery browser, adding ccauth support to python-chi, improving
  long-running commands on CHI@Edge, retiring the vendor-data service, and refreshing
  our documentation. In the community, Kate Keahey delivered a keynote at the ISC
  High Performance 2026 Reproducibility Workshop.</p>
authors: []
categories:
- Chameleon Changelog
- Featured
date: '2026-07-01'
featured: true
hide_image: false
image: 'https://chameleoncloud.org/media/filer_public/38/ce/38ce5c45-dfa5-421a-95c2-a283e31854a9/newsletter-june-2026.jpg'
related_posts:
- slug: chameleon-newsletter-changelog-may-2026
  title: Chameleon Newsletter & Changelog May 2026
- slug: chameleon-newsletter-changelog-april-2026
  title: Chameleon Newsletter & Changelog April 2026
- slug: chameleon-newsletter-changelog-march-2026
  title: Chameleon Newsletter & Changelog March 2026
slug: chameleon-newsletter-changelog-june-2026
subtitle: Welcome to the Chameleon June 2026 Newsletter!
title: Chameleon Newsletter & Changelog June 2026
---

<p>Welcome to the Chameleon June 2026 Newsletter! This month is a reminder not to miss out on limited-time Ponte Vecchio (Intel GPU) nodes and the plentiful hardware available at CHI@NCAR. We're also previewing a redesigned Resource Discovery browser, adding ccauth support to python-chi, improving long-running commands on CHI@Edge, retiring the vendor-data service, and refreshing our documentation. In the community, Kate Keahey delivered a keynote at the ISC High Performance 2026 Reproducibility Workshop, and our usual Tips&amp;Tricks and User Experiment blogs are linked below.</p>

<h2>Resource Updates</h2>

<p><strong>Ponte Vecchio (Intel GPU) &ndash; Don't miss out!:</strong> Last month, we announced that a set of <strong>Ponte Vecchio (Intel GPU) nodes</strong> are now available on Chameleon for a <strong>limited time only!</strong> Be sure to act quickly if you are interested. They will only be around for a bit.</p>

<p><strong>One more reminder: lots of available hardware at CHI@NCAR:</strong> A reminder that <a href="https://chi.hpc.ucar.edu/project/">CHI@NCAR</a> is now a full Chameleon site, and we've got plenty of capacity ready for your experiments and students. If you have a large class coming up in Fall 2027, this site could be useful for spinning up large clusters.</p>

<h2>Changelog</h2>

<p><strong>Redesigned Resource Discovery (Preview)!</strong> One of the first steps in any Chameleon experiment is discovering what hardware fits your needs. The current <a href="https://chameleoncloud.org/hardware/">Resource Discovery</a> application has served Chameleon users well since the project began, but it has shortcomings: for example, it doesn't include availability information for a node (i.e., when you can actually make a reservation). This month, we are excited to announce a brand new <a href="https://blog.chameleoncloud.org/posts/major-updates-to-chameleon-resource-discovery/">Resource Discovery browser</a> with a completely updated interface. This interface now lets you filter by availability, and improves the overall experience of filtering for specific hardware properties. Additionally, it's now easier to compare usage between sites, letting you plan for both large scale experiments, and experiments where you want to renew a lease.</p>

<p>This browser is still in preview, so we are eager to gather feedback from the community. You can leave us a comment in the new Resource Discovery browser (click the "<strong>feedback</strong>" button at the top of the page) or, if you'd like to leave more detailed feedback, fill out our feedback form <a href="https://forms.gle/cwB7KnuTDmhXc5nh6">here</a>. Please contact us via the <a href="https://chameleoncloud.org/help">Help Desk</a> if you run into bugs or technical issues. Stay tuned for VM instance support in the future.</p>

<p><strong>Support for ccauth in python-chi.</strong> Last month, <a href="https://blog.chameleoncloud.org/posts/chameleon-newsletter-changelog-may-2026/">we released ccauth</a> as a new method for authenticating with the CLI via a "device flow," meaning that instead of setting up environment variables with credentials, you instead <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/cli/ccauth.html">open a link in your browser</a>. This month, we've added this same authentication method to python-chi via the <code>use_device_auth</code> function. If you have the latest version of python-chi installed, and you install <a href="https://github.com/ChameleonCloud/ccauth">ccauth via pip</a>, you can simply call <code>context.use_device_auth()</code> at the top of your script to set up credentials. No more messing around with openrc files or a clouds.yaml config!</p>

<p><strong>Improved long-running commands on CHI@Edge.</strong> Our edge testbed, CHI@Edge, allows users to run containerized workloads on devices, including Raspberry Pis and Nvidia Jetson Nanos. While typically you will want to run your experiment as the container's command, it is also possible to execute one-off commands for debugging, like <code>ls</code>, <code>ps</code>, etc. These one-off commands would timeout if they took a while to execute. This month, we've improved this, so that you can also run long running commands like <code>bash</code> or <code>apt-get update</code> inside your container. Right now, you can run these commands via <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/cli/index.html">the CLI</a> using <code>openstack appcontainer exec --interactive</code>.</p>

<p><strong>Vendor-data removal.</strong> <a href="https://blog.chameleoncloud.org/posts/chameleon-newsletter-changelog-march-2026/">Back in March</a>, we deprecated our vendor-data service which automatically configured new instances with credentials. This month, we've stopped the service at our sites. If you need to authenticate from within your instance, see our <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/cli/vendordata_auth_removal.html">new documentation</a> on the topic. Importantly, if your experiment automatically orchestrates Chameleon resources from an instance (e.g., if you have a script which provisions an instance, runs an experiment, and uploads data), you will now need to provide your own application credential. For any questions or concerns, please contact us via the <a href="https://chameleoncloud.org/help">Help Desk</a>.</p>

<p><strong>Documentation improvements.</strong> We've refreshed the CLI, KVM, Trovi, and federation guides with clearer troubleshooting, cross-references, and python-chi examples &mdash; check out the updated <a href="https://chameleoncloud.readthedocs.io/en/latest/">docs</a> for a smoother experience with your Chameleon workflows.</p>

<h2>Community News</h2>

<p><strong>Kate Keahey Keynotes ISC High Performance 2026 Reproducibility Workshop.</strong> Chameleon Cloud PI Kate Keahey delivered a keynote at the 1st Workshop on Sustainable Practices for Reproducibility in HPC (REPRO-HPC), held June 26 at <a href="https://isc-hpc.com/">ISC High Performance 2026</a> in Hamburg, Germany. The workshop, co-located with ISC26, tackled the reproducibility challenges facing HPC and systems research &mdash; complex software stacks, cutting-edge hardware, and costly experiments &mdash; themes central to Chameleon's own <a href="http://trovi.chameleoncloud.org">Trovi</a> reproducibility work. Keahey shared the keynote slot with Helena Vela Beltran of Do IT Now (EESSI). <a href="https://www.anl.gov/cels/article/argonne-at-isc-2026">Argonne coverage</a> | <a href="https://www.hpcwire.com/off-the-wire/argonne-brings-ai-quantum-and-hpc-expertise-to-isc-2026/">HPCwire coverage</a></p>

<p><strong>Tips and Tricks: Getting Access to Chameleon as a Student Researcher.</strong> Not sure how to get on Chameleon without your own allocation? Our latest Tips and Tricks post walks through every path available to student researchers &mdash; from joining a PI's project to using Daypass for allocation-free exploration. <a href="https://blog.chameleoncloud.org/posts/tips-and-tricks-getting-access-to-chameleon-as-a-student/">Read more</a></p>

<p><strong>User Experiment: I/O Analysis is All You Need.</strong> Xiaoyang Lu (Illinois Institute of Technology) built AttenIO, an I/O-driven accelerator for long-sequence self-attention that delivers up to 3.4&times; speedup over FlashAttention-2 by minimizing data movement across the memory hierarchy &mdash; all benchmarked on Chameleon. <a href="https://blog.chameleoncloud.org/posts/attenio-io-analysis-long-sequence-attention/">Read more</a></p>
