---
abstract: '<p><span id="docs-internal-guid-520b1bd6-e360-7619-b325-e727e1207ff6">Did
  you ever find yourself spending half of your 7 day lease iterating on the environment
  configuration for your experiment and worried that the remaining 4 days are not
  enough to run it? If so read on: we are aware that configuring your experimental
  environment can be a bit of a journey and have packed the system with tools and
  features that will make it smoother. </span></p>'
authors:
- Kate Keahey
categories:
- Tips and Tricks
date: '2018-03-01 21:54:40+00:00'
featured: false
hide_image: true
image: ''
related_posts: []
slug: how-make-most-your-seven-day-lease
subtitle: ''
title: How to Make the Most of your Seven Day Lease
---

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;">Did you ever find yourself spending half of your 7 day lease iterating on the environment configuration for your experiment and worried that the remaining 4 days are not enough to run it? If so read on: we are aware that configuring your experimental environment can be a bit of a journey and have packed the system with tools and features that will make it smoother.</p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-520b1bd6-e361-2b0b-f1c0-4d5cd0f6b0ff">The tips below will help you not only make the most of your 7-day lease but also help package your work so that you can come back to it months afterwards, easily share it with your collaborators, or provide it as a starting point for others wanting to reproduce it or build on it. If you want to amend them -- or if you have other ideas on how to make the most of your 7 day lease and would like to share them with others -- please, comments on this post.  </span></p>

<p> </p>

<p dir="ltr"><span id="docs-internal-guid-520b1bd6-e361-2b0b-f1c0-4d5cd0f6b0ff">Tips and tricks to make the most of your 7-Day lease:</span></p>

<p> </p>

<ol style="margin-top: 0pt; margin-bottom: 0pt;">
	<li dir="ltr">
	<p dir="ltr">Use appliances/images from the <a href="https://www.chameleoncloud.org/appliances/">appliance catalog</a> or take a look at the many appliances that our users made public on the Glance image repositories at <a href="https://chi.tacc.chameleoncloud.org/dashboard/project/images">TACC</a> and <a href="https://chi.uc.chameleoncloud.org/dashboard/project/images">UC</a> -- many of them already come with popular libraries or applications like CUDA, TensorFlow, or MPI installed -- starting out with something that takes you 50% of the way will make your work easier and faster.</p>
	</li>
</ol>

<p> </p>

<ol start="2" style="margin-top: 0pt; margin-bottom: 0pt;">
	<li dir="ltr">
	<p dir="ltr">When you modify your image by installing something on it <a href="https://www.chameleoncloud.org/advanced-configure-and-interact/#toc-snapshot-an-instance">snapshot it</a> often: this saves a new image that contains all the hard work you put into configuration so far. You can boot from this image whenever you create a new lease so no configuration work will have to be repeated. You can also share your image with collaborators and colleagues who build on or extend your work. Did you know that the exact same image can be used at both UC and TACC? This means that if your preferred site or resource is not available you can still start your configuration work, snapshot the image, and then upload and deploy it on your site/resource of choice. If you take many snapshots as your experimental setup evolves, we recommend using e.g., a date stamp as part of the name to tell them apart -- you should consider periodically culling the images you no longer need.</p>
	</li>
</ol>

<p><br>
 </p>

<ol start="3" style="margin-top: 0pt; margin-bottom: 0pt;">
	<li dir="ltr">
	<p dir="ltr"><a href="https://www.chameleoncloud.org/docs/complex-appliances/" style="">Use orchestration to deploy complex appliances</a> such as <a href="https://www.chameleoncloud.org/appliances/11/">OpenStack installation</a> or <a href="https://www.chameleoncloud.org/appliances/25/">NFS cluster</a>. Configuring complex appliance deployments, such as virtual clusters, frequently requires finishing the configuration steps at deployment time to e.g., configure information about IP addresses or hostnames of the components. The orchestrator will allow you to streamline the process so that the your virtual cluster gets deployed correctly every time, even if the hots change. The two examples we use -- OpenStack and NFS cluster -- are already available from our <a href="https://www.chameleoncloud.org/appliances/">appliance catalog</a> but you may configure many others! If you don’t want to use the orchestrator you can try scripting (Bash, Perl, Python, etc.) or configuration management tools (Ansible, Puppet, Chef, etc.)</p>
	</li>
</ol>

<p> </p>

<ol start="4" style="margin-top: 0pt; margin-bottom: 0pt;">
	<li dir="ltr">
	<p dir="ltr">Did you know that you can <a href="https://www.chameleoncloud.org/provision-resources/">easily extend your lease for another week</a>? Every Chameleon lease can be extended for another 7 days within 48 hours of its expiration -- unless of course somebody made an advance reservation for just that time. Even then, if there are equivalent resources elsewhere in the system you can email them and ask them to release the resources to you. In exceptional circumstances when this does not work, you can also ask us directly to make an exception for a particular lease -- to do so you will need to <a href="https://www.chameleoncloud.org/user/help/ticket/new/">open a ticket</a>.</p>
	</li>
</ol>

<p> </p>

<ol start="5" style="margin-top: 0pt; margin-bottom: 0pt;">
	<li dir="ltr">
	<p dir="ltr">Once you have created an image for your experiment, remember to publish it. If your image is of general usefulness, e.g., if you work on popular tools like workflow systems, databases, or visualization systems, having it easily available as a Chameleon appliance may help others get started (see #1 above). If your image is very specfic to your work, it may help others reproduce what you have done.</p>
	</li>
</ol>

<p> </p>

<p dir="ltr">Do you have any tips and tricks that you use to make the most of your Chameleon leases that you would like to share with others?</p>

<div> </div>
