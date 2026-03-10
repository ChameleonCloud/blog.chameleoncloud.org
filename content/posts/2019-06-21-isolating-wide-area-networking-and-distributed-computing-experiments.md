---
abstract: '<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom:
  0pt;"><span style="color: rgb(0, 0, 0); font-family: Arial; font-size: 14.6667px;
  white-space: pre-wrap;">Chameleon''s DirectStitch capabilities enable isolated direct
  OSI layer 2 connections between tenant networks and external facilities, including
  other Chameleon sites.</span></p>'
authors:
- Paul Ruth
categories:
- Tips and Tricks
date: '2019-06-21 16:47:24+00:00'
featured: false
hide_image: true
image: ''
slug: isolating-wide-area-networking-and-distributed-computing-experiments
subtitle: ''
title: Isolating Wide-area Networking and Distributed Computing Experiments
---

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-3dc7e520-7fff-16b3-5f44-4c112c4dd7e5"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Many networking and distributed computing experiments require servers and clients distributed across a wide-area environment. Typically, these experiments use the publicly accessible Internet to send network traffic between the different parts of the experiment.  Although the Internet is easy to use and adequate for many experiments, it does come with limitations. The shared nature of the Internet makes it difficult to control for congestion and security issues caused by factors outside of your experiment. Further, the Internet architecture requires the use of the IP protocol and most institutions use relatively slow firewalls to filter traffic that does not conform to TCP and UDP protocols using a set of secure port numbers. Often experiments need an isolated higher bandwidth networking environment where cross traffic can be controlled and arbitrary, sometimes custom, OSI layer 2 protocols can be used. </span></span></p>

<h3 dir="ltr" style="line-height: 1.38; margin-top: 16pt; margin-bottom: 4pt;"><span id="docs-internal-guid-3dc7e520-7fff-16b3-5f44-4c112c4dd7e5"><span style="font-size: 14pt; font-family: Arial; color: rgb(67, 67, 67); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Chameleon DirectStitch</span></span></h3>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-3dc7e520-7fff-16b3-5f44-4c112c4dd7e5"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Chameleon's DirectStitch capabilities enable isolated direct OSI layer 2 connections between tenant networks and external facilities, including other Chameleon sites. Basic isolated tenant networks are private networks for connecting cloud nodes. Typically, each node on the private network can communicate with other nodes on the network and use a NAT router managed by the Chameleon's OpenStack system to communicate with the public Internet. </span></span><br>
 </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-3dc7e520-7fff-16b3-5f44-4c112c4dd7e5"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Chameleon DirectStitch works by adding a port to the isolated network's switch that connects to Internet2's Advanced Layer 2 Service (AL2S) on a specific VLAN tag. The user can then use AL2S to connect a layer 2 circuit between the Chameleon DirectStitch port and other endpoint on AL2S.  </span></span></p>

<p> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-3dc7e520-7fff-16b3-5f44-4c112c4dd7e5"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"> </span></span></p>

<h3 dir="ltr" style="line-height: 1.38; margin-top: 16pt; margin-bottom: 4pt;"><span id="docs-internal-guid-3dc7e520-7fff-16b3-5f44-4c112c4dd7e5"><span style="font-size: 14pt; font-family: Arial; color: rgb(67, 67, 67); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"><img src="https://lh5.googleusercontent.com/7c5w6euqF2iqlMswD7qX3E383CfT7Xk3feljfrUulkZMSBvwPDGMrLiOfuiABD1uFhqAVWvtvC6lFI7wvU-4BCh8T4FB8fsulMPdp0NRDGnaQHM0VMNA-UZow7PRT6p-_9e-Ht0u" width="624" style="border: none;" height="355"></span></span></h3>

<p> </p>

<p><span id="docs-internal-guid-3dc7e520-7fff-16b3-5f44-4c112c4dd7e5"><span style="font-size: 14pt; font-family: Arial; color: rgb(67, 67, 67); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Isolating Chameleon Network Experiments </span></span></p>

<p><span id="docs-internal-guid-3dc7e520-7fff-16b3-5f44-4c112c4dd7e5"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Many Chameleon users are familiar with the ‘sharedwan1’ network that spans both UC and TACC.  This network simplifies the deployment of high-bandwidth Chameleon experiments across both sites.  Using It is a simple as deploying nodes at each site connected to ‘sharedwan1’ instead of ‘sharednet1’ and using the local (‘fixed’) IP addresses.  Traffic between nodes should have lower latency, higher-bandwidth (10 Gbps/node, 100 Gbps aggregate), and less interference from Internet routers and traffic along the path between the sites.  However, this network is shared among all Chameleon users and is controlled by the Chameleon admin. </span></span></p>

<p> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-3dc7e520-7fff-16b3-5f44-4c112c4dd7e5"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"><img src="https://lh6.googleusercontent.com/9CqoKY-Xp-e-7fcNWJV3gSXBeRUyvWrYDRB1Oa6UPeXEATwMwems5NkITg8m9-NVoCZbnGL16ElJaxt8yXQwuZiwz0L84lnVj5Sz6N0-K4iJmHgLax9dea9mLd6ccMLB10p862sZ" width="624" style="border: none;" height="247"></span></span></p>

<p> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-3dc7e520-7fff-16b3-5f44-4c112c4dd7e5"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">What if you wanted your own isolated ‘sharedwan1’?  What if you wanted to control the network of your wide-area experiment using OpenFlow?</span></span></p>

<p><span id="docs-internal-guid-3dc7e520-7fff-16b3-5f44-4c112c4dd7e5"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">The most common use of DirectStitch is to create tenant controlled isolated networks distributed across Chameleon sites.  These networks have the same latency and bandwidth characteristics as ‘sharedwan1’ but are isolated not only from the Internet but from other Chameleon users as well.</span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-3dc7e520-7fff-16b3-5f44-4c112c4dd7e5"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">The Chameleon team has simplified the deployment of these networks and have included Jupyter notebook tutorial for all Chameleon users accessible at: https://jupyter.chameleoncloud.org/hub/user-redirect/lab/tree/notebooks/tutorials/networking/Tutorial-DirectStitch.ipynb</span></span><br>
 </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-3dc7e520-7fff-16b3-5f44-4c112c4dd7e5"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Anyone interested in trying tenant controlled wide-area networking experiments is invited to try the tutorial. </span></span></p>

<p> </p>
