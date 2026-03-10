---
abstract: "<p>Chameleon integrates directly with Jupyter Notebook to provide an experimental\
  \ environment that has everything you could need for research - a cloud testbed,\
  \ a way to combine actionable code with written documentation, and sharing capabilities\
  \ through Zenodo. Learn more about how to take advantage of all these capabilities\
  \ and package your notebooks for publishing.\_</p>"
authors:
- Isabel Brunkan
categories:
- Tips and Tricks
date: '2020-10-20 22:16:57+00:00'
featured: false
hide_image: true
image: ''
slug: tips-and-tricks-packaging-experiments-reproducibility
subtitle: ''
title: Packaging Experiments for Reproducibility
---

<p dir="ltr">Did you ever find yourself in a situation where you needed to package an experiment for reproducibility? Perhaps you were preparing homework for students, finalizing a summer project and wanted your collaborators to be able to build on your work easily, or perhaps the conference you are submitting to requires it — whatever the reason, packaging experiments so that they can be easily repeated and potentially extended is increasingly a fundamental precondition to sharing research.<b> </b></p>

<p dir="ltr"> </p>

<p dir="ltr">How can a testbed like <a href="https://www.chameleoncloud.org/">Chameleon</a> help? First and foremost, it is a <a href="https://ieeexplore.ieee.org/document/9195551">shareable instrument </a> — all users can have access to the same hardware. It’s no longer the case that I can carry out an experiment on a GPU cluster in my basement — and you can’t because you don’t have access to such a cluster. Secondly, Chameleon is a cloud — users access it by configuring images, orchestration templates, and other digital artifacts and deploying them on the testbed to create an experimental environment — the same artifacts can then be used by others to repeat this deployment and thus recreate that experimental environment. Thus, just by virtue of using Chameleon for your experiments, you are going a long way towards making your experiment repeatable. </p>

<p> </p>

<p dir="ltr">What’s missing? We still need to implement the experiment in this environment, gather, analyze, and visualize data, and share it — preferably all within one well integrated environment. <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/jupyter.html">Jupyter Notebook</a> provides most of these additional capabilities (more on that <a href="https://www.chameleoncloud.org/blog/2019/10/25/reproducible-workflow-jupyter-chameleon/">here</a>), and integrated with Chameleon, repeatability and reproducibility are made easy. In this blog we are going to describe a process for packaging an experiment for repeatability. </p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-ef1eff9a-7fff-48db-b831-45a1c3f78d61">Step 1: Create Your Experimental Environment</b></p>

<p dir="ltr">To begin any experiment on Chameleon, the first step is creating your environment. You could do this using any <a href="https://www.chameleoncloud.org/blog/2020/05/29/choosing-right-orchestration-chameleon/">orchestration method</a>, but it is particularly convenient to do from a Jupyter Notebook — using the same container set up commands you’d use in the CLI. Since Jupyter is integrated with the testbed, your Chameleon credentials are implicit in the Jupyter cells, making it easy to build an experimental container: start a reservation, launch an instance, or SSH into one you’ve already launched from the GUI. Look at some of the examples below — you may be able to copy part of the experiment packaging to start your own experiment! </p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-ef1eff9a-7fff-48db-b831-45a1c3f78d61">Step 2: Run the Experiment </b></p>

<p dir="ltr">With your experimental container ready, you can quickly and easily code up what it takes to run your experiment (check out <a href="https://zenodo.org/record/3993323#.X45-pC2z2u4">example #2</a> below!). Depending on the complexity of the experiment, you can put this code in a separate notebook (and then reuse your experimental container for multiple different experiments). You can run, tweak, and rerun your experiment as you shape it. A big advantage of using Jupyter is that the integration of code with text allows you to explain your experimental steps, justify choices, and discuss alternative approaches.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-ba13fec7-7fff-7b64-44c9-993eb077267f">Step 3: Analyze Your Data</b></p>

<p dir="ltr">The reason why Jupyter is such a handy tool is that it is also a conducive environment for data analysis — after the experiment is finished or as you go, download the results locally to analyze and visualize them within Jupyter. Because Jupyter enables graphical and image visualization, you can include these in your notebook, so your container, experiment, and results are all in the same place.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-ba13fec7-7fff-7b64-44c9-993eb077267f">Step 4: Share Your Work</b></p>

<p dir="ltr">Ultimately, implementing your experiments within the Chameleon-Jupyter Notebook environment allows you to replicate your environment and experiment exactly — saving your container-building commands and experiment code in one place. In doing this, others — whether collaborators, reviewers, or other researchers interested in this area — can easily repeat your experiment by launching your notebook. <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/jupyter/jupyter_sharing.html?highlight=sharing">Chameleon’s integration</a> with <a href="https://zenodo.org/">Zenodo</a>, a digital publishing platform, allows you to publish your digital representation of an experiment and provides a DOI: you can now reference your experiment from your paper! </p>

<p dir="ltr">Chameleon, as a shareable, cloud testbed, is designed for experimental collaboration. The Jupyter Notebook integration allows you to mix explanatory text with actionable code, replay experiments, or break them down cell by cell. Whether to avoid future troubleshooting or provide educational value, the Chameleon-Jupyter Notebook combination unifies cloud capabilities with code and text. The best part about running your Chameleon experiments with Jupyter Notebook is the convenience — the inherent experimental repeatability is an added bonus. </p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-2665a730-7fff-ab77-22df-54146a08b5a0">If you are interested in seeing how others followed these steps, here are some examples of experiments in different areas: </b></p>

<ol>
	<li dir="ltr">
	<p dir="ltr"><b id="docs-internal-guid-2665a730-7fff-ab77-22df-54146a08b5a0"><a href="https://www.chameleoncloud.org/media/filer_public/7b/b9/7bb9687f-cefc-4c14-aeed-87f5a81192f4/1570480976.pdf">Application-based QoS Support with P4 and OpenFlow</a>: </b>a networking experiment showing an early use of Jupyter notebook for packaging -- while no published Juypyter notebook for this one exists, you can view it in <a href="https://www.youtube.com/watch?v=HmGuZeYDN7U">this short screencast</a> available on our <a href="https://www.youtube.com/user/ChameleonCloud">YouTube channel</a>.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr"><b id="docs-internal-guid-2665a730-7fff-ab77-22df-54146a08b5a0"><a href="https://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf">Image Classification with AlexNet on the Stanford Dogs Dataset</a>: </b>a machine learning experiment packaged in Jupyter Notebook, designed to be run with tools available within Chameleon and OpenStack. The <a href="https://zenodo.org/record/3993323#.X45-pC2z2u4">packaged notebook</a> is available on Zenodo, making it easy to reproduce in ~1 hour and perfect to use to teach machine learning or how to use the Chameleon testbed. </p>
	</li>
	<li dir="ltr">
	<p dir="ltr"><b id="docs-internal-guid-2665a730-7fff-ab77-22df-54146a08b5a0"><a href="https://www.usenix.org/system/files/conference/fast17/fast17-yan.pdf">Tiny-Tail Flash: Near Perfect Elimination of Garbage Collection Tail Latencies in NAND SSDs Reproduction</a>: </b>For this experiment, <a href="https://zenodo.org/record/3981543#.X49Bmi2z1QI">a Jupyter notebook</a> is packaged and available from Zenodo, reproducing the Dev Tools Release experiment from this paper.</p>
	</li>
</ol>

<p dir="ltr"> </p>

<p dir="ltr">If you would like to try out this packaging method, our <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/jupyter.html">Jupyter documentation</a> is a good place to start. Feel free also to explore the examples above — some elements, like the creation of an experimental container or certain data analysis patterns — could be generic to many experiments and will allow you to get started faster. And if you do package your experiment using this method, please <a href="mailto:contact@chameleoncloud.org">let us know</a> — we’d love to profile it on our blog!  </p>

<p><br>
 </p>

<p> </p>