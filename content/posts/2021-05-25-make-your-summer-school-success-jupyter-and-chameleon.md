---
abstract: "<p>Organizing a summer school, bootcamp or workshop this summer? Having\
  \ trouble finding a consistent and predictable environment? Learn all about how\
  \ to use the Chameleon JupyterHub artifact to configure resources (including GPUs!)\
  \ and create a shared Jupyter notebook computing environment that any event attendee\
  \ can use. You can manage users, deploy Chameleon resources, and use\_the Help Desk\
  \ throughout your event!</p>"
authors:
- Jason Anderson
categories:
- Tips and Tricks
date: '2021-05-25 18:17:53+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/6c/2e/6c2ead0c-6e6d-40ba-ae70-b47722718583/img_5889.jpeg
slug: make-your-summer-school-success-jupyter-and-chameleon
subtitle: ''
title: Make Your Summer School a Success with Jupyter and Chameleon
---

<p dir="ltr">Summer is often a time of Summer Schools, Bootcamps, and other hands-on workshops. Given that many of the spaces that would normally house such events (e.g., libraries, labs, community centers) remain shuttered due to the pandemic, event organizers now have to figure out how to run these events remotely. Providing a consistent and predictable environment to attendees is one of the biggest challenges here. Fortunately, Chameleon can help!</p>

<p dir="ltr">The <a href="https://www.chameleoncloud.org/experiment/share/1">Chameleon JupyterHub artifact</a> allows you to configure resources (including our GPU nodes for example) and create a shared Jupyter notebook computing environment that any event attendee can use. The artifact is actually also a Jupyter notebook! Its job is to describe the process of configuring a Jupyter environment for your event, including how to reserve resources on Chameleon, configure the JupyterHub server to your liking, and onboard attendees.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-23927911-7fff-0e87-2a51-08f0b02836d2">Why JupyterHub? </b></p>

<p dir="ltr">JupyterHub provides a multi-user environment where every attendee gets an isolated computing environment, which you can customize by pre-installing relevant tools or otherwise preconfiguring for the user. <a href="https://jupyterhub.readthedocs.io/en/stable/gallery-jhub-deployments.html">The list of events and institutions leveraging the platform for education and events</a> is large, and growing!</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-23927911-7fff-0e87-2a51-08f0b02836d2">How can I manage users for my workshop? </b></p>

<p dir="ltr">When you first set up the JupyterHub server, you will have one admin account for an event organizer. Additionally, the JupyterHub server will accept open registration; any user can register for an account, but they must be approved by the admin user. This allows attendees to easily self-register, but adds a low-touch level of control for the organizer.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-23927911-7fff-0e87-2a51-08f0b02836d2">My workshop needs persistent data, how can I manage data for my workshop? </b></p>

<p dir="ltr">The artifact contains instructions on how to share data sets or other files to all attendee environments. Additionally, you can snapshot the entire JupyterHub environment to preserve the state of the user database and all user home directories.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-23927911-7fff-0e87-2a51-08f0b02836d2">Should I use KVM or bare metal resources for my workshop? </b></p>

<p dir="ltr">Chameleon provides both a <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm.html">KVM</a> and a <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/baremetal.html">bare metal cloud</a>. KVM is better-suited to longer-running events, such as a Summer School, as there are no policy restrictions on how long the resources can be allocated to your project. However, virtual machines provisioned on the KVM cloud will not have access to more specialized hardware such as GPUs, and are overall less powerful than a bare metal instance. The bare metal cloud requires reserving resources in advance due to demand, and limits reservations to 7 days (renewable as long as no other user has made a reservation following yours). For this reason, it is better-suited to shorter events, or else you must re-create the environment several times, leveraging <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images.html?highlight=snapshot#the-cc-snapshot-utility">snapshots</a> for example.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-23927911-7fff-0e87-2a51-08f0b02836d2">My workshop requires a cluster, how should I handle this situation? </b></p>

<p dir="ltr">The best way to structure such an event is to provision the cluster and JupyterHub separately. The added benefit is that you could use, e.g., the bare metal cloud for the cluster, leveraging the powerful hardware there, and then use KVM for the JupyterHub server, taking advantage of the longer shelf-life of instances provisioned there. Attendees can then connect to your cluster from their Jupyter environment.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-23927911-7fff-0e87-2a51-08f0b02836d2">My workshop requires more than one week and/or takes place one day a week over consecutive weeks and the Chameleon lease is 7 days: what is the best way to handle that? </b></p>

<p dir="ltr">If your workshop follows a model where attendees are interacting with a cluster that accepts jobs, e.g., MPI or Slurm, then you can consider splitting the cluster environment from the JupyterHub server, as explained for a prior question. Otherwise, you can use Chameleon's <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images.html?highlight=snapshot#the-cc-snapshot-utility">snapshot utility</a> to archive the configured JupyterHub server, and then re-instantiate it via Chameleon's GUI or CLI. In this case it may also make sense to make a separate lease for a Floating IP (public IP) address. Floating IP addresses are less in demand, and it is likely you would be able to preserve a single address for the duration of your event, removing the need to repeat some setup, e.g., generating SSL certificates for your server's new address.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-23927911-7fff-0e87-2a51-08f0b02836d2">What type of support can I rely on from the Chameleon team and what kind of support will I be providing myself? </b></p>

<p dir="ltr">The Chameleon JupyterHub artifact is supported by Chameleon operators, which means that you can use the Help Desk to ask questions, get advice about what configuration you should use, and report problems with the setup process. However, Chameleon cannot provide support for the event itself, including support for specific software or libraries you will require or issues experienced by attendees. As with support we give for experimenters, Chameleon provides the platform and the capability: what you build with it is ultimately your responsibility. That said, we always like to at least hear about what you did and how it went!</p>