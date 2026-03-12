---
abstract: "<p>Learn more about Trovi, Chameleon's experiment repository,\_and how\
  \ you can use it to collaborate on experiments and share your work. The blog also\
  \ covers Trovi's integrations with Zenodo and GitHub, creating a more seamless process\
  \ for running your experiment - from production to publication.\_</p>"
authors:
- Mark Powers
categories:
- Tips and Tricks
date: '2022-06-01 04:21:36+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/f5/10/f5109883-817b-4478-8509-a27d08a57147/screen_shot_2022-05-31_at_92321_pm.png
related_posts: []
slug: sharing-experiments-with-trovi
subtitle: ''
title: Sharing Experiments with Trovi
---

<p dir="ltr">Have you ever read a research article and wished you could rerun the experiment, dig into the code or see how hardware was specifically configured? Some pieces might offer GitHub or download links as a way to view the static code that went into the experiment, but this isn’t the most effective way to reproduce and explore it. Trovi, Chameleon’s experiment repository, helps solve it by providing a repository of experiments integrated with the testbed on which they were produced so that you can execute those experiments in just one click. Trovi lowers the barrier to reproducing research by combining the reproducible artifacts  and the experimental environment in which they can be reproduced. </p>

<p> </p>

<p dir="ltr">Interested in trying it out for yourself? You can browse the repository of artifacts <a href="https://www.chameleoncloud.org/experiment/share/">here</a>, and use it as a way to find and run experiments (fun fact: Trovi means find in esperanto). After clicking “Launch”, you’ll be taken to a Jupyter notebook containing a copy of the experiment files. This interface lets you run each part of the experiment individually, step by step. In doing this, you’re reproducing an experiment exactly the way the authors did, or, you can introduce variation by changing portions of the experiment. <br>
<br>
 </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-c52eb586-7fff-2278-188b-91954e209d33"><img height="381" src="https://lh5.googleusercontent.com/9BqP-Xiqx7iH-9nFzqBz7guGgEU6dfF7Eqj6ajJKUvWBTsmqjU4dcsRsV9CVvBIsjRYtql31fmCXcczT2iLNmMVzjyB_P8gI6FztIEs14iD1eM1w1PtHDpVKGUXxBs1Tfw8EA1swxX6YJBYEeg" width="624"></b></p>

<p dir="ltr" style="text-align: center;">Launching an experiment in one click, from a <a href="https://www.chameleoncloud.org/blog/2020/11/17/trovi-google-drive-chameleon-experiments/">previous post</a>.</p>

<p> </p>

<p dir="ltr">But it doesn’t stop there! Trovi can do more than just store artifacts. Our <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/sharing.html#publishing-to-zenodo">Zenodo integration</a> makes it easy to cite your artifact in a paper or presentation? Zenodo is an <a href="https://about.zenodo.org/">open access storage repository</a> backed by CERN, and provides DOIs for Trovi artifacts. By adding a DOI, your artifact becomes citable, for both your own use and others. </p>

<p> </p>

<p dir="ltr">Already storing things on GitHub or tracking files via git? Trovi also has integration with git, allowing you to create an artifact from any git repository. After making changes in Jupyter, you are also free to <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/sharing.html#exporting-via-git">export your data</a> back to your git repository. You can skip this step by just creating Jupyter notebooks of your experiment with the Chameleon <a href="https://jupyter.chameleoncloud.org/">Jupyter interface</a>.</p>

<p> </p>

<p dir="ltr">And last but not least – very important for all of you who are using other experimental platforms: Trovi is designed as an <a href="https://chameleoncloud.gitbook.io/trovi/">open platform</a>, meaning that anyone can integrate it with another testbed via the public <a href="https://trovi.chameleoncloud.org/docs/swagger/#/">API</a> we provide. This allows any testbed or cloud to use Trovi to store artifacts and integrate with it in the same way as with Chameleon, potentially running experiments over both as we have recently done with <a href="https://ieeexplore.ieee.org/abstract/document/9484517">Chameleon and commercial clouds</a>. Trovi is also <a href="https://github.com/chameleoncloud/trovi">open source</a>, allowing users to see what is going on under the hood, and get creative! We’d love to see how you could extend the service with more functionality in the future.</p>

<p><br>
Interested in seeing what Trovi has to offer? There are over 30 public artifacts on Trovi right now that you can check out today! We’ve showcased some of these artifacts <a href="https://chameleoncloud.org/blog/2021/07/28/reproducibility-chameleon-trovi-meets-youtube/">here</a> and <a href="https://chameleoncloud.org/blog/2021/01/26/interactive-and-repeatable-experiments-chameleon-jupyter-notebook/">here</a>. One of our most popular artifacts is <a href="https://chameleoncloud.org/experiment/share/cb042a44-cb21-437a-9f61-cde1dab042ae">LinnOS</a>, which has had almost 450 views since its creation in September 2020.</p>