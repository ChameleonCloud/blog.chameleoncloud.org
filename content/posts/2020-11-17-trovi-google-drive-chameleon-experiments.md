---
abstract: "<p>Trovi is the next iteration of the Chameleon experiment management and\
  \ sharing platform. With Trovi,\_you can set up and configure your experimental\
  \ environment from within a Jupyter notebook, document and save your experiment\
  \ similarly in notebook form, and privately share it with collaborators or publish\
  \ it for any Chameleon user to build on. Learn more inside!</p>"
authors:
- Jason Anderson
categories:
- Tips and Tricks
date: '2020-11-17 00:03:05+00:00'
featured: false
hide_image: true
image: ''
slug: trovi-google-drive-chameleon-experiments
subtitle: ''
title: 'Trovi: the Google Drive for Chameleon Experiments'
---

<p dir="ltr">One important aspect of reproducibility is discoverability--what good is a packaged, reproducible experiment if nobody can find it and use it? One thinks of trees falling in forests. Consider the problem of the professor who wants to design a class for the next year, where students submit lab assignments: how do they provide these course materials such that students can work through them, ideally without fighting with library dependencies and OS problems that ultimately distract from the lab's goal? Or, consider the problem of a researcher preparing a paper for submission: how can they show the latest run of results to their advisor or colleagues? How can they encapsulate their work into a digital artifact that meets the conference's criteria? Finally, consider that you're getting started with a testbed: how do you find some useful examples of what others have done, which possibly highlight possibilities you didn't previously consider?</p>

<p dir="ltr">This is why on Chameleon we are providing new capabilities for finding, saving and sharing experiments on Chameleon, which we collectively dub <a href="https://www.chameleoncloud.org/experiment/share/">Trovi</a> (from the Esperanto trovi, meaning to find!) With Trovi you can package your experiments as a Jupyter notebook, save iterations of your experiment privately, but also share your work with others and even ultimately publish your experiment as a citable research artifact.</p>

<p dir="ltr">Here's a look at how this tool and others can help you in your day-to-day work.</p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-3f1980d6-7fff-cd35-28c4-267a898d45df">Problem: How can I find an already-packaged experiment that I could ask my students to reproduce and extend?</b></p>

<p dir="ltr">Trovi already has several experiments publicly available for all Chameleon users. They include examples of actual experiments, "quick start" tutorials, and examples illustrating some of the testbed's more advanced capabilities (see the end of this post for a full list!) You can search for experiments with keywords and also filter for experiments that are private to you, shared with a particular project, or are publicly available. For example, as a teacher, you could share all of your class assignments under a particular project--any students who you add to your project will automatically be able to see and launch the assignments (as Jupyter notebooks and supporting documentation/files) on Chameleon.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-3f1980d6-7fff-cd35-28c4-267a898d45df">Problem: Setting up my environment again for a new lease takes significant time and steps.</b></p>

<p dir="ltr">Chameleon users are <a href="https://www.chameleoncloud.org/blog/2020/10/20/tips-and-tricks-packaging-experiments-reproducibility/">increasingly using Jupyter notebooks to package their experiment setup</a>. Experiments on Trovi typically are expressed as Jupyter notebooks, where each cell represents a step in the experiment workflow: making a reservation for resources, configuring those resources on the testbed, and then executing the experiment steps. Performing these steps within Jupyter is easy, as Chameleon CLI and Python clients are fully integrated. Here's a little preview of the <a href="https://www.chameleoncloud.org/experiment/share/22">OpenFlow Quick Start example</a>, which you can launch on Trovi and try out yourself:</p>

<p dir="ltr"><b id="docs-internal-guid-3f1980d6-7fff-cd35-28c4-267a898d45df"><img height="270" src="https://lh4.googleusercontent.com/r5M5_-Z6Q35Z4Eya9tV7kbW4YYt-bQX3fW3DPiKbAOXhC6M9RWPxTdS5SwVEErR0xs42qCj7a5ovM2vippQ29W6fEBvnA_8QIk5cDwnPcEcHt8Ujo9d3sxD2tJMGz0ZPx44XFg2M" width="400"></b></p>

<p dir="ltr">Using this method, setting up your experiment environment again is quite simple and easy to replicate when you come back later.</p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-3f1980d6-7fff-cd35-28c4-267a898d45df">Problem: I want to package my experimental environment but I'm not sure how.</b></p>

<p dir="ltr">To snapshot the disk of any of your bare metal nodes, use the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images.html#the-cc-snapshot-utility">cc-snapshot utility</a>, which comes built-in on all Chameleon base disk images. This is a good way to save a configuration of e.g., kernel modules, installed packages and settings. Another option is to use Jupyter notebook cells to perform these operations, as the <a href="https://www.chameleoncloud.org/experiment/share/3">power experiment example</a> does. Finally, you can use Ansible, which can simplify some aspects of remote configuration, but does require a bit of familiarity with the tool--the <a href="https://www.chameleoncloud.org/experiment/share/1">JupyterHub example</a> uses this approach.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-3f1980d6-7fff-cd35-28c4-267a898d45df">Problem: My packaged experiment works well for me, but how can I show it to somebody else?</b></p>

<p dir="ltr">This is perhaps the most powerful feature of Trovi: you can share your packaged experiments with entire Chameleon projects or via private link, similar to how Google Drive documents can be shared. <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/sharing.html#adjusting-sharing-settings">Check out the docs to learn more</a>--one nice benefit is that any Chameleon user that has access to your experiment will be able to easily launch it within their own account.</p>

<p dir="ltr">Because a GIF is worth a thousand words, here is how easy it is to re-launch an experiment saved to Trovi:</p>

<p dir="ltr"><b id="docs-internal-guid-3f1980d6-7fff-cd35-28c4-267a898d45df"><img height="381" src="https://lh5.googleusercontent.com/ZHKjxWeoNrrG74GLtHCcxzwPLT0OgV_yZYmTeKKjgR5wm6kaiXsVz2P2GxqL8Y81-35S1kZd8XDtzHFez1LPGwHbqnbfSC5LtfGav3d2L3fyDzgB0A-z5ZqVkrIU-DGldXWM8_2E" width="624"></b></p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-3f1980d6-7fff-cd35-28c4-267a898d45df">Problem: How do I reference a packaged Chameleon experiment as a digital artifact?</b></p>

<p dir="ltr">Increasingly, conferences encourage attaching digital artifacts to paper submissions. This is very easy to do with an experiment packaged on Trovi! You can publish any saved version of your experiment to Zenodo, which will archive it in long-term storage and additionally assign a unique DOI suitable for citation. As an example, here's the DOI assigned to the JupyterHub example: <a href="https://doi.org/10.5281/zenodo.3463619">10.5281/zenodo.3463619</a></p>

<p dir="ltr"> </p>

<p dir="ltr">Check out the existing content available on <a href="https://www.chameleoncloud.org/experiment/share/public">Trovi</a>, and feel free to share your own experiments for others to browse! Try out the Chameleon Quick Start notebooks to get started on Chameleon or the Example Experiments section to see real experiments from foundational papers for use in classes or to try to extend them. </p>

<p dir="ltr"><b id="docs-internal-guid-3f1980d6-7fff-cd35-28c4-267a898d45df">Chameleon Quick Start:</b></p>

<p dir="ltr"><a href="https://www.chameleoncloud.org/experiment/share/22">Openflow Quick Start Example</a>: an artifact designed to help you get started using OpenFlow on Chameleon and can be used as a base for OpenFlow experiments or advanced network appliances. </p>

<p><a href="https://www.chameleoncloud.org/experiment/share/6">Jupyter Usage Metric Exploration</a>: This notebook is an example data analysis notebook looking at usage patterns on Chameleon. Feel free to use as a model for your own data analysis needs.</p>

<p dir="ltr"><a href="https://www.chameleoncloud.org/experiment/share/3">Power Management Experiment Example</a>: This example illustrates how to create a reproducible experiment in power management and describes tools available within the Chameleon base images, as well as the orchestration and snapshot capabilities.</p>

<p><b id="docs-internal-guid-3f1980d6-7fff-cd35-28c4-267a898d45df">Example Experiments on Chameleon:</b></p>

<p dir="ltr"><a href="https://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf">Image Classification with AlexNet on the Stanford Dogs Dataset</a>: a machine learning experiment packaged in Jupyter Notebook, designed to be run with tools available within Chameleon and OpenStack. The <a href="https://zenodo.org/record/3993323#.X45-pC2z2u4">packaged notebook</a> is available on Zenodo, making it easy to reproduce in ~1 hour and perfect to use to teach machine learning or how to use the Chameleon testbed.</p>

<p dir="ltr"><a href="https://www.usenix.org/system/files/conference/fast17/fast17-yan.pdf">Tiny-Tail Flash: Near Perfect Elimination of Garbage Collection Tail Latencies in NAND SSDs Reproduction</a>: For this experiment, <a href="https://zenodo.org/record/3981543#.X49Bmi2z1QI">a Jupyter notebook</a> is packaged and available from Zenodo, reproducing the Dev Tools Release experiment from this paper.</p>