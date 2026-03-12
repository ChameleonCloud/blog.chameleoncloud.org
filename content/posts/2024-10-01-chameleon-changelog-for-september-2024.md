---
abstract: <p>This month we have python-chi 1.0 released, and a new bare metal experiment
  pattern artifact to go with it!</p>
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2024-10-01 21:45:49+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/00/47/00470a03-9f43-4add-8a83-9490416dd177/53768969585_6967a8228b_c.jpg
related_posts: []
slug: chameleon-changelog-for-september-2024
subtitle: ''
title: Chameleon Changelog for September 2024
---

<p style="text-align: center;"><img media="" src="https://chameleoncloud.org/media/filer_public/00/47/00470a03-9f43-4add-8a83-9490416dd177/53768969585_6967a8228b_c.jpg" width="500"></p>

<p style="text-align: center;"><a href="https://www.flickr.com/photos/berniedup/53768969585/in/photolist-2pVo2nK-2pVgcMo-2pSQfqm-2pRP8Uz-2pMQwSF-2pLYPcu-2pKbxus-2pGHxRN-2pDEk4e-2pDye2u-2pDEk3T-2pDEZce-2pDDKHF-2pDye29-2pDCGLP-2pDDKHv-2pCN5bN-2pagSSo-2pCiCrX-2pCpJ9Z-2pCpJ9U-2pCpago-2pCo551-2pCpJ9J-2pCqkYW-2pCqkZ2-2pCo54p-2pAAC79-2pArd7i-2pAoUTR-2pA84Wh-2pA959g-2pA958z-2pA84VW-2pA3Cxk-2pA3Cxf-2pA84Vv-2pA9MZM-2pxzze8-2pxAjF4-2pxu6Xo-2pwqLya-2pwqLqQ-2prZxLN-2p86ADF-2prp8mY-2ppC2m8-2pnMTTd-2pmZYup-2pmPJt3">Bernard DUPONT via Flickr</a></p>

<p>Dear Chameleon users,</p>

<p>Welcome back to the new academic year! We’ve noticed an uptick in usage on the testbed as new classes and experiments start up. If this is your first time, or it has been a while since you used Chameleon, you may be interested in one of our recent webinars</p>

<ul>
	<li><a href="https://www.youtube.com/watch?v=rJ_7eToywuE">Introduction to Chameleon</a></li>
	<li><a href="https://www.youtube.com/watch?v=b0Sy6YCBX_8">CHI@Edge Tutorial</a></li>
	<li><a href="https://www.youtube.com/watch?v=t3WBFknXzTg">Experiment Orchestration with Jupyter, python-chi, and more</a></li>
</ul>

<p>This month, we have been spending a lot of time behind the scenes, but we have a few things we wanted to share.</p>

<p><b>Python-chi 1.0!</b> A <a href="https://chameleoncloud.org/blog/2024/08/02/chameleon-changelog-for-july-2024/">few months back</a>, we announced a dev release of python-chi. This month, we have finally released this as python-chi 1.0. We hope that this release makes it easier to orchestrate resources via python, with <a href="https://python-chi.readthedocs.io/en/latest/">improved documentation</a> that explains different parameters and return types. We now have a module for <a href="https://python-chi.readthedocs.io/en/latest/modules/storage.html#chi.storage.Object">the object store</a>, making it very easy to upload and download data, and you can now browse the hardware catalog programmatically <a href="https://python-chi.readthedocs.io/en/latest/modules/hardware.html">via the hardware module</a>. This also includes information about lower level documentation for using <a href="https://python-chi.readthedocs.io/en/latest/modules/clients.html">the OpenStack clients</a>, so that you can unlock the full potential of the testbed. Additionally, if you are using python-chi in our <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/jupyter.html">jupyter interface</a>, you’ll see widgets such as progress bars and tables to better show you what is going on in your experiment. As always, if you have any questions or feedback, please let us know <a href="https://chameleoncloud.org/help">via the help desk</a>.</p>

<p><b>Updated Bare Metal Experiment Pattern. </b>If you want to get started with the new python-chi, check out the new <a href="https://chameleoncloud.org/experiment/share/50692573-4094-466c-b4fe-0ed3471f8993">Bare Metal Experiment Pattern</a> artifact. With one click, you can launch this artifact on Jupyterhub, and you’ll be running a sample Chameleon experiment that does some simple power measurements on a bare metal instance. We’ve designed this artifact to divide things up into simple sections, making it easier than ever to use in order to package your own experiment for Chameleon. If your experiment and analysis code is stored on GitHub, you just need to edit a few lines from the notebook, and you’ll have made great progress towards <a href="https://chameleoncloud.org/blog/2024/09/25/call-for-presentations-community-workshop-on-practical-reproducibility-in-hpc/#">practical reproducibility</a> for your experiment!</p>

<p>Happy experimenting!</p>