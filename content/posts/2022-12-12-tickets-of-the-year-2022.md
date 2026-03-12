---
abstract: <p>As has become holiday tradition, we review some of our most common tickets
  of 2022, and provide answers and context that we hope is a helpful gift for all
  of our experimenters in the coming year.</p>
authors:
- Adam Cooper
categories:
- Tips and Tricks
date: '2022-12-12 18:01:47+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/f0/20/f02006b1-afb1-4582-993e-f9e9e3ae5d54/christmas-santa-vintage-letter.jpg
related_posts:
- slug: tickets-of-the-year-2021-edition
  title: 'Tickets of the Year: 2021 Edition'
- slug: tickets-year-solutions-your-2020-ticket-problems
  title: 'Tickets of the Year: Solutions to Your 2020 (Ticket) Problems'
slug: tickets-of-the-year-2022
subtitle: ''
title: 'Tickets of the Year: 2022'
---

<p>It’s the end of the year, so that means it’s time for our annual TIckets of the Year blog! This blog encompasses some of our most common help desk tickets and outlines some answers for them, so it can hopefully be a helpful reference if you run into any of these problems. If you need more help, the best places to look would be <a href="https://chameleoncloud.readthedocs.io/en/latest/">the docs</a>, <a href="https://chameleoncloud.org/learn/frequently-asked-questions/">the FAQ</a>, or <a href="https://chameleoncloud.org/user/help/">submitting a new ticket to the help desk</a>. </p>

<p>If you’re curious about the most common tickets we’ve encountered in the past, you can check out our Tickets of the Year blogs from <a href="https://chameleoncloud.org/blog/2021/12/14/tickets-of-the-year-2021-edition/">2021</a> and <a href="https://chameleoncloud.org/blog/2020/12/21/tickets-year-solutions-your-2020-ticket-problems/">2020</a>.</p>

<h2>Tickets of the Year!</h2>

<p id="cant-connect-ssh"><strong><a href="#cant-connect-ssh">Ticket</a></strong>: Your instance has started, but you can’t connect to it via SSH even though you’ve <a href="https://chameleoncloud.readthedocs.io/en/latest/getting-started/index.html#associating-an-ip-address">associated a floating IP address</a> and <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/gui.html#key-pairs">set up your keys correctly</a>. You go to check the web console to diagnose the issue, but that’s not working either!<br>
<strong>Solution</strong>: You might have a bad image that failed to boot properly, even though it looks like your instance is active. This can sometimes happen if you’re using a custom image which has some weird state change occur while it is being built. It might be a good idea to try one of the officially supported Chameleon images on the same node to narrow down the issue. If that doesn’t work at all, it’s a good idea to monitor the web console as the node boots so you can see output from the kernel or our init scripts, which often yields an answer to the problem. The answer might be an internal networking/hardware issue, which you should report to the help desk along with whatever errors you observed.</p>

<p id="not-enough-resources"><strong><a href="#not-enough-resources">Ticket</a></strong>: I know what resources I want, but when I go to make a lease to reserve them, it says there are “not enough resources available!”<br>
<strong>Solution</strong>: It’s probably because the hardware isn’t available. Your best bet to confirm this would be to check the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/reservations.html#the-lease-calendars">resource calendar</a> at the appropriate site. If that hardware is not available in the time window you need it, you can check the <a href="https://chameleoncloud.org/hardware/">hardware browser</a> to see if there is any other hardware which meets your needs. For more details on how to filter for your desired specifications, check out <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/discovery.html">the docs</a>. Another option is to make a lease which starts in the future, so that you can reserve the hardware as soon as the existing reservation ends.</p>

<p id="cant-make-lease"><strong><a href="#cant-make-lease">Ticket</a></strong>: I know for a fact that my hardware is available, but I still can’t make a lease!<br>
<strong>Solution</strong>: Your project’s allocation has probably expired, or will expire during the time of your desired lease. It’s also possible that your allocation no longer has any <a href="https://chameleoncloud.readthedocs.io/en/latest/user/project.html#service-units">SUs</a> available. You can double check this <a href="https://chameleoncloud.readthedocs.io/en/latest/user/project.html#view-charge">here</a>, and ask your PI to <a href="https://chameleoncloud.readthedocs.io/en/latest/user/project.html#recharge-or-extend-your-allocation">request a renewal/recharge</a> so that you can reserve your resources.</p>

<p id="old-credentials"><strong><a href="#old-credentials">Ticket</a></strong>: I haven’t logged into Chameleon in a long time, and now I can’t use my old credentials anymore!<br>
<strong>Solution</strong>: You may have a legacy account, or perhaps an internal identifier was changed by TACC or Globus. No need to make a new account! Simply report it to the help desk using the same email address as your broken account, and we can make sure it is properly linked up to Chameleon. If the issue is that you want to use a new email address, you can <a href="https://app.globus.org/account/identities">link it to your existing account under Globus</a>, and then set it as your primary identity under the "Manage Identities" menu.</p>

<p id="ssh-tips"><strong><a href="#ssh-tips">Ticket</a></strong>: I don’t know how to SSH into my instance!<br>
<strong>Solution</strong>: We allow users to provision SSH keys on their instances in 2 different ways: You can either <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/gui.html?highlight=keys#creating-a-key-pair">generate a keypair</a> in our web GUI, or you can <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/gui.html#importing-a-key-pair">import an existing keypair from your local machine</a>. Then, you can load them onto your instance at creation time. &lt;picture&gt; If you accidentally start up an instance without the right keys loaded, you can always open your ~/.ssh/authorized_keys file using the web console, and paste the right public key in. Once you do this, you will be able to SSH to your instance. It is important that you never upload your private key, and never enable SSH password authentication!&lt;/picture&gt;</p>

<p><img src="https://chameleoncloud.org/media/filer_public/bb/cc/bbcc3981-2e38-4212-a977-6e8d9aeb0b5d/keys.png" style="width: 600px; height: 514px;"></p>

<p id="timed-out"><strong><a href="#timed-out">Ticket</a></strong>: I waited a long time for my instance to spawn, and it eventually timed out.<br>
<strong>Solution</strong>: Similar to <a href="#cant-connect-ssh">the above ticket</a>, it could be a bad image or other start-up errors. You should keep an eye on the web console while your image spawns and see if it reports any errors. Another issue could be that the network switch attached to your node was overloaded while your instance was spawning. Did you try to spawn many instances of the same type at the same time? It might help to limit that to 1-3 instances at the same time. It could also be the case that another user overloaded the switch if you only tried to spawn 1 instance. It never hurts to try again. If not, it could be internal hardware/networking issues, in which case, it’s best to report the issue to the help desk.</p>

<p id="expose-port"><strong><a href="#expose-port">Ticket</a></strong>: I have a Postgres/Spark/Zookeeper/Kubernetes/some other service running on my instance which I want to expose to the open internet!<br>
<strong>Solution</strong>: Don’t do that! There is very rarely a need to allow incoming connections to your instance under any circumstances. If you have a service which needs to be contacted via the internet, the best way to do this is within a secure, encrypted tunnel. We highly recommend an <a href="https://linuxize.com/post/how-to-setup-ssh-tunneling/">SSH tunnel</a>, since it is the easiest to set up. We never recommend changing firewall rules, and there is no need to mess with security groups unless you are using the KVM cloud. </p>

<p id="storage"><strong><a href="#storage">Ticket</a></strong>: How do I store my data for a long-term experiment? How can I make it easily accessible to multiple nodes or users?<br>
<strong>Solution</strong>: Luckily for you, we recently published another <a href="https://chameleoncloud.org/blog/2022/10/26/data-storage-management-and-sharing-on-chameleon/">blog post</a> which can hopefully answer all your storage questions! In this blog, we go over different ways to store your data, including ephemeral NFS shares, Object Storage, and Block Storage.</p>

<p id="missing-invite"><strong><a href="#missing-invite">Ticket</a></strong>: My PI invited me to our project, but I never received my invite!<br>
<strong>Solution</strong>: It could be that the invite went to your spam folder. In some cases, email providers (particularly Google) reject our emails outright. If this happens, open a new help ticket or send an email to <a href="mailto:help@chameleoncloud.org">help@chameleoncloud.org</a> from the same email address that your PI invited, and we can help you out with an invite link. </p>

<h2>Happy Holidays!</h2>

<p>As these are some of the most common issues reported on Chameleon, we hope this blog helps everyone on mitigating these pesky issues on Chameleon! Have a great holiday, and a happy new year!</p>