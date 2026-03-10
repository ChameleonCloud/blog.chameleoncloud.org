---
abstract: <p>Discover the powerful updates in Python-chi 1.0, Chameleon's official
  Python library. This new release brings improved typing, new modules for hardware
  and storage management, interactive Jupyter widgets, clearer error messages, and
  easier low-level access. Learn how these enhancements can simplify your experiment
  workflow, from resource allocation to data analysis. Whether you're a seasoned Chameleon
  user or just getting started, Python-chi 1.0 offers tools to make your research
  more efficient and reproducible.</p>
authors:
- Mark Powers
categories:
- Tips and Tricks
date: '2024-10-21 19:07:30+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/ae/24/ae24a03c-284f-4642-91c3-af2405ea3c6c/python-chi-widget.png
slug: packaging-your-experiments-on-chameleon-with-python-chi-10
subtitle: Streamlining Chameleon Experiments with Enhanced Python Library
title: Packaging Your Experiments on Chameleon with Python-chi 1.0
---

<p>You're most likely already familiar with <a href="https://chameleoncloud.readthedocs.io/en/latest/user/help.html">the web dashboard</a> for using a Chameleon site or you prefer to use a <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/cli.html">CLI</a>. Each interface has its own advantages and disadvantages. While it's easy to get started with the GUI, sometimes it's helpful to be able to write a shell script that does everything for you automatically. However, there is yet another interface to Chameleon, <strong>Python-chi</strong>, our official Python library for the Chameleon Infrastructure (CHI) that pairs with JupyterHub. With the power of Python-chi, you can easily write scripts to dynamically manage testbed resources.</p>

<p>Recently, we released <a href="https://python-chi.readthedocs.io/en/latest/">Python-chi version 1.0</a>, which was updated to include in-demand improvements based on feedback from our users. These changes include:</p>

<p><strong>Improved typing</strong> - Before, our Python-chi methods were closely using the lower level OpenStack functions. These work differently for each service type, so making reservations returned dictionaries but creating an instance returned objects. Now, we've defined our own consistent Python types. This makes it much easier to put together a working script <a href="https://python-chi.readthedocs.io/en/latest/">from the documentation</a> rather than having to copy and paste from existing snippets, and you can more easily use auto-complete tools.</p>

<p><strong>New modules</strong> - We added some new modules for important Chameleon services. The most interesting addition is the <a href="https://python-chi.readthedocs.io/en/latest/modules/hardware.html">hardware module</a>, which allows you to query the hardware browser and availability calendar together. For example, this would allow you to find nodes available immediately with a GPU, which you could pass directly into a new lease. There is also the new <a href="https://python-chi.readthedocs.io/en/latest/modules/storage.html">storage module</a>, which lets you use both the shared file system and the object store.</p>

<p><strong>New widgets</strong> - One advantage of using Jupyter is the ability for a rich user interface. To improve the experience of using Python-chi in Jupyter, we've added brand new widgets. These include dropdown selectors for choosing a project and site, progress bars while waiting for leases and instances, and tables to display information about your resources. Not only are these nicer to look at than code, but they also help validate inputs – no more typos entering your project number!</p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/ae/24/ae24a03c-284f-4642-91c3-af2405ea3c6c/python-chi-widget.png"></p>

<p><strong>Updated error messages</strong> - Errors on Chameleon can be confusing if you are unfamiliar with some of the internals of the testbed. We've updated Python-chi to <a href="https://python-chi.readthedocs.io/en/latest/modules/exception.html">differentiate types of errors</a>: value errors, which are similar to 4xx HTTP codes, would indicate there is something wrong with the submitted request, such as a typo in the site name or node type. Resource errors indicate that requests are valid, but resources cannot be used as requested, such as your project having insufficient SUs, or nodes matching your reservation being unavailable. Lastly, we define service errors, similar to 5xx HTTP codes, indicating an unexpected error occurred, such as hardware failure with a node.</p>

<p><strong>Easier low-level access</strong> - As you may know, Chameleon is built on OpenStack, which is the software that powers our cloud services. Python-chi is aimed to support 95% of Chameleon experiment workflows, but with the power of OpenStack, there is much more configuration you can do at a lower level. We've made it easier to switch from using our high-level Python-chi context to the OpenStack Python context via the <a href="https://python-chi.readthedocs.io/en/latest/modules/clients.html">client's module</a>, including documentation for how to use each client. This may help with less common uses of Chameleon's resources, such as with <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm.html#load-balancer-as-a-service">Load Balancer as a Service</a> or <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/networks.html">advanced networking</a>.</p>

<p>If you want to get started with Python-chi 1.0, a great place to start is the <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/50692573-4094-466c-b4fe-0ed3471f8993">updated Bare Metal Experiment Pattern Trovi Artifact (GitHub)</a>. This new notebook demonstrates how streamlined Python-chi 1.0 can be. We call this example an "experiment pattern," as we hope that it is mainly applicable as a basis for your experiment. To get started with this pattern, we recommend <a href="https://github.com/ChameleonCloud/bare_metal_experiment_pattern/fork">forking the GitHub repo</a> and after committing any changes, <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/sharing.html#importing-an-artifact">importing the artifact to Trovi via Git</a>. We've split the experiment process into five steps:</p>

<p>1. Query resources and make a lease.<br>
2. Provision a single node<br>
3. Copy experiment files and install dependencies<br>
4. Run the experiment and upload the data<br>
5. Analyze data</p>

<p>If your experiment is already on GitHub and requires a single bare metal node, you'll be able to jump to step 3 to point to your repository and potentially update the names of the setup scripts. If there are specific requirements for the type of node your experiment runs on, you can update the <a href="https://python-chi.readthedocs.io/en/latest/modules/hardware.html#chi.hardware.get_nodes">hardware query</a> in step 1. You will also need to adapt the experiment execution and analysis steps 4 and 5, but we hope that our example will be a helpful starting point. For more complex experiment topologies, we encourage you to <a href="https://python-chi.readthedocs.io/en/latest/modules/server.html#chi.server.Server">check out our documentation</a>.</p>

<p>As always, if you have any questions or feedback, we are available via <a href="https://chameleoncloud.org/user/help/ticket/new/guest/">the Help Desk</a>.</p>