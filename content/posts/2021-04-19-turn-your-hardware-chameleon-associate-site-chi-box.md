---
abstract: <p>Do you have a research cluster with an inflexible interface? Does it
  not provide the level of access (root) you need to run repeatable experiments? Would
  you like a well-defined and easy way to contribute under-used resources to the community?
  Learn what it takes to set up a Chameleon associate site which will give you access
  to industry-standard APIs, best practices and automation to run a research testbed,
  and support from the Chameleon team for you and your users.</p>
authors:
- Michael Sherman
categories:
- Tips and Tricks
date: '2021-04-19 20:42:23+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/26/f3/26f3a8cc-ef56-4e5f-a637-3d9ef7d56496/chi-in-a-box.png
slug: turn-your-hardware-chameleon-associate-site-chi-box
subtitle: ''
title: Turn Your Hardware into a Chameleon Associate Site with CHI-in-a-Box
---

<p dir="ltr">Do you happen to have a research cluster, but users complain that the interface is inflexible, or it doesn’t provide the level of access (root) and isolation needed to run repeatable experiments? Or maybe you would like a well-defined and easy to implement way to contribute resources to the community at large when your users don’t need them. Or perhaps you are simply worried about the cost of setting up a research testbed from scratch – and then operating it for others.</p>

<p dir="ltr">Setting up a Chameleon Associate Site (potentially on a part-time basis) allows you to join a federation of testbed resources specifically designed to meet the Computer Science research use case. Chameleon Infrastructure (CHI) provides industry-standard APIs for interacting with resources, and provides best-practices and automation around running a research testbed, separate from just running a commodity cloud. Your users will have the same experience that they do at our other sites, being able to run the same experiments and use the same interfaces while the Chameleon team provides support both to you and your users.  </p>

<p> </p>

<h2 dir="ltr"><b id="docs-internal-guid-79a85a21-7fff-8799-e0d7-7797d8b6d214">What is an Associate Site?</b></h2>

<p dir="ltr">A Chameleon Associate Site can be thought of as a cloud “region” of Chameleon, running on your own hardware. It is federated with the users and groups of the larger Chameleon testbed and has access to a number of centralized resources, such as the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/jupyter.html">Chameleon shared Jupyter environment</a> and <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/ep.html">Experiment Precis</a> -- but it operates independently. The specific configuration and policy are largely determined by the site’s own needs and interests. An Associate Site can easily be configured by using the packaging of CHameleon Infrastructure called <a href="https://github.com/ChameleonCloud/chi-in-a-box#currently-included-with-chi-in-a-box">CHI-in-a-box</a>.</p>

<p dir="ltr">The smallest possible site might consist of a single management node, and a few compute nodes. However, the management node can also easily support several racks of nodes. Once your management node is up and running, bare-metal nodes can come and go as needed, depending on what you’re able to support allowing you to flexibly regulate the number of resources you contribute at any one time.</p>

<h2 dir="ltr"> </h2>

<h2 dir="ltr"><b id="docs-internal-guid-79a85a21-7fff-8799-e0d7-7797d8b6d214">What is CHI-in-a-box, anyway?</b></h2>

<p dir="ltr">Associate Sites are configured using a tool called CHI-in-a-box. CHI (pronounced like the “chee” in cheese) stands for “Chameleon Infrastructure” -- and it comes as a package (“box”), to make it easy for you to deploy.</p>

<p dir="ltr">Since CHI-in-a-box is used for managing the core sites as well as associate sites, it shares the same codebase and is kept up to date as we add features. It comes with sane defaults, a tested set of features, and tools to automate common operations tasks.</p>

<p dir="ltr">You can follow our step-by-step <a href="https://github.com/ChameleonCloud/chi-in-a-box/wiki/QuickStart">QuickStart Guide</a> to get a minimal site up and running, then add nodes and features incrementally as you go. During normal operations, a set of site-configurations are checked into source control, and deployed via ansible playbooks. This ensures that the configuration is repeatable and observable. Enrollment and modification of bare-metal nodes can be done via the openstack CLI interface, using the <a href="https://pypi.org/project/doniclient/">plugin for our inventory service</a>.</p>

<p dir="ltr">You can learn more about the experience of setting up an Associate Site in <a href="https://bit.ly/2M5pD4y">this interview</a> with the first CHI-in-a-box site set up at Northwestern University!</p>

<h2 dir="ltr"> </h2>

<h2 dir="ltr"><b id="docs-internal-guid-79a85a21-7fff-8799-e0d7-7797d8b6d214">What are the minimum Associate Site requirements?</b></h2>

<p dir="ltr">For operators, you’ll need a server to use as the management node, and ensure that your site meets our <a href="https://github.com/ChameleonCloud/chi-in-a-box/wiki/Installation-guide#installation-assumptions">installation assumptions</a>.</p>

<p dir="ltr">The management node should have 8gb of ram, 40gb of disk space, two physical network interfaces, one of which needs to be on a publicly routable network. The compute node can either run virtualization using KVM, or be a bare-metal node managed via IPMI.</p>

<p dir="ltr">For a larger site, it’s recommended to have 10gb/s or faster network interfaces on the management node, since it acts as a router for all tenant networks. We also recommend a dedicated interface for local administration of the management node. Additional storage, either within the management node, or external, is needed as the number of disk images grows.</p>

<p>Specific requirements are documented in our <a href="https://github.com/ChameleonCloud/chi-in-a-box/wiki/Hardware-requirements#management-nodes">Site Requirements Guide</a>.</p>

<p dir="ltr"> </p>

<h2 dir="ltr"><b id="docs-internal-guid-79a85a21-7fff-8799-e0d7-7797d8b6d214">What does a completed site look like?</b></h2>

<p dir="ltr">After setup is completed, your site will appear to the rest of the Chameleon testbed, with its resources on the Chameleon host calendar, which shows active reservations, with time on the horizontal axis, and nodes IDs on the vertical.</p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-79a85a21-7fff-8799-e0d7-7797d8b6d214"><img height="400" src="https://lh3.googleusercontent.com/Lnnp7z4eQauQNXnMOuWVfOUdfwti3qy7fcK8flKW8sdC9Y7UHrM0hTFcKs3nF-wQOjeMDfj8PMqD8kIPp_yT5FaVPZjXzvpvmqFAM9HPUnQziHgFGDbVcKYa4THsHPfnBHSdOxCX" width="549"></b></p>

<p> </p>

<p dir="ltr">Users will be able to access your site using their existing accounts through our federated login, and the Chameleon team will triage user support requests, and delegate to you on questions relating to your site configuration.</p>

<h2 dir="ltr"><b id="docs-internal-guid-79a85a21-7fff-8799-e0d7-7797d8b6d214">What does it take to build an associate site?</b></h2>

<p dir="ltr">Building a site consists of the following major steps:</p>

<ol>
	<li dir="ltr">
	<p dir="ltr">Plan site requirements, and gather information.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Provision a management node, and use that information to generate a site-config file.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Customize features and services on the management node according to your site’s needs.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Add compute nodes, or enroll bare-metal nodes for use.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">In the bare-metal use-case, configure vlan aware switches for management by the controller.</p>
	</li>
</ol>

<p> </p>

<p dir="ltr">A development setup can be built within a day, and we provide a <a href="http://www.chameleoncloud.org/experiment/share/35">QuickStart Notebook</a> to test it on top of Chameleon.</p>

<p dir="ltr">The rough time estimate to set up a production site depends on the scale of the planned site, and the completeness of information gathered. While the initial setup of the control node is mostly automated, there will be trial and error in customizing your site configuration, especially around networking, as so much is site-specific. If staff are familiar with OpenStack, the time spent in trial and error can be reduced as the requirements will be well understood.</p>

<p dir="ltr">To set up a medium sized production site,  a rough estimate of the time needed would be roughly two weeks of total effort: roughly a week for the management node and network and the rest for node configuration. The time spent on adding bare-metal nodes is mostly spent on physical racking and cabling, and scales with the size of the site. Once nodes are enrolled, significant automation is available for testing and maintenance.</p>

<h2 dir="ltr"><b id="docs-internal-guid-79a85a21-7fff-8799-e0d7-7797d8b6d214">How hard is it to run an Associate Site?</b></h2>

<p dir="ltr">CHI-in-a-Box takes advantage of our experience running Chameleon at several sites, with a diverse set of hardware and workloads, so that you don’t need to re-learn the same operational lessons.</p>

<p dir="ltr">Once operational, maintenance of the deployment primarily revolves around system upgrades and fixing occasional glitches. CHI-in-a-Box packaging includes operational tools called “<a href="https://github.com/chameleoncloud/hammers">Hammers</a>” -- bots that fix the testbed automatically -- and they should cover most known issues.</p>

<p dir="ltr">You will also be able to take advantage of the built-in alerting infrastructure (using Prometheus, Alertmanager, Grafana, and Kibana) , which will make dealing with many other issues such as hardware or deployment failures easy. Every alert comes with an actionable runbook to help the operator triage and identify the root cause of the failure. </p>

<p> </p>

<p dir="ltr" style="text-align: center;"><b><img height="253" src="https://lh4.googleusercontent.com/axjJd-86vLbg9ZiXfIdPY-jzHTukoOeA7yWQOGioRPW6ABQTkVG-pjxTBEeDfc3dMpKYgahggUIG6j62N9SlznF70LqQdq-09nYc0CJXH9rDS5mWS0KvG-xFFUDjJaWb2RB_Obcr" width="624"></b></p>

<p dir="ltr">The tooling provides a HA-ready setup using HAProxy/keepalived for redundancy, for when uptime is a primary concern (requires multi-node deployment) and automated backups of important data (Glance images, MySQL databases), for a better night's rest.</p>

<p dir="ltr">Since it integrates with Chameleon's existing user and allocation management system, it removes the need to operate your own user workflow, authentication, and authorization systems.</p>

<p dir="ltr">System upgrades are pushed out by the Chameleon team in the form of new releases to CHI-in-a-Box, which may come with new OpenStack service container images. The rollout of upgrades is automated, though requires a brief window of downtime (a conservative 2-4 hours is typical).</p>

<p dir="ltr">User support of resources contributed to Chameleon, as well as operations of shared services, such as Jupyter or creation and maintenance of images, are handled by the Chameleon team so all your operational effort is contained by operating the site and its resources. </p>

<h2 dir="ltr" style="text-align: center;"><b id="docs-internal-guid-79a85a21-7fff-8799-e0d7-7797d8b6d214"><img alt="chi-in-a-box" height="290" src="https://lh6.googleusercontent.com/t3NxxCRCu_iZxnvIPTj6Z0kB4ucOhojSm4whgF-EMZdkcz4JlccR087Rb9HloSGs8QN-p6mKuPBTQoMFAZUbbLhHcCSQNMIv6eIVNID0eiPEA8VuHe40CR8CwbXGvYjX6boFZU8i" width="290"></b></h2>

<h2 dir="ltr"><b id="docs-internal-guid-79a85a21-7fff-8799-e0d7-7797d8b6d214">I’m interested, now what?</b></h2>

<p dir="ltr">For starters, read through the repository for more information. We’ve tried to address common use cases, but we’re always interested to learn about more. If you’re interested in a feature that’s not described, it may be in the works. Letting us know helps us prioritize which features to focus on next. This is especially true if you’re able to contribute development time.</p>

<p dir="ltr">Whether you’re interested in setting up a full associate site, or using the infrastructure for your own, more independent use-case, please let us know! Send an email to <a href="mailto:contact@chameleoncloud.org">contact@chameleoncloud.org</a>.</p>