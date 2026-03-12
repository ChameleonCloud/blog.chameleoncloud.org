---
abstract: <p>Learn all the do's and don'ts of keeping your experiment server secure
  to maximize your experiment time!</p>
authors:
- Jason Anderson
categories:
- Tips and Tricks
date: '2021-06-28 23:15:55+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/3f/f5/3ff5a652-a869-45f9-8d9f-9deb313c50f8/img_5895.jpeg
related_posts: []
slug: best-practices-making-your-experiments-secure
subtitle: ''
title: Best Practices for Making Your Experiments Secure
---

<p dir="ltr">So your experiment server has been hacked. Not only is this a bit embarrassing, it can lead to your experiments being terminated by Chameleon support staff (to prevent further infection or malicious traffic), and you can lose valuable time setting things up securely again! Furthermore, if there is a pattern of bad security hygiene, we may need to disable your account to prevent future incidents.</p>

<p dir="ltr"> </p>

<p dir="ltr">It doesn't have to be this way! In fact, there are a few simple steps you can take to ensure that your experiment environment is as secure as possible. Here are a few do's and don'ts to keep in mind.</p>

<p dir="ltr"> </p>

<p dir="ltr"><strong>DO change the passwords.</strong> If you are basing your experiment on an image or software downloaded from the internet with a well-known default or admin password, change it! Consider that you move into a new apartment, and the key to your front door has already been copied by everybody in the city. Wouldn't you feel more comfortable changing the locks?</p>

<p dir="ltr"> </p>

<p dir="ltr"><strong>DO NOT change firewall rules or other security defaults. </strong>All Chameleon instances that are built using the Chameleon base images (for, e.g. CentOS or Ubuntu) come pre-configured with SSH settings and a <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/networks/networks_basic.html#firewall">firewall policy</a> that is designed to protect your experimental environment from intrusion. In particular, do not alter SSH to allow password authentication; use strong public/private key pairs instead.</p>

<p dir="ltr"> </p>

<p dir="ltr"><strong>DO use a bastion host for sensitive experiments. </strong>Sometimes you need to run software you know is insecure, but you don't have a choice, because you need to test a specific version or configuration. In this case, it is useful to reserve an additional node to serve as a <a href="https://www.chameleoncloud.org/blog/2019/02/27/save-planet-use-fewer-ips/">login bastion</a>. The bastion is the only host that needs a public IP address; after connecting to the bastion, you simply jump through to other hosts on your private network from there. Pro tip: a bastion is also a good pattern to follow on a multi-node cluster setup! While it's possible to assign public IP addresses to each node in a multi-node cluster, this is wasteful (we only have so many public IPs!) and unnecessarily exposes each node to intrusion. Instead, designate a single node to be your login bastion and always log in to your cluster from that node.</p>

<p dir="ltr"> </p>

<p dir="ltr"><strong>DO NOT leave internet-facing services running longer than necessary. </strong>Automated scanners (e.g. <a href="https://www.shodan.io/">Shodan</a>) are running constantly to find and exploit new services that appear on the web. For a humorous demonstration of this, refer to <a href="https://www.theatlantic.com/technology/archive/2016/10/we-built-a-fake-web-toaster-and-it-was-hacked-in-an-hour/505571/">this Atlantic article</a> describing how a fake IoT toaster was hacked within an hour of making its internet debut. Combined with the tendency of security researchers and black hat hackers to find application/framework vulnerabilities at an impressive pace, it logically follows that keeping any service on the web for some significant amount of time presents risk. Therefore, consider shutting down any internet-facing applications when you're not using your node. If you want an automated solution, you could leverage the <a href="https://www.gnu.org/software/bash/manual/bash.html#Invoked-as-an-interactive-login-shell_002c-or-with-_002d_002dlogin">.bash_logout file</a>, which allows configuring commands to run when you log out of the machine.</p>

<p dir="ltr"> </p>

<p dir="ltr"><strong>DO NOT bind web services on all interfaces unless absolutely necessary</strong>. Most web services can be configured to listen on only a specific IP address, but some default to listening on, e.g., 0.0.0.0, which effectively means "any address". What this means in practice is that a server that you may think is only running locally can actually be reached over the internet! Ensure that your application/service is set to only listen on a local loopback address (127.0.0.1) to avoid this, or at least set it to a private IP address on your network.</p>

<p dir="ltr"> </p>

<p dir="ltr">As Ben Franklin said, an ounce of prevention is worth a pound of cure. So it is with network security: by taking a few steps, thinking about risk, and using tools already at your disposal, you can ensure your experiments are properly secured, now and in the future.</p>