---
abstract: <p>This month we're introducing a dedicated Resource Updates section to
  our newsletter, announcing Ponte Vecchio GPUs at CHI@TACC for a limited time,
  improving CLI authentication with the new ccauth tool, increasing the image size
  limit to 100GB, adding Ubuntu 26.04 support with a new fractional GPU image, and
  improving CHI@Edge BYOD enrollment. In the community, Kate Keahey delivered a keynote
  at CCGrid 2026 in Sydney.</p>
authors:
categories:
- Chameleon Changelog
- Featured
date: '2026-06-01'
featured: true
hide_image: false
image: 'https://chameleoncloud.org/media/filer_public/62/f3/62f3840e-41d4-484f-b5c4-0c1f3cbf987a/may_newsletter_2026.jpg'
related_posts:
- slug: chameleon-newsletter-changelog-april-2026
  title: Chameleon Newsletter & Changelog April 2026
- slug: chameleon-newsletter-changelog-march-2026
  title: Chameleon Newsletter & Changelog March 2026
- slug: chameleon-newsletter-changelog-february-2026
  title: Chameleon Newsletter & Changelog February 2026
slug: chameleon-newsletter-changelog-may-2026
subtitle: Welcome to the Chameleon May 2026 Newsletter!
title: Chameleon Newsletter & Changelog May 2026
---

<p>Welcome to the Chameleon May 2026 Newsletter! Starting this month, we're tracking important resource news in a dedicated section so you can keep up with hardware changes that might affect your work. This month features Ponte Vecchio GPUs at CHI@TACC for a limited time, a new ccauth tool to simplify CLI authentication, an increased image size limit of 100GB, Ubuntu 26.04 support with a new fractional GPU image, and CHI@Edge BYOD enrollment improvements. In the community, Kate Keahey delivered a keynote at CCGrid 2026 in Sydney, Australia, and our usual Tips&Tricks and User Experiments blogs are linked below.</p>

<h2>Resource Updates</h2>

<p><em>Moving forward, we will track resource news in a dedicated section of our newsletter, so that you can keep track of important resource updates on the system that might affect your work.</em></p>

<p><strong>New Nodes Available — Limited Time!:</strong> <strong>Ponte Vecchio GPUs</strong> are now available on Chameleon for a <strong>limited time only!</strong> More information below in the changelog.</p>

<p><strong>CHI@NCAR — Ready for Your Workloads:</strong> A reminder that <a href="https://chi.hpc.ucar.edu/project/"><strong>CHI@NCAR</strong></a> is now a full Chameleon site, and we've got plenty of capacity ready for your experiments and students. If you have a large class coming up in Fall 2027, this site could be useful for spinning up large clusters. The site now features <strong>40 new Compute Zen 5 nodes</strong>, each equipped with:</p>

<ul>
    <li><strong>AMD EPYC 4545P</strong> 16-core processor</li>
    <li><strong>64 GiB of memory</strong></li>
    <li><strong>1 TB NVMe storage</strong> — great for I/O-heavy workloads requiring fast interactive storage</li>
</ul>

<p>The site also has <strong>75 TB of object storage</strong> available. Don't be shy!</p>

<h2>Changelog</h2>

<p><strong>Ponte Vecchio GPUs at CHI@TACC!</strong> For a limited time, CHI@TACC has 2 new nodes with Intel Ponte Vecchio GPUs. These nodes have Intel Xeon Platinum 8468 CPUs, 1TB of RAM, and 4x Ponte Vecchio XT GPUs. These GPUs may be of interest to anyone looking to experiment with novel hardware, or for anyone wanting to use 128GB of VRAM. You can find the full specification for these nodes in our <a href="https://chameleoncloud.org/hardware/">hardware browser</a> under node type <code>gpu_pontevecchio</code>. We do not yet have an image with preconfigured drivers like we do for CUDA and ROCm, so in the meantime please follow <a href="https://dgpu-docs.intel.com/driver/client/overview.html">the Intel docs</a> when configuring your instances.</p>

<p><strong>CLI authentication improvements: ccauth.</strong> Chameleon supports 3 main interfaces: the web GUI, python-chi (our python sdk), or the openstack CLI. The web GUI automatically logs you into our testbed via our <a href="https://chameleoncloud.readthedocs.io/en/latest/user/federation.html">federated identity service</a>, and similarly if you are using <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/jupyter/index.html">python-chi from our JupyterHub</a>, your credentials will be automatically configured. To <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/cli/authentication.html">authenticate to the CLI</a>, you previously had to configure a password, and download an <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/cli/rc_script.html#the-openstack-rc-script">openrc</a> script or application credential file. While this is OK for a single project and site, it becomes tedious if, for example, you are running an experiment on KVM@TACC and you need to use the object store, which is at CHI@TACC and requires different credentials.</p>

<p>To improve this CLI workflow, we've built the tool <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/cli/ccauth.html">ccauth</a>. This tool uses a "device flow" method to authenticate, meaning that on first login you'll be asked to open a URL in your browser, meaning you no longer need to manually download credential files. As an example of the improved workflow, we've written new documentation on how to easily use ccauth to <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/swift/swift_cli.html#object-store-cli-kvm">configure access to the CHI@TACC object store</a> from KVM@TACC, or any site. We've also added a similar tool to our instances, <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/cli/cc_login.html">cc-login</a>, which can be used to generate the openrc file that is set up when your instance is provisioned.</p>

<p><strong>Support for larger images.</strong> Previously, anytime you wanted to launch an instance on Chameleon you were limited to images smaller than 20GB but this month we've increased this limit to 100GB. Our <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images/cc_snapshot.html">cc-snapshot utility</a> can be used to build a custom image from your baremetal instance after installing your experiment dependencies. While a 20GB image was huge 10 years ago, users reported that these days they need larger images, especially when installing machine learning software. Please keep in mind that creating images this large with cc-snapshot may be unstable. As an alternative, you could use an image build tool like <a href="https://github.com/ChameleonCloud/CC-Images/">CC-images</a> or export a KVM snapshot.</p>

<p><strong>Ubuntu 26.04 and support for images for fractional GPU leases.</strong> This month, we have a new image for the latest LTS version of <a href="https://documentation.ubuntu.com/release-notes/26.04">Ubuntu 26.04</a>! This comes with all sorts of updates to packages, including version 7.0 of the Linux kernel. In March, we released <a href="https://blog.chameleoncloud.org/posts/chameleon-newsletter-changelog-march-2026/">fractional GPU instances</a> on KVM@TACC via the <code>g1.h100.vgpu.1g.12gb</code> flavor. Instances of this flavor use 1/7th the resources of the PCI passthrough flavors, meaning that there is much more capacity for this instance type, making them a great candidate for education use. When we announced this feature there was not yet a Chameleon supported image, and instead you had to use an instance snapshot. This month we have released a special image under the name <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images/supported_images.html#chameleon-supported-images">CC-Ubuntu24.04-CUDA-VGPU</a> that comes with the drivers preconfigured for this type of instance.</p>

<p><strong>CHI@Edge BYOD improvements.</strong> Chameleon's Edge testbed, CHI@Edge, allows you to orchestrate containerized workloads on our devices such as <a href="https://chameleoncloud.gitbook.io/chi-edge/hardware-info/device-type">Raspberry Pis and NVIDIA Orins</a>. But did you know you can also use our <a href="https://chameleoncloud.gitbook.io/chi-edge/device-enrollment/edge-sdk">bring-your-own-device</a> (BYOD) framework to enroll devices on your own into the testbed? This month we've improved BYOD to show more information during the enrollment process. You will now see the up to date status for your device, better indicating where enrollment issues are occurring.</p>

<h2>Community News</h2>

<p><strong>Keahey Delivers Keynote at CCGrid 2026:</strong> In this <a href="https://chameleoncloud.org/media/filer_public/a9/01/a901567c-b6e0-4929-988d-936273b920e4/ccgrid_keynote_2026.pdf">talk</a>, our lead PI, Kate Keahey, presents lessons learned from her development of two NSF-funded, influential, and very distinct experimental systems — the Chameleon project and the FLOTO instrument for distributed broadband research. In this keynote talk delivered at CCGrid 2026 in Sydney, Australia, she describes how to leverage the exponentially growing opportunities in experimental system design. View the presentation <a href="https://chameleoncloud.org/media/filer_public/a9/01/a901567c-b6e0-4929-988d-936273b920e4/ccgrid_keynote_2026.pdf">here</a>.</p>

<p><strong>Tips&Tricks Blog of the Month:</strong> <a href="https://blog.chameleoncloud.org/posts/bringing-external-reproducibility-artifacts-into-trovi/">Bringing External Reproducibility Artifacts Into Trovi</a> — Trovi is expanding beyond user-uploaded artifacts to include selected reproducibility artifacts from major computer science conferences like EuroSys, SOSP, and SC. We've built a pipeline to crawl, index, and surface these external artifacts in the same interface you already use, and connected them to Chameleon so you can go from discovering an interesting artifact to running it on bare metal in minutes.</p>

<p><strong>User Blog of the Month:</strong> <a href="https://blog.chameleoncloud.org/posts/upfuzz-fuzzing-distributed-storage-upgrade-bugs/">UpFuzz: Hunting the Data-Format Bugs That Break Distributed-Storage Upgrades</a> — Distributed storage systems are upgraded constantly, and one subtle class of bug — data format incompatibility, where a new version misreads data written by the old one — ranks among the leading causes of cloud incidents during upgrades, with consequences as severe as data loss and cluster-wide outages. UpFuzz, an award-winning open-source fuzzer from Purdue University, is the first tool built specifically to hunt these cross-version bugs. It has already uncovered 15 previously unknown failures in the latest stable releases of Cassandra, HBase, and HDFS, and its evaluation was run on Chameleon's bare metal infrastructure.</p>
