---
abstract: "<p>We have created and shared a new Jupyter notebook that shows a better\
  \ way\_to combine standard isolated Chameleon networks with DirectStitch capabilities.\
  \ This more advanced method shows how to separate management of the stitched links\
  \ from the compute nodes.</p>"
authors:
- Paul Ruth
categories:
- Tips and Tricks
date: '2020-08-31 21:04:01+00:00'
featured: false
hide_image: true
image: ''
related_posts: []
slug: managing-multiple-external-links-stitched-single-chameleon-network
subtitle: ''
title: Managing Multiple External Links Stitched to a Single Chameleon Network
---

<p>Chameleon provides support for sophisticated networking experiments using GENI-style stitching. This capability enables users to deploy networking experiments (layer 2 and layer 3) that can extend across multiple resources: 1) the Chameleon network; 2) remote compute facilities such as GENI and public clouds; and 3) physical resources on their own campus networks. </p>

<p dir="ltr">Although this flexible capability has been available for many years, most users choose to deploy wide-area networking experiments in the static way shown in the <a href="https://jupyter.chameleoncloud.org/hub/user-redirect/lab/tree/notebooks/tutorials/networking/Tutorial-DirectStitch.ipynb">basic DirectStitch tutorial</a>. The method presented in the basic tutorial is limited to a single externally stitched VLAN and it is difficult to modify the network independently from the compute nodes. </p>

<p dir="ltr">We have created and shared a new Jupyter notebook that shows a better way  to combine standard isolated Chameleon networks with DirectStitch capabilities. This more advanced method shows how to separate management of the stitched links from the compute nodes. Separate management allows for multiple stitched links to be dynamically added and removed after the experiment has been instantiated. The flexibility provided by this method makes it the recommended method for all DirectStitch experiments. </p>

<p dir="ltr">The new Jupyter notebook can be directly accessed here: <a href="https://jupyter.chameleoncloud.org/hub/user-redirect/lab/tree/notebooks/tutorials/networking/Tutorial-AdvancedDirectStitch.ipynb">https://jupyter.chameleoncloud.org/hub/user-redirect/lab/tree/notebooks/tutorials/networking/Tutorial-AdvancedDirectStitch.ipynb</a>. If your browser does not link directly to the notebook using this link, you can go to <a href="https://jupyter.chameleoncloud.org/">https://jupyter.chameleoncloud.org/</a> and navigate to the notebook at ~/notebooks/tutorials/networking/Tutorial-AdvancedDirectStitch.ipynb<br>
<br>
We invite anyone interested in learning about these tips and tricks to look at the notebook. If you have questions about deploying an experiment using multiple stitched links, please <a href="https://www.chameleoncloud.org/user/help/ticket/new/guest/">contact us</a> so that we can help you get started with this capability.</p>