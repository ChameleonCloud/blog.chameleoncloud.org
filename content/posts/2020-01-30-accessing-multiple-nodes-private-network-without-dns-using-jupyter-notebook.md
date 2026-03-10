---
abstract: "A Jupyter notebook has been added to your Chameleon Jupyter Hub environment\
  \ to show how to automate deploying a server and several clients which are configured\
  \ with the\_names and IPs for every single other host in a custom isolated network.\
  \ Also included are examples of several tricks you might find useful for deploying\
  \ a complex experiment.<p></p>"
authors:
- Paul Ruth
categories:
- Tips and Tricks
date: '2020-01-30 19:40:59+00:00'
featured: false
hide_image: true
image: ''
slug: accessing-multiple-nodes-private-network-without-dns-using-jupyter-notebook
subtitle: ''
title: Accessing multiple nodes in a private network without DNS using Jupyter Notebook
---

<p>Authors: Paul Ruth and Mauricio Tavares</p>

Large distributed software systems often require domain name resolution so applications can refer to nodes by name (hostname) rather than IP address.  Typically this is achieved through Domain Name System (DNS). For temporal experiments it is more expedient to configure the /etc/hosts file in each node rather than deploying an additional node as the experiment’s DNS server. However, if the number of nodes increases past two, manually configuring each node and keeping track of the IPs and hostnames becomes geometrically time-consuming and prone to mistakes. <br>
 <p></p>

<p dir="ltr">A Jupyter notebook has been added to your Chameleon Jupyter Hub environment to show how to automate deploying a server and several clients which are configured with the names and IPs for every single other host in a custom isolated network. Also included are examples of several tricks you might find useful for deploying a complex experiment. <br>
 </p>

<p dir="ltr">In addition to showing how to configure /etc/hosts, this notebook presents useful command line (CLI) examples of:</p>

<ul>
	<li dir="ltr">
	<p dir="ltr">Creating leases with multiple reservations</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Reserving floating IPs</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Creating isolated networks</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Adding subnet and router to an isolated network so it can be accessed from outside</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Using SSH/SCP to create and upload node configurations.<br>
	 </p>
	</li>
</ul>

<p dir="ltr">The new Jupyter notebook is accessible at: <a href="https://jupyter.chameleoncloud.org/hub/user-redirect/lab/tree/notebooks/examples/configuration/UsingSSHToConfigureNameResolution.ipynb">https://jupyter.chameleoncloud.org/hub/user-redirect/lab/tree/notebooks/examples/configuration/UsingSSHToConfigureNameResolution.ipynb</a></p>

<p dir="ltr">We invite anyone interested in learning about these tips and tricks to run the notebook. </p>

<p> </p>