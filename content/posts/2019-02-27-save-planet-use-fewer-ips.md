---
abstract: "<p><a href=\"https://en.wikipedia.org/wiki/IPv4_address_exhaustion\">IPv4\
  \ address exhaustion</a>, along with natural resources depletion and global warming,\
  \ has long been recognized as one of the greatest\_environmental\_threats facing\
  \ humanity. Read on to learn how to keep\_floating IPs afloat!\_</p>"
authors:
- Kate Keahey
categories:
- Tips and Tricks
date: '2019-02-27 00:21:15+00:00'
featured: false
hide_image: true
image: ''
slug: save-planet-use-fewer-ips
subtitle: ''
title: Save the Planet, Use Fewer IPs
---

<p>Yo dawg, float me some IPs – ah, how often do we hear that line around research labs and coding dens… Unfortunately, few of us realize that <a href="https://en.wikipedia.org/wiki/IPv4_address_exhaustion">IPv4 address exhaustion</a>, along with natural resources depletion and global warming, has long been recognized as one of the greatest existential threats facing humanity. Along with everybody else, the Chameleon testbed has a severely rationed number of public IP addresses that can be assigned to user instances. While we feel that our users generally deserve the stars and the moon, we find that those may often be easier to give than anything in the IPv4 space. </p>

<p>However, the good news is that in most cases you can get by without this scarce and expensive commodity. To understand how, I sat down with Chameleon Ticketmaster and IP Environmentalist in Chief, Jake Colleran. According to Jake you can connect to all of your instances with just one floating IP address using a technique called “bastion host”. This allows the IPs to retreat to a bastion and defend themselves from overuse. </p>

<p>Here is how it works. First, you create however many instances you need; they will be connected by default to a VLAN called sharednet1 (if you need more isolation you can <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/networks/networks_vlan.html#configuring-networking-using-the-cli">create your own VLAN</a> instead). “A bastion host is a gateway to all your instances on a network”, says Jake, “to create it, simply pick one of your nodes and associate a floating IP with your instance”. This makes that node accessible via <em>ssh </em>over public internet. Once you <em>ssh </em>into that one instance (using the public IP), you can <em>ssh </em>into any of your other nodes connected to its VLAN  (via their private IPs) like so:<span style="background-color: rgb(238, 238, 238);">   </span></p>

<div style="background: #eee; border: 1px solid #ccc; padding: 5px 10px;">
<p>[local]</p>

<p>$ ssh-add /path/to/&lt;keypair&gt;.pem&lt;/keypair&gt;</p>

<p>$ ssh -A cc@&lt;floating_ip_address&gt;&lt;/floating_ip_address&gt;</p>

<p>[remote]</p>

<p>$ ssh cc@&lt;private_ip_address&gt;&lt;/private_ip_address&gt;</p>
</div>

<p>But wait, there's more! Jake explains that what really makes it work is his favorite environmentally friendly shortcut using the -J option of the ssh command:<br>
 </p>

<div style="background: #eee; border: 1px solid #ccc; padding: 5px 10px;">
<p>$ ssh-add /path/to/&lt;keypair&gt;.pem &lt;/keypair&gt;</p>

<p>$ ssh -J cc@&lt;floating_ip_address cc=""&gt;&lt;/floating_ip_address&gt;</p>
</div>

<p>“This simple technique makes it as easy to use the bastion login with just one floating IP as assigning lots to every instance you can think of”, enthuses Jake, “This should keep us afloat in floating IPs for some time to come” </p>

<p>All of this is so much writing to say: go green, use those floating IPs responsibly -- and whenever you can, please recycle. </p>

<p>We have only one planet! </p>