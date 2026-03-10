---
abstract: "<p><a href=\"http://falsifiable.us/\">Popper</a>\_is a protocol for creating\
  \ reproducible experiments designed to leverage\_popular\_<a href=\"https://en.wikipedia.org/wiki/DevOps\"\
  >DevOps</a>\_tools and techniques, such as Git, Docker and continuous integration\
  \ (CI) in order to produce experiments that can be re-executed on different environments\
  \ with a single command.</p>"
authors:
- Ivo Jimenez
categories:
- User Experiments
date: '2018-07-17 21:56:42+00:00'
featured: false
hide_image: true
image: ''
slug: popper-devops-approach-carrying-out-experiments-chameleon
subtitle: ''
title: 'Popper: A DevOps Approach to Carrying Out Experiments on Chameleon'
---

<p>The advantages of packaging experiments in a way that makes it easy for others to re-execute are abundantly clear: for personal projects, where one can easily go back to an experimentation that was "abandoned" a few months back; academic articles, where one wants to publish an experiment associated to a publication, so others can re-run it easily; or for class projects, where students share their homework and final class report in the form of executable code to their professors. This idea of reproducible research has been on the rise in recent years in many areas of computational and data science, and with it the demand for tools that are designed specifically for creating experiments in this way.</p>

<p><a href="http://falsifiable.us/">Popper</a> is a protocol for creating reproducible experiments. Popper is designed as a way of leveraging popular <a href="https://en.wikipedia.org/wiki/DevOps">DevOps</a> tools and techniques, such as Git, Docker and continuous integration (CI) in order to produce experiments that can be re-executed on different environments with a single command.</p>

<p>In the context of Popper, we refer to <a href="http://popper.rtfd.io/en/latest/sections/concepts.html#popper-pipelines">experiments as pipelines</a>. These pipelines consist of stages, where stages are (Bash) shell scripts that dictate the steps of an experiment (one script per stage). As part of our efforts, we provide a CLI tool to easily bootstrap and manage repositories of pipelines.</p>

<p>An interesting use case is automatically reproducing experiments on cloud services. To illustrate this, we've developed a <a href="https://github.com/popperized/popper-readthedocs-examples/tree/master/pipelines/chameleon-benchmarking">pipeline</a> that runs a simple experiment on ChameleonCloud. This pipeline can be used as a learning example and also as a starter template for creating reproducible experiments that run on Chameleon. To obtain this pipeline, one can use the Popper CLI tool:</p>

<div style="background: #eee; border: 1px solid #ccc; padding: 5px 10px;">
<pre><code>mkdir my-cool-paper
cd my-cool-paper
git init
popper init
popper add popperized/popper-readthedocs-examples/chameleon-benchmarking</code></pre>
</div>

<p>The above snippet initializes a new Git repo; "Popperizes" the repository (<code>popper init</code>); and downloads the Chameleon pipeline (<code>popper add</code>), placing it into the <code>pipelines</code> folder of our repository. To keep things simple, the pipeline has three stages and only requires <a href="https://docs.docker.com/install/">Docker</a> to be installed on the machine where it is being executed. The experiment has the following stages:</p>

<ol>
	<li><code>setup</code>: creates a reservation and allocates the requested resources on Chameleon using <a href="https://github.com/BeyondTheClouds/enoslib"><code>enoslib</code></a> (a blog post on Enos can be found <a href="https://www.chameleoncloud.org/blog/2018/06/11/enos-framework-experimenting-openstack/">here</a>). The <a href="https://github.com/popperized/popper-readthedocs-examples/blob/master/pipelines/chameleon-benchmarking/scripts/request.py"><code>scripts/request.py</code></a> file is where resources are specified. If you use this pipeline to bootstrap an experiment, this file needs to be modified in order to specify the actual number and types of machines you need. Once this stage is done, the information about each allocated node is written in the <code>inventory</code> directory.</li>
	<li><code>run</code>: this stage is the one that carries out the actual experiment. In our case we are running a couple of benchmarks using <a href="https://github.com/ivotron/baseliner"><code>baseliner</code></a>, and saving the results by retrieving output files into the <code>results/</code>folder. Of course, this stage should be changed to fit your needs. For example, a tool for running a <a href="https://github.com/pditommaso/awesome-pipeline">workflow</a>, automating the <a href="https://github.com/kahun/awesome-sysadmin#configuration-management">configuration</a>, or <a href="https://github.com/kahun/awesome-sysadmin#monitoring">monitoring</a> resources, can be used to orchestrate an experiment on this allocation.</li>
	<li><code>teardown</code>: deletes the lease used for the experiment.</li>
</ol>

<p>Once you've obtained the pipeline, you can issue <code>popper run chameleon-benchmarking</code> to start the experiment. But it does not have to stop there. Another feature of Popper is the ability to set up our experiments to run automatically on CI environments through the <code>popper ci</code> command. You can also add a <code>validation</code> stage to make sure that a pipeline produces the expected results. Using this, one can check the integrity of an experimentation pipeline whenever a new change is introduced (a commit from us or collaborators).</p>

<p>The goal for Popper is to make it a domain-agnostic tool, so a pipeline can implement a scientific exploration from many fields, for example <a href="https://github.com/popperized/swc-lesson-pipelines/tree/master/pipelines/docker-data-science">Data Science</a>, <a href="https://github.com/popperized/popper-readthedocs-examples/tree/master/pipelines/genomics">Genomics</a>, or <a href="https://github.com/popperized/popper-readthedocs-examples/tree/master/pipelines/vagrant-linux">Linux kernel research</a>. Since pipelines are made up of familiar shell scripts, it is often straightforward to "popperize" existing experiments. We also provide many <a href="https://github.com/popperized/popper-readthedocs-examples">examples and starter piplines</a> that you can take advantage of by using the <code>popper add</code> command. You can read more on the <a href="http://popper.rtfd.io/">official documentation</a>, take a <a href="https://popperized.github.io/swc-lesson">self-paced hands-on tutorial</a>, and, if you are interested in contributing or require any assistance when using Popper, you can take a look at our <a href="https://github.com/systemslab/popper/issues">issue tracker</a> or reach out to us on <a href="https://gitter.im/falsifiable-us/popper">gitter</a>.</p>

<p><strong>Contribution Meta-Data:</strong></p>

<p>Type of contribution: Software<br>
Author(s): Rafael A. Castillo, Francisco E. Gonzalez, Ivo Jimenez<br>
Link to code/repository: https://github.com/systemslab/popper<br>
License: MIT<br>
Link to documentation: http://popper.readthedocs.io<br>
Dependencies: Docker, Popper<br>
e-mail: ivo.jimenez@ucsc.edu<br>
Community: https://gitter.im/falsifiable-us/popper</p>

<p> </p>

<p> </p>