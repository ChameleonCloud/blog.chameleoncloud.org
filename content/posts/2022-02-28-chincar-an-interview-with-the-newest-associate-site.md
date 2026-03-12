---
abstract: "<p>Discover\_Chameleon's newest Associate Site in this interview with the\
  \ National Center for Atmospheric Research (NCAR). Learn all about the process of\
  \ setting up an Associate Site, how the NCAR site came about, and most importantly,\
  \ what resources are available for you to experiment with!</p>"
authors:
- Jenett Tillotson
categories:
- Tips and Tricks
date: '2022-02-28 16:49:30+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/35/df/35df30f9-3eac-4ee4-9f52-ac0df364d8c9/8c9a4695.jpg
related_posts: []
slug: chincar-an-interview-with-the-newest-associate-site
subtitle: ''
title: 'CHI@NCAR: An Interview with the Newest Associate Site'
---

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-32bbfc2c-7fff-7336-6b48-5ebf3a1874ec"><img height="416" src="https://lh4.googleusercontent.com/10XqgaSqwozuljZTO9m9EVsLgjzV7L2dlydUp4XpnNJili8F6roiy7K4s_RPKtbHQ1SD1AnE1KO9rSlFIn4x48RC5EdaGaWd4X11o7P03mRdvyrDBLF-pLGVneCeoiKZc0pfax4i" width="624"></b></p>

<p dir="ltr"><b id="docs-internal-guid-30d4ebd4-7fff-fbf5-78c2-fbdd00852e9c">Welcome to the Chameleon family – we are super excited to partner with you to advance computer science systems research! First, can you tell our readers about NCAR?</b></p>

<p dir="ltr">The National Center for Atmospheric Research (NCAR) is an NSF funded research center for university climate scientists from across the United States. Our Computational and Information Systems Lab (CISL) maintains supercomputing resources to support this research. We currently operate the Cheyenne supercomputer, a 5.3PF HPE/SGI ICE cluster which provides the majority of computational power utilized by our community.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-30d4ebd4-7fff-fbf5-78c2-fbdd00852e9c">How did the NCAR/Chameleon collaboration emerge? </b></p>

<p dir="ltr">NCAR first partnered with Chameleon through the IndySCC, a virtual student cluster competition aimed at helping student teams prepare for the main Student Cluster Competition held at the annual Supercomputing conference. Chameleon provided an easy way for teams to access remote hardware and use them in a 48-hour data processing competition with a power usage limitation. Teams were given access to hardware that was currently available on Chameleon, and we were also able to bring loaner hardware online for the teams to use. We monitored power usage and provided power usage data to the teams. The Chameleon team was central to all aspects of providing the hardware for the competition and instrumental in making the competition a success.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-30d4ebd4-7fff-fbf5-78c2-fbdd00852e9c">What resources are you contributing to the Chameleon testbed and where did they come from? </b></p>

<p dir="ltr">As part of the procurement process at NCAR, we evaluated the ARM ThunderX2 processors as possible candidates for our next computational system. Through NSF funds we acquired a login node and four compute nodes based on the Gigabyte R281-T94 system. After NCAR thoroughly evaluated these nodes, we felt Chameleon would be a good way to make these machines available to other researchers for evaluation purposes. </p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-30d4ebd4-7fff-fbf5-78c2-fbdd00852e9c">Tell us about the experience of becoming an Associate Site. Specifically, what was the process of installing CHI-in-a-Box like? Have you worked with systems like that before? </b></p>

<p dir="ltr">So first, as one of CISL’s senior systems engineers I’ve had many years of experience with a wide variety of cluster managing software – but I never had any direct experience with Openstack. We did hit some snags: in particular, Chameleon staff had to make a few adaptations for CHI to support the unique machines we were contributing to the testbed. Firstly, due to our use of the sideband interface for BMC connectivity, they had to develop a flat network configuration to support our network setup. Secondly, they also added ARM+UEFI to the catalog of supported images and compiled the ironic pre-boot image and ipxe kernel in order to support the aarch64 processor. Two hardware issues were worked around by modifying the default Ironic configuration: secure erase was disabled, as the disks erroneously reported support for this feature, but would lock up during deployment; and power state monitoring was disabled, as the BMCs frequently reported transient error states. Both of these are likely due to the developmental and cutting-edge nature of these machines. All in all, Chameleon was no more difficult to install or configure than any other method used to setup these nodes. The main difficulty came from the uniqueness of the hardware and the differences between the network configuration of the machines and what Chameleon expected.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-30d4ebd4-7fff-fbf5-78c2-fbdd00852e9c">How did you like working with the Chameleon operations team?</b></p>

<p dir="ltr">’I've known some members of the Chameleon team for years and have worked with them on previous projects. I’m always impressed by Kate and her teams, and Chameleon was no exception. The Chameleon team solved several complex issues in a short amount of time. They obviously have a wide range of knowledge across all sorts of HPC systems and are dedicated to the project. I enjoyed working with them immensely.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-30d4ebd4-7fff-fbf5-78c2-fbdd00852e9c">How will the NCAR site be operated going forward? </b></p>

<p dir="ltr">We plan for the ARM Chameleon cluster to eventually be operated by student workers. Given the complexity but then also the structure of the system, it would be an excellent opportunity for a junior systems engineer to gain experience with the technologies used by Chameleon and learn how to support a non-mission critical environment.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-30d4ebd4-7fff-fbf5-78c2-fbdd00852e9c">What Chameleon features are available at your site and which ones are not? </b></p>

<p dir="ltr">We installed the bare metal flavor of CHI as this made the most sense for the hardware we are contributing – I think the most interest will come from researchers working on power management and HPC and those studies typically require bare metal access. The main things that are not available are network stitching and BYOC due to the flat network configuration I talked about earlier.</p>

<p><br>
 </p>

<p dir="ltr"><b id="docs-internal-guid-30d4ebd4-7fff-fbf5-78c2-fbdd00852e9c">What advice would you give to others wanting to configure Chameleon Associate sites?</b></p>

<p dir="ltr">Take security into consideration from the start. We connected our Chameleon nodes to our DMZ so they wouldn’t affect our production equipment. We also used a completely separate set of hardware for the infrastructure to support these nodes. Consider having external traffic pass through the management node so that you can monitor Internet traffic closely not only for things your nodes may be doing to other machines but for hackers who might be able to get control of your machines.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-30d4ebd4-7fff-fbf5-78c2-fbdd00852e9c">What resources are available? </b></p>

<p dir="ltr">The <a href="https://chameleoncloud.org/experiment/sites/chincar/">CHI@NCAR site</a> has 5 <a href="https://www.gigabyte.com/us/Enterprise/ARM-Server/R181-T92-rev-100">ARM ThunderX2 nodes</a>, each with 2x Marvell ThunderX2 CN9980 32-core ARM processors, for a total of 64 cores and 256 threads, as well as up to 256Gb of RAM, 4x 2TB HDDs, and 10Gb/s networking. Chameleon users can access the NCAR resources on the <a href="https://chameleoncloud.org/experiment/sites/chincar/">CHI@NCAR site</a> under the Experiment tab. </p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-30d4ebd4-7fff-fbf5-78c2-fbdd00852e9c">Tell us a little bit about yourself</b>:</p>

<p dir="ltr">I am a Senior Systems Engineer working for the National Center for Atmospheric (NCAR) research. I have been working as an HPC systems professional for over 18 years. My career started at Purdue University as a Linux Systems Administrator where I fell into research computing after being recruited to install the computer infrastructure for the Envision Center, a visualization center still in operation today. My first cluster was a twelve-node cluster that drove a passive stereo, rear-projected tiled wall. After that I moved into more general purpose HPC systems work and eventually to Indiana University where I was a Senior Cluster Systems Administrator for eleven years. I managed several IBM and Cray supercomputers and various support infrastructure for these machines. I now work for NCAR where I help maintain research computing infrastructure for climate scientists across the country including a 5.3PF HPE/SGI ICE machine and over 120 PB of parallel file system storage. I find being a systems professional to be a rewarding career. I work on cutting edge technologies solving problems often seen by our team for the first time. I’m always learning and growing, so I never get bored. I spend a lot of my free time as a community organizer. I help lead the Systems Professional chapter of the HPC Special Interest Group of the ACM which organizes several information sharing workshops during the year. I am a founding member of Bloominglabs, a makerspace in Bloomington, Indiana, where I still serve as the treasurer. I’m also active in Discardia, a group whose mission is to divert materials from the waste stream, and we are currently organizing our annual Trashion Refashion Runway event where we turn trash into fashion to highlight the waste issues in our communities.</p>

<p><br>
 </p>