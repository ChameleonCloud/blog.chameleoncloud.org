---
abstract: '<p><span id="docs-internal-guid-0903c69c-7fff-e740-e194-9e0a756b8572"><span
  style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color:
  transparent; vertical-align: baseline; white-space: pre-wrap;">Ready-to-use Data
  Transfer Node (DTN) is provided, and it can be used to provide efficient network
  data transfer over a long fat network. In addition, </span></span><span id="docs-internal-guid-946c421d-7fff-0533-019c-6c0f7650f932"><span
  style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color:
  transparent; vertical-align: baseline; white-space: pre-wrap;">a Chameleon Complex
  Appliance is publish for easy spawning a set of DTNs in Chameleon Cloud.</span></span></p>'
authors:
- Se-young Yu
categories:
- User Experiments
date: '2018-10-19 14:46:46+00:00'
featured: false
hide_image: true
image: ''
related_posts: []
slug: transferring-large-data-flows-chameleon
subtitle: ''
title: Transferring Large Data Flows on Chameleon
---

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-11526616-7fff-e666-f694-d9689e18fe87"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Scientific research requires efficient transfer system for large data flows, including high-performance data movement in experimental cloud environments. Many different components that are involved in high-speed transfer such as the maximum TCP congestion window size, MTU, and NIC tx/rx ring sizes need to be tuned to achieve a high-speed network data transfer. Often, learning, setting up, and tuning the system and tools take the majority of the time for experimenters. Providing a optimized environment, tools for experiments, and reference performance results for researchers would assist them to be more productive.</span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-11526616-7fff-e666-f694-d9689e18fe87"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">We prepared a Data Transfer Node (DTN) that can be used to provide efficient network data transfer over a long fat network. <a href="https://www.chameleoncloud.org/appliances/50/"><strong>Chameleon Large Data Flow Appliance</strong></a> is a template for users to spawn a set of DTNs in Chameleon Cloud. Each ready-to-use DTN instance is carefully tuned to improve throughput for a large data flow, such as big data transfer and streaming. </span></span><span id="docs-internal-guid-11526616-7fff-e666-f694-d9689e18fe87"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">A <strong>DTN</strong> in Chameleon Cloud allows users to experiment with sharing a large dataset in scientific collaboration, developing transfer application for high-speed network and simulate various network environment in the cloud. </span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-11526616-7fff-e666-f694-d9689e18fe87"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">A useful use case is to experiment with network throughput and disk-to-disk transfer between DTN for measuring the performance. Users can execute an automated test for network and disk to measure disk I/O rate, available network capacity and end-to-end disk transfer performance between the optimized DTN. They can also emulate various delay, jitter, and packet loss in the network to simulate a specific network environment. Another use case is to test different file transfer protocols.</span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-11526616-7fff-e666-f694-d9689e18fe87"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">To do such testing, simply login to one of the DTN and enter the following command.</span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<div style="background: rgb(238, 238, 238); border: 1px solid rgb(204, 204, 204); padding: 5px 10px;">
<pre dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><code>cd Cham_LF_test
sudo ./set_network_delay.bash -s
./run_server.bas
</code></pre>
</div>

<p> </p>

<p><span id="docs-internal-guid-11526616-7fff-e666-f694-d9689e18fe87"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">After that, login to another DTN through the head node and enter</span></span></p>

<div style="background: rgb(238, 238, 238); border: 1px solid rgb(204, 204, 204); padding: 5px 10px;">
<pre dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><code>cd Cham_LF_test
</code>./run_test.bash IP_of_server</pre>
</div>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-11526616-7fff-e666-f694-d9689e18fe87"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">This will run a series of test, benchmarking disk speed and network speed of the DTNs with 30 ms delay and 3 ms jitter. The user can reset the network emulation using</span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<div style="background: rgb(238, 238, 238); border: 1px solid rgb(204, 204, 204); padding: 5px 10px;">
<pre dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><code>cd Cham_LF_test
sudo ./set_network_delay.bash -u</code>
</pre>
</div>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-11526616-7fff-e666-f694-d9689e18fe87"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">The set of tools and testers enable users to experiment with high-speed network and high-performance DTN in Chameleon Cloud. The users can build their own tool from the optimized DTN and test the performance.</span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><br>
 </p>

<p dir="ltr" style="line-height: 1.2; margin-top: 0pt; margin-bottom: 8pt;"><span id="docs-internal-guid-11526616-7fff-e666-f694-d9689e18fe87"><span style="font-size: 11pt; font-family: Arial; background-color: transparent; font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">Contribution Meta-Data:</span></span></p>

<p dir="ltr" style="line-height: 1.2; margin-top: 0pt; margin-bottom: 8pt;"><span id="docs-internal-guid-11526616-7fff-e666-f694-d9689e18fe87"><span style="font-size: 11pt; font-family: Arial; background-color: transparent; font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">Type of contribution:</span><span style="font-size: 11pt; font-family: Arial; background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"> Software/Chameleon appliance</span></span></p>

<p dir="ltr" style="line-height: 1.2; margin-top: 0pt; margin-bottom: 8pt;"><span id="docs-internal-guid-11526616-7fff-e666-f694-d9689e18fe87"><span style="font-size: 11pt; font-family: Arial; background-color: transparent; font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">Author(s)</span><span style="font-size: 11pt; font-family: Arial; background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">: Se-young Yu, Fei Yeh and Jim Chen</span></span></p>

<p dir="ltr" style="line-height: 1.2; margin-top: 0pt; margin-bottom: 8pt;"><span id="docs-internal-guid-11526616-7fff-e666-f694-d9689e18fe87"><span style="font-size: 11pt; font-family: Arial; background-color: transparent; font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">Link to code/repository: </span><span style="font-size: 11pt; font-family: Arial; background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"> <a href="https://www.chameleoncloud.org/appliances/50/">https://www.chameleoncloud.org/appliances/50/</a></span></span></p>

<p dir="ltr" style="line-height: 1.2; margin-top: 0pt; margin-bottom: 8pt;"><span id="docs-internal-guid-11526616-7fff-e666-f694-d9689e18fe87"><span style="font-size: 11pt; font-family: Arial; background-color: transparent; font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">License/terms of use: </span><span style="font-size: 11pt; font-family: Arial; background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"> GPL V2</span></span></p>

<p dir="ltr" style="line-height: 1.2; margin-top: 0pt; margin-bottom: 8pt;"><span id="docs-internal-guid-11526616-7fff-e666-f694-d9689e18fe87"><span style="font-size: 11pt; font-family: Arial; background-color: transparent; font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">Link to documentation:</span><span style="font-size: 11pt; font-family: Arial; background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"> <a href="https://www.chameleoncloud.org/appliances/50/docs/">https://www.chameleoncloud.org/appliances/50/docs/</a></span></span></p>

<p dir="ltr" style="line-height: 1.2; margin-top: 0pt; margin-bottom: 8pt;"><span id="docs-internal-guid-11526616-7fff-e666-f694-d9689e18fe87"><span style="font-size: 11pt; font-family: Arial; background-color: transparent; font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">Dependencies:</span><span style="font-size: 11pt; font-family: Arial; background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"> Python3, CC-Ubuntu16.04-20180413</span></span></p>

<p dir="ltr" style="line-height: 1.2; margin-top: 0pt; margin-bottom: 8pt;"><span id="docs-internal-guid-11526616-7fff-e666-f694-d9689e18fe87"><span style="font-size: 11pt; font-family: Arial; background-color: transparent; font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">Support email:</span><span style="font-size: 11pt; font-family: Arial; background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"> young.yu@northwestern.edu</span></span></p>

<p dir="ltr" style="line-height: 1.2; margin-top: 0pt; margin-bottom: 8pt;"><span id="docs-internal-guid-11526616-7fff-e666-f694-d9689e18fe87"><span style="font-size: 11pt; font-family: Arial; background-color: transparent; font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">Community contact: </span><span style="font-size: 11pt; font-family: Arial; background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">young.yu@northwestern.edu</span></span></p>

<p> </p>