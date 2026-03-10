---
abstract: "<p>Chamaleon now supports isloated OpenFlow experiements controlled by\
  \ users.\_ This tips blog post shows you how to get started using OpenFlow on Chameleon.\_\
  </p>"
authors:
- Paul Ruth
categories:
- Tips and Tricks
date: '2018-08-17 16:57:09+00:00'
featured: false
hide_image: true
image: ''
slug: software-defined-networking-openflow-chameleon
subtitle: ''
title: Software Defined Networking with OpenFLow on Chameleon
---

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-85fbd57d-7fff-0b73-5de3-be68b47069c6"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Do you have a software-defined networking (SDN) experiment but do not have exclusive access to your own OpenFlow switch?  Or maybe you have an experiment with non-standard networking requirements that can not be supported by traditional learning switches.  If so, you might be interested in using Chameleon’s new Bring-Your-Own-Controller (BYOC) functionality. This new capability enables users, like you, to create and control your own exclusive OpenFlow switch that connect your Chameleon nodes.</span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-85fbd57d-7fff-0b73-5de3-be68b47069c6"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">BYOC is part of the expanded deployment for Chameleon’s phase 2. It enables tenants to allocate OpenFlow switches controlled by their own OpenFlow controller. This capability is limited to the phase 2 hardware additions that include the Corsa DP2000 series OpenFlow switches and Skylake compute nodes.  The Corsa switches allow for the creation of mutually isolated forwarding contexts that function as OpenFlow switches. Each forwarding context isolates traffic between users and connected to a user-defined OpenFlow controller residing within Chameleon or on an external host.</span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">The easiest way to get started working with OpenFlow on Chameleon is with the <a href="https://www.chameleoncloud.org/appliances/56/">OpenFlow: Quick Start Appliance</a>. This complex appliance can be used to create a full OpenFlow experiment including a Ryu OpenFlow controller, an OpenFlow network, and a couple of nodes that use the network.  Detailed directions are included with the appliance. Feel free to modify the code in the controller to manipulate the network switch.</span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<div dir="ltr" style="background: #eee; border: 1px solid #ccc; padding: 5px 10px;">
<p><span id="docs-internal-guid-85fbd57d-7fff-0b73-5de3-be68b47069c6"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Tip: Modify the Ryu OpenFlow controller by editing </span></span><span style="color: rgb(0, 0, 0); font-family: Arial; font-size: 14.6667px; white-space: pre-wrap;">simple_switch_13_custom_chameleon.py and r</span><span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">estarting the Ryu controller service.</span></span></p>

<p><span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">&gt; vim /opt/ryu/simple_switch_13_custom_chameleon.py</span></span></p>

<p><span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">&gt; systemctl restart ryu</span></span></p>
</div>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-85fbd57d-7fff-0b73-5de3-be68b47069c6"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">After gaining a bit of experience with the Quick Start Appliance you may want to incorporate OpenFlow into your own experiments.  You can create OpenFlow switches on Chameleon using either the CLI or a complex appliance (it is currently not possible to create OpenFlow switches using the horizon GUI directly).  Directions for using the CLI are documented <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/networks/networks_sdn.html#">here</a></span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">.  However, we recommend using a complex appliance to create your OpenFlow networks.</span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<div style="background: #eee; border: 1px solid #ccc; padding: 5px 10px;">
<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-85fbd57d-7fff-0b73-5de3-be68b47069c6"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Note: we recommend using complex appliances to create almost all experiment.  If you are not using <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/complex.html">complex appliances</a> then you should consider learning about them.</span></span></p>
</div>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-85fbd57d-7fff-0b73-5de3-be68b47069c6"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">We have provided a complex appliance that creates a basic OpenFlow network connected to an OpenFlow controller of your choice.  The <a href="https://www.chameleoncloud.org/appliances/58/">OpenFlow BYOC Network</a></span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"> appliance creates a network and the corresponding subnet and router to make it useful on Chameleon. You will, of course, need to have your own OpenFlow controller to make the network traffic flow.  Conveniently, you can use the <a href="https://www.chameleoncloud.org/appliances/54/">Ryu OpenFlow Controller</a> appliance</span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"> to run a controller on Chameleon. </span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<h2 dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;">Example</h2>

<p> </p>

<p>Step 1: Deploy an OpenFlow controller.  This example shows how to deploy the controler using the <a href="https://www.chameleoncloud.org/appliances/54/">complex appliance</a> mentioned above.  However, any OpenFlow controller can be used as long as it is accessible over the Internet. The parameters in the form should be set similar to what is in the image below.  The result will be an instance named "controller".  Note the floating IP of the controller instance.  The IP will be necessary to configure an OpenFlow network that connects to the controller.</p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/b7/44/b7448cb3-be2d-469d-8591-fe7222b5d4e4/ryu-stack.png" width="624"></p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/3a/4b/3a4b0a8f-91a0-4b79-bf85-38c78ac0c3e7/controllerinstance.png" width="624"></p>

<p>Step 2:  Create the network using the <span style="background-color: transparent; font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); vertical-align: baseline; white-space: pre-wrap;"><a href="https://www.chameleoncloud.org/appliances/58/">OpenFlow BYOC Network</a></span><span style="background-color: transparent; font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); vertical-align: baseline; white-space: pre-wrap;"> appliance. Fill in the stack's form with the IP and port number of your controller. The result of this stack will be a network that you can now use when creating new instances.</span></p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/c7/af/c7af1eb8-bee0-4d13-a230-5cdc36a19275/networkstack.png" width="624"></p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/12/77/1277409e-aecf-48df-8a5d-d5e44b623c10/network.png" width="624"></p>

<p>Step 3: Create new instances connected to the new network. Your new network will now be available and listed when you create new compute nodes.</p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/5d/76/5d7695eb-822f-4cf9-a3d5-a6c3358991f8/launchinstance.png" width="624"></p>

<h2>Special notes and warnings</h2>

<p><span style="color: rgb(0, 0, 0); font-family: Arial; font-size: 14.6667px; white-space: pre-wrap;">Interested users should be warned that all OpenFlow switches have their unique quirks and our Corsas are no exception. If you are having problems porting your controller to Chameleon, check the Chameleon documentation for a list of <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/networks/networks_sdn.html#controllers-for-corsa-dp2000-series-switches">quirks</a> that we have identified.</span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p><br>
<br>
 </p>