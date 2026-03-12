---
abstract: "<p>Interested in large-scale\_networking research? Learn more about GENI-style\
  \ stitching and how to optimize host tuning for 20x performance increases\_with\
  \ Python's paramiko package. This blog complements a fully packaged experiment on\
  \ Trovi, so you can practice doing this yourself! New to Trovi? This blog also outlines\
  \ how to start running the notebook\_on Trovi.</p>"
authors:
- Mason Hicks
categories:
- Tips and Tricks
date: '2021-08-16 20:50:19+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/53/f8/53f85358-78a1-4c47-a714-343c1da49862/screen_shot_2021-08-16_at_15232_pm.png
related_posts: []
slug: using-paramiko-tune-network-performance
subtitle: ''
title: Using Paramiko to Tune Network Performance
---

<p dir="ltr">Many networking experiments necessitate transferring data across wide areas, making networking configuration essential. Chameleon allows users to take advantage of GENI-style stitching and experiment with the network flow between two stitched nodes. ExoGeni network stitching allows for users to easily perform experiments on the layer 2 and layer 3 networks of computer systems. There are TCP (Transmission Control Protocol) buffers on each side of a transfer connection that hold data before it is transferred. When this buffer reaches its capacity, the receiver node will alert the sender node that it cannot send any more data until this cache has been cleared. Once the cache is filled, the receiver node will refuse any more data until it is emptied. Through proper host tuning, which is modifying our buffer size and our congestion window, we can see massive performance increases of up to 20 times depending on the automatic tuning of your experiment’s operating system.</p>

<p>Although today’s high-bandwidth network cards provide 10, 40, or even 100 Gbps of bandwidth, this performance affects the TCP algorithms and buffer size.  Often, the default TCP configuration supports performance for a set of typical applications. Many scientific workloads involve very large data transfers across high-latency networks that do not conform to standard TCP configuration assumptions.  These situations require custom TCP tuning to achieve maximum network performance.</p>

<p>We have shared a new Jupyter notebook that shows an easier way to perform host tuning on nodes using Python’s paramiko package, which allows for a user to remotely access their node and perform command-line operations using the Python programming language. This integrates well with Chameleon’s own python-chi library, which can allocate hardware resources quickly. By taking advantage of paramiko, we can create a more streamlined approach to tuning nodes on any Chameleon site by connecting to and tuning the hosts with pre-written scripts that manually tune the TCP buffers from simple Jupyter notebook cells, and then test them using the iPerf3 performance measurement tool.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-1995d753-7fff-f28d-10aa-41319ba7505f">What’s in the notebook?</b></p>

<p>The tutorial notebook follows a structure of:</p>

<ol>
	<li dir="ltr">
	<p dir="ltr">Configure the environment</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Create a network and server at the UChicago site</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Create a network and server at the TACC site</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Start the servers </p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Stitch the circuit with ExoGENI</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Clean up resources</p>
	</li>
</ol>

<p> </p>

<p dir="ltr">Each of these sections contains the code necessary to run the commands and a brief explanation. Some sections contain links to other tutorials so you can see more detail about necessary steps, for example, creating a server or adding a subnet - and if you see a To Do note, that just means there are plans to create another tutorial for that step! You can check back to see if it’s been added in the future.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-1995d753-7fff-f28d-10aa-41319ba7505f">How do I access the notebook? </b></p>

<p dir="ltr">The new notebook can be found on <a href="https://www.chameleoncloud.org/experiment/share/">Trovi</a>, Chameleon’s sharing portal, under <a href="https://www.chameleoncloud.org/experiment/share/33">Chameleon User Guide: Networking</a>. </p>

<p dir="ltr"><b id="docs-internal-guid-1995d753-7fff-f28d-10aa-41319ba7505f"><img height="241" src="https://lh3.googleusercontent.com/1oF2AcqvGE5bqRUDE2HRqWwx4wc3A-AqVh4sdphxdHL5uA62AQ8T1oJ07iT_QKtROUX3zaPFjZlW0h2870yGjJQu6X-X9TZ8nPdUcRy24oBfVpxcWlPY77kXmi0eOMfb7mWwAy0m" width="624"></b></p>

<p dir="ltr"> </p>

<p dir="ltr">After selecting ‘Launch on Chameleon’, Jupyter will launch and you’ll be able to access any of the networking tutorials. The networking tutorial described in this blog is the Python-Stitching-Chameleon notebook. After selecting this notebook, you’ll be able to run all cells and try it out for yourself!</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-1995d753-7fff-f28d-10aa-41319ba7505f"><img height="311" src="https://lh3.googleusercontent.com/9gwBPC6i9FCeXyZ_hCQlD6xaVxlIz0Bk0BHY3M_kFaxNziOcWTLMt8HFQDzIqyS5EPS9NRa6kKlcmhJIB-D7XRkhIbMxsXL9ZMVPAfsRA_1CVkN2zC1drIyozZSSd9SRzIgfUXhy" width="624"></b></p>

<p><br>
We invite anyone interested in learning about these tips and tricks to look at the notebook. If you have questions about deploying an experiment using host tuning, please contact us (contact@chameleoncloud.org) so that we can help you get started with this capability.</p>