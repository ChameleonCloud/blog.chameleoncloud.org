---
abstract: "<p>Get the inside scoop on Chameleon Cloud\u2019s common user issues and\
  \ smart fixes in our latest 'Tips and Tricks' blog, highlighting a year of learning\
  \ and problem-solving.</p>"
authors:
- Marc Richardson
categories:
- Tips and Tricks
date: '2023-12-19 00:39:19+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/b3/d7/b3d7b535-0b78-49e0-ba7f-16c6f8669bcc/dalle_2023-12-18_155045_-_a_digital_illustration_featuring_a_group_of_chameleons.png
related_posts:
- slug: tickets-of-the-year-2022
  title: 'Tickets of the Year: 2022'
- slug: tickets-of-the-year-2021-edition
  title: 'Tickets of the Year: 2021 Edition'
- slug: tickets-year-solutions-your-2020-ticket-problems
  title: 'Tickets of the Year: Solutions to Your 2020 (Ticket) Problems'
slug: tickets-of-the-year-on-chameleon-2023
subtitle: Read our tips and tricks for some common issues that users faced in 2023
title: Tickets of the Year on Chameleon (2023)
---

<p><img height="auto" src="https://chameleoncloud.org/media/filer_public/b3/d7/b3d7b535-0b78-49e0-ba7f-16c6f8669bcc/dalle_2023-12-18_155045_-_a_digital_illustration_featuring_a_group_of_chameleons.png" width="50%"></p>

<p>As the year winds down on Chameleon Cloud, let's gather around for a cozy look back at the memorable moments of 2022. In our "Tickets of the Year" blog post, we’re spotlighting the unique challenges and clever solutions from our user community. It's a concise, jolly recap of the year’s highlights, offering insights and tips to enhance your Chameleon Cloud experience. Here's to a year of great questions and even better answers!</p>

<h1>Tickets of the Year - 2023</h1>

<h2>1. Trouble Connecting to Instances: The Dreaded 'Network Unreachable' Error</h2>

<p>This issue often pops up when your instance instance doesn't discover its private IP due to a DHCP failure.</p>

<p><strong>Symptoms</strong>:</p>

<p>The output of <code>ip addr</code> does not show the instance’s private IP.</p>

<p><strong>Quick Fix</strong>:</p>

<p>Running <code>sudo dhclient</code> on the instance usually does the trick, triggering the DHCP client IP discovery.</p>

<p><strong>Success Indicators</strong>:</p>

<ul>
	<li>The private IP shows up after running <code>ip addr</code>.</li>
	<li>The instance responds to pings and SSH access is restored.</li>
</ul>

<p>Of course, if you are still having trouble after trying our tip, please reach out to us at the Help Desk!</p>

<h2>2. Lease Creation Woes: 'Not Enough Resources Available'</h2>

<p>A common hiccup occurs when users fail to create a lease, encountering the 'Not enough resources available' error. This usually happens when the desired node type isn’t available.</p>

<p><strong>Pro Tips</strong>:</p>

<ul>
	<li>Always check the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/reservations.html#the-lease-calendars">lease calendar</a> for availability.</li>
	<li>If your desired node type isn't available, schedule a lease for a future date.</li>
	<li>For extending a lease, if the same node type isn’t available, back up your data and configurations, and reserve a new node.</li>
</ul>

<h2>3. Lease Creation Woes Continued: Expired Allocation</h2>

<p>If you still have issues reserving a resource type, then check your allocation expiration. Your project’s allocation may be expired, or will expire during the time of your desired lease. It’s also possible that your allocation no longer has any <a href="https://chameleoncloud.readthedocs.io/en/latest/user/project.html#service-units">SUs</a> available. You can double check this <a href="https://chameleoncloud.readthedocs.io/en/latest/user/project.html">here</a>, and <a href="https://chameleoncloud.readthedocs.io/en/latest/user/project.html#recharge-or-extend-your-allocation">request a renewal/recharge</a> so that you can reserve your resources.</p>

<h2>4. Data Storage and cc-snapshot Limitations</h2>

<p>The <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images.html#the-cc-snapshot-utility">cc-snapshot tool</a> is fantastic for saving configurations, but beware, it's not ideal for storing large amounts of data.</p>

<p><strong>What to Watch Fo</strong>r:</p>

<p>Running cc-snapshot on instances with too much data might cause it to fail or, even worse, result in data loss if there's no separate backup.</p>

<p><strong>Best Practices</strong>:</p>

<ul>
	<li>Always back up your data to the object store before using cc-snapshot.</li>
	<li>You can use the <code>my_mounting_point</code> mount on your instance or the swift CLI for a more reliable backup.</li>
	<li>Read our blog post on <a href="https://chameleoncloud.org/blog/2022/10/26/data-storage-management-and-sharing-on-chameleon/">data storage, management, and sharing on Chameleon</a>.</li>
</ul>

<h2>5. This Trovi Artifact Isn’t Working!</h2>

<p>Running into issues with artifacts is a part of the research process, but knowing the right channel for assistance can make a big difference. Many of the artifacts on <a href="https://chameleoncloud.org/experiment/share">Trovi</a> are contributed by Chameleon users. Each Trovi artifact will list an author. Artifact authors are often the best place to start when looking for help.</p>

<p><strong>When to Contact the Artifact author vs. Help Desk?</strong></p>

<ul>
	<li><em>Specific Artifact Issues</em>: If you're facing challenges with an artifact, consider reaching out to the artifact's author first. They're best equipped to assist with issues specific to their creation.</li>
	<li><em>Chameleon-Supported Artifacts</em>: For artifacts with the Chameleon badge on Trovi, our help desk is ready to assist.</li>
	<li><em>General Infrastructure Issues</em>: Even if your issue isn’t about the content of an artifact, like if JupyterHub is down and you can’t launch an artifact on Chameleon, our help desk is here to help. Reach out to us for any infrastructure-related concerns.</li>
</ul>

<p><strong>Why Distinguish Between These Scenarios?</strong></p>

<p>Understanding whether your issue is specific to an artifact or related to the broader Chameleon infrastructure will guide you to the fastest and most appropriate form of assistance, ensuring smoother progress in your research.</p>

<h2>6. Navigating Image Updates on Chameleon</h2>

<p>Using the right <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images.html">image</a> version is crucial for your work on Chameleon, and understanding how to access them can save you a lot of hassle. Here's a tip to keep in mind:</p>

<p><strong>Always Use the Latest or Stick to the Immutable?</strong></p>

<ul>
	<li><strong>For the Latest Version</strong>: Refer to the image by its name, like CC-Ubuntu20.04. This ensures you're always using the most updated version available.</li>
	<li><strong>For Reproducibility</strong>: Use the image's UUID. It's immutable, meaning it won’t change over time, ensuring consistent results if you need to replicate your environment or results.</li>
</ul>

<p><strong>Why It Matters</strong>:</p>

<p>Depending on your project's needs, choosing between the latest version and a specific UUID can impact your work's reproducibility and reliability. Make sure to select the option that best aligns with your project goals.</p>

<hr>
<p>We hope these tips help you navigate some of the common roadblocks on Chameleon Cloud. Remember, our community is here to support you, so never hesitate to reach out if you’re stuck or just need a bit of guidance.</p>

<p>Here’s to another year of breakthroughs and learning on Chameleon Cloud!</p>

<p>Happy Computing!</p>