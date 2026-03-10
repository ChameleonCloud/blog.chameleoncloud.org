---
abstract: <p>This month we celebrated 9 years of Chameleon, and shared the exciting
  news of Chameleon Phase 4! We also completed the openstack upgrade at CHI@UC, updated
  the Getting Started, and released a dev version of python-chi.</p>
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2024-08-02 00:02:07+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/aa/97/aa97bd88-c227-47ef-bcd3-8d6a4ef42551/chameleon9.png
slug: chameleon-changelog-for-july-2024
subtitle: ''
title: Chameleon Changelog for July 2024
---

<p style="text-align: center;"><img height="500" media="" src="https://chameleoncloud.org/media/filer_public/aa/97/aa97bd88-c227-47ef-bcd3-8d6a4ef42551/chameleon9.png"></p>

<p>Dear Chameleon users,</p>

<p>A few days ago, we celebrated the 9th anniversary of Chameleon! There were streamers, there was cake, and a gift: four more years of Chameleon. We are thrilled to share the <a href="https://cs.uchicago.edu/news/chameleon-testbed-secures-12-million-in-funding-for-phase-4-expanding-frontiers-in-computer-science-research/">plans for Chameleon Phase 4</a>. In particular, we are thrilled to announce that in phase 4 <a href="https://www.chameleoncloud.org/blog/2022/02/28/chincar-an-interview-with-the-newest-associate-site/">CHI@NCAR</a> becomes an official Chameleon site,, new hardware (including H100 GPUs), more flexible management of the virtualized and bare-metal partitions of the system, further advancements on CHI@Edge, and improvements to our reproducibility platform. Before all these significant changes take place however, here is news of what we’ve been up to last month.</p>

<p><b>CHI@UC Antelope Upgrade!</b> The long awaited Antelope upgrade for OpenStack at CHI@UC is finally here. As most of you know, <a href="https://www.openstack.org/">OpenStack</a> is the mainstream cloud infrastructure that our sites are built on so that an upgrade affects critical capabilities of the system and usually improves its robustness and usability. A significant amount of effort has gone into preparing for this upgrade over the last few months. In this particular upgrade, the most noticeable new feature is a significant upgrade to the web serial console – and you can finally use copy/paste with it. This upgrade will also help us with future development and new features. Thank you for your patience as we worked through some issues during the upgrade process over the last few weeks. Again, this upgrade only took place at CHI@UC, and we’ll be rolling out upgrades to TACC and the Chameleon associate sites in the near future.</p>

<p><b>Updating Getting Started Guide.</b> If you are a seasoned Chameleon user, you might remember your first days with the testbed, working through <a href="https://chameleoncloud.readthedocs.io/en/latest/getting-started/index.html">the Getting Started guide</a>. A lot has changed since the guide was originally written: the web interface has changed, we’ve added new interfaces for <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/jupyter.html">Jupyter</a> and <a href="https://python-chi.readthedocs.io/en/latest/">python-chi</a>, nodes can connect to <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/networks/networks_fabnet.html">Fabric’s FABNET</a>, and share artifacts with <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/sharing.html">Trovi</a>. This month, we updated our Getting Started guide to reflect all these new features new users may want to know about. Even if you have been using Chameleon for years, you may still learn something new by <a href="https://chameleoncloud.readthedocs.io/en/latest/getting-started/index.html">reading through it</a>. We are always happy to receive feedback, and if you have any on this new guide, please let us know <a href="https://chameleoncloud.org/user/help/">via the help desk</a>.</p>

<p><b>Python-chi “dev” release</b>. If you want to programmatically configure resources on the testbed, our python library, known as <a href="https://python-chi.readthedocs.io/en/latest/">python-chi</a>, is the best way to do it. While OpenStack offers python clients for many services, each cloud service (such as for networking, compute, reservation) does things differently, making it hard for non-experts to use these clients. So, several years ago, we created python-chi to improve this. We have been designing an improved version of python-chi based on user feedback to fix things like inconsistent types, lack of documentation, and confusing errors. We are also adding support for Jupyter widgets to improve the user experience, which will, for example, let you select your project from a dropdown list rather than having to set it via code. This effort is a work in progress, but we’ve released a “dev” version that you can start using now. You can do so by <a href="https://python-chi.readthedocs.io/en/dev/">reading the documentation</a>, or in your own experiments by adding</p>

<p style="text-align: center;"><code>!pip install git+https://github.com/ChameleonCloud/python-chi.git@dev </code></p>

<p>to the top of your Jupyter notebook. If you have any thoughts on the new functionality, please feel free to share with us <a href="https://chameleoncloud.org/user/help/">via the help desk</a>.</p>

<p>Happy experimenting!</p>