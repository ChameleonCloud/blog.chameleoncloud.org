---
abstract: <p>Sit down with Fei Yeh, an associate researcher with the International
  Center for Advanced Internet Research (iCAIR) at Northwestern University, to learn
  how a Chameleon associate site was set up, how you can use it, and his experience.</p>
authors:
- Fei Yeh
categories:
- Tips and Tricks
date: '2021-02-19 17:00:17+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/44/63/446399a7-0265-43eb-a935-088be8cdb3d0/zoom_snowy-arch.jpg
slug: setting-associate-site-interview-northwestern-university
subtitle: ''
title: 'Setting Up an Associate Site: An Interview With Northwestern University'
---

<p dir="ltr"><b id="docs-internal-guid-0016def9-7fff-2116-e4a6-677201d765a7"><img height="351" src="https://lh5.googleusercontent.com/XX-EgELDm1sBxVQa5isRQZ1I7ivlHuv1PNoltYPE1W3Fe-nO3oYcN_X1W8039h79FD__XcqPOd7i4LC_ldPQskfeTdnkDtPRZbRU9lJYz-p24NH8mJ1qix6MuT6hc1ASyOdNfm0_" width="624"></b></p>

<p dir="ltr"><b id="docs-internal-guid-cfd04dce-7fff-514c-3457-c7dfcab6a30e">Congratulations on setting up the first Chameleon Associate Site! What can you tell us about your site?</b></p>

<p dir="ltr">StarLight International/National Communications Exchange Facility is an international research facility as well as an international exchange point for supporting scientific research and is probably the first such facility in the US. It was originally developed with funding from the National Science Foundation, by the joint efforts of the Electronic Visualization Laboratory (EVL) at the University of Illinois at Chicago (UIC), iCAIR (International Center for Advanced Internet Research) at Northwestern University, and the Mathematics and Computer Science (MCS) Division at Argonne National Laboratory, in partnership with Canada's CANARIE and Holland's SURFnet networks. Our mission is to provide tools, techniques, and technologies that support data-intensive science, for example, allowing users and applications to control core resources, including lightpaths, dynamically. These mechanisms can be used to empower applications to dynamically adjust and optimize network resources to meet their requirements. Through research, we attempt to innovate advanced networking in every possible way.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-cfd04dce-7fff-514c-3457-c7dfcab6a30e">What kind of hardware is available at your Associate Site and how can people use it?</b></p>

<p dir="ltr">There are three Dell PowerEdge R630, each connected to both 10GE and 100GE network switches capable of dynamic flexible L1 and L2 on-demand networking across international testbeds, including a 100Gbps P4 programmable switch. We expect to add another two PowerEdge R740xd servers soon. These capabilities add a range of new networking experiments to what Chameleon already supports by providing nodes equipped with 100G NICs not present anywhere else on the testbed. These resources allow users to experiment with large flows in new ways, including across thousands of miles national and internationally, distances that usually only can be mimicked in simulations.</p>

<p dir="ltr">These new capabilities are available to all Chameleon users via federated login. Up till now, they have been used mostly by select collaborators who were already aware of the Chameleon resource at StarLight. We hope that the announcement of the NU Chameleon Associate Site site in the recent <a href="https://www.chameleoncloud.org/blog/2021/02/02/chameleon-changelog-january-2021/">changelog</a> will lead to more users trying them out for experimentation. </p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-cfd04dce-7fff-514c-3457-c7dfcab6a30e">On a practical level, what does it mean to be a Chameleon Associate Site? </b></p>

<p dir="ltr">Here at StarLight, we provide, maintain, and operate the hardware. The Chameleon operations team provides support for installation, configuration, and upgrades. Additionally now that the site is generally available, they also provide user support via the Chameleon Help Desk. We are collaborating with the Chameleon operations team to define these mutual responsibilities more formally so that we have a path forward in every contingency that may occur. Once the systems are configured and running there are only occasional checks to make sure resources are recycled correctly and minor fixes and updates are applied.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-cfd04dce-7fff-514c-3457-c7dfcab6a30e">What can you tell us about the configuration process? </b></p>

<p dir="ltr">The CHI-in-a-box repository reduced a lot of the installation/configuration process. However, due to the complexity of OpenStack and the new networking capabilities at StarLight, it still took a bit of trial and error before the current working configuration was finalized and correctly installed. In the end, we decided to tailor the NU site to be almost identical to TACC and UC to ensure compatible architecture. </p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-cfd04dce-7fff-514c-3457-c7dfcab6a30e">The Chameleon Infrastructure (CHI) is built on top of OpenStack. Why create a CHI site rather than simply use OpenStack with bare metal reconfiguration? </b></p>

<p dir="ltr">One reason is that CHI is a version of OpenStack that has been enhanced to support computer science systems research. It includes capabilities that bare metal version of OpenStack does not support such as snapshotting (saving configured images), network stitching, the Bring Your Own Controller functionality that allows users to program their own SDN-enabled network controllers,  support for identity federation, and integration with Jupyter -- and probably some more I am forgetting now. It also comes with a library of pre-configured images that somebody else supports. It would take a lot of time to develop or integrate any of those capabilities yourself.</p>

<p dir="ltr">Another reason is that CHI comes with the expertise of the Chameleon Team having run OpenStack for many years and includes all sorts of operational tools for for maintenance and troubleshooting, such as infrastructure monitoring and failure detection via Prometheus, a collection of runbooks to handle common problems, and even bots that monitor the site and automatically fix some error conditions. That again would take a long time to develop on your own. Also, as an associate site we operate only the hardware on the site; all user support is provided by the Chameleon team so that is a good thing too.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-cfd04dce-7fff-514c-3457-c7dfcab6a30e">How did you like working with the Chameleon operations team? </b></p>

<p dir="ltr">The Chameleon operations team has been instrumental in helping me with maintenance, updates, and re-installs.  Despite trying to view the new installation process through the eyes of someone who has had almost no experience installing and troubleshooting OpenStack, I still learned a lot of new OpenStack features and settings that I was not aware of in previous versions.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-cfd04dce-7fff-514c-3457-c7dfcab6a30e">Tell us a little bit about yourself: </b></p>

<p dir="ltr">I’ve worked at iCAIR/Northwestern for close to 20 years since I graduated, and I still feel right at home in the academic research community.  I love learning in all its forms, especially reading. A day is well spent if I have read (although these days it’s almost guaranteed in electronic format) and learned just one new thing. These days I get to spend a lot more time with my family and pets at my new house in the far west suburbs of Chicago.  Having lived and worked in the city for better half of my life, I’m beginning to remember that wildlife is actually a thing, especially given the current circumstances.</p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-cfd04dce-7fff-514c-3457-c7dfcab6a30e">How do you compare setting up a CHI site to working with other academic infrastructure? </b></p>

<p dir="ltr">I have worked with many distributed computing environments, Grid Computing, Virtual Machines, and now Cloud computing and containers.  It’s very interesting to see how far the software has come in terms of ease-of-use and how much more service-oriented it has become.</p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-cfd04dce-7fff-514c-3457-c7dfcab6a30e">What advice would you give to others wanting to configure Chameleon Associate sites?</b></p>

<p dir="ltr">A bit of skill in everything cloud-related will come in handy: some networking, some hardware and software debugging.  I think it will be helpful to create a repository of all the configuration options required to get CHI up and running, and then generate the install configuration from that data.  Familiarity with how OpenStack works is very helpful, as well as how to run and debug docker containers. I recommend spending about a day each, learning the basics of both software suites.</p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-1aaff5a8-7fff-2ab4-c891-2601c38cc1eb">Interested readers can use the resources at the Northwestern associate site by selecting 'CHI@NU' from the possible sites once inside the Project Dashboard. </b></p>

<p dir="ltr"><b id="docs-internal-guid-1aaff5a8-7fff-2ab4-c891-2601c38cc1eb"><img height="532" src="https://lh3.googleusercontent.com/xRWgOgWFXH6ht3MdQIQLUXhMgVLqry-OhUmjS49FZI3dhpKO11ZWyBkcq8Z8TRDijgUlpOv9BwMKg6zETSpxgLeof13cpF7fVgT59SPKQ6YfKv55kxNEghndx2mB0r5NLbJYjcw1" width="624"></b></p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-1aaff5a8-7fff-2ab4-c891-2601c38cc1eb">Additionally, the most current resources available at CHI@NU can be seen on the <a href="https://www.chameleoncloud.org/hardware/">Hardware Discovery pag</a>e, by selecting ‘Site’ as NU underneath the Resource Browser category.</b></p>

<p dir="ltr"><b id="docs-internal-guid-c295622b-7fff-8d0f-2b40-526fe2bee00c"><img height="695" src="https://lh5.googleusercontent.com/lWlKMtFdDlfF0YL7ngYMq87E1O4wBPrDLvo7poQsuREJN5J1YHhVLVzpfgFc8ncvNvl8lJycEh8dCLMnj2MQDy8g2J5sBoANFAptGLtZw1mq9ZZ38cZoS_kiQyPQ0QzrdBYI8YzU" width="624"></b></p>

<p><br>
 </p>

<p dir="ltr"> </p>