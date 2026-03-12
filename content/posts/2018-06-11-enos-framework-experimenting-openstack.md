---
abstract: "<p>ENOS is\_an\_integrated framework that facilitates experimenting with\_\
  OpenStack. ENOS allows researchers to easily\_express different configurations,\
  \ enabling fine-grained investigations of\_OpenStack services. ENOS collects performance\
  \ metrics at runtime and stores\_them for post-mortem analysis and sharing.</p>"
authors:
- Matthieu Simonin
categories:
- User Experiments
date: '2018-06-11 22:35:51+00:00'
featured: false
hide_image: true
image: ''
related_posts: []
slug: enos-framework-experimenting-openstack
subtitle: ''
title: 'ENOS: a Framework for Experimenting with OpenStack'
---

<p>OpenStack growth has been impressive over the last past years. It has now a huge codebase and a large community supporting it. However, with the success comes an increased complexity, and both users and developpers are in great difficulty when testing the impact of individual changes on the overall performance. Diving into complex software such as OpenStack is tedious: reliable tools are necessary to ease the efforts of our community and make science as collaborative as possible.</p>

<p>In this spirit, we developed ENOS [1,2,3,4], an integrated framework that relies on container technologies for deploying and evaluating OpenStack on several testbeds. ENOS allows researchers to easily express different configurations, enabling fine-grained investigations of OpenStack services. ENOS collects performance metrics at runtime and stores them for post-mortem analysis and sharing.</p>

<p>From a highlevel point of view, a typical worklow using ENOS is as simple as the following:</p>

<div style="background: #eee; border: 1px solid #ccc; padding: 5px 10px;"> enos deploy<br>
 enos bench<br>
 enos backup</div>

<p>The deployment can target several infrastructures including Chameleon Cloud for large experiments or local deployments for development purposes.</p>

<p>For example, to deploy a basic multiple nodes OpenStack cloud you can install enos from pypi, configure it to use Chameleon[5] and launch `enos deploy`. A lease will be  created automatically and the required machines will be provisioned automatically. The above has to be performed from a service node that can be either a dedicated Chameleon machine or your local machine.</p>

<p>ENOS allows for different customizations including changes in the topology of the services, or alternative configurations. Several benchmarking tools are included in ENOS like Rally [6] for control plane testing, Shaker [7] for data plane testing and OSProfiler [8] for profiling. System metrics are collected and exposed and query-able using Grafana [9] and InfluxDB [10]. Metrics and benchmarks reports are available for post-mortem analysis thanks to the backup performed by ENOS.</p>

<p>ENOS has been used in various evaluation of OpenStack presented in several OpenStack related events  [11,12, 13]. Everyone is welcome to contribute by submitting patches, reporting issues or simply come and talk on gitter[14].</p>

<p><em>The author would like to thank Adrien Lebre for his contributions to this post and Ronan-Alexandre Cherrueau for his much valued work on EnOS.</em></p>

<p><strong>Contribution Meta-Data:</strong></p>

<p><strong>Type of contribution:</strong> software<br>
<strong>Author(s)</strong>: Ronan-Alexandre Cherrueau / Matthieu Simonin<br>
<strong>Link to code/repository: </strong> <a href="https://github.com/BeyondTheClouds/enos">https://github.com/BeyondTheClouds/enos</a><br>
<strong>License/terms of use: </strong> GPL V3<br>
<strong>Link to documentation:</strong> <a href="https://enos.readthedocs.io/">https://enos.readthedocs.io/</a><br>
<strong>Dependencies:</strong> Ansible / Docker<br>
<strong>Support email:</strong> discovery-contact@inria.fr<br>
<strong>Community contact:</strong></p>

<p><a href="https://gitter.im/BeyondTheClouds/enos?utm_source=badge&amp;utm_medium=badge&amp;utm_campaign=pr-badge&amp;utm_content=badge">https://gitter.im/BeyondTheClouds/enosutm_source=badge&amp;utm_medium=badge&amp;utm_campaign=pr-badge&amp;utm_content=badge</a></p>

<p>References:</p>

<p>[1]: <a href="https://ieeexplore.ieee.org/document/7973741/">https://ieeexplore.ieee.org/document/7973741/</a><br>
[2]: <a href="https://hal.inria.fr/hal-01415522">https://hal.inria.fr/hal-01415522</a><br>
[3]: <a href="https://enos.readthedocs.io/">https://enos.readthedocs.io/</a><br>
[4]: <a href="https://github.com/BeyondTheClouds/enos">https://github.com/BeyondTheClouds/enos</a><br>
[5]: <a href="https://enos.readthedocs.io/en/stable/provider/openstack.html#chameleon-cloud-bare-metal">https://enos.readthedocs.io/en/stable/provider/openstack.html#chameleon-cloud-bare-metal</a><br>
[6]: <a href="https://rally.readthedocs.io/">https://rally.readthedocs.io/</a><br>
[7]: <a href="https://pyshaker.readthedocs.io/">https://pyshaker.readthedocs.io/</a><br>
[8]: <a href="https://docs.openstack.org/osprofiler">https://docs.openstack.org/osprofiler</a><br>
[9]: <a href="https://grafana.com">https://grafana.com</a><br>
[10]: <a href="https://www.influxdata.com">https://www.influxdata.com</a><br>
[11]: <a href="https://www.openstack.org/videos/barcelona-2016/chasing-1000-nodes-scale">https://www.openstack.org/videos/barcelona-2016/chasing-1000-nodes-scale</a><br>
[12]: <a href="https://www.openstack.org/videos/boston-2017/toward-fog-edge-and-nfv-deployments-evaluating-openstack-wanwide">https://www.openstack.org/videos/boston-2017/toward-fog-edge-and-nfv-deployments-evaluating-openstack-wanwide</a><br>
[13]: <a href="https://www.openstack.org/videos/sydney-2017/reproducible-performance-evaluations-of-different-openstack-deployments-with-enos">https://www.openstack.org/videos/sydney-2017/reproducible-performance-evaluations-of-different-openstack-deployments-with-enos</a><br>
[14]: <a href="https://gitter.im/BeyondTheClouds/enos">https://gitter.im/BeyondTheClouds/enos</a></p>