---
abstract: "<p>Have you completed the Chameleon Getting Started guide and are wondering\
  \ what comes next? This post will help you dive deeper by moving beyond the basics.\
  \ You will learn how to interact with the Chameleon API from the command line on\
  \ an instance and from your laptop. We'll also cover how to use tools like\_rclone\
  \ and cc-snapshot to securely save and manage your valuable research data.</p>"
authors:
- Paul Marshall
categories:
- Tips and Tricks
date: '2025-08-18 20:50:44+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/51/1d/511d0d87-5ae4-4457-8121-e713be049c5f/chameleon-at-work.png
slug: back-to-school-graduating-from-the-getting-started-guide
subtitle: 'Beyond the Basics: A Guide to the Command Line and Data Management'
title: 'Back to School: Graduating from the Getting Started Guide'
---

<p>You've read the Chameleon <a href="https://chameleoncloud.readthedocs.io/en/latest/getting-started/">Getting Started guide</a> and might be wondering: what comes next?</p>

<p>First, give yourself a high five for completing the first step.</p>

<p>Now, let's get back to school and dive a little deeper, moving beyond the basics. We’ll use some pre-populated credential files to interact with the API from a Chameleon instance and then we’ll download a set of application credentials to interact with it from our laptop. Then we’ll leverage tools on Chameleon images like <code>rclone</code> and <code>cc-snapshot</code> to securely save and manage your data.</p>

<p>By the end of the Getting Started guide you've launched an instance, allocated and attached a floating IP, and signed in via SSH as the cc user (the default user on Chameleon-supported images). If you've read some of our previous posts like <a href="https://chameleoncloud.org/blog/2025/05/19/leveraging-new-and-improved-chameleon-images/">Leveraging New and Improved Chameleon Images</a>, which discuss the contents of a Chameleon image, you'll know that we include a few special ingredients to make life with Chameleon a bit easier.</p>

<h2>API Authentication</h2>

<p>One of those ingredients is a credential file named <code>openrc</code> that you'll find in the home directory of the <code>cc</code> user. The <code>openrc</code> file contains credentials you need to interact with the Chameleon OpenStack APIs. This lets you level up from using the web interface to the command line or Python, where you can inspect resources in more detail and begin scripting against Chameleon.</p>

<p>To use it you need to source the file:</p>

<pre><code> source ~/openrc
</code></pre>

<p>After that you'll be authenticated so you can use the <code>openstack cli</code> (pre-installed in Chameleon images) for interacting with the APIs. One thing to note: the credentials in the <code>openrc</code> file are only valid for 24 hours once they have been generated. After that you may see an error like <code>Could not recognize Fernet token (HTTP 404)</code>. If your credentials expire, simply run the <code>cc-generate-openrc</code> command to generate a new set, then <code>source ~/openrc</code> again to use them.</p>

<p>You can explore more about the node you are on:</p>

<pre><code> openstack reservation host show node id
</code></pre>

<p>List different images you could launch:</p>

<pre><code> openstack image list
</code></pre>

<p>And many, many more tasks that we’ll leave as an <a href="https://docs.openstack.org/python-openstackclient/latest/">exercise to the reader</a>.</p>

<p>The <code>openrc</code> file and pre-installed OpenStack commands in Chameleon images are handy when you are SSH'd into an instance. However, given that instances are somewhat ephemeral with time-bound leases and your laptop isn't, you may also want to have a set of credentials locally and install the OpenStack clients on your laptop. This allows your laptop to function as a "control center" for Chameleon resource interactions. You can develop and execute your workflows from your laptop against different Chameleon regions to meet your infrastructure needs. The best way to grab a set of credentials for your laptop is to login to the web interface and browse to Identity -&gt; Application Credentials.</p>

<p><img src="https://chameleoncloud.org/media/filer_public/09/4f/094f2ca4-6384-4bb3-ad7c-52f58a056f8d/app_creds.png"></p>

<p>From there you can create a set of application credentials, give it a reasonable expiration date a few months out, and then download the file. You'll want to put the credentials in a file called <code>~/.config/openstack/clouds.yaml</code>.</p>

<p>That file has a basic format of:</p>

<pre><code> clouds:
  cloud name:
    credentials
</code></pre>

<p>To use the credentials you can set the environment variable <code>OS_CLOUD</code> to the name of the cloud you want to use.</p>

<p>If your file looks like:</p>

<pre><code> clouds:
  chi_uc:
    credentials
</code></pre>

<p>You would set <code>export OS_CLOUD=chi_uc</code> to have your OpenStack clients use those credentials.</p>

<h2>Saving Your Data</h2>

<p>Now that you're ready to use your instance for your actual research, you'll want to make sure you know how to save your work. Remember, the instance is running with a time-bound lease that will eventually expire. If it expires before you save your work off-instance Chameleon will delete your instance and you'll lose your work! Of course, you can transfer your data off the instance any way you like: copy/paste it, scp it, whatever works. But we've included two built-in methods that make saving your data on Chameleon a breeze.</p>

<p>First, we bundle <code>rclone</code> into the image and which allows you to mount containers from the object store into the home directory of the cc user on boot. The mount point appears in a directory called <code>cc_my_mounting_point</code> from the home directory of the <code>cc</code> user.</p>

<p>To mount a container into that directory you can run:</p>

<pre><code> cc-mount-object-store start your_container_name
</code></pre>

<p>Check that the mount is running with:</p>

<pre><code> cc-mount-object-store status your_container_name
</code></pre>

<p>List all of your running mounts with:</p>

<pre><code> cc-mount-object-store list
</code></pre>

<p>And stop the mount with:</p>

<pre><code> cc-mount-object-store stop your_container_name
</code></pre>

<p>If a container is not mounted for some reason there will be an empty file named <code>THIS_IS_NOT_MOUNTED</code> in the directory, letting you know that saving files to that directory won't copy them to the object store. Please keep in mind it is your responsibility to double check that the files you copy into these directories are actually uploaded to the object store and contain the data you expect.</p>

<p>The second method for saving data is to use the <code>cc-snapshot</code> tool that is bundled in the image and lets you take a snapshot of your running instance, saving it as a new image to Glance. Once the image is in Glance you can boot new instances with the image and when they come up they'll have all of your data.</p>

<p><img src="https://chameleoncloud.org/media/filer_public/bc/81/bc817fab-2bbb-4d48-b397-f2477d25c513/images.png"></p>

<p><small>In the Chameleon web interface you can find the images under Compute -&gt; Images and then search for the image with the name you provided</small></p>

<p>It's important to note that if you have sensitive data you shouldn't make the image public since that will allow any Chameleon user to boot it and access your data. Again, remember to verify your disk images, don’t just assume everything was saved and uploaded as you expect! It’s best practice to verify any data you save to make sure it was saved correctly.</p>

<p>It's typically optimal to use rclone when working on a project with frequent updates or iterations, allowing you to efficiently sync and save your work in a lightweight manner. Creating a snapshot on the other hand is better to capture the entire state of your environment--such as creating a reproducible base for future experiments, sharing a complete setup with others, or solidifying a stable milestone with your experiment.</p>

<h2>Trovi Artifacts and Tutorials</h2>

<p>After you’ve set up instances for your own work, it may be worthwhile to explore more advanced artifacts and tutorials some of Chameleon’s power users have contributed for the benefit of the community.</p>

<p><img src="https://chameleoncloud.org/media/filer_public/7d/e4/7de46b7a-032f-4b92-826f-03a26069dc83/trovi.png"></p>

<p>Some great examples include other ways of saving your data with persistent storage in the <a href="https://chameleoncloud.org/learn/tutorials/persistent-storage-chameleon">Persistent storage on Chameleon tutorial</a>. There are also examples and tutorials for using Chameleon for machine learning through a variety of tutorials:</p>

<ul>
	<li><a href="https://chameleoncloud.org/learn/tutorials/build-mlops-pipeline">Build an MLOps Pipeline</a></li>
	<li><a href="https://chameleoncloud.org/learn/tutorials/evaluation-ml-systems-closing-feedback-loop">Evaluation of ML systems by closing the feedback loop</a></li>
	<li><a href="https://chameleoncloud.org/learn/tutorials/offline-evaluation-ml-systems">Offline evaluation of ML systems</a></li>
	<li><a href="https://chameleoncloud.org/learn/tutorials/online-evaluation-ml-systems">Online evaluation of ML systems</a></li>
	<li><a href="https://chameleoncloud.org/learn/tutorials/system-optimizations-serving-machine-learning-models">System optimizations for serving machine learning models</a></li>
</ul>

<p>And some particularly advanced tutorials even cover some of the more exotic aspects of Chameleon using edge devices, specifically, the tutorial: <a href="https://chameleoncloud.org/learn/tutorials/serving-machine-learning-models-edge-devices">Serving machine learning models on edge devices</a>.</p>

<h2>Feedback</h2>

<p>With these tips and tricks added to your toolkit you're ready to start the new school year and level up your experience on Chameleon, using it to its full potential for your research. As always, reach out to us at the <a href="https://chameleoncloud.org/help">help desk</a> if you have any questions or run into any problems.</p>

<p>We're looking forward to hearing about all the exciting discoveries from our users this year. Finally, we hope if you dig a bit deeper into Chameleon you’ll consider creating your own Trovi artifacts, whether they’re experiments, tutorials, or other resources, to share with the community!</p>