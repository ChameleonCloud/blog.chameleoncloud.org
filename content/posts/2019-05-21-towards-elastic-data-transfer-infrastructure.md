---
abstract: '<p><span id="docs-internal-guid-f43e6e2b-7fff-1f3e-df0b-d1811463b33f"><span
  style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color:
  transparent; vertical-align: baseline; white-space: pre-wrap;">Motivated by the
  opportunity to optimize the architecture of data transfer infrastructure, we recently
  prototyped an elastic architecture for data transfer on Chameleon Cloud in which
  the DTNs expand and shrink based on the demand...</span></span></p>'
authors:
- Joaquin Chung Miranda
categories:
- User Experiments
date: '2019-05-21 13:18:38+00:00'
featured: false
hide_image: true
image: ''
related_posts: []
slug: towards-elastic-data-transfer-infrastructure
subtitle: ''
title: Towards an Elastic Data Transfer Infrastructure
---

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-b5017596-7fff-75f8-b0be-68d8cbf59f52"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">Research Project Description</span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span id="docs-internal-guid-b5017596-7fff-75f8-b0be-68d8cbf59f52"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Data transfer over wide area network is an integral part of many science workflows. These workflows move data produced at experimental, observational and/or computational facilities to geographically distributed resources for analysis, sharing, and storing. Enhancements in the data transfer infrastructure of universities have improved the performance of data transfers for a number of users and science workflows. Despite these positive developments, our analyses of approximately 40 billion GridFTP command logs totaling 3.3 exabytes and 4.8 million transfers logs collected by the Globus transfer service from 2014/01/01 to 2018/01/01 show that data transfer nodes (DTNs) are completely idle (i.e., no transfers) 94.3% of the time, and 80% of the DTNs are active less than 6% of the time [1]. Motivated by the opportunity to optimize the architecture of data transfer infrastructure, we recently prototyped an elastic architecture for data transfer on Chameleon Cloud in which the DTNs expand and shrink based on the demand. Our architecture is composed of agents that monitor resource utilization at bare metal nodes and an orchestrator that decides when to provision/deprovision resources.</span></span></p>

<p> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: center;"><span id="docs-internal-guid-b5017596-7fff-75f8-b0be-68d8cbf59f52"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"><img src="https://lh4.googleusercontent.com/wxW5J1Hu4rnsQrZxchmueFimxx94-cK5E1AR8KosSioGjafnYlOPj-BW2KkpSS-Qtm_0CwATExt-W-nFCR3rSTu12I8U4sNEMvOoKx635cF7bSiqya6YyHsA58mXYb3xmZarouxA" width="624" style="border: none;" height="416"></span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: center;"><span id="docs-internal-guid-b5017596-7fff-75f8-b0be-68d8cbf59f52"><span style="font-size: 9pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; font-style: italic; vertical-align: baseline; white-space: pre-wrap;">Figure 1 - Elastic data transfer infrastructure (DTI) architecture</span></span></p>

<p> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-b5017596-7fff-75f8-b0be-68d8cbf59f52"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">Elastic Data Transfer Infrastructure (DTI) Prototype</span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span id="docs-internal-guid-b5017596-7fff-75f8-b0be-68d8cbf59f52"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">We realized an instantiation of our proposed elastic DTI in the bare metal infrastructure of the Chameleon testbed. Our prototype is composed of eight bare metal nodes with 48 cores Intel Xeon CPU E5-2670 v3 @ 2.30GHz and 128GB of RAM running Ubuntu 16.04.5 LTS. All nodes are connected to Chameleon’s shared LAN using 10 Gigabit Ethernet interfaces. For our experiments, four nodes work as server DTNs and the remaining four as client DTNs. We use Docker containers (version 18.09.0) as our virtual resources. All containers run Globus GridFTP server version 12.12 as the data transfer software. We use Globus URL Copy version 9.29 to launch client transfers.</span></span></p>

<p> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span id="docs-internal-guid-b5017596-7fff-75f8-b0be-68d8cbf59f52"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">We implemented the orchestrator and agents for our elastic DTI in Python and the communication between them using gRPC [2]. The agents collect CPU and network utilization statistics with a sampling frequency of one second. The orchestrator polls agents every second, computes thresholds, and decides whether a container needs to be provisioned or removed. Our initial experiments only use CPU usage to determine load and static thresholds to decide when to provision/deprovision resource. We did preliminary evaluations using a trace with transfers whose characteristics follow that of real datasets (both file size and dataset size) [1] and whose arrival times follow a Poisson distribution with ? = 3 seconds. We evaluated our elastic DTI using simple static thresholds, defined as percentages of average CPU utilization. We used three provisioning/deprovisioning schemes defined by a combination of high and low thresholds, and we used the “HIGH/LOW” notation for naming our schemes. We kept the low CPU usage threshold at 10% for each scheme and varied the high usage threshold as 30%, 50%, and 70%. </span></span></p>

<p> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span id="docs-internal-guid-b5017596-7fff-75f8-b0be-68d8cbf59f52"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">Preliminary Results</span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span id="docs-internal-guid-b5017596-7fff-75f8-b0be-68d8cbf59f52"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Initial results show that &gt;90% of the CPU resources can be saved when compared with a typical DTN deployment, with the slowdown incurred by around 50% of the transfers being compensated by speedups for an equal proportion of transfers. Figure 2 shows the distribution of bounded slowdown for different elastic DTI schemes compared with a typical DTN deployment baseline. We observe that the median slowdown of transfers in all scenarios is close to 1, which implies that roughly half the number of transfers has better performance than does the baseline and that the performance of the rest of the transfers is worse than baseline. Among the 50% of the transfers that performs poorly, half of the transfers have a slowdown less than 2X, and all of them have a slowdown less than 3X.</span></span></p>

<p> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: center;"><span id="docs-internal-guid-b5017596-7fff-75f8-b0be-68d8cbf59f52"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"><img src="https://lh4.googleusercontent.com/PJLYiss9FA0QK9FE_AoQrwhEk8F_M2FPHOksW66acsOJ40ufnFomUNiYQH5hSbrqxgre_DukQF4H4hIOfVn188Lcq6hCoxel5ZY-3N96iJwkqkcMQicFVPv7fUch-OAn9kC860s5" width="624" style="border: none;" height="384"></span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: center;"><span id="docs-internal-guid-b5017596-7fff-75f8-b0be-68d8cbf59f52"><span style="font-size: 9pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; font-style: italic; vertical-align: baseline; white-space: pre-wrap;">Figure 2 - Slowdown for several elastic DTI schemes with respect to baseline</span></span></p>

<p> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span id="docs-internal-guid-b5017596-7fff-75f8-b0be-68d8cbf59f52"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">References:</span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span id="docs-internal-guid-b5017596-7fff-75f8-b0be-68d8cbf59f52"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">[1] Zhengchun Liu, Rajkumar Kettimuthu, Ian Foster, and Nageswara S.V. Rao. Cross-geography scientific data transfer trends and user behavior patterns. In 27th ACM Symposium on High-Performance Parallel and Distributed Computing, HPDC ’18, New York, NY, USA, 2018. ACM.</span></span></p>

<p> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt; text-align: justify;"><span id="docs-internal-guid-b5017596-7fff-75f8-b0be-68d8cbf59f52"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">[2] gRPC. https://grpc.io/</span></span></p>

<div> </div>
