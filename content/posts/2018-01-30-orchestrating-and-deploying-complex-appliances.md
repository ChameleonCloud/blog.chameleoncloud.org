---
abstract: "<p>If you are a distributed systems, networking or HPC researcher, you\
  \ may be interested in Chameleon's Orchestration capabilities. Orchestration allows\
  \ you to perform \"one click\" deployment of\_<em>Complex Appliances</em>\_- clusters\
  \ of bare metal machines with user defined networking.</p>"
authors:
- Joon Yee Chuah
categories:
- Tips and Tricks
date: '2018-01-30 15:46:34+00:00'
featured: false
hide_image: true
image: ''
slug: orchestrating-and-deploying-complex-appliances
subtitle: ''
title: Orchestrating and Deploying Complex Appliances
---

<p>Configuring a cluster manually can be very time consuming. Every host needs to be aware of other hosts, and SSH keys must be distributed to allow access. Chameleon implements OpenStack's Heat Orchestration to solve this problem. With "one-click" you could deploy a cluster with user defined networking. Some use cases are:</p>

<ul>
	<li>A server node and several client node</li>
	<li>An MPI cluster across Infiniband nodes</li>
	<li>Several hosts on different subnets with routing between them</li>
</ul>

<h3>Complex Appliance Examples</h3>

<p>We call these clusters <em>Complex Appliances. </em>Where a "simple" appliance would be a single bare-metal node, a <em>Complex Appliance</em> may feature several nodes. You can view some examples of pre-written complex appliances on the Chameleon Cloud portal's <a href="https://www.chameleoncloud.org/appliances/">Appliance Catalog</a>. Complex appliances are marked with the cluster badge in the upper right corner:</p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/f0/9f/f09f3636-5f8f-4007-89a9-6c74c861bbe8/appliance_badge.png"></p>

<p>Let's check out the <a href="https://www.chameleoncloud.org/appliances/25/">NFS Share complex appliance</a>. When launched, this appliance will feature:</p>

<ul>
	<li>A server with an NFS export</li>
	<li>A user specified number of clients</li>
	<li>Automatic configuration of clients that mount the server's NFS export</li>
	<li>SSH keys configured on all hosts</li>
</ul>

<h3>Templates</h3>

<p>Most of the work is actually done using a Heat Orchestration Template - a YAML file that specifies which components to use to launch the entire complex appliance. If you click on the <a href="https://www.chameleoncloud.org/appliances/api/appliances/25/template">Get Template</a> link from the appliance description, you can see the contents of the template. </p>

<p>How do we get this template into Chameleon? You have several options. You could download it to your local computer and upload it to the dashboard, or simply copy and paste the contents directly into the dashboard. These options are good if you need to modify an existing template. Alternatively, you can speciy a URL in the dashboard and let Chameleon find it on the Internet. This is what we're going to go with since we are working with a template that has been posted on Chameleon's Appliance Catalog.</p>

<h3>Launching on the Dashboard</h3>

<p>Let's go ahead and log in to the dashboard to launch this template. First, you will need a reservation for at least two nodes - one for the server and one for each client. Assuming that you have made this reservation, we can next go to the Stacks tab by clicking Project &gt; Orchestration &gt; Stacks.</p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/89/ab/89ab3621-fa58-4b75-be7b-c4e40a91afe9/stacks.png"></p>

<p>You can now start the launching process simply by clicking the <em>Launch Stack</em> button. "Stack" is OpenStack's terminology for a multi-node Complex Appliance. The first dialog that you are presented with allows you to specify the template you are using. Remember that we are going to be using the direct URL to the template.</p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/77/6a/776a9e56-bb51-4299-9fb0-28a975b55ff6/launch_dialog.png"></p>

<p>Once you click "Next" the template will be read, verified for syntax correctness, and then you are presented with the parameters for launching this particular stack. First, you will need to specify a stack name and enter in your Chameleon password. The interesting thing about Heat templates is that the next few dialog options are parameters that are <em>specified by the template</em>. At a base minimum, Chameleon templates will require an SSH key parameter as well as a reservation parameter for scheduling and launching an accessible stack. You will notice that this particular template also includes a <i>Client Count</i> input parameter, used to generate any number of clients to connect to the NFS server. When you are writing your own templates, specifying input parameters allows you to make your Complex Appliance deeply reconfigurable by the user at launch time!</p>

<h3>Outputs</h3>

<p>When launching a Simple Appliance (such as a single bare-metal node from an image) you typically need to specify a floating IP. With Orchestration, the floating IP association process can be automated. This particular template ties a floating IP to the server and lists it as an "output." You can view all of the template's outputs by clicking on your Complex Appliance and clicking on the "Overview" tab.</p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/39/f2/39f2f2b6-95d5-4d93-a35a-4fc1ec09eb3d/launch_options.png"></p>

<h3>Next steps</h3>

<p>Chameleon supports a large number of features that can be orchestrated. An easy modification you can make to existing templates is to change the image name used to launch individual nodes. The template used in this example uses the <i>CC-CentOS7</i> image. You can also modify the startup scripts for each instance from within the template. However, this template only begins to touch on some of the options available from within Chameleon. Chameleon's capabilities also include orchestrating OpenStack's Neutron networking resources, including subnets with custom routing. You can view these resource types by clicking on Project &gt; Orchestration &gt; Resource Types.</p>
