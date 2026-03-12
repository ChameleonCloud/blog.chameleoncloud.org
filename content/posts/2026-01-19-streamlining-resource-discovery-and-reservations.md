---
abstract: "<p>We\u2019re excited to shine a spotlight on the recently refreshed hardware\
  \ discovery browser on Chameleon! Launched a little while ago, this upgrade makes\
  \ it easier and faster to pinpoint the exact hardware you need for your experiments,\
  \ connecting you directly to real-time scheduling and reservations.</p>\n\n<p>As\
  \ you most likely know, Chameleon offers dedicated, reservable resources. That means\
  \ your work gets exclusive access to the nodes you choose but navigating hardware\
  \ specs and reservation calendars together can sometimes be a bit of frustration.</p>\n\
  \n<p>The new resource discovery experience helps you link \u201Cwhat hardware am\
  \ I getting?\u201D with \u201Cwhen can I actually run?\u201D into a more streamlined\
  \ workflow than previously.</p>"
authors:
- Paul Marshall
categories:
- Tips and Tricks
date: '2026-01-19 15:57:43+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/3b/44/3b440a6a-a470-4864-aee6-50b065ba3dc8/image2.png
related_posts:
- slug: composible-hardware-on-chameleon-now
  title: Composable Hardware on Chameleon NOW!
- slug: announcing-new-hardware-for-chiuc
  title: New Experiments with New CHI@UC Hardware
- slug: chameleon-legacy-hardware
  title: Chameleon Legacy Hardware
slug: streamlining-resource-discovery-and-reservations
subtitle: Learn about our recent upgrades to resource discovery and reservations on
  Chameleon
title: Streamlining Resource Discovery and Reservations
---

<h1>Streamlining Resource Discovery and Reservations</h1>

<p>We're excited to shine a spotlight on the recently refreshed hardware discovery browser on Chameleon! Launched a little while ago, this upgrade makes it easier and faster to pinpoint the exact hardware you need for your experiments, connecting you directly to real-time scheduling and reservations.</p>

<p>As you most likely know, Chameleon offers dedicated, reservable resources. That means your work gets exclusive access to the nodes you choose but navigating hardware specs and reservation calendars together can sometimes be a bit of frustration.</p>

<p>The new resource discovery experience helps you link "what hardware am I getting?" with "when can I actually run?" into a more streamlined workflow than previously.</p>

<h1>What's New in Resource Discovery?</h1>

<p><img alt="Node reservation interface with pre-selected filter" src="https://chameleoncloud.org/media/filer_public/f5/00/f5003fd8-d787-48ea-83ec-254585e5c651/image4.png"></p>

<ul>
	<li><strong>Simplified UI</strong>: Instantly search and filter hundreds of nodes by CPU type, RAM, storage sizes, accelerators (GPUs/FPGAs), network, and more, in a simplified interface with very detailed information hidden initially. For those of you who need that detailed information, don't worry! It's still there, you just have to expand the view (Click +Advanced Filters, then click +Show Detailed Fields):</li>
</ul>

<p><img alt="Hardware browser filtered for NVDIMM nodes" src="https://chameleoncloud.org/media/filer_public/d4/9b/d49b9070-d9b7-48dd-8128-016cd0937340/image6.png"></p>

<ul>
	<li><strong>Host Calendar Links</strong>: Every site listed in the node browser now comes with a direct link to its live reservation calendar in the Chameleon dashboard (login required) by clicking on "View Host Calendar":</li>
</ul>

<p><img alt="Check availability and reserve node buttons" src="https://chameleoncloud.org/media/filer_public/9a/ad/9aad123b-d986-47bd-bce7-a0191af770ab/image3.png"></p>

<ul>
	<li><strong>Availability &amp; Reservation Buttons</strong>: On each node's detail page, you can immediately check its real-time availability and reserve it in a single click, which also takes you into the Chameleon dashboard (again, login required): the calendar for "Check Availability" or to the node reservation page with the node pre-selected for "Reserve Node":</li>
</ul>

<p>For example, once you click on "Reserve Node" and login, you'll be able to give the lease a name, choose the lease length, and when you click next you'll notice the filter already applied for your node:</p>

<p><img alt="Calendar view with clickable node names" src="https://chameleoncloud.org/media/filer_public/81/95/8195f164-f493-41e4-8553-142c160ac185/image5.png" width="600"></p>

<ul>
	<li><strong>Reserve directly from the calendar</strong>: if you are in the calendar view and you see an available node that you want to reserve, you can click on the node name (e.g. nc46 in the image below), it will pre-set the node name in the filter similar to the case in the image above showing node c03-14.</li>
</ul>

<p><img alt="Host calendar view" src="https://chameleoncloud.org/media/filer_public/3b/44/3b440a6a-a470-4864-aee6-50b065ba3dc8/image2.png" width="800"></p>

<p>With these changes, it's easier than ever to answer:</p>

<p>Can I get my required hardware and is it available when I need it?</p>

<h1>Example Use Case: NVDIMM</h1>

<p>Now that you've seen how easy it is to filter and reserve hardware, let's take a closer look at the hardware browser using an example.</p>

<p>Let's say you're researching persistent key-value stores for ultra-fast, crash-resilient data access. For example, you're developing or benchmarking storage engines like RocksDB. These experiments need persistent memory that combines the speed of RAM with the durability of storage, letting your data survive reboots and failures without sacrificing performance.</p>

<p>To set this up, start by identifying nodes equipped with Intel Optane persistent memory (NVDIMM) using the hardware browser. Just filter for nodes with 3840 GiB RAM, which ensures you have the capacity for cutting-edge persistent storage software:</p>

<p><img alt="Advanced filters interface" src="https://chameleoncloud.org/media/filer_public/f4/4a/f44a0357-8c6b-4f53-a3cc-5bc5d54ad10f/image1.png"></p>

<p>Once you've found the right nodes, you'll want to check when they're available. Head to the node's detail page to open the site's availability calendar. With just a few clicks, you'll know when you can reserve the hardware and start your experiment.</p>

<p>A couple of notes about NVDIMM:</p>

<p>First, it is available in two modes:</p>

<ul>
	<li>Memory Mode: DCPMM modules appear as large, albeit slightly slower, standard RAM. Perfect for experiments needing multi-terabyte memory.</li>
	<li>App-Direct Mode: DCPMMs are exposed as dedicated persistent memory, accessible via NVDIMM drivers and APIs. Great for cutting-edge software requiring explicit persistence.</li>
</ul>

<p>Second note about it: Switching between modes requires a config change in the BIOS per <a href="https://dl.dell.com/topicspdf/dcpmm-user-guide_en-us.pdf">Dell's manual</a>. Contact the <a href="https://chameleoncloud.org/user/help/">Chameleon help desk</a> for support changing this option.</p>

<p>We are working to improve the hardware browser even further by including this type of information about different hardware characteristics directly in the browser. Stay tuned for updates!</p>

<h1>Ready to Connect Hardware With Your Schedule?</h1>

<p>Start exploring hardware on Chameleon with the <a href="https://www.chameleoncloud.org/hardware/">hardware discovery browser</a>: filter for what you need, check availability, and reserve the hardware with just a few clicks.</p>

<p>Tell us what works for you, what you'd tweak, and what features you want next over on the <a href="https://forum.chameleoncloud.org/">Chameleon forums</a>.</p>