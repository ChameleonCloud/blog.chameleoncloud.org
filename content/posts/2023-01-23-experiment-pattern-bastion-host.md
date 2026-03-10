---
abstract: <p>We go over the benefits of using a bastion host to administer your cluster.
  It's the easiest way to deploy a secure cluster of hosts for your experiments, and
  it also helps to save resources!</p>
authors:
- Adam Cooper
categories:
- Tips and Tricks
date: '2023-01-23 17:04:39+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/a3/74/a374ce7b-6d1e-4dc3-b989-d3410c30cd3d/high_castle_and_bastions_in_malbork.jpg
slug: experiment-pattern-bastion-host
subtitle: The easiest way to deploy a secure cluster for scientific research
title: 'Experiment Pattern: Bastion Host'
---

<p><b id="docs-internal-guid-ba0c1647-7fff-bb94-3fe9-e1ce720f9da2"><img src="https://chameleoncloud.org/media/filer_public/a3/74/a374ce7b-6d1e-4dc3-b989-d3410c30cd3d/high_castle_and_bastions_in_malbork.jpg" style="width: 800px; height: 594px;"></b></p>

<p style="color: rgb(170, 170, 170); font-style: italic;">This <a href="https://commons.wikimedia.org/wiki/File:High_Castle_and_bastions_in_Malbork.jpg">image</a> is licensed under the <a href="https://en.wikipedia.org/wiki/en:Creative_Commons">Creative Commons</a> Attribution-Share Alike <a href="https://creativecommons.org/licenses/by-sa/3.0/deed.en">3.0 Unported</a>, <a href="https://creativecommons.org/licenses/by-sa/2.5/deed.en">2.5 Generic</a>, <a href="https://creativecommons.org/licenses/by-sa/2.0/deed.en">2.0 Generic</a>, and <a href="https://creativecommons.org/licenses/by-sa/1.0/deed.en">1.0 Generic license</a>.</p>

<p>One of the most difficult problems about running experiments across multiple remote compute resources is to do so  securely. The simplest approach is to just spawn the computehosts, and assign a floating IP address to each host. This way, one can access all their hosts over the Internet. </p>

<h2>What is wrong with the simplest approach?</h2>

<h3>Security</h3>

<p>Certain experiments may expose dashboards or other services like databases with sensitive data and permissions to the Internet. There are also experiments which require the use of old, outdated, or unmaintained software for the purposes of reproducibility or because of  lack of community support. When you expose a service to the Internet, you are also exposing it to hackers who <em>will</em> find it and <em>will</em> attempt to compromise it <em>immediately</em>. Our hardware is very powerful, and is thus an extremely valuable target to hackers. As has happened to multiple projects in the past, your server could be compromised by a malicious party, and your valuable time could be wasted as all your nodes have to be shut down in response. These mistakes can arise due to carelessness or even simple misunderstandings. It’s better to eliminate the possibility of this happening by reducing the <a href="https://www.ibm.com/topics/attack-surface">attack surface</a> for hackers. This means that one does not directly expose their entire project to the open Internet. We’ve talked about this before in our <a href="https://www.chameleoncloud.org/blog/2021/06/28/best-practices-making-your-experiments-secure/">security best practices blog</a>; we highly recommend checking it out for more security tips.</p>

<h3>Efficiency</h3>

<p>The obvious issue with reserving a floating IP address for every host is that you have to reserve all those IP addresses! An unfortunate reality is that there is a finite number of public IP addresses available for use across the entire Internet. Back when the Internet was just beginning to take shape, the ~4.3 billion IPv4 addresses seemed like plenty to go around for the entire world. Now, we know that is not enough, and the world has already <a href="https://en.wikipedia.org/wiki/IPv4_address_exhaustion">run out</a>! Chameleon owns and is able to lease a very very small subset of the global IP address space, and <a href="https://www.chameleoncloud.org/blog/2019/02/27/save-planet-use-fewer-ips/">we ask that you use them sparingly</a>, and release them when you no longer need them. If your experiment requires you to use multiple compute nodes, wouldn’t it be better to only use up a single public IP address instead of one for each node?</p>

<h2>What is bastion host and why should you use it?</h2>

<p>If your resources are a precious prize sought after by hackers, then there needs to be an effective way to limit their access. In medieval warfare, the inside of a fortress was protected by walls, guarded by a bastion. . In securing your experiments, a bastion host functions in the same way. A bastion host is a single host which exposes itself to the Internet, and allows other more-valuable or vulnerable hosts to be protected behind it. The goal of the bastion host is to limit the attack surface by only exposing one highly-secure service (SSH) to the Internet. That service also uses a single public IP address, and it gives you access to a secure tunnel over which you can communicate with your other nodes. Our <a href="https://www.chameleoncloud.org/blog/2019/02/27/save-planet-use-fewer-ips/">save the planet blog post</a> tells you exactly how.</p>

<p>To help you set up your first bastion host environment, we’ve published an <a href="https://www.chameleoncloud.org/blog/2022/09/26/experiment-patterns-making-complex-experiments-easy/">experiment pattern</a> on <a href="https://chameleoncloud.org/experiment/share/8e893a1e-4833-4a6b-b596-d046f12018ba">Trovi</a> which automatically deploys a basic bastion/worker cluster that can be easily tuned and extended for your experiment’s needs! At the end of the notebook, it provides a list of remote connections which can be used to securely dispatch jobs to all your workers, which is a great jumping off point for actual experimentation. </p>

<h2>Are my capabilities limited behind a bastion host?</h2>

<p>Not at all! Since you’re connecting to your workers via SSH, you have full shell access to your hosts. If you want to access a “web-facing” service running on your nodes, you can do that as well via an <a href="https://www.ssh.com/academy/ssh/tunneling">SSH tunnel</a>. You can also facilitate this process with excellent free tools like <a href="https://sshuttle.readthedocs.io/en/stable/manpage.html">sshuttle</a>. This is incredibly useful for accessing things like databases or incredibly-insecure-by-default protocols like <a href="https://en.wikipedia.org/wiki/Virtual_Network_Computing#Security">VNC</a>. There is basically zero reason not to use an SSH tunnel unless you are researching something which specifically prevents you from doing it.</p>

<h2>Can I do it without any extra work?</h2>

<p>We published a <a href="https://chameleoncloud.org/experiment/share/8e893a1e-4833-4a6b-b596-d046f12018ba">tutorial notebook</a> so that you don’t have to figure out how to set this up on your own. The simple explanation is that your project has one public-facing host (the bastion host) which accepts incoming connections via SSH. The SSH protocol is then able to use that connection to tunnel to your worker nodes securely behind a private network. Neat! With this notebook, you can tweak parameters, copy, cut, and paste to implement bastion host architecture in your own experiments with ease. Please, try it out for yourself, and as always, feel free to <a href="https://chameleoncloud.readthedocs.io/en/latest/user/help.html">reach out for help</a> if anything goes wrong.</p>

<h1>Happy experimenting!</h1>