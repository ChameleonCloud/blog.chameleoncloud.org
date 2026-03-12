---
abstract: "<p>Recognizing the need for easier modification of running containers,\
  \ we\u2019ve introduced a straightforward method for SSHing into CHI@Edge containers,\
  \ enhancing your development and experimentation processes. Our new tutorial on\
  \ Trovi helps you create an SSH-ready base container, extending the CHI@Edge \u201C\
  hello world\u201D example to enable remote access. This allows you to troubleshoot,\
  \ configure, and update containers as if they were real servers. Access the tutorial\
  \ via the CHI@Edge dashboard, and start developing with enhanced flexibility and\
  \ ease.</p>"
authors:
- Soufiane Jounaid
categories:
- Tips and Tricks
date: '2024-05-21 16:47:55+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/e6/ee/e6ee63f7-f3de-4395-9a1d-efe4509ceb8a/pxl_20210528_221216206.jpg
related_posts:
- slug: chiedge-transitioning-from-successful-preview-to-full-production
  title: 'CHI@Edge: Transitioning from Successful Preview to Full Production'
- slug: chiedge-community-workshop-report
  title: CHI@Edge Community Workshop Report
- slug: chiedge-webinar
  title: CHI@Edge Webinars
slug: seamless-ssh-container-access-with-chiedge
subtitle: Simplifying Your Development Process
title: Seamless SSH Container Access with CHI@Edge
---

<p><em>As we mentioned in our <a href="https://chameleoncloud.org/blog/2024/04/15/chiedge-transitioning-from-successful-preview-to-full-production/">previous blog post</a>, CHI@Edge is now in production with all the improvements and insights that we learned from early users during its preview. To kick off this new era of Chameleon, we will publish a series of Tips&amp;Tricks blogs on CHI@Edge features (some to be released soon) in the coming months. Stay tuned to our blog!</em></p>

<p style="text-align: center;"><img src="https://chameleoncloud.org/media/filer_public/2d/77/2d771b7b-e0bc-4c2e-9f89-c1a62bb5c695/pxl_20230324_233723016.jpg"></p>

<p> </p>

<p>The primary way to schedule workloads on <a href="https://chameleoncloud.org/experiment/chiedge/">CHI@Edge</a> devices is through containers. The Chameleon team chose a container-focused architecture due to its simplicity and versatility. Users can build containers declaratively through Dockerfiles and run them on edge devices in a reproducible manner. To achieve our design, we built CHI@Edge on a <a href="https://kubernetes.io/">Kubernetes</a> backend that is largely stateless. However, we’ve observed through years of preview that experiment setups are almost never achieved without some back-and-forth tinkering; researchers need the ability to modify running containers on CHI@Edge in a simple, familiar, and straightforward manner.</p>

<p>Currently, users can access containers through a web console in the CHI@Edge dashboard. However, it can suffer from visual issues, such as a character-on-line limit, and is sometimes slow to use, which does not contribute much to a smooth user experience. To improve container access, we are releasing a new method that relies on a familiar and trusted tool: SSH. Now, in addition to using the web console, you can SSH into running containers on CHI@Edge, making your development and experimentation smoother, faster, and more customizable.</p>

<h3>Simplifying the Development Process</h3>

<p style="text-align: center;"><img src="https://chameleoncloud.org/media/filer_public/95/af/95af96ab-3473-483b-a467-0161d5a7b109/image3.png" width="60%"></p>

<p>So, how do we enable SSH access? Most containers are very minimal. They don’t come with common utilities like an SSH server or other niceties that would allow remote login. Containers are intended to be run and thrown away, not modified or logged into. However, lots of common development tools and workflows can use SSH to treat a remote server as if it were a local one, making for a nice development experience.</p>

<p>To help you tap the potential of these workflows on CHI@Edge - and treat your container more like it was a real server - we have a new tutorial designed to walk you through the process of creating a base container that is SSH-ready. This tutorial extends our “hello world” example to install SSH into a container, and then SSH to it like it was a “real” server. User workloads can then be built on top of this base container.</p>

<h3>How to Get Started</h3>

<p style="text-align: center;"><img src="https://chameleoncloud.org/media/filer_public/85/44/854488ec-4808-4d97-8a53-c94ab51c5087/image1.png" width="60%"></p>

<p>Follow these simple steps below to learn more about how to configure your container to enable SSH and use the protocol for container access.</p>

<ol>
	<li><strong>Log in to CHI@Edge</strong>: Access your edge devices through the <a href="https://chi.edge.chameleoncloud.org/project/container/containers">CHI@Edge dashboard</a> on the Chameleon portal.</li>
	<li><strong>Follow the Tutorial</strong>: Use our <a href="https://www.chameleoncloud.org/experiment/share/4b08e80c-df0a-4866-bf29-19b5ad6a2950">Jupyter tutorial</a> to guide yourself through the steps to create an SSH-ready container. You can launch the artifact like any other Trovi artifact.</li>
	<li><strong>Start Developing</strong>: Once you have access, you can begin troubleshooting, configuring, monitoring, or updating your container as needed.</li>
</ol>

<h3>Conclusion</h3>

<p>At CHI@Edge, we are committed to enhancing your development experience. Our new tool for SSHing into running containers is designed to provide you with the familiar access you need, when you need it, without the complexity. For more detailed instructions, check out our comprehensive <a href="https://www.chameleoncloud.org/experiment/share/4b08e80c-df0a-4866-bf29-19b5ad6a2950">Jupyter tutorial</a>. If you have any questions or need further assistance, don’t hesitate to reach out to our support team.</p>

<p>It bears noting that the web console will still be available for use and may remain the preferred access point for your projects, depending on your experiment needs. Be aware that SSH access can consume more resources than using the web console. Additionally, SSH access will work only with containers that you have configured to enable SSH, while you can use the web console to access any container regardless of configuration. The console is still a great option for people who just need to try something quickly in a container.</p>

<p>Happy researching!</p>