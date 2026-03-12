---
abstract: '<p><span style="color: rgb(0, 0, 0); font-family: Arial; font-size: 14.6667px;
  white-space: pre-wrap;">Did you ever want to create a lease for a specific node?
  Did you ever want to create a lease that does NOT include a specific node? Ignore
  a node that has been reserved? Reserve a whole rack perhaps? Or just a few nodes
  but on the same rack? Then look no farther; here are five tips and tricks for node
  selection and node avoidance!</span></p>'
authors:
- Jacob Colleran
categories:
- Tips and Tricks
date: '2019-08-14 17:54:31+00:00'
featured: false
hide_image: true
image: ''
related_posts: []
slug: five-ways-get-what-you-want-chameleon
subtitle: ''
title: Five Ways to Get What You Want on Chameleon
---

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 3pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">We know that most of our users like to allocate resources by simply selecting the node type that looks good – however, some of you like things to be more exact. Did you ever want to create a lease for a specific node? Did you ever want to create a lease that does NOT include a specific node? Ignore a node that has been reserved? Reserve a whole rack perhaps? Or just a few nodes but on the same rack? Then look no farther; here are five tips and tricks for node selection and node avoidance!</span></span><br>
 </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">The key to success is to use </span><a href="https://chameleoncloud.readthedocs.io/en/latest/technical/discovery.html#chameleon-resource-browser" style=""><span style="font-size: 11pt; font-family: Arial; color: rgb(17, 85, 204); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Blazar’s resource selection</span></a><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">; it provides a lot of options and gives you more fine grained control over which nodes you lease and their location. You can even specify the rack placement of your nodes and ensure full bandwidth between them.</span></span><br>
 </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">While the most common way to use resource selection is to specify  `node_type` under Resource Properties on the Create Lease pop-up window on the GUI, there are more options. One of the most overlooked is `uid` (the node id that you get from the lease calendar or the node catalogue). We will now go over five common reservation scenarios and show you how to get exactly what you want in each. If you have other cases, let us know via the </span><a href="https://www.chameleoncloud.org/user/help/" style=""><span style="font-size: 11pt; font-family: Arial; color: rgb(17, 85, 204); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Help Desk</span></a><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"> or leave a comment!</span></span><br>
 </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 11.5pt; font-family: Arial; color: rgb(29, 28, 29); font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">How do I allocate a specific node?</span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 11.5pt; font-family: Arial; color: rgb(29, 28, 29); vertical-align: baseline; white-space: pre-wrap;">You can specify the uid of a node in the resource properties field to create a reservation for a specific node.</span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 11.5pt; font-family: Arial; color: rgb(29, 28, 29); vertical-align: baseline; white-space: pre-wrap;"><span style="border: none; display: inline-block; overflow: hidden; width: 318px; height: 405px;"><img src="https://lh5.googleusercontent.com/NlCbE-oluEg1ifsCuLkodzKiUzOGBBFDEpg7QWWQa0t451FyNaHlUqsDiXjpMw31JBuV-NJjnnv8PWlnNGYTLKbZt-Gv3raK9c8DtTTGOcMXE03OuxyiGGLBp23rG2P_P7QPgXKt" width="318" style="margin-left: 0px; margin-top: 0px;" height="405"></span></span></span></p>

<p> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 8pt; font-family: Consolas, sans-serif; color: rgb(199, 37, 78); background-color: rgb(249, 242, 244); vertical-align: baseline; white-space: pre-wrap;">blazar lease-create --physical-reservation \ </span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-left: 36pt; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 8pt; font-family: Consolas, sans-serif; color: rgb(199, 37, 78); background-color: rgb(249, 242, 244); vertical-align: baseline; white-space: pre-wrap;">min=1,max=1,resource_properties='["=", "$uid","00401ba8-4fb0-4f1e-a7dc-e93065ebdd15"]' \ --start-date "2019-08-30 15:00" \</span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-left: 36pt; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 8pt; font-family: Consolas, sans-serif; color: rgb(199, 37, 78); background-color: rgb(249, 242, 244); vertical-align: baseline; white-space: pre-wrap;">--end-date "2019-09-01 15:00" \</span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-left: 36pt; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 8pt; font-family: Consolas, sans-serif; color: rgb(199, 37, 78); background-color: rgb(249, 242, 244); vertical-align: baseline; white-space: pre-wrap;">my-custom-lease</span></span></p>

<p><br>
<br>
 </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">How can I avoid making a specific node part of my lease? </span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">If there is a node (or nodes) you want to avoid, you can tell that to the reservation system like this:</span></span></p>

<p> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">    </span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"><span style="border: none; display: inline-block; overflow: hidden; width: 624px; height: 268px;"><img src="https://lh3.googleusercontent.com/fXQxk51ieg70sy4TJ73bo2-TofLH9_yX_GiaChgM19JlPrZv65rpvDoPAAJuCEiPTuAx4-CSPRCmBHijdU-XrOOedqfQr6MJNt61G-ZO6ORU4mAG44wwI6v3u17jCahYF3IbiV1u" width="624" style="margin-left: 0px; margin-top: 0px;" height="268"></span></span></span></p>

<p> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Or using the </span><a href="https://chameleoncloud.readthedocs.io/en/latest/technical/reservations.html#provisioning-and-managing-resources-using-the-cli" style=""><span style="font-size: 11pt; font-family: Arial; color: rgb(17, 85, 204); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Blazar CLI</span></a><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">:</span></span></p>

<p> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">    </span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"><span style="border: none; display: inline-block; overflow: hidden; width: 624px; height: 99px;"><img src="https://lh4.googleusercontent.com/5Mmkp--wLcQ_ti3LGdyNKat1yohGywD0T69EHMeMyYzs4QdhzNUoe9cNKbE7r_DPBnNmjn1cdgMAdWlvLlf9oR5dUgRUO4CL5eOCoSYK0DyUw9SJy_6TkMXo9TM_tuJSoJJV5GJg" width="624" style="" height="297.9207"></span></span></span></p>

<p> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">If a node is already part of my lease, can I avoid using it? </span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">If you have already created a large reservation and you suspect one of the nodes may be bad, or don’t want to use it for any other reason, you can also use `Scheduler Hints` in Nova to arrange for this node to be dropped when launching an instance. You don’t have to create a whole new lease. Instead, use the query option as a scheduler hint when launching the instance. On the CLI, the command would look like this:</span></span></p>

<p> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"><span style="border: none; display: inline-block; overflow: hidden; width: 624px; height: 196px;"><img src="https://lh3.googleusercontent.com/Kol-rMjswzSnORoY2lNZRKQ46j5iiaRj2sC7cf5JT-wlTp2tJpZzsuU0sBbcOkUr1ftOKtA9JBZvHwlk4rBkf3Jcp_ZMR292F4k333nMkzfkyOTHen_s5VaFLRC6y2psO8p0Flrg" width="624" style="margin-left: 0px; margin-top: 0px;" height="196"></span></span></span></p>

<p><br>
 </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 11.5pt; font-family: Arial; color: rgb(29, 28, 29); font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">How do I allocate a whole rack?</span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 11.5pt; font-family: Arial; color: rgb(29, 28, 29); vertical-align: baseline; white-space: pre-wrap;">The easiest way to reserve an entire rack is to generate the command line function using Chameleon’s hardware resource discovery </span><a href="https://www.chameleoncloud.org/hardware/" style=""><span style="font-size: 11.5pt; font-family: Arial; color: rgb(17, 85, 204); vertical-align: baseline; white-space: pre-wrap;">tool</span></a><span style="font-size: 11.5pt; font-family: Arial; color: rgb(29, 28, 29); vertical-align: baseline; white-space: pre-wrap;">. After selecting a region (UC or TACC) use the `advanced filters` below the site selection to see fine-grained option selections. Scroll down to the option to select a specific rack and you will see something similar to this:</span></span></p>

<p> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 11.5pt; font-family: Arial; color: rgb(29, 28, 29); vertical-align: baseline; white-space: pre-wrap;"><span style="border: none; display: inline-block; overflow: hidden; width: 624px; height: 452px;"><img src="https://lh6.googleusercontent.com/ETjNo0jylOtDfcO6VC0ys5RnWLgv69y6T9T2jGwwiY4sjBdff52gFvOSa6CCD2BWvhjZm8WiMMKu8rvBROFy-Q2ClUtOZbkPn7e7HzSI52aPVQ4wXQRNFYS_u4X6mqZJa2Y52mOS" width="624" style="margin-left: 0px; margin-top: 0px;" height="452"></span></span></span></p>

<p><br>
 </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 11.5pt; font-family: Arial; color: rgb(29, 28, 29); vertical-align: baseline; white-space: pre-wrap;">Once you click `reserve`, you will be able to input the start and end dates of your reservation and the number of nodes you require. If you want to reserve the entire rack, make sure to set the minimum and maximum amount of nodes to the number of nodes on the rack. For instance, on rack 1 there are 42 nodes (as indicated in parentheses adjacent to rack 1 in the picture above.) so you would set both the minimum and maximum nodes to 42 as the example below:</span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 11.5pt; font-family: Arial; color: rgb(29, 28, 29); vertical-align: baseline; white-space: pre-wrap;"><span style="border: none; display: inline-block; overflow: hidden; width: 606px; height: 628px;"><img src="https://lh3.googleusercontent.com/kDOpoqjHy_Y9DYIQswUm9jNQxA-Jz9Vs7PQcGlXuBA-59YR2jAeZZesfT_QIswK9JPZCuNjx-Harkmazt2gP9aBXrQe2-mMon5u0mGAc2u28YFaUWuwAlx2tC3bN0No2fHYfvs-_" width="606" style="margin-left: 0px; margin-top: 0px;" height="628"></span></span></span></p>

<p> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 11.5pt; font-family: Arial; color: rgb(29, 28, 29); vertical-align: baseline; white-space: pre-wrap;">This will generate a script you can run from the command line (see below). For more information on using the CLI to reserve resources, see the documentation </span><a href="https://www.chameleoncloud.org/hardware/" style=""><span style="font-size: 11.5pt; font-family: Arial; color: rgb(17, 85, 204); vertical-align: baseline; white-space: pre-wrap;">here</span></a><span style="font-size: 11.5pt; font-family: Arial; color: rgb(29, 28, 29); vertical-align: baseline; white-space: pre-wrap;">.</span></span></p>

<p> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 11.5pt; font-family: Arial; color: rgb(29, 28, 29); vertical-align: baseline; white-space: pre-wrap;"><span style="border: none; display: inline-block; overflow: hidden; width: 605px; height: 343px;"><img src="https://lh6.googleusercontent.com/7nNiySX-6dUJuRgVlwqFiU27795xZbeaa4jlPMYwV6B1l_S-b7gSEtx-B7hFlLgo7FndbozAd8NRgqZixrl5gye31RyrA22fhI-OMtlP6JuUYPe06Ysacj3vfkPciyNFAv9Yl_lJ" width="605" style="margin-left: 0px; margin-top: 0px;" height="343"></span></span></span></p>

<p> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 11.5pt; font-family: Arial; color: rgb(29, 28, 29); font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">How do I allocate 2 nodes on the same rack?</span></span></p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">To allocate two nodes on the same rack, you can follow the same steps above for reserving a whole rack using Chameleon’s hardware discovery tool, but set the minimum and maximum node counts to just 2. However, if you already know what rack and node types you need, it may be easier to just specify the node constraints under resource properties when creating your lease in the GUI. See the example below:</span></span></p>

<p> </p>

<p dir="ltr" style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;"><span id="docs-internal-guid-6088a95e-7fff-36b6-9095-340872446dcc"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"><span style="border: none; display: inline-block; overflow: hidden; width: 318px; height: 417px;"><img src="https://lh4.googleusercontent.com/MWmDzwpbBJvUNw8Emqu2HqDhnN0j462O8ykt8N4JOCIoZCtu2T9zLyg8yKj6KKNw_HzFTLLvyLlmTfmOhVug665D8VGn0kNfGARZyz2_FGuqpvSFWR7AX6z9xRw95eRwSp631nD5" width="318" style="margin-left: 0px; margin-top: 0px;" height="417"></span></span></span></p>

<p><br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
 </p>
