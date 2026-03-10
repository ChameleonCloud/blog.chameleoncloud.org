---
abstract: "<p dir=\"ltr\">Is your instance not launching? Are your Floating IPs drifting\
  \ aimlessly through the ether? Do you have a PI eligibility request? Chameleon tickets\
  \ are the fastest way to <a href=\"https://www.chameleoncloud.org/user/help/\">reach\
  \ the Chameleon support team</a> and receive assistance for all your testbed needs.\
  \ It\u2019s 2020. Everyone could use a little extra help.\_</p>\n\n<p dir=\"ltr\"\
  >As 2021 and Oscars season approaches, the Chameleon team has compiled \u201CTickets\
  \ of the Year\u201D designed to help you avoid (at least some of) the same stumbling\
  \ blocks of 2020. Read on to learn about some of the most common tickets, their\
  \ solutions, and some special ticket award categories. You can always reach out\
  \ to the <a href=\"https://www.chameleoncloud.org/user/help/\">Help Desk team</a>\
  \ for white-glove troubleshooting help.\_</p>"
authors:
- Isabel Brunkan
categories:
- Tips and Tricks
date: '2020-12-21 17:55:10+00:00'
featured: false
hide_image: true
image: ''
slug: tickets-year-solutions-your-2020-ticket-problems
subtitle: ''
title: 'Tickets of the Year: Solutions to Your 2020 (Ticket) Problems'
---

<p dir="ltr">Is your instance not launching? Are your Floating IPs drifting aimlessly through the ether? Do you have a PI eligibility request? Chameleon tickets are the fastest way to <a href="https://www.chameleoncloud.org/user/help/">reach the Chameleon support team</a> and receive assistance for all your testbed needs. It’s 2020. Everyone could use a little extra help. </p>

<p dir="ltr">As 2021 and Oscars season approaches, the Chameleon team has compiled “Tickets of the Year” designed to help you avoid (at least some of) the same stumbling blocks of 2020. Read on to learn about some of the most common tickets, their solutions, and some special ticket award categories. You can always reach out to the <a href="https://www.chameleoncloud.org/user/help/">Help Desk team</a> for white-glove troubleshooting help. </p>

<p> </p>

<p dir="ltr">Without further ado, the Oscar for the <strong>Most Often Encountered Error</strong> goes to… <strong>“No Host Found” Error</strong>! </p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Problem: </b>Are you frequently encountering the “No Host Found” error when trying to reserve a lease? While COVID might prevent you from hosting a typical Christmas, with this fix, you’ll always be able to find a host on Chameleon.</p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Solution:</b> This error occurs when all the nodes of the type you’re trying to reserve have already been reserved for the time frame that you want. While we can’t free them up for you, you can visit the <a href="https://chi.tacc.chameleoncloud.org/project/leases/calendar/">Host Calendar</a>, select the type of resource you want to experiment on, and see the time frames that are reserved and available. One important thing to note is the site that you’re reserving resources on - like UChicago versus TACC - as the sites have different resources and availability. </p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308"><img height="239" src="https://lh4.googleusercontent.com/sf9ytzEEDipPFaquEY_johC2zVGQYcrMg4sNOanAgdX5UF9obfJrUp9mdV0FqhDMLWcjwEyxQVXwdog_sEKk4K02DUZ43q3Xqm6hDcShE2wMSYhDAj8f3yik9vrZUwb56ED7x8cj" width="624"></b></p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Category: Most Wanted: The Problem Report</b></p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Winner: The Help Desk Email: What Should I Include?</b></p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Problem: </b>You probably haven’t been in an office since the beginning of 2020. Whether you’ve mastered email writing or still rethink every sentence, we’ve got you covered. Here’s everything you can include to help us resolve your problem faster and get you back to experimenting. </p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Solution: </b>More information is always better! Attachments, error messages, outputs - include it all. That being said, here are some key points to make sure to include: </p>

<ul>
	<li dir="ltr">
	<p dir="ltr">Project Name </p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Username</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">UUID of the Instance or Lease (if applicable): To find the UUID in the GUI, click on your Instance/Lease name and ‘Lease Detail’ will appear. The UUID is located below the ‘Name’, with the heading ‘Id’.</p>
	</li>
</ul>

<p>Just as a reminder, the <a href="https://www.chameleoncloud.org/user/help/">Help Desk button</a> is available on the Chameleon webpage, right next to your username. When you’re in the experimental portal (CHI@UC, CHI@TACC, CHI@NU), the <a href="https://www.chameleoncloud.org/user/help/">Help Desk button</a> is in the drop down menu after clicking on your username.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Category: The Most Avoidable Problem</b></p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Winner: Launching with Specialized Nodes</b></p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Problem: </b>Chameleon offers a variety of hardware (<a href="https://www.chameleoncloud.org/about/hardware-description/">explore the options</a>); one common difficulty our users encounter are launch issues when using a specialized node of certain types: either GPU, FPGA or ARM64. Usually, users reserve the specialized node, but then try to launch a standard image rather than a specialized image. This normally leads to launch issues, and reports of being unable to ssh into the instance.</p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Solution: </b>Luckily, there’s a quick fix for this difficulty. Simply use the specialized image that corresponds to the node you’re reserving. </p>

<p dir="ltr">For GPU:<b> </b>use CUDA specific images like CC-CentOS7-CUDA10</p>

<p dir="ltr">For FPGA:<b> </b>use FPGA specific images like CC-CentOS7-FPGA</p>

<p dir="ltr">For ARM64:<b> </b>use ARM64 specific images like CC-Ubuntu16.04-ARM64</p>

<p><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Note: </b>You may encounter a similar issue if launching a non-specialized node with a specialized image. For example, trying to launch a Skylakes or Haswell node with a FPGA image. </p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Category: The Largest Problem </b></p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Winner: Large Scale Network Deployment</b></p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Problem: </b>In large-scale network projects, the experiment can be performance sensitive. However, the location of the nodes and racks that you’re using in your experiment can significantly impact performance, leading to asymmetric network behavior. If your experiment is performance sensitive, mitigating against this kind of behavior is crucial.</p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Solution: </b>Use nodes that are in the same section of a rack. If you’re seeing asymmetric network behavior, it is likely because your nodes are at different locations on a rack. The bottom and the top of a rack each have their own switch, with an interconnect between them, which explains the difference in networking behavior.</p>

<ol>
	<li dir="ltr">
	<p dir="ltr">To choose your nodes, use the <a href="https://chi.tacc.chameleoncloud.org/project/leases/calendar/">host calendar</a> under the Leases tab on your Chameleon portal page to identify free nodes in the same section of the rack. </p>
	</li>
</ol>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">          <img height="331" src="https://lh6.googleusercontent.com/WUXBe3By03bz5xo0k_rU15py5NJoatv2IbsjO3GXsjKTexMfhP-Nx1ODbQ7PjkgC0EGdwJt_lZz_p9kHjQvtTpMbf-9lJ1jp9jTSX77tAy74b9Qh6iLd3k3Y3LaMO3VNAg4K4XNf" width="624"></b></p>

<ol start="2">
	<li dir="ltr">
	<p dir="ltr">After identifying enough free nodes, you can create a lease with specific nodes using the CLI and this <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/reservations.html#provisioning-and-managing-resources-using-the-cli">guide</a>. A <a href="https://www.chameleoncloud.org/blog/2019/08/14/five-ways-get-what-you-want-chameleon/">Chameleon blog post</a> also highlights how to allocate nodes on the same rack. </p>
	</li>
</ol>

<p dir="ltr">As an example, if you wanted to create a lease with multiple nodes, you can adapt the following command (currently set for 2 nodes): </p>

<p dir="ltr"><code>blazar lease-create --physical-reservation min=2,max=2,resource_properties='["or",["=","$name","&lt;node_name_1&gt;"],["=","$name","&lt;node_name_2&gt;"]]' &lt;your_lease_name&gt;&lt;/your_lease_name&gt;&lt;/node_name_2&gt;&lt;/node_name_1&gt;</code></p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Category: The Most Annoying</b></p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Winner: CloudFuse Breaking Up</b></p>

<p><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Problem: </b>Experiencing trouble with CloudFuse for object storage and migration? CloudFuse can sometimes have stability issues and will have trouble uploading large files (especially above 4GB). </p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Solution: </b>One simple, quick solution is to try remounting: </p>

<ol>
	<li dir="ltr">
	<p dir="ltr">Download your v2 or v3 RC file from the Chameleon web interface (click your username at the top right).</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Create a file in your home directory <tt>(/home/cc/openrc</tt>) on the instance and copy the contents of the RC file into it.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Source the file: <code>$ source openrc</code></p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Now you need to mount the object store. It's usually better to unmount it first:</p>

	<ol>
		<li dir="ltr">
		<p dir="ltr"><code>$ cc-cloudfuse unmount my_mounting_point</code></p>
		</li>
		<li dir="ltr">
		<p dir="ltr"><code>$ cc-cloudfuse mount my_mounting_point</code></p>
		</li>
	</ol>
	</li>
</ol>

<p>While remounting is a good fix, if stability is important to you, try using <a href="https://wiki.openstack.org/wiki/Swift">Swift</a>, the OpenStack Object Store. Though Swift requires more scripting knowledge, it’s more stable, and you can also automate with it! Check out their <a href="https://docs.openstack.org/swift/latest/overview_large_objects.html">Large Object documentation</a> to learn more. </p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Category: Easiest to Fix on Your Own</b></p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Winner: It’s Raining Errors: Leases in Error State</b></p>

<p><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Problem: </b>Are your leases falling into an error state? This can happen when an action isn’t applied to a lease, likely because it fails to meet Chameleon requirements, like an extension is too long. Luckily, there’s an easy fix to get it back up and running.</p>

<p><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Solution: </b>To reset your lease, it just needs to be ‘touched’. You can do this within the GUI or CLI with the blazar lease-update process: </p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">In the GUI: </b></p>

<ol>
	<li dir="ltr">
	<p dir="ltr">Click update lease</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Set the name to what it already is</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Click save!</p>
	</li>
</ol>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">In the CLI: </b></p>

<p dir="ltr">Simply use this command: <code>$ blazar lease-update &lt;lease uid=""&gt; --name &lt;current lease="" name=""&gt;&lt;/current&gt;&lt;/lease&gt;</code></p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Category: Most Overlooked Fix</b></p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Winner: Connectivity: Pinging Your Instance</b></p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Problem: </b>While 2020 is the poster child for connectivity issues, don’t let that be the case with your Chameleon leases! Look no farther if you’re having trouble pinging your instance or ssh-ing in.</p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Solution: </b>Using Chameleon’s GUI interface, you can access a remote console to your instance. Once you’re there, you can check the console to see if instances have been deployed (and troubleshoot) or determine what failed. To access the console on your Chameleon portal page simply go to ‘Compute’ &gt; ‘Instances’. Once you’re on the ‘Instances’ page, click the instance name and select the ‘Console’ tab. It may take a minute to load, but then you’ll be able to troubleshoot your connectivity issues yourself, and see why you can’t connect to your instances!<br>
<br>
<b><img height="304" src="https://lh5.googleusercontent.com/T6HeuAWIDt1CVoTwIvYggDVWxxmynVZ6Og6NLvjxQQ_Ye-bD7wG2961NbyalRi5lxxSYdKWilpJfrLLMFLTrjDtZRfns6OG2Fh-HU0uzitsbnVY5uQHtrf68wnwoHEqoRely6R79" width="624"></b></p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Category: Commonly Misused Feature</b></p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Winner: PI Requests </b></p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Problem: </b>While it's tempting to want to be a PI - and have all the power and responsibility that accompany it - there are a few logistical requirements to check off first. </p>

<p dir="ltr"><b id="docs-internal-guid-83c26ce8-7fff-79ef-c4cf-38c6b9032308">Solution: </b>To be a PI, you must be a member of one of the following groups:<b> </b></p>

<ol>
	<li dir="ltr">
	<p dir="ltr">A faculty member of an academic institution </p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Research staff of a federally funded lab, center or agency</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Conducting research at a museum, observatory, library etc.<b> </b></p>
	</li>
	<li dir="ltr">
	<p dir="ltr">NSF Graduate Student Fellows</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">State educational offices or organizations</p>
	</li>
</ol>

<p>Each group is explained more fully in the <a href="https://www.chameleoncloud.org/learn/frequently-asked-questions/#toc-who-is-eligible-to-be-chameleon-pi-">Chameleon FAQ</a>. If you believe that you are an exception, Chameleon occasionally provides exceptions on a case-by-case basis. </p>

<p dir="ltr"> </p>

<p>One last reminder before Chameleon signs off for the holidays, the <a href="https://www.chameleoncloud.org/user/help/">Help Desk button</a> is available on the Chameleon webpage, right next to your username. When you’re in the experimental portal (CHI@UC, CHI@TACC, CHI@NU), the <a href="https://www.chameleoncloud.org/user/help/">Help Desk button</a> is in the drop down menu after clicking on your username. No ticket is too small, no problem too complicated, and now you have everything you need to write the perfect Help Desk ticket.</p>

<p dir="ltr"> </p>

<p dir="ltr">That’s all, folks. We’ll see you next year!</p>