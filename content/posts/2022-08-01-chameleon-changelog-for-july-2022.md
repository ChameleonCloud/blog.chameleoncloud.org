---
abstract: "<p>This month, we are excited to announce integration with the Fabric testbed!\
  \ We also have updates to the filesystem, including support for it at CHI@TACC,\
  \ new nodes with CHI@UC with A100 GPUs and IceLake CPUs, and lots of usability improvements\
  \ to the testbed.<br>\n\_</p>"
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2022-08-01 20:12:45+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/c7/ca/c7ca3cba-f0f2-423a-b7ca-77940cc86f93/chameleon_fabric.png
slug: chameleon-changelog-for-july-2022
subtitle: ''
title: Chameleon Changelog for July 2022
---

<p><b id="docs-internal-guid-bcac9f20-7fff-6388-8a77-c17efc0294cd"><img height="95" src="https://lh4.googleusercontent.com/N3Wn63pn54e5RI24dJPEc78cCqfJ4VnxcV2OMme4cYrZNRqKx81mJ4g0aLjJkV5BjBGCJuezlhvj0TwtCpx7b9aL5FoB91XMb-0mk23D2xhHEGkG9C0dfhqDqKpYbj2zocBQPtSUO4cSWaXTkM7JEYo" width="624"></b></p>

<p>Dear Chameleon users,<br>
<br>
It’s another busy month on Chameleon, bringing a mix of new features and improvements to usability.</p>

<p><strong>Integration with FABRIC!</strong> We are happy to announce the completion of our initial integration with the <a href="https://fabric-testbed.net/">FABRIC networking testbed</a>. You can now create experiments spanning FABRIC and Chameleon that are “stitched” together with direct high-speed network connections. These multi-testbed experiments can be instantiated and controlled using a single Jupyter notebook. You can find examples of Jupyter multi-testbed experiment notebooks designed for both the Chameleon Jupyter environment (<a href="https://www.chameleoncloud.org/experiment/share/9284120f-3436-41f3-9e82-238e0628ec6c">Trovi artifact</a>) and the FABRIC Jupyter environment (<a href="https://github.com/fabric-testbed/jupyter-examples/blob/master/fabric_examples/complex_recipes/Chameleon_Facility_Port/Chameleon_Facility_Port.ipynb">pre-installed from github</a>), you can run them either way. Feel free to try these examples and incorporate them into your experiments. A FABRIC account and project is required and can be created on the <a href="https://portal.fabric-testbed.net/">FABRIC portal</a>. This is just the start of this collaboration, expect more examples and functionality to be released soon! And as always, if there are more specific features that would aid in your experiments, please let us know.</p>

<p><strong>New IceLake + A100 nodes at CHI@UC.</strong> The GPU nodes are some of the most utilized nodes on Chameleon. We’ve added 5 new GPU nodes at UC, each with 4x Nvidia A100 GPUs and Lake Intel Xeon 8380 CPUs. 4 of these nodes are PCIe based, while the 5th uses the higher wattage SXM form factor, with an NVLink interconnect.  You can <a href="https://chameleoncloud.org/hardware/">filter for these nodes</a> by gpu name, or by using the “node_type” of <em>gpu_a100</em>, or <em>gpu_a100_nvlink</em>.</p>

<p><strong>More about the Filesystem.</strong> <a href="https://bit.ly/3a9zani">Last month</a>, we announced a new shared filesystem service which allows you to mount a network share to your baremetal servers. To help you getting started, we have a Jupyter tutorial added to Trovi. This <a href="https://www.chameleoncloud.org/experiment/share/81af3cca-76cd-4a2e-83e1-3deb1fc7cf14">tutorial</a> explores how to create a share and access the share with a reserved storage network using <a href="https://python-chi.readthedocs.io/en/latest/index.html">python-chi</a>. That is to say, we added support for share service in our python-chi library. More exciting news: the filesystem service is now available at both CHI@UC and CHI@TACC!</p>

<p><strong>KVM artifact and python-chi support.</strong> Our python interface, python-chi, now has support for the KVM cloud at TACC. Among other, this means it is now easy to use our KVM cloud inside the Jupyter environment, a much requested feature. If you are unfamiliar with Chameleon’s KVM cloud, we’ve just posted a tips&amp;tricks <a href="https://chameleoncloud.org/blog/2022/07/19/experimenting-with-virtual-machines-on-chameleon/">blog</a> all about using KVM, and we showcase the python-chi support in with a new <a href="https://chameleoncloud.org/blog/2022/07/19/experimenting-with-virtual-machines-on-chameleon/">Trovi artifact</a>.</p>

<p><strong>Jupyter Notebook updates.</strong> As you may know, Jupyter servers spawned through our <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/jupyter.html">Jupyter interface</a> come pre-populated with some example notebooks that show how to set up Chameleon resources for different types of experiments. These notebooks recently got updated to show you the latest and most effective ways to manage your Chameleon resources via JupyterHub and the python-chi interface. You can see the updated notebooks <a href="https://github.com/ChameleonCloud/notebooks">here</a>. We also made similar updates to <a href="https://chameleoncloud.org/blog/2022/07/19/experimenting-with-virtual-machines-on-chameleon/">Chameleon-owned Trovi artifacts</a>.</p>

<p><strong>Usability improvements.</strong> Last month, we made it possible to reallocate a node in your lease if you are experiencing issues via the command line. Now, we’ve updated the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/reservations.html#reallocating-a-node-in-your-lease">web dashboard</a> to make this process as simple as possible on the lease detail page. The new host will have the same resource properties as the one it replaces, so you’ll be able to continue your experiments on it right away. Keep in mind, if you replace a malfunctioning node, please make sure to report it to the <a href="https://chameleoncloud.org/user/help/">help desk</a> so that we can fix it!</p>

<p><b id="docs-internal-guid-4ddc0a1f-7fff-e741-fed0-217df3a70ef9"><img height="170" src="https://lh5.googleusercontent.com/5zNTsXBVxOYyjf8uYW3nvtYLi0hWeeidQccZfAdcMajQaKOhB1jgDDwG-IekXyU5dWFrnWiwahny61gxd6aDCgkd3jJ46RRbYKuijwTbol_nPKxdUWHYzwJmGtQZg3_RLXh20n0yW6IDlBO481Uf_I4" width="607"></b><br>
Also, some of you reported that the error messages when using <a href="https://chameleoncloud.org/experiment/share/">Trovi</a> were not always informative – we updated them in both our portal and JupyterHub to make them easier to understand. </p>

<p><strong>Xena upgrades on associate sites.</strong> <a href="https://chameleoncloud.org/blog/2022/02/28/chincar-an-interview-with-the-newest-associate-site/">CHI@NCAR</a> has been updated to the Xena release, joining UC and TACC. CHI@NCAR’s site currently has ARM ThunderX2 nodes, making it the Chameleon site for you if you want to use ARM architecture.</p>

<p>That’s a lot of new things to try – happy experimenting! </p>