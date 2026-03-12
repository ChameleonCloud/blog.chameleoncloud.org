---
abstract: "<p>Great news in Chameleon-land! We\u2019re kicking off the new year with\
  \ upgrades and fixes to JupyterHub, and usability improvements to the web dashboard\
  \ Horizon \u2013 and save the date for the first post-pandemic in-person Chameleon\
  \ User Meeting!\_<br>\n\_</p>"
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2023-02-02 22:10:18+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/86/59/8659210d-7e42-4ba0-b899-c887a89c4f09/jan_changelog.png
related_posts: []
slug: 2023-january-changelog
subtitle: ''
title: Chameleon Changelog for January 2023
---

<p style="text-align: center;"><b id="docs-internal-guid-caa61b6b-7fff-99aa-69f7-8d87a4642cfd"><img height="480" src="https://lh4.googleusercontent.com/JGb1aP4Ax94kj9xASCzpRBEUMwmt_75xMkwmp7RurIAhWJAcfASZt59fnYq8kp4QNQ3sfdRa6mD2k6iEVIb9X2AO422GmIKj7Hf-tbR5RH-gcez_mB1cqO60kY8CtWZmYaAjD-OiWtuLHlmlqpJh290" width="480"></b></p>

<p>Dear Chameleon users,</p>

<p>We hope everyone had a wonderful start to the year now that experiments and classes have begun again. The #1 New Year’s resolution for us this year is to make the testbed easier to use and more efficient for everybody and we are kicking it off with a couple of much needed upgrades. </p>

<p><strong>Jupyter server upgrade.</strong> Many of you are using Chameleon via <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/jupyter.html">our JupyterHub server</a>, which allows you to orchestrate Chameleon experiments in a programmable Jupyter notebook –  this is important as a programmatic interface naturally records the actions you take to create your experiment and they can be therefore easily repeated by someone else which means you can share reproducible experiments and <a href="https://chameleoncloud.org/blog/2022/09/26/experiment-patterns-making-complex-experiments-easy/">experiment patterns</a>. This month, we did a large infrastructure migration to a scalable Kubernetes deployment, and fixed several long-standing problems as a result. In particular, there should be no more stability adventures with the storage system, which caused several issues last year. You may also notice that your server spawns much faster, has more memory, and the python version is updated to 3.10. While we were at it, we also fixed a few authentication bugs and issues with Trovi artifacts. This is all for the best but as with any new upgrades things might take a while to work themselves out, if you experience any issues with Jupyter, please let us know via the <a href="https://chameleoncloud.org/user/help/ticket/new/">help desk</a>.</p>

<p><strong>Horizon usability improvements.</strong> While many of our users prefer a programmable interface to the testbed for the reasons stated above, sometimes you just need to do things quickly via a GUI. In Chameleon this role is filled by <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/gui.html">Horizon, the web dashboard for all of our Chameleon sites</a>, and it has received several usability improvements this month. Some of the options that display in Horizon (e.g., security group management) were incompatible with our baremetal sites. We removed these options, which simplify the interface considerably, a much awaited change. In addition, we also added a feature that allows you to filter by all Chameleon supported images, making it easy to quickly find the images you need.</p>

<p style="text-align: center;"><b id="docs-internal-guid-c4c87735-7fff-cedc-e75f-c5808666b415"><img height="406" src="https://lh3.googleusercontent.com/qYCwq--ZMPZZhvPrJdtoD79czrjU3L3TXbHItkmGT2zmA1eVvgKdmiSlB-6DHcVmtROOAjcJ_E-0gaQFnJYpfqPpqsShvpH48vrwtfEiL60EQoZMYUEdITvSQu3yjWINRbVLdoYU-L0Zh92QZA89L9U" width="536"></b></p>

<p><strong>Chameleon User Meeting.</strong> We saved the best for last – save the date: we will have the first post-pandemic Chameleon User Meeting on May 2-3 in Chicago! As many of you know, our <a href="https://chameleoncloud.org/chiedge-community-workshop/?tk5VAFwlx9IKSoczFi3XlNv4xbGeNn8pzAlCu9555gi2238lu36PAj8jQgtch3U">last User Meeting</a> was held virtually and had edge computing as the theme. We are happy to announce that the theme for this year’s meeting data systems – we will send the formal call for presentation abstracts shortly but in the meantime, think about all the wonderful things related to data that you are doing and could share with us! As in the past years, we will provide travel support for the ten best submissions – we’d love to see you all in Chicago in May!</p>

<p>Happy experimenting!<br>
 </p>