---
abstract: "<p>To all of you starting a new academic year \u2013 welcome back! To help\
  \ you hit the ground running with your research we would like to share some tips\
  \ and tricks on how to make your experiments on Chameleon more productive.</p>"
authors:
- Kate Keahey
categories:
- Tips and Tricks
date: '2022-09-26 19:00:18+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/3f/ef/3fef2f21-8267-4b7f-8a22-f0bb0ac70505/image.png
slug: experiment-patterns-making-complex-experiments-easy
subtitle: ''
title: 'Experiment Patterns: Making Complex Experiments Easy'
---

<p>The most significant enabler of research productivity in the 20th century has got to be the <a href="https://www.tiny.cloud/blog/copy-paste-inventor/">invention of cut&amp;paste</a>. </p>

<p>Let’s say one day you wake up with a great idea for your next paper. To verify it, you need to create an experimental container where you can train a model on a substantial dataset and then periodically send data from multiple edge devices deployed in the field to update the model. You know how to get the data. You have the models. You know exactly what to measure and how. You know the area well and can already envision how your result will advance it. Everything seems tantalizingly within reach. But the conference deadline is just a few short weeks away. Go! </p>

<p>What is the hardest thing to do? It really boils down to this: can you set up the <a href="https://chameleoncloud.org/media/filer_public/58/5e/585e3b51-e37c-4f86-a0ad-729cb68c68f1/cloudcom2019_case_for_integrating_experimental_containers_with_notebooks.pdf">experimental container</a> composed of <a href="https://chameleoncloud.org/experiment/chiedge/">multiple edge devices</a>, <a href="https://chameleoncloud.org/hardware/">a powerful GPU instance</a> in the cloud, with attached <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/shares.html">persistent storage</a>? You’ve heard that Chameleon can give you all those resources, but can you get through all the documentation and learn how to use it quickly enough to configure something that will allow you to run your experiment? You can – because this, my friend, is where experiment patterns come to your rescue.  </p>

<p>The idea is simple: let’s look if others have implemented this kind of experimental container before – of elements of this experimental container – cut&amp;paste what’s needed and combine it to support the exact experimental pattern you need. Every experiment can be seen as a succession of multiple stages: First, we set up and test an experimental container. Then, we configure the environment, run programs and benchmarks, collect data, and generally do what the experiment requires. And finally, we analyze data and think of ways to present it to support our arguments. Every experiment contains this “experiment setup” stage and it is generally true that every experimental container can support many, many experiments – since this is the case, if somebody already wrote a program to set one up, why not reuse it? For more complex experiments, why not simply cut&amp;paste from multiple patterns and combine them – perhaps with a little something thrown in – to create the exact pattern you need? </p>

<p>And you won’t have to look far to find existing experiment patterns because some of us already implemented repeatable experiments with well-defined experimental containers as Jupyter notebooks and shared them via Chameleon’s <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/sharing.html">Trovi service</a>. Some of them have an “experiment pattern” tag, others may be labeled as “tutorial” or “user guide” (which is effectively an experiment pattern with a lot of comments and potentially different options of doing things), others may be simply somebody’s experiment from which we can “borrow” the part that sets things up. Let’s look at some building blocks <a href="https://chameleoncloud.org/experiment/share/">available on Chameleon right now</a> that allow you to get started quickly by cutting and pasting from other experiments:</p>

<p><a href="https://chameleoncloud.org/experiment/share/370ce99a-3e03-43e9-83e3-b61fd9692dc0"><strong>Power Management on Bare Metal Instance.</strong></a> This experiment sets up an experimental container consisting of a single bare metal instance on Chameleon – in other words, it implements a “single bare metal instance” experiment pattern. If this is all you want to do, you can simply copy this Jupyter notebook and replace the power management part (stage 2) with your experiment. </p>

<p><a href="https://chameleoncloud.org/experiment/share/1cc7be9e-045a-4390-a752-127d9c2fc9fa"><strong>Managing CPU Performance on KVM Instance.</strong></a> This experiment sets up an experimental container consisting of a KVM instance on Chameleon – in other words, it implements a “KVM instance” experiment pattern – useful if your experiment does not need bare metal or specialized hardware. If you’d rather run your experiment in a VM for whatever reason, this Jupyter notebook provides a good starting point – simply replace the CPU throttling part (stage 2) with your experiment. </p>

<p><a href="https://chameleoncloud.org/experiment/share/37991779-fd7b-4ab0-8d6f-e726a9204946"><strong>Edge to Cloud Experiment Pattern.</strong></a> This notebook explicitly focuses on the first  stage of an edge to cloud experiment: setting up an experimental container that provisions an instance on an edge device (either one from the pool Chameleon provides or one that you or your collaborators added to the testbed) and then also an instance with a GPU on the testbed. You can use this configuration in multiple ways: to provision just an edge device (delete the GPU part), just the GPU instance (delete the edge device) – or to set up multiple edge devices (cut the edge part and paste multiple times) or multiple GPUs. </p>

<p><a href="https://chameleoncloud.org/experiment/share/81af3cca-76cd-4a2e-83e1-3deb1fc7cf14"><strong>Shared Filesystem Tutorial.</strong></a> Likewise, this notebook only sets up an experimental container – one that creates a persistent share on the filesystem and attaches it to an instance. </p>

<p>There are many more to explore in networking, orchestration, or setting up specific services – just got to Trovi and browse; chances are you will find something that will help you get started. </p>

<p>And what of your experiment? Armed with the experiment patterns above, you can already see a light in the tunnel: you can get what you want by combining the edge to cloud and shared filesystem experiment patterns. While cut&amp;paste is a pleasurable activity and we can none of us ever wait to start, I highly recommend that you run the selected experiment patterns first, make sure that they work for you, learn about what they do, and iron out any wrinkles: this way you will stand on solid foundation and reduce any uncertainty later on. Chameleon is constantly changing – Chameleons do that – and you never know when some bit of functionality might get an update and start to behave just slightly differently. Running through the notebook will familiarize you with the bits of system that make the experiment pattern work, give you confidence in how things are supposed to work, and allow you to deal with one variable at a time if some problems do occur later. Once you make sure things work as expected, I’d make a copy of the edge to cloud experiment pattern notebook and then just cut aaaaand …paste!</p>

<p>The power of experiment patterns is that you never have to start from scratch – you can build something very complex very quickly by reusing existing elements. The objective of experiment patterns is to allow you to  spend as little time as possible in experiment setup – the tedious and time consuming part of experimentation – and to get to the part where you are configuring your unique experiment sooner and keep your focus and energy there – so you can get to the result you envision as quickly as possible. If we were always to start from scratch every experiment would be a major time investment – but most of it has been covered by people who came before us so now we can just cut aaaaand …paste!</p>

<p><br>
So now that you know about experiment patterns, tell us: what experiment patterns that we don’t have would be useful to you?<br>
 </p>