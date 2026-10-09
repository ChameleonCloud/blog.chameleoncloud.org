---
abstract: <p>Warm welcome back! We hope that your summer was fabulous in every possible
  way and now that finally both the semester and the quarter have started you are
  ready to embark on new adventures. We are here for this with tips for Chameleon
  newbies and an update for our wizened veterans.</p>
authors:
- Kate Keahey
categories:
- Tips and Tricks
- Featured
date: '2026-10-09 14:00:00+00:00'
featured: true
hide_image: false
image:
related_posts:
- slug: one-place-to-plan-an-experiment-bare-metal-vms-and-availability
  title: "One Place to Plan an Experiment: Bare Metal, VMs, and Availability"
- slug: tips-and-tricks-getting-access-to-chameleon-as-a-student
  title: Getting Access to Chameleon as a Student Researcher
- slug: back-to-school-graduating-from-the-getting-started-guide
  title: 'Back to School: Graduating from the Getting Started Guide'
slug: back-to-school-with-chameleon-2026
title: Back to School with Chameleon!
---

Warm welcome back! We hope that your summer was fabulous in every possible way and now that finally both the semester and the quarter have started you are ready to embark on new adventures. We are here for this with tips for Chameleon newbies and an update for our wizened veterans.

## Let’s Get Acquainted: a Guide for Chameleon Newbies

If you are not quite the wizened veteran yet, we are here for you with some useful tips on how to acquire some grey hair and some tasteful wizening.

**Where to Learn.** But of course -- by clicking on the “Learn” option on the main Chameleon menu -- which will take you to [documentation](https://chameleoncloud.readthedocs.io/en/latest/), with the [quickstart guide](https://chameleoncloud.readthedocs.io/en/latest/#getting-started) (part of the docs) deserving a special mention as a good entry point to the system. We now also have [a documentation chatbot](https://ai.chameleoncloud.org) if you prefer to learn about things in conversational style – use at your own peril, but do let us know if you get in trouble. Policies and basics are covered in the [FAQ](https://www.chameleoncloud.org/learn/frequently-asked-questions/). And if you really, really get lost the [helpdesk](mailto:helpdesk@chameleoncloud.org) is always your friend – operators are standing by to help you through any difficulty.

**Solutions to problems.** Where documentation tells you how to use the system, if you have a specific problem to solve such as “how do I learn about Chameleon?”, “should I use bare metal or VMs?”, or “how do I set up a bastion host?” chances are it would have been covered in the [tips&tricks section](https://blog.chameleoncloud.org/categories/tips-and-tricks/) of the [Chameleon blog](https://blog.chameleoncloud.org). The blog is also the place where we post all the announcements, the monthly newsletter, and where users sometimes share their experiments (let us know via the [helpdesk](mailto:helpdesk@chameleoncloud.org) if you would like to do that) so it is a good place to keep track of what is happening on the system.

**Webinars.** If you prefer to learn by watching, our latest webinars are available on the [Chameleon Youtube channel](https://www.youtube.com/user/ChameleonCloud) (youtube icon off the main page). The latest [Introduction to Chameleon](https://www.youtube.com/watch?v=LFEGa7sSZxY) is a good place to start, though there are also plenty of advanced topics covered such as [how to use Chameleon for experimentation at the edge](https://www.youtube.com/watch?v=P4LazPMiXF4), [how to create an MPI cluster](https://www.youtube.com/watch?v=U3Q80dRJpiE), as well as topics that highlight content contributed by Chameleon users, e.g., classes teaching ML operations or storage.

**Don’t Start from Scratch.** Are you the kind of person who prefers to learn by modifying an existing example? Me too. Chameleon has a programmatic interface (via python-chi) so it is possible to save your experimental setup – and over the years a lot of our users have done just that and made available a treasure trove of content. If you have an experiment in mind, chances are somebody has set up something similar on the platform in the past. To find it, we move to the “Experiment” tab on the main Chameleon menu bar and select “Trovi”. Trovi is Chameleon’s repository of digital content representing experiments, demos and homework for classes, experimental patterns, and more. You can find experiments by clicking on tags -- if you click “appliance” that will take you to Chameleon-supported images for example, or if you click on “experiment pattern” that is the best way to lay your hands on something you could modify – or if you click on “reproducible research” that will take you to packaged results from recent conferences that you can replay on the system and learn from. Or you can click on badges to browse the available educational content, say. Or just get hold of that search bar and start typing!

If you find any particular Trovi artifact helpful, make sure to leave a comment for the author: they walked an extra mile so you don’t have to walk an extra ten miles, and chances are your thumbs up will make their day! And if you have an interesting class, or a cool research result, or some updates to somebody else’s to contribute, [please do](https://chameleoncloud.readthedocs.io/en/latest/technical/experiments/index.html) -- there is a very good chance that somebody will find it interesting and it will help us as a community advance science faster. And of course if you have any questions about this let us know via the [helpdesk](mailto:helpdesk@chameleoncloud.org).

**Become a Part of the Community.** And talking of a community. First, you should be subscribed to the [users and outages mailing list](https://chameleoncloud.org/user/profile/) and it is also useful to monitor the [outages page](https://chameleoncloud.org/user/outages/) and the [Chameleon blog](https://blog.chameleoncloud.org) for announcements – these connect you to vital information about the system: you don’t want to schedule your important demo on the one day we are down. But also -- Chameleon is an NSF-supported offering open access to high-end, expensive resources -- we don’t charge for them but one way you can give back is by contributing the fruits of your labor, creativity, and knowledge to the community. Publishing your artifacts on Trovi so that others can replay your results or teach based on content you developed is one way. If you found solutions (or even if you found good questions, this is valuable content too!) you can engage via [the user forums](https://forum.chameleoncloud.org/). Last but not least, please make sure [to acknowledge or reference Chameleon](https://www.chameleoncloud.org/learn/frequently-asked-questions/#toc-how-should-i-acknowledge-chameleon-) in your publications – it is important to demonstrate that the system is used so that we may continue to serve you.

And if you have questions – you guessed it, the [helpdesk](mailto:helpdesk@chameleoncloud.org) has the answer!

## While You Were Out

If you are a wizened veteran with many a “not enough hosts” under your belt (we don’t do this anymore, but if you really ARE wizened that must have come from somewhere) you will be glad to know that we now – have more hosts! And a way to mix and match them.

**New site, more hardware.** Yes, I know NCAR has been there for a while – but now it’s **there in style** with 40 Compute Zen 5 nodes, each with an AMD EPYC 4545P 16-core processor, 64 GiB of memory, and 1 TB of NVMe storage, plus 75 TB of object storage – these things boot so fast you’ll have to be careful not to choke on your coffee. And now also 5 NVIDIA Grace A02 nodes – though these need no announcing, everybody seems to have noticed before they were even out – this is why we have advance reservations. And I do have to put in a word for my personal favorite – not at NCAR -- the **Ponte Vecchio (Intel GPU)** nodes at CHI@TACC. In short, new toys!

**New Look, Chameleon-style.** Now this one makes the system quite unrecognizable. It organizes the information better, lets you filter by availability and hardware properties, includes VMs, and generally makes it easier to “spot and snag”. And once you find what you need you actually add it all to the shopping cart (I am not making this up!) and you check out with a nice python-chi reservation sequence – what’s not to like. We will keep the old version for a few months so that you can get comfortable with the new one but its days are numbered (and the numbers go up to about 90).

**Better together: VMs and bare metal.** Bare metal and VMs now share one interface at CHI@TACC as opposed to being two different sites, so you can mix and match: provision either through the same API and put both on the same network. This means that for example VMs can use the CHI@TACC object store, file shares, and fabnetv4 connectivity. You’ll notice that in the web GUI, the "Compute" tab is split into "Bare metal compute" and "Virtual compute." This one also has the old version running in parallel to facilitate transition – but it’s out with the old, in with the new here as well.

That’s it for today folks, way more than I wanted to say but that’s why this blog is a bit late. Enjoy the system!
