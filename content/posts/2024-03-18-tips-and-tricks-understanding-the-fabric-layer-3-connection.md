---
abstract: <p>Discover how Chameleon's testbed capabilities have been enhanced with
  the introduction of the FABRIC Layer 3 connection in our new blog post. Learn about
  the powerful and flexible networking options it offers, how it simplifies the process
  of routing to FABRIC resources, and how it enables low-latency and high-bandwidth
  traffic routing between CHI@UC and CHI@TACC.</p>
authors:
- Michael Sherman
categories:
- Tips and Tricks
date: '2024-03-18 21:28:26+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/28/fe/28fe7fbc-8c87-4df2-b11a-e95387168c33/fabnet-diagram.png
related_posts:
- slug: fabric-updated-trovi-example-for-using-fabric-with-chameleon
  title: 'FABRIC: Updated Trovi Example for using FABRIC with Chameleon'
- slug: fabrics-first-facilitlyport-deploying-experiments-spanning-chameleon-and-fabric
  title: "FABRIC\u2019s First FacilitlyPort: Deploying Experiments Spanning Chameleon\
    \ and FABRIC"
slug: tips-and-tricks-understanding-the-fabric-layer-3-connection
subtitle: 'Multi-site experiments with FABRIC: Sometimes Layer 3 is all you need'
title: Understanding the New FABRIC Layer 3 Connection
---

<p>Greetings, Chameleon users! For our Tips and Tricks this month, we're diving into an exciting development that enhances our testbed capabilities - the FABRIC Layer 3 connection. This addition is part of our continued effort to provide you with powerful, flexible networking options for your experiments.</p>

<p><img height="auto" src="https://chameleoncloud.org/media/filer_public/28/fe/28fe7fbc-8c87-4df2-b11a-e95387168c33/fabnet-diagram.png" width="60%"></p>

<p><strong>Figure 1</strong>: Diagram of fabnet Layer 3 Connection</p>

<p><a href="https://portal.fabric-testbed.net/">FABRIC</a>, like Chameleon, is an NSF-funded testbed, but with a focus on networking capabilities.  In 2023, we became proud hosts of the first <a href="https://chameleoncloud.org/blog/2022/08/24/fabrics-first-facilitlyport-deploying-experiments-spanning-chameleon-and-fabric/">FABRIC facility port</a> at our University of Chicago Chameleon site (CHI@UC). And, we've previously added support for <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/networks/networks_stitching.html">Layer 2 stitching</a> to FABRIC, which allows you to create an experiment using resources on both testbeds. This month, we've taken this a step further and set up a shared network at both CHI@UC and CHI@TACC that routes to the FABRIC internal network.</p>

<p>What does this mean for you? For starters, this means you can route to FABRIC resources without having to set up custom Layer 2 stitching for common cases. This simplifies the process and allows you to focus more on your experiments.</p>

<p>But the benefits don't stop there. Even if you're not a FABRIC user, you can take advantage of this network to route traffic between CHI@UC and CHI@TACC. This is a significant improvement over routing via public IPs. Using the FABRIC network between sites gives you lower latency and higher bandwidth than floating IPs - up to <strong>25Gb/s per flow</strong>. And all this without the need to set up FABRIC resources and reserve a Chameleon stitched network.</p>

<p>To get started using this connect, see our documentation, or follow these brief steps:</p>

<ol>
	<li><strong>Identify the Fabnet network</strong>: At available sites, you can see the fabnetv4 network in Horizon or by executing the following command: <code>OS_CLOUD=tacc openstack network show fabnetv4 --fit-width</code>. This will provide detailed information about the network.</li>
	<li><strong>Launch a server on fabnet</strong>: Use the following command to launch a server on fabnet: <code>openstack server create --network fabnetv4 ..</code>&lt;other options="" usual=""&gt;<code>.</code> Please note that the fabnet router will not send traffic to the public internet. As with any other isolated network, all internet-bound traffic will still traverse a neutron router at the Chameleon site.&lt;/other&gt;</li>
	<li><strong>Check the new paths</strong>: After launching your instance, you can use traceroutes to demonstrate the new paths. For example, <code>mtr -n 8.8.8.8 --report</code> can be used to traceroute from TACC to Google public DNS which still traverses the Neutron router, while <code>mtr -n 10.191.130.1 --report</code> will traceroute to the FABRIC router at TACC.</li>
</ol>

<p><img height="auto" src="https://chameleoncloud.org/media/filer_public/f4/ff/f4ffe6c1-4e6d-4127-b25f-771841e3696e/fabnet-demo.png" width="60%"></p>

<p>If you’re looking for something more interactive, our <a href="https://www.chameleoncloud.org/experiment/share/6c53cb25-0942-4d9c-ad27-e1bdb4e83fa5">artifact on Chameleon Trovi</a> demonstrates sending traffic between CHI@UC or CHI@TACC and a FABRIC slice using the "fabnetv4" layer 3 network. While the fabnet connection provides low latency and high bandwidth, it may not be the optimal choice for all experiments. Be sure to check your requirements and test your setup to ensure it meets your needs.</p>

<p>Whether you're a FABRIC user or not, this development is fantastic news. It opens a world of possibilities for your experiments and simplifies the process of sending traffic between sites. Stay tuned for more tips and tricks to help you make the most of your Chameleon experience. Remember, this network is publicly available at CHI@TACC and CHI@UC. Happy experimenting!</p>