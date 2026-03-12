---
abstract: "<p>In today\u2019s Tips &amp; Tricks post we explore the idea of practical\
  \ reproducibility: how to make experiments not only reproducible but reproducible\
  \ in a practical way, i.e. making it as natural to play with science as it is today\
  \ to read about it via publications. To make this happen we need your help \u2013\
  \ your experiments packaged in a way that will allow others to easily build upon\
  \ them by extending them. Let us know what you think!</p>"
authors:
- Kate Keahey
categories:
- Tips and Tricks
date: '2023-03-20 20:45:12+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/ff/44/ff4460af-6a20-4587-9c19-ec490c2bc672/142655589_recursive_mirrors___photograph__matte_painting__hq__4k.png
related_posts:
- slug: sc-the-largest-reproducibility-laboratory
  title: 'SC: The largest Reproducibility Laboratory'
- slug: sharing-experiments-with-trovi
  title: Sharing Experiments with Trovi
- slug: chameleon-hackathon-2021-experiments-reproducibility-and-packagability
  title: Chameleon Hackathon 2021 -- Experiments Reproducibility and Packagability
- slug: reproducibility-chameleon-trovi-meets-youtube
  title: 'Reproducibility on Chameleon: Trovi meets YouTube'
- slug: reproducing-solid-state-drive-simulator-research-results-chameleon
  title: Reproducing Solid State Drive Simulator Research Results on Chameleon
- slug: trovi-google-drive-chameleon-experiments
  title: 'Trovi: the Google Drive for Chameleon Experiments'
- slug: chameleon-and-reproducibility-linnos-case-study
  title: 'Chameleon and Reproducibility: LinnOS Case Study'
- slug: tips-and-tricks-packaging-experiments-reproducibility
  title: Packaging Experiments for Reproducibility
- slug: reproducible-workflow-jupyter-chameleon
  title: A reproducible workflow with Jupyter on Chameleon
slug: the-practical-reproducibility-opportunity
subtitle: ''
title: The Practical Reproducibility Opportunity
---

<p> </p>

<p style="text-align: center;"><b id="docs-internal-guid-c54f510d-7fff-47b6-790a-c66f3b5e2622"><img src="https://chameleoncloud.org/media/filer_public/ff/44/ff4460af-6a20-4587-9c19-ec490c2bc672/142655589_recursive_mirrors___photograph__matte_painting__hq__4k.png" style="width: 480px; height: 480px;"></b></p>

<p>Imagine a world where you don’t just read about new research in papers, blogs, and reports – but can immediately verify or challenge new results, extend them by interactively inserting new ideas, or integrate them into your teaching. Now, open your eyes and help us build it – and lest you think this is not achievable, let us explain. </p>

<p>We first note that <a href="https://ieeexplore.ieee.org/document/9195551">open platforms, like Chameleon, are a tremendous opportunity for creating, shaping, and enjoying reproducible research</a>: when everybody has access to the same cutting edge hardware,  it is no longer the case that I can do ML research because I have a GPU cluster – but you can’t, because you don’t. You can access the same hardware I can – which means that you can reproduce or extend my result. Second, using a cloud like Chameleon means that at minimum you have to create an image that you will deploy on remote testbed resources and that fully encapsulates your experimental environment – you just <a href="https://chameleoncloud.org/appliances/">grab one of our stock images</a>, add whatever configuration you need, and then snapshot. And once you snapshot it, anybody could boot from this image as just as easily. This is not the case when you do experiments on your local resource, workstation, or laptop where you may not fully know – or may have forgotten – how they were configured. So using a testbed means that anybody could easily redeploy your experimental environment which is halfway to reproducibility – and we have not done anything special yet, we are just following the instructions and using Chameleon the way it is supposed to be used!</p>

<p>But here’s where we need your help. Over the years, our users created literally hundreds of thousands of images, orchestration templates, and countless notebooks. They are public, too. That’s a wealth of content, but as of right now it is not really shareable for various reasons: because it can be very hard to find, it represents only half of a solution and is not much use without the other half, or potential “consumers” of this content lack access to hardware, content, or both. Overtime, we sought to create tools and process for overcoming obstacles to creating better interfaces, services, and tools that should help our users make their research more sharable – a quick review is below with a big request to help us understand how we can make them better. </p>

<p><strong>Packaging experiments.</strong> Packaging experiments requires a <em>programmatic</em> interface to the testbed – in other words, turning your experiment configuration into something that you can run and re-run. This could mean <a href="https://chameleoncloud.org/blog/2020/05/29/choosing-right-orchestration-chameleon/">experiment orchestration</a> – but many of us prefer a non-transactional, imperative interface such as a command line interface (CLI) – or, even better, a python program – because they make it easier to re-run experiments bit by bit, fixing or extending things as we go. We have provided <a href="https://python-chi.readthedocs.io/en/latest/">python</a> and <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/cli.html">CLI</a> interfaces to the testbed long ago  – but the really exciting thing is that now we can <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/jupyter.html">provide them via Jupyter</a> which will allow you to integrate code with text and graphs, very handy for that immediate gratification of visualizing results – in other words, you are not only using a programmatic interface to the testbed – but an interface that is a fusion of results, explanation, and data analysis – realistically, something like that has to happen if we want to marry results and process. <a href="https://chameleoncloud.org/blog/2020/10/20/tips-and-tricks-packaging-experiments-reproducibility/">Tips on using Chameleon via the Jupyter interface</a> have been used by quite a few of our users with <a href="https://chameleoncloud.org/blog/2021/07/28/reproducibility-chameleon-trovi-meets-youtube/">interesting results</a>.</p>

<p><strong>Sharing experiments.</strong> A Jupyter notebook allows you to create a particularly elegant connection between the images you use, the resource selection for your experiment, and the body and data used in your experiment. The next challenge is how to publish, advertise, and ultimately find those notebooks such that they can actually be read (remember those hundreds of thousands of images that are not easy to find for the experiment you want to reproduce?) Here, the big difference between traditional methods of sharing research – such as papers – and sharing digital artifacts is that a paper does not need any special equipment to interpret, while digital artifacts need to be processed, visualized, or executed. The <a href="https://chameleoncloud.org/blog/2022/06/01/sharing-experiments-with-trovi/">Chameleon Trovi experiment repository</a> provides a solution to these two challenges in that it creates an <em>indexing system</em> for experiments that is also <em>integrated with the testbed</em> and therefore means that experiments are packaged as “compute capsules”, i.e., a combination of digital content and resources on which it can be executed.</p>

<p><strong>Access for reproducibility.</strong> Last but not least, what good is a packaged experiment if not everybody can gain access to reproduce it? This is why we created <a href="https://chameleoncloud.org/blog/2022/01/24/interactive-science-made-easy-with-chameleon-daypass/">Chameleon daypass that allows experiment authors to give access to the testbed</a> to colleagues for the purpose of reproducing their experiments. This means that reproducing an experiment could be as easy as clicking through a graph in the electronic copy of your paper or scanning a QR code on a poster!</p>

<p>These three capabilities combined should allow you to create <a href="https://chameleoncloud.org/blog/2022/09/26/experiment-patterns-making-complex-experiments-easy/">experiment patterns</a>, i.e., experimental containers that could support multiple experiments. Taking an extra few steps in your experiment development process, packaging them in notebooks, and making them available via Trovi will multiply their usefulness by making them available to others. We implemented <a href="https://chameleoncloud.org/blog/2022/10/04/chameleon-changelog-for-september-2022/">metrics in Trovi</a> so you could can see how many people view and/or execute your experiments. Give it a whirl and let us know if it works for you – or if not, what we should change!</p>

<p>Last, but not least – come to the reproducibility hackathon at the <a href="https://chameleoncloud.org/chameleon-cloud-users-meeting/user-meeting-2023/">Chameleon User Meeting</a> – we will help you package your experiments! And if you are interested in reproducibility, take a look at  the <a href="https://voices.uchicago.edu/repeto/">REPETO project</a> – it is organizing activities around the practical side of reproducibility.</p>

<p> </p>