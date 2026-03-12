---
abstract: "<p dir=\"ltr\" style=\"line-height: 1.38; margin-top: 0pt; margin-bottom:\
  \ 0pt;\">\_</p>\n\n<p dir=\"ltr\" style=\"font-size: 13px; line-height: 1.38; margin-top:\
  \ 0pt; margin-bottom: 0pt;\"><span id=\"docs-internal-guid-8fa9872c-f47e-13ab-47ef-190c64d5c1dc\"\
  ><span style=\"font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color:\
  \ transparent; vertical-align: baseline; white-space: pre-wrap;\">Did you ever wonder\
  \ how much power was consumed by executing a program? The Chameleon team recently\
  \ implemented a feature that automatically collects power usage data on all low\
  \ power nodes in the system. Instantaneous power usage data (in watts) are collected\
  \ through the IPMI interface on the chassis controller for the nodes. This \u201C\
  out-of-band\u201D approach does not consume additional power on the node itself\
  \ and runs even when the node is powered off. Low power nodes for which power usage\
  \ data are now being collected include all Intel Atoms, low power Xeons, and ARM64s.\
  \ In this blog post we look at this new feature and use it to calculate the power\
  \ consumption associated with </span></span><span style=\"color: rgb(0, 0, 0); font-family:\
  \ Arial; font-size: 14.6667px; white-space: pre-wrap;\">multiplying two large Python\
  \ numpy arrays.</span></p>\n\n<div>\_</div>"
authors:
- Joe Stubbs
categories:
- Tips and Tricks
date: '2018-06-22 19:58:06+00:00'
featured: false
hide_image: true
image: ''
related_posts: []
slug: monitoring-power-consumption-low-power-nodes
subtitle: ''
title: 'Power to People: Monitoring Power Consumption of Low Power Nodes'
---

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-8fa9872c-f47e-13ab-47ef-190c64d5c1dc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">Summary</span></span></p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-8fa9872c-f47e-13ab-47ef-190c64d5c1dc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Did you ever wonder how much power was consumed by executing a program? The Chameleon team recently implemented a feature that automatically collects power usage data on all low power nodes in the system. Instantaneous power usage data (in watts) are collected through the IPMI interface on the chassis controller for the nodes. This “out-of-band” approach does not consume additional power on the node itself and runs even when the node is powered off. Low power nodes for which power usage data are now being collected include all Intel Atoms, low power Xeons, and ARM64s. In this blog post we look at this new feature and use it to calculate the power consumption associated with </span></span><span style="color: rgb(0, 0, 0); font-family: Arial; font-size: 14.6667px; white-space: pre-wrap;">multiplying two large Python numpy arrays.</span></p>

<div style="font-size: 13px;"> </div>

<p style="font-size: 13px;"><span id="docs-internal-guid-8fa9872c-f47e-13ab-47ef-190c64d5c1dc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">Pre-requisites </span></span></p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-8fa9872c-f47e-13ab-47ef-190c64d5c1dc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">To illustrate the power monitoring feature, we assume we have reserved a low-power Atom node and installed the CLI and metrics plugins (for instructions on how to reserve a node, see <a href="http://chameleoncloud.readthedocs.io/en/latest/technical/reservations.html">Reservations</a></span></span>; <span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">for installation instructions, see the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/metrics.html">Metrics</a> ddocumentation. </span></p>

<p style="font-size: 13px;"> </p>

<p style="font-size: 13px;"><span id="docs-internal-guid-8fa9872c-f47e-13ab-47ef-190c64d5c1dc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">Getting Power Data for an Instance</span></span></p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-8fa9872c-f47e-13ab-47ef-190c64d5c1dc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">To retrieve power data for a specific low power node, nothing needs to be configured on the node: all we need is the node’s UUID and the Chameleon command line interface (CLI). Once you have an instance reserved, retrieve the corresponding node UUID (not the instance UUID) by selecting your lease from the Lease tab on CHI@TACC: </span></span></p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-8fa9872c-f47e-13ab-47ef-190c64d5c1dc"><a href="https://chi.tacc.chameleoncloud.org/dashboard/project/leases/"><span style="font-size: 11pt; font-family: Arial; color: rgb(17, 85, 204); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">https://chi.tacc.chameleoncloud.org/dashboard/project/leases/</span></a></span></p>

<p style="font-size: 13px;"> </p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-8fa9872c-f47e-13ab-47ef-190c64d5c1dc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">The node ID is displayed at the bottom of the Lease Details page under “Nodes”</span></span></p>

<p style="font-size: 13px;"> </p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-8fa9872c-f47e-13ab-47ef-190c64d5c1dc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"><img src="https://lh6.googleusercontent.com/Qq32Bb6LxWVyZkgsot0CGhe457mmIu_AmElszbnMhQhJ-mgx6u6eu_oP6KT5feuI2Ul6UWcnS5W24kccPUPT14Hcu8MTaTHVYF-zQsmdzsblnQMTevVr2ccJ-kfqnm2UzNFoiT4Y" width="624" height="539"></span></span></p>

<p style="font-size: 13px;"> </p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-8fa9872c-f47e-13ab-47ef-190c64d5c1dc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">From the screenshot above, the node ID for my node can be seen to be <code>05dd5e25-440f-4492-b3b8-9d39af83b8bc</code></span></span></p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-8fa9872c-f47e-13ab-47ef-190c64d5c1dc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Once we have identified the UUID of the node, we can start retrieving power consumption data using the CLI. The basic command is:</span></span></p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-indent: 36pt;"><span id="docs-internal-guid-8fa9872c-f47e-13ab-47ef-190c64d5c1dc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; font-style: italic; vertical-align: baseline; white-space: pre-wrap;">$ openstack metric measures show power --resource-id=&lt;node_uuid&gt; --refresh</span></span></p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-indent: 36pt;"> </p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">*Note: in an effort to preserve computing resources, the metrics API does not always make the most recent metrics available in its responses. In order to ensure the </span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; font-style: italic; vertical-align: baseline; white-space: pre-wrap;">show power</span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"> command retrieves the very latest data, pass the </span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; font-style: italic; vertical-align: baseline; white-space: pre-wrap;">--refresh</span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"> command. We recommend always passing the --</span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; font-style: italic; vertical-align: baseline; white-space: pre-wrap;">refresh</span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"> option, at least the first time a query is issued. In a future release, we plan to make all metrics data immediately available which will make the </span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; font-style: italic; vertical-align: baseline; white-space: pre-wrap;">--refresh </span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">option unnecessary.</span></p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-8fa9872c-f47e-13ab-47ef-190c64d5c1dc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">For general information on using the OpenStack CLI to collect metrics, see the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/metrics.html">documentation</a>.</span></span></p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="background-color: transparent; color: rgb(0, 0, 0); font-family: Arial; font-size: 11pt; white-space: pre-wrap;">Let’s look at power consumption right before our reservation started.</span></p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><code><span style="font-size: 13px;">$ openstack metric measures show power --start 2018-05-14T14:35:00 --stop 2018-05-14T14:55:00 --resource-id=$uuid --refresh"</span></code></p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><code>+---------------------------+----------------+---------------------------------+<br>
| timestamp                 | granularity    | value                           |<br>
+---------------------------+----------------+---------------------------------+<br>
| 2018-05-14T14:00:00-05:00 |      3600.0    | 3.04133333333                   |<br>
| 2018-05-14T14:38:00-05:00 |        60.0    | 3.075                           |<br>
| 2018-05-14T14:40:00-05:00 |        60.0    | 2.988                           |<br>
| 2018-05-14T14:38:29-05:00 |         1.0    | 3.075                           |<br>
| 2018-05-14T14:40:49-05:00 |         1.0    | 2.988                           |<br>
+---------------------------+-------------+------------------------------------+</code></p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-8fa9872c-f47e-13ab-47ef-190c64d5c1dc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">We see the power consumption was right at 3W even though the node was not in use. That’s actually expected because the node uses some power even when the CPU is not running.</span></span></p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-8fa9872c-f47e-13ab-47ef-190c64d5c1dc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">What power consumption was required to boot the node? Let’s retrieve the power consumption data points for a 45 minute interval, starting about 15 minutes before we launched the instance.</span></span></p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p style="font-size: 13px;"><code>$ openstack metric measures show power --start 2018-05-14T14:30:00-00:00 --stop 2018-05-14T15:20:00-00:00 --resource-id=$uuid --refresh</code></p>

<p style="font-size: 13px;"><code>+---------------------------+-------------+--------------------+<br>
| timestamp                 | granularity | value              |<br>
+---------------------------+-------------+--------------------+<br>
| 2018-05-14T14:30:00-05:00 |        60.0 | 3.075              |<br>
| 2018-05-14T14:32:00-05:00 |        60.0 | 3.0315             |<br>
| 2018-05-14T14:38:00-05:00 |        60.0 | 3.075              |<br>
| 2018-05-14T14:40:00-05:00 |        60.0 | 2.988              |<br>
| 2018-05-14T14:42:00-05:00 |        60.0 | 3.075              |<br>
| 2018-05-14T14:43:00-05:00 |        60.0 | 3.074              |<br>
| 2018-05-14T14:44:00-05:00 |        60.0 | 2.914              |<br>
| 2018-05-14T14:45:00-05:00 |        60.0 | 2.84               |<br>
| 2018-05-14T14:46:00-05:00 |        60.0 | 8.7165             |<br>
| 2018-05-14T14:47:00-05:00 |        60.0 | 8.752              |<br>
| 2018-05-14T14:48:00-05:00 |        60.0 | 8.839              |<br>
| 2018-05-14T14:53:00-05:00 |        60.0 | 12.979             |<br>
| 2018-05-14T14:54:00-05:00 |        60.0 | 7.723              |<br>
| 2018-05-14T14:57:00-05:00 |        60.0 | 12.52              |<br>
| 2018-05-14T14:58:00-05:00 |        60.0 | 13.562             |<br>
| 2018-05-14T14:59:00-05:00 |        60.0 | 9.062              |<br>
| 2018-05-14T15:00:00-05:00 |        60.0 | 9.372              |<br>
| 2018-05-14T15:01:00-05:00 |        60.0 | 8.752              |<br>
| 2018-05-14T15:02:00-05:00 |        60.0 | 8.913              |<br>
| 2018-05-14T15:03:00-05:00 |        60.0 | 8.9065             |<br>
| 2018-05-14T15:04:00-05:00 |        60.0 | 8.603              |<br>
| 2018-05-14T15:08:00-05:00 |        60.0 | 8.913              |<br>
| 2018-05-14T15:10:00-05:00 |        60.0 | 8.677              |<br>
| 2018-05-14T15:14:00-05:00 |        60.0 | 8.839              |<br>
| 2018-05-14T15:15:00-05:00 |        60.0 | 8.913              |<br>
| 2018-05-14T15:17:00-05:00 |        60.0 | 8.8795             |<br>
| 2018-05-14T15:18:00-05:00 |        60.0 | 9.065              |<br>
+---------------------------+-------------+--------------------+</code></p>

<p style="font-size: 13px;"> </p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-8fa9872c-f47e-13ab-47ef-190c64d5c1dc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">The following plot shows the power consumption as a function of time. We see power consumption ramping up while the node is powering on until it reaches a steady state of about 9W.</span></span></p>

<div style="font-size: 13px;"> </div>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-8fa9872c-f47e-13ab-47ef-190c64d5c1dc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"><img src="https://lh3.googleusercontent.com/boez0ttxpx9rM0t0-2ADD29ep2EAgX9r0TF3WpSeWZ0tHfGWxwo3BW9MbmUWQYGM2su2mfh-H4X4GqzzvDhufKno89Kp3mFjMnG2tHuaqD-K3VTfBBXY9AHlsQnw8mwHRjsW8q_U" width="432" height="258"></span></span></p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-8fa9872c-f47e-13ab-47ef-190c64d5c1dc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Finally, let us SSH to the node and run some computation. We’ll use Python’s numpy library to multiply two large matrices. While it is running, we will check resource consumption, and after it is done, we will compare that with power consumption. </span></span></p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Here is a basic Python function to multiply two numpy arrays of a fixed size. </span></p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><code>In [1]: import numpy as np<br>
In [2]: def f(std_dev, size):<br>
  ...:     A = np.random.normal(0, std_dev, (size, size))<br>
  ...:     B = np.random.normal(0, std_dev, (size, size))<br>
  ...:     C = np.dot(A, B)<br>
  ...:     return C[0]<br>
In [3]: for i in range(20):<br>
  ...:     f(100, 8138)</code></p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span style="color: rgb(0, 0, 0); font-family: Arial; font-size: 14.6667px; white-space: pre-wrap;">After running the code above, l</span><span style="color: rgb(0, 0, 0); font-family: Arial; font-size: 14.6667px; white-space: pre-wrap;">et's retrieve and plot the associated power consumption data.</span></p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><code>$ openstack metric measures show power --start 2018-05-14T18:04:00 --stop 2018-05-14T18:33:00 --resource-id=$uuid --refresh<br>
+---------------------------+-------------+-------------------+<br>
| timestamp                 | granularity | value             |<br>
+---------------------------+-------------+-------------------+<br>
| 2018-05-14T18:04:00-05:00 |        60.0 | 8.952             |<br>
| 2018-05-14T18:04:10-05:00 |         1.0 | 8.842             |<br>
| 2018-05-14T18:04:49-05:00 |         1.0 | 9.062             |<br>
| 2018-05-14T18:07:00-05:00 |        60.0 | 9.607             |<br>
| 2018-05-14T18:07:50-05:00 |         1.0 | 9.607             |<br>
| 2018-05-14T18:09:00-05:00 |        60.0 | 12.062            |<br>
| 2018-05-14T18:09:29-05:00 |         1.0 | 12.062            |<br>
| 2018-05-14T18:12:00-05:00 |        60.0 | 25.8905           |<br>
| 2018-05-14T18:12:29-05:00 |         1.0 | 25.748            |<br>
| 2018-05-14T18:12:50-05:00 |         1.0 | 26.033            |<br>
| 2018-05-14T18:14:00-05:00 |        60.0 | 25.822            |<br>
| 2018-05-14T18:14:50-05:00 |         1.0 | 25.822            |<br>
| 2018-05-14T18:17:00-05:00 |        60.0 | 28.115            |<br>
| 2018-05-14T18:17:10-05:00 |         1.0 | 28.115            |<br>
| 2018-05-14T18:20:00-05:00 |        60.0 | 27.5486666667     |<br>
| 2018-05-14T18:20:10-05:00 |         1.0 | 28.189            |<br>
| 2018-05-14T18:20:29-05:00 |         1.0 | 28.189            |<br>
| 2018-05-14T18:20:49-05:00 |         1.0 | 26.268            |<br>
| 2018-05-14T18:24:00-05:00 |        60.0 | 24.658            |<br>
| 2018-05-14T18:25:00-05:00 |        60.0 | 27.954            |<br>
| 2018-05-14T18:26:00-05:00 |        60.0 | 28.115            |<br>
| 2018-05-14T18:28:00-05:00 |        60.0 | 26.9995           |<br>
| 2018-05-14T18:24:29-05:00 |         1.0 | 24.658            |<br>
| 2018-05-14T18:25:29-05:00 |         1.0 | 27.954            |<br>
| 2018-05-14T18:26:10-05:00 |         1.0 | 28.115            |<br>
| 2018-05-14T18:28:10-05:00 |         1.0 | 25.884            |<br>
| 2018-05-14T18:28:29-05:00 |         1.0 | 28.115            |<br>
| 2018-05-14T18:30:00-05:00 |        60.0 | 9.136             |<br>
| 2018-05-14T18:30:29-05:00 |         1.0 | 9.136             |<br>
+---------------------------+-------------+-------------------+</code></p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-8fa9872c-f47e-13ab-47ef-190c64d5c1dc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"><img src="https://lh5.googleusercontent.com/qWxzN2Bd0jjUo5Vdx-g457-zXJ9jaFktXuMGc_rgv41mDzaaeXAGCrA8_LFZQ2Ty-scK7mI-toHgCT2dHmc5X_yyoehwoVt1pa8kRyYv1aibfFjdGLef76K3jJqUOEuIR2Miv_xY" width="453" height="253"></span></span></p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="font-size: 13px; line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-8fa9872c-f47e-13ab-47ef-190c64d5c1dc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">We can see that multiplying large matrices consumed between 25 and 27.5 W.</span></span></p>

<div> </div>
