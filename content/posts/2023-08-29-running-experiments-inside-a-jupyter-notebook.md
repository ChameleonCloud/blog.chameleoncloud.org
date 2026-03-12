---
abstract: "<p>Chameleon\u2019s JupyterHub is a great way to organize your experiments\
  \ for practical reproducibility. To overcome its resource limitations, we describe\
  \ how to extend the Jupyter Server Trovi artifact so that you can run your full\
  \ experiment inside a Jupyter notebook.<br>\n\_</p>"
authors: []
categories:
- Tips and Tricks
- Announcements
date: '2023-08-29 21:52:05+00:00'
featured: false
hide_image: true
image: ''
related_posts: []
slug: running-experiments-inside-a-jupyter-notebook
subtitle: ''
title: Running experiments inside a Jupyter Notebook
---

<p>Researchers on Chameleon are working on interesting problems in computer science. For research to be impactful, it should be reproducible by others in the field, and easily extended when new researchers are inspired by the original results. This is why on Chameleon we are working to provide tools for <a href="https://chameleoncloud.org/blog/2023/03/20/the-practical-reproducibility-opportunity/">practical reproducibility</a>. There are three parts of practical reproducibility are packaging, sharing, and access (you can <a href="https://chameleoncloud.org/media/filer_public/25/18/25189b96-c3a2-4a55-b99b-c25322fe6682/reproducibility_on_chameleon-3.pdf">read more in our paper</a>). Sharing and access are addressed on Chameleon with Trovi and Daypass respectively. The packaging of an experiment is the form in which the configuration, program, and benchmarks run, along with the data and tools for its analysis. <a href="https://chameleoncloud.org/blog/2020/10/20/tips-and-tricks-packaging-experiments-reproducibility/">We’ve written before</a> in more detail about how to do each of these steps on <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/jupyter.html">Chameleon’s JupyterHub</a>. If you would like to see examples of how different types of experiments look packaged for this, you see existing <a href="https://chameleoncloud.org/blog/2022/09/26/experiment-patterns-making-complex-experiments-easy/">experiment patterns</a> on <a href="https://chameleoncloud.org/experiment/share/?filter=tag%3Aexperiment+pattern">Trovi</a>.</p>

<p>These examples typically set up and configure resources via python-chi, and once their instance(s) are running, they run commands on it via ssh to execute the experiment and collect data all from within a notebook running on Chameleon’s JupyterHub. This data is copied off of the instance, and then the notebook can analyze it, typically outputting some graph to share eventually in a paper. There are 2 limitations of this workflow:</p>

<ol>
	<li>Rather than run via SSH, some researchers write their experimental program as a notebook, and want to run it directly on the instance to make use of its CPU, RAM, or GPU.</li>
	<li>Chameleon’s JupyterHub runs notebooks in a low power environment, with only 2 CPU threads, a few GB of RAM, and only a GB of storage. Depending on your data, this may not be a sufficient environment in which to analyze it.</li>
</ol>

<p><img media="" src="https://chameleoncloud.org/media/filer_public/65/20/6520f441-0913-46d9-b057-b15a66d58b61/img1.png" style=""></p>

<p><i>The limited multiprocessing capabilities of Chameleons’ JupyterHub</i></p>

<p>To get around these limitations, we’ve created the <a href="https://chameleoncloud.org/experiment/share/39ae6822-b078-4707-8323-76eaf3a7e213">Basic Jupyter Server artifact</a>, which demonstrates how to install and connect to a secure Jupyter environment on a Chameleon instance. The interesting parts of this process, which should work on any Chameleon instance, are:</p>

<ol>
	<li>Install the jupyter-notebook package on an instance, and configure it.</li>
	<li>Start a service to run the notebook server with.</li>
	<li>Connect to your instance via an SSH tunnel from your laptop or desktop computer.</li>
</ol>

<p>Once this is done, you should see the Jupyter notebook home screen. You can select “new &gt; terminal” and execute “lscpu” (or “nvidia-smi”) to confirm that it is running on a powerful Chameleon node.</p>

<p><img src="https://chameleoncloud.org/media/filer_public/7e/da/7edadb71-6d84-4b21-aebb-20ea2d924763/img_lab.png" media="" style=""></p>

<p>You can augment the installation of jupyter-notebook to copy your experiment or data analysis notebooks to the node. Then upon opening them, you’ll see the notebook kernel is running directly on the instance, as expected. If your instance has a GPU, this will enable you to use it with CUDA inside the notebook. <br>
 </p>

<p><img media="" src="https://chameleoncloud.org/media/filer_public/ac/b9/acb92f4a-fe03-4954-9ca9-1eb3f1a2c03a/img2.png" style=""></p>

<p><i>Powerful multiprocessing capabilities of Jupyter running on a Chameleon node</i></p>

<p>Using this method, your Jupyter notebooks have the full power of <a href="https://chameleoncloud.org/hardware/">Chameleon’s hardware</a>. You could now access low level properties about the machine, train a machine learning model, or stitch to <a href="https://chameleoncloud.org/blog/2023/05/22/fabric-updated-trovi-example-for-using-fabric-with-chameleon/">Fabric</a> all natively in your notebooks python kernel. If you are feeling adventurous, you could even take a <a href="https://chameleoncloud.org/blog/2023/03/28/reproduce-rerun-repeat-the-fun-way-to-learn-machine-learning/">Colab notebook</a>, and upload it to this open environment (some translation may be required, your instance won’t have the same pre-installed libraries). The possibilities are endless!</p>