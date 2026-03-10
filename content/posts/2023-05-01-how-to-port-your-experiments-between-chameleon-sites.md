---
abstract: <p>Chameleon's resources are distributed across multiple sites. If you'd
  like to move your work between sites, say to take advantage of different hardware,
  or to find available nodes, good news! It's pretty easy, and this post spells out
  the details.</p>
authors:
- Michael Sherman
categories:
- Tips and Tricks
date: '2023-05-01 18:10:42+00:00'
featured: false
hide_image: true
image: ''
slug: how-to-port-your-experiments-between-chameleon-sites
subtitle: Best practices for using resources across multiple sites
title: How to Port your experiments between Chameleon Sites
---

<p>Chameleon's resources are distributed across several sites, large and small. There are a few reasons you might want to move your work to a different site:<br>
First, while Chameleon has a lot of resources, each site has different hardware available, and if you developed an experiment to use the gpu_a100_pcie nodes at UC, you may want to see how it performs on the gpu_mi100 nodes at TACC instead. <br>
The second is a matter of availability: many kinds of resource are available at multiple sites, even if the “node_types” don’t match exactly. Nodes with Intel Skylake or Cascade Lake generation cpus, or with Infiniband are available at both UC and TACC, and moving your work lets you take advantage of these when one site is very busy, or has an outage. </p>

<p>All of your work is fundamentally portable between Chameleon sites. As all of the sites share a common API, and federated authentication, all that you need to do is pick a site, move the data that your experiment needs, and maybe update some names in your scripts.</p>

<h1>Finding Resources at each Site:</h1>

<p>The first question you might ask is, how can you find similar resources between sites? <br>
As always, the <a href="https://chameleoncloud.org/hardware/">Chameleon Resource Browser</a> is the “source of truth” for what resources are available at each site. Most “node_types” are unique to a given site, but many are similar, differing only by CPU generation or GPU model.<br>
You can drill down more finely by using the advanced filters instead of node types, as documented here: <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/discovery.html">Resource discovery — Chameleon Cloud Documentation</a></p>

<h1>Glance Images:</h1>

<p>Chameleon’s bare metal disk images will work across all Chameleon sites without any changes. In addition, good news: all of our basic <a href="https://chameleoncloud.org/appliances/">“supported images”</a> are already available at each site. If this is what you’re using, you’re already done!</p>

<p>However, if you’re using a custom image, e.g. created with <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images.html#the-cc-snapshot-utility">cc-snapshot</a>, you’ll need to copy it between sites yourself. To do so, you’ll need to download it from the first site, then upload it to the second. See the following docs pages for more:</p>

<ul>
	<li><a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images.html#managing-images-using-the-gui">Horizon: managing images using the gui</a></li>
	<li><a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images.html#managing-images-using-the-cli">CLI: managing images using the CLI</a></li>
</ul>

<h2>Worked example with the CLI</h2>

<p>This example assumes that you have downloaded <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/cli.html#cli-rc-script">openrc</a> files from UC and TACC, and changed names as needed. If you have a slow internet connection, you can run this from a chameleon node to speed things up!</p>

<p><code>#!/bin/bash</code></p>

<p><code># download from UC<br>
source uc-openrc.sh<br>
openstack image save my-snapshot --file my-snapshot.img</code></p>

<p><code># upload to TACC<br>
source tacc-openrc.sh<br>
openstack image create my-snapshot \<br>
  --container-format bare \<br>
  --disk-format qcow2 \<br>
  --file my-snapshot.img</code></p>

<h1>Persistent Data</h1>

<p>Your experiment might depend on, or generate, large amounts of data. We provide several tools to help you with this. In particular, CHI@UC and CHI@TACC each host an Object Store, and a Filesystem Share that you can use.</p>

<h2>Moving Object Store Data</h2>

<p>The object store at either site can be accessed over the WAN from anywhere, so why would you want to move this data? First, you’ll see improved performance if you access an object store “local” to your instances, instead of further away. Second, in the case of an outage, having a copy of your data elsewhere will keep it available for your use.</p>

<p>As with the glance images, you’ll need to download, then upload the data. See the docs at: </p>

<ul>
	<li><a href="https://chameleoncloud.readthedocs.io/en/latest/technical/swift.html#managing-object-store-using-the-gui">Horizon: Object Store, using the GUI</a></li>
	<li><a href="https://chameleoncloud.readthedocs.io/en/latest/technical/swift.html#managing-object-store-using-the-cli">CLI: Object Store, Using the CLI</a></li>
</ul>

<p>If you have a lot of data, either in large files, or many small files, it will be faster to use a Chameleon instance to do the sync instead of your local machine. This can be done using the CLI, or any swift compatible utility, such as <a href="https://rclone.org/swift/">rclone</a>.</p>

<h3>Example:</h3>

<p><code>#!/bin/bash</code></p>

<p><code># download from UC<br>
source uc-openrc.sh<br>
openstack object save my-container my-data.tar.gz</code></p>

<p><code># upload to TACC<br>
# creates object my.data.tar.gz in contianer my-container, from source file my-data.tar.gz</code></p>

<p><br>
<code>source tacc-openrc.sh<br>
openstack object create my-container my-data.tar.gz my-data.tar.gz</code></p>

<h2>Moving Filesystem Data</h2>

<p>Unlike the object store, the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/shares.html">shared filesystem is site-local</a>. Data stored in the filesystem shares can only be accessed by instances at that site that mount it. Therefore, if you need to move it to a different site, the easiest way is to use an instance to copy the data into the object store first, then follow those instructions to move it to the other site.</p>

<h2>I just have a running instance, where do I start?</h2>

<p>If you have a lot of data, or state tied up in a running instance, you’ll first need to move it to a more persistent form, before moving it to a different site. We provide a utility, <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images.html#the-cc-snapshot-utility">cc-snapshot</a>, to make a new disk image out of a running baremetal instance. However, this comes with a few caveats!</p>

<ol>
	<li>Snapshots are unreliable above 10GB, and if above 20GB, won’t be able to be used to spawn new instances.  Instead, put <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/swift.html">large datasets into the object store</a>.</li>
	<li>Any data mounted from the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/shares.html">shared filesystem is site-local</a>. This should also be copied into the object store if you need to use it at a different site.</li>
	<li>When you make your snapshot, exclude copies of this data</li>
	<li>When you launch a new instance with the snapshot, download or mount the data as needed.</li>
</ol>

<h3>CLI Example with the object store!</h3>

<p>This assumes your “big dataset” is at “/scratch/my-data”<br>
1. On the instance you’re “saving”:<br>
<code>#!/bin/bash</code></p>

<p><code>openstack container create my-container<br>
tar -czf my-data.tar.gz /scratch/my-data<br>
openstack object create my-container my-data.tar.gz my-data.tar.gz</code></p>

<p><code># exclude the tar file and the dataset when making the snapshot<br>
cc-snapshot -e /scratch/my-data -e my-data.tar.gz my-snapshot</code><br>
 </p>

<p>2. On the new instance you booted from the new image “my-snapshot”<br>
<code>mkdir /scratch/<br>
openstack object save my-container my-data.tar.gz<br>
tar -xzf my-data.tar.gz /scratch/my-data</code></p>

<h1>Running your work at the new site</h1>

<p>Finally, after moving your data to the new site, you can execute your experiments as usual, with the following notes:</p>

<ul>
	<li>When you create leases and reservation, be sure to update the hardware selectors if needed</li>
	<li>When launching instances from custom disk images, you’ll need to refer to whatever name you created when copying the image (if different from original)</li>
	<li>If you have any scripts and/or Juptyer notebooks that do stuff programmatically, they’ll need to be updated to authenticate to the new site, and to reference the new names or uuids, as above.</li>
</ul>