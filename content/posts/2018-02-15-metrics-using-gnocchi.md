---
abstract: <p>One of Chameleon's newest features is metrics using Gnocchi. In this
  post, we will cover how to quickly get started with Gnocchi, including how to access
  collected metrics and customize which metrics are reported from your Chameleon instances.</p>
authors:
- Joon Yee Chuah
categories:
- Tips and Tricks
date: '2018-02-15 17:14:51+00:00'
featured: false
hide_image: true
image: ''
related_posts: []
slug: metrics-using-gnocchi
subtitle: ''
title: Metrics using Gnocchi
---

<p>Gnocchi is OpenStack's "Metrics-as-a-Service" component. Gnocchi is currently available on Chameleon resources at the University of Chicago, and will be online soon at Texas Advanced Computing Center. Chameleon images (<a href="https://www.chameleoncloud.org/appliances/1/">CC-CentOS7</a> and <a href="https://www.chameleoncloud.org/appliances/19/">CC-Ubuntu</a>) are already configured to send metrics to Gnocchi. Gnocchi is the service which aggregates metrics that are sent to it from Chameleon instances that are running the <code>collectd</code> service. We can access Gnocchi and retrieve metrics through a command line client or programmatically.</p>

<p> </p>

<h3>Configuring Your Instance</h3>

<p>Conveniently, there is not much to configure after you launch an instance. If you are using CC-CentOS7 or CC-Ubuntu-16.04, everything works "out of the box." Let's say that we've launched a CC-CentOS7. On the instance details page in the GUI, it lists the instance's UUID.</p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/7c/c4/7cc432c8-c98d-4b23-b6af-0f0613d0c098/gnocchi_details.png"></p>

<p>In this case, my instance's UUID is <code>304dc702-c57a-471c-81df-6e711d793e50</code>. This UUID will be used to identify the instance within Gnocchi. Write this down for later!</p>

<p>The CC-CentOS7 appliance comes with the <code>collectd</code> service installed. <code>collectd</code>  is preconfigured to collect metrics from the system and send them to the Gnocchi. I can see that it is running by typing <code>sudo systemctl status collectd</code> at the prompt. This is the response:</p>

<p> </p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/76/c2/76c2942f-2632-440e-9b5c-da8b8af1264f/collectd_status.png"></p>

<p> </p>

<p>By default, CC-CentOS7 reports minimal metrics such as network usage. You may load additional plugins by editing <code>/etc/collectd.conf</code> and uncommenting any of the LoadPlugin lines.</p>

<p> </p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/27/7c/277cf087-801a-4f1c-a7b2-e39752885a79/collectd_conf.png"></p>

<p> </p>

<p>After editing the configuration file, you can restart the service with <code>sudo systemctl restart collectd</code></p>

<h3>The OpenStack Client</h3>

<p>Your metrics are stored and aggregated on Chameleon. Aggregation does not occur in real time, so it may take a while for the latest metrics to become available. However, all metrics are stored as they are reported so don't worry about losing measurements. To access the metrics from your local machine, first we need to install the OpenStack client using Python Pip. You can do this with <code>pip install python-openstackclient</code>.</p>

<p>To access your Project using the OpenStack CLI, we need to configure environment variables that allow us to access our project. If you are using macOS or a Linux based shell (or the Ubuntu shell in Windows 10) you can download your Project's OpenStack RC file. From within the GUI, click on the dropdown with your username in the upper right corner and click the <em>OpenStack RC File v3</em> link. </p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/5b/98/5b98db34-61b9-430a-be1f-3a7e901eaba0/openstack_rc.png"></p>

<p>This will download a file with your project name on it. In my case, my filename was <code>CH-819507-openrc.sh</code>. Now we can run it using <code>source CH-819507-openrc.sh</code>. You will be prompted to enter in your Chameleon password. Now you can open the OpenStack client by typing <code>openstack</code> into your terminal.</p>

<p>Retrieving Metrics</p>

<p>Each instance that you launch is a <em>resource</em> in the OpenStack client. If you want to view a list of resources, you can type <code>metric resource list</code>. You will be presented with a table that lists resource UUIDs. Since we have the UUID of the instance, we can jump straight to a list of metrics collected from the instance by typing <code>metric resource show <i>&lt;uuid&gt;</i></code>.</p>

<p> </p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/d8/72/d8729668-b3fb-4129-8e7c-fd7617132878/resource_show.png"></p>

<p> </p>

<p>Each metric has a name and UUID. You can display the individual metric timestamps and values by typing in <code>metric measures show <i>&lt;uuid&gt;</i></code> where <code><i>&lt;uuid&gt;</i></code> is the UUID of the metric. (Not the resource!) </p>

<p> </p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/d1/52/d152904b-e2ae-4429-84f8-3798957ee966/measures_show.png"></p>

<p> </p>

<h3>Summary</h3>

<p>This is a simple introduction to Gnocchi's capabilities. Gnocchi also has an associated Python package for accessing and storing metrics. You can view <a href="https://gnocchi.xyz/">Gnocchi's documentation</a> for more details.</p>
