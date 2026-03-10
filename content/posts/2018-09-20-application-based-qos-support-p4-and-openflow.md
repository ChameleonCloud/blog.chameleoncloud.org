---
abstract: '<p><span id="docs-internal-guid-3fdd3a83-7fff-9636-82ae-9f29df6cb96d"><span
  style="font-size: 10.5pt; font-family: Arial; color: rgb(0, 0, 0); vertical-align:
  baseline; white-space: pre-wrap;">This blog describes a prototype of a system that
  leverages the capabilities of flexible switches that incorporate protocol-independent
  packet processing in order to intelligently route traffic based on application headers.</span></span></p>'
authors:
- Divyashri Bhat
categories:
- User Experiments
date: '2018-09-20 15:15:13+00:00'
featured: false
hide_image: true
image: ''
slug: application-based-qos-support-p4-and-openflow
subtitle: ''
title: Application-based QoS support with P4 and OpenFlow
---

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span id="docs-internal-guid-06288ef3-7fff-2efa-1593-9155f517d85b"><span style="font-size: 10.5pt; font-family: Arial; color: rgb(0, 0, 0); vertical-align: baseline; white-space: pre-wrap;">Although Software Defined WANs are now widely deployed by several production networks, they are largely restricted to traffic engineering approaches based on layer 4 (L4) of the network protocol stack Quality-of-Service (QoS) improvements. However, the emergence of application protocols such as QUIC and HTTP/2 creates the need for an investigation of layer 5-based (L5) approaches in order to improve users’ Quality-of-Experience (QoE). This blog describes a prototype of a system that leverages the capabilities of flexible switches that incorporate protocol-independent packet processing in order to intelligently route traffic based on application headers. We use simultaneous file transfers as an example to show how applications such as ABR video streaming, GridFTP, or others can benefit from application header-based traffic engineering. Our prototype consists of a deployment on the Chameleon testbed, leveraging its SDN-enabled Corsa switches and Q-in-Q technology to efficiently orchestrate traffic at the core while software P4 switches are deployed at the edge to translate QoE requirements. In order to provide a single vantage point for our SDN experiments and structure them in repeatable fashion we use a Jupyter notebook technology integrated with the Chameleon testbed.</span></span></p>

<p> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span id="docs-internal-guid-06288ef3-7fff-2efa-1593-9155f517d85b"><span style="font-size: 10.5pt; font-family: Arial; color: rgb(0, 0, 0); vertical-align: baseline; white-space: pre-wrap;">This work will be presented as a demo at LCN 2018, Chicago, IL. To read the full paper go </span><a href="https://github.com/dbhat/lcndemo2018/blob/master/lcndemo2018.pdf" style=""><span style="font-size: 10.5pt; font-family: Arial; color: rgb(17, 85, 204); vertical-align: baseline; white-space: pre-wrap;">here.</span></a></span></p>

<p> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span id="docs-internal-guid-06288ef3-7fff-2efa-1593-9155f517d85b"><span style="font-size: 10.5pt; font-family: Arial; color: rgb(0, 0, 0); vertical-align: baseline; white-space: pre-wrap;"><img height="220" src="https://lh6.googleusercontent.com/38zajgb_n4T2MyflqlyMM0NoXbASYJaC2jmHMrfQ1h8eoG983y8_RS9QSr3fUDbqR_Ot_vCkqHWN2E7a5IMKZ9uD0BQPENCJ0Qc5A7XLoozJzqfFj9oIXsxSf6eVBEJLI38A3krW" style="" width="616"></span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span id="docs-internal-guid-06288ef3-7fff-2efa-1593-9155f517d85b"><span style="font-size: 10.5pt; font-family: Arial; color: rgb(0, 0, 0); font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">Note</span><span style="font-size: 10.5pt; font-family: Arial; color: rgb(0, 0, 0); vertical-align: baseline; white-space: pre-wrap;">: This experiment uses the Bring-Your-Own-Controller (BYOC) feature provided by Chameleon. For more details on how to run SDN experiments with Chameleon click </span><a href="https://www.chameleoncloud.org/blog/2018/08/17/software-defined-networking-openflow-chameleon/" style=""><span style="font-size: 10.5pt; font-family: Arial; color: rgb(17, 85, 204); vertical-align: baseline; white-space: pre-wrap;">here</span></a><span style="font-size: 10.5pt; font-family: Arial; color: rgb(0, 0, 0); vertical-align: baseline; white-space: pre-wrap;">.</span></span></p>

<p> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span id="docs-internal-guid-06288ef3-7fff-2efa-1593-9155f517d85b"><span style="font-size: 10.5pt; font-family: Arial; color: rgb(0, 0, 0); font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">Resources and Tools Required</span></span></p>

<ol style="margin-top: 0pt; margin-bottom: 0pt;">
	<li style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span><span style="font-size: 10.5pt; vertical-align: baseline; white-space: pre-wrap;">Bare-metal (8) - One Client, One Server, Two Cross Traffic, Two P4 switches, One controller and One Jupyter (All Ubuntu 16.04)</span></span></li>
	<li style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span><span style="font-size: 10.5pt; vertical-align: baseline; white-space: pre-wrap;"><span id="docs-internal-guid-06288ef3-7fff-2efa-1593-9155f517d85b"><span style="font-size: 10.5pt; vertical-align: baseline; white-space: pre-wrap;">Network </span></span></span></span>
	<ul>
		<li style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span id="docs-internal-guid-06288ef3-7fff-2efa-1593-9155f517d85b"><span style="font-size: 10.5pt; vertical-align: baseline; white-space: pre-wrap;">AL2S by Internet2</span></span></li>
		<li style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span id="docs-internal-guid-06288ef3-7fff-2efa-1593-9155f517d85b"><span style="font-size: 10.5pt; vertical-align: baseline; white-space: pre-wrap;">Two Corsa switches: TACC and UC</span></span></li>
	</ul>
	</li>
</ol>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span id="docs-internal-guid-06288ef3-7fff-2efa-1593-9155f517d85b"><span style="font-size: 10.5pt; font-family: Arial; color: rgb(0, 0, 0); vertical-align: baseline; white-space: pre-wrap;">For more details and steps on how to setup the environment go </span><a href="https://github.com/dbhat/lcndemo2018/blob/master/reproducibility_artifacts/ResourcesandTools.md" style=""><span style="font-size: 10.5pt; font-family: Arial; color: rgb(17, 85, 204); vertical-align: baseline; white-space: pre-wrap;">here.</span></a><span style="font-size: 10.5pt; font-family: Arial; color: rgb(0, 0, 0); vertical-align: baseline; white-space: pre-wrap;"> </span></span></p>

<p> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span id="docs-internal-guid-06288ef3-7fff-2efa-1593-9155f517d85b"><span style="font-size: 10.5pt; font-family: Arial; color: rgb(0, 0, 0); font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">Experiment Procedure</span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span id="docs-internal-guid-06288ef3-7fff-2efa-1593-9155f517d85b"><span style="font-size: 10.5pt; font-family: Arial; color: rgb(0, 0, 0); vertical-align: baseline; white-space: pre-wrap;">In this experiment we will use two types of P4 rules: a </span><span style="font-size: 10.5pt; font-family: Arial; color: rgb(0, 0, 0); font-style: italic; vertical-align: baseline; white-space: pre-wrap;">Baseline</span><span style="font-size: 10.5pt; font-family: Arial; color: rgb(0, 0, 0); vertical-align: baseline; white-space: pre-wrap;"> rule which forwards all HTTP/2 streams on a single path and a </span><span style="font-size: 10.5pt; font-family: Arial; color: rgb(0, 0, 0); font-style: italic; vertical-align: baseline; white-space: pre-wrap;">Fast Path</span><span style="font-size: 10.5pt; font-family: Arial; color: rgb(0, 0, 0); vertical-align: baseline; white-space: pre-wrap;"> rule which differentiates between original and retransmitted segments using the </span><span style="font-size: 10.5pt; font-family: Arial; color: rgb(0, 0, 0); font-style: italic; vertical-align: baseline; white-space: pre-wrap;">Stream ID</span><span style="font-size: 10.5pt; font-family: Arial; color: rgb(0, 0, 0); vertical-align: baseline; white-space: pre-wrap;"> to direct retransmissions on a path with better QoS. We use VLAN tags, i.e., Q-in-Q technology to translate Stream IDs into VLAN tags after which a second VLAN tag is attached before the packet is forwarded along the appropriate 802.1Q circuit. This technology allows us to translate edge routing traffic engineering principles which we implement in Layer-5 into the core network to be interpreted as a Layer-2 VLan tag.</span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span id="docs-internal-guid-06288ef3-7fff-2efa-1593-9155f517d85b"><span style="font-size: 10.5pt; font-family: Arial; color: rgb(0, 0, 0); vertical-align: baseline; white-space: pre-wrap;">The procedure is as follows.</span></span></p>

<ol style="margin-top: 0pt; margin-bottom: 0pt;">
	<li style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span><span style="font-size: 10.5pt; vertical-align: baseline; white-space: pre-wrap;">Obtain Resources on Chameleon and perform the setup as explained </span><a href="https://github.com/dbhat/lcndemo2018/blob/master/reproducibility_artifacts/ResourcesandTools.md" style=""><span style="font-size: 10.5pt; color: rgb(17, 85, 204); vertical-align: baseline; white-space: pre-wrap;">here</span></a><span style="font-size: 10.5pt; vertical-align: baseline; white-space: pre-wrap;">.</span></span></li>
	<li style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span><span style="font-size: 10.5pt; vertical-align: baseline; white-space: pre-wrap;"><span id="docs-internal-guid-06288ef3-7fff-2efa-1593-9155f517d85b"><span style="font-size: 10.5pt; vertical-align: baseline; white-space: pre-wrap;">Compile and build the following P4 binaries:</span></span></span></span>
	<ul>
		<li style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span id="docs-internal-guid-06288ef3-7fff-2efa-1593-9155f517d85b"><span style="font-size: 10.5pt; vertical-align: baseline; white-space: pre-wrap;">Run P4 switch - </span><span style="font-size: 10.5pt; font-style: italic; vertical-align: baseline; white-space: pre-wrap;">Baseline</span></span></li>
		<li style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span id="docs-internal-guid-06288ef3-7fff-2efa-1593-9155f517d85b"><span style="font-size: 10.5pt; vertical-align: baseline; white-space: pre-wrap;">Run P4 switch - </span><span style="font-size: 10.5pt; font-style: italic; vertical-align: baseline; white-space: pre-wrap;">Fast Path</span></span></li>
	</ul>
	</li>
	<li style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span><span style="font-size: 10.5pt; font-style: italic; vertical-align: baseline; white-space: pre-wrap;"><span id="docs-internal-guid-06288ef3-7fff-2efa-1593-9155f517d85b"><span style="font-size: 10.5pt; vertical-align: baseline; white-space: pre-wrap;">Repeat the above for the following experiment scenarios. Note that all settings below are for </span><span style="font-size: 10.5pt; font-style: italic; vertical-align: baseline; white-space: pre-wrap;">Circuit1</span><span style="font-size: 10.5pt; vertical-align: baseline; white-space: pre-wrap;"> where we artificially emulate a "Slow Path". </span><span style="font-size: 10.5pt; font-style: italic; vertical-align: baseline; white-space: pre-wrap;">Circuit2 </span><span style="font-size: 10.5pt; vertical-align: baseline; white-space: pre-wrap;">is a 10Gbps VLAN circuit.</span></span></span></span>
	<ul>
		<li style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span id="docs-internal-guid-06288ef3-7fff-2efa-1593-9155f517d85b"><span style="font-size: 10.5pt; vertical-align: baseline; white-space: pre-wrap;">Bandwidth =100Mbps, Delay=30ms</span></span></li>
		<li style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span id="docs-internal-guid-06288ef3-7fff-2efa-1593-9155f517d85b"><span style="font-size: 10.5pt; vertical-align: baseline; white-space: pre-wrap;">Bandwidth =100Mbps, Delay=90ms</span></span></li>
		<li style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span id="docs-internal-guid-06288ef3-7fff-2efa-1593-9155f517d85b"><span style="font-size: 10.5pt; vertical-align: baseline; white-space: pre-wrap;">Bandwidth =100Mbps, Delay=110ms</span></span></li>
		<li style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span id="docs-internal-guid-06288ef3-7fff-2efa-1593-9155f517d85b"><span style="font-size: 10.5pt; vertical-align: baseline; white-space: pre-wrap;">Bandwidth =100Mbps, Delay=30ms, Loss=0.05%</span></span></li>
	</ul>
	</li>
</ol>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: center;"><span id="docs-internal-guid-06288ef3-7fff-2efa-1593-9155f517d85b"><span style="font-size: 10.5pt; font-family: Arial; color: rgb(0, 0, 0); vertical-align: baseline; white-space: pre-wrap;"><img height="289" src="https://lh5.googleusercontent.com/ukje98ZvZGjI2fV_DaR5TzzK4Asyk9-6ZAElBJ0aDpR8T1HXtQ8FrsJFmxOBRg7DG6SnBPr-Fb-NFGoR4YGKrx8oegyGrhpVKjeGYZlalN9gda-aEHX-bgUJcR-eVpdTfVsLGeLM" style="" width="433"></span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span id="docs-internal-guid-06288ef3-7fff-2efa-1593-9155f517d85b"><span style="font-size: 10.5pt; font-family: Arial; color: rgb(0, 0, 0); vertical-align: baseline; white-space: pre-wrap;">The performance improvement here is a measure of the improvement over the corresponding </span><span style="font-size: 10.5pt; font-family: Arial; color: rgb(0, 0, 0); font-style: italic; vertical-align: baseline; white-space: pre-wrap;">Baseline</span><span style="font-size: 10.5pt; font-family: Arial; color: rgb(0, 0, 0); vertical-align: baseline; white-space: pre-wrap;"> case, where original and retransmitted ABR segments are transmitted on the same path versus the case where retransmitted segments are sent over a </span><span style="font-size: 10.5pt; font-family: Arial; color: rgb(0, 0, 0); font-style: italic; vertical-align: baseline; white-space: pre-wrap;">Fast Path</span><span style="font-size: 10.5pt; font-family: Arial; color: rgb(0, 0, 0); vertical-align: baseline; white-space: pre-wrap;">.</span></span></p>

<p> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span id="docs-internal-guid-06288ef3-7fff-2efa-1593-9155f517d85b"><span style="font-size: 10.5pt; font-family: Arial; color: rgb(0, 0, 0); vertical-align: baseline; white-space: pre-wrap;">Until the advent of technologies like P4, it was only possible to perform traffic engineering for headers between L2-L4. With the flexible parser and pipeline that P4 provides, we have seen that L5 application-level headers can be used for performing traffic engineering which can improve overall throughput by upto 70% in some cases and reduce delay by upto 50% while using a better path for ABR video segment retransmission.</span></span></p>

<div> </div>

<p> </p>