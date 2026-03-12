---
abstract: <p>It's the end of the year, so that means it's time for our annual Tickets
  of the Year blog! This blog covers some of our most common help desk tickets and
  provides solutions, so it can hopefully be a helpful reference if you run into any
  of these problems. If you need more help, the best places to look would be the <a
  href="https://chameleoncloud.readthedocs.io/">docs</a>, the <a href="https://chameleoncloud.org/learn/frequently-asked-questions/">FAQ</a>,
  or submitting a new ticket to the <a href="https://www.chameleoncloud.org/user/help/">help
  desk</a>.</p>
authors:
- Marc Richardson
categories:
- Tips and Tricks
date: '2025-12-15 16:06:49+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/d8/f9/d8f9cd8c-c082-471b-a7ea-aff311bf011d/image.jpg
related_posts:
- slug: chameleon-tickets-of-the-year-2024
  title: Chameleon Tickets of the Year 2024
- slug: tickets-of-the-year-on-chameleon-2023
  title: Tickets of the Year on Chameleon (2023)
- slug: tickets-of-the-year-2022
  title: 'Tickets of the Year: 2022'
- slug: tickets-of-the-year-2021-edition
  title: 'Tickets of the Year: 2021 Edition'
- slug: tickets-year-solutions-your-2020-ticket-problems
  title: 'Tickets of the Year: Solutions to Your 2020 (Ticket) Problems'
slug: tickets-of-the-year-2025
subtitle: Tips and Tricks for Resolving Common Help Desk Tickets
title: 'Tickets of the Year: 2025'
---

<h2>Tickets of the Year: 2025</h2>

<p>It's the end of the year, so that means it's time for our annual Tickets of the Year blog! This blog covers some of our most common help desk tickets and provides solutions, so it can hopefully be a helpful reference if you run into any of these problems. If you need more help, the best places to look would be the <a href="https://chameleoncloud.readthedocs.io/">docs</a>, the <a href="https://chameleoncloud.org/learn/frequently-asked-questions/">FAQ</a>, or submitting a new ticket to the <a href="https://www.chameleoncloud.org/user/help/">help desk</a>.</p>

<p>If you're curious about the most common tickets we've encountered in the past, you can check out our Tickets of the Year blogs from <a href="https://www.chameleoncloud.org/blog/2024/12/19/chameleon-tickets-of-the-year-2024/">2024</a>, <a href="https://www.chameleoncloud.org/blog/2023/12/19/tickets-of-the-year-on-chameleon-2023/">2023</a>, <a href="https://www.chameleoncloud.org/blog/2022/12/12/tickets-of-the-year-2022/">2022</a>, <a href="https://www.chameleoncloud.org/blog/2021/12/14/tickets-of-the-year-2021-edition/">2021</a>, and <a href="https://www.chameleoncloud.org/blog/2020/12/21/tickets-of-the-year-solutions-to-your-2020-ticket-problems/">2020</a>.</p>

<h3>Tickets of the Year!</h3>

<p><strong>Ticket:</strong> You've successfully reserved and launched an instance with A100 GPUs, but when you try to run your CUDA code, you get an error saying "no CUDA-capable device is detected"<br>
<strong>Solution:</strong> This is usually a driver or environment issue. First, verify that the GPU is actually visible to your instance by running <code>nvidia-smi</code>. If this command isn't found or shows no GPUs, you may need to install the NVIDIA drivers. For most Chameleon images, you can install drivers using our convenience script: <code>sudo /usr/local/bin/install_nvidia_drivers.sh</code>. After installation, reboot your instance. If you're working in a container, make sure you're using the NVIDIA container runtime and that your container has access to the GPU devices. You can verify CUDA availability with <code>nvidia-smi</code> inside the container. For persistent issues, check that your CUDA version is compatible with the installed driver version.</p>

<p><strong>Ticket:</strong> You're trying to set up a Spark cluster or another distributed computing framework on Chameleon, and you want to make sure you're doing it securely<br>
<strong>Solution:</strong> Great question! For distributed computing setups, security is crucial. First, <strong>never expose your cluster services directly to the public internet</strong>. Instead, use Chameleon's private network to allow communication between your cluster nodes—all instances within the same project can communicate over the shared private network (typically 192.168.X.X addresses). For accessing web interfaces (like Spark UI), use SSH tunneling rather than opening ports. One easy approach is to use <code>sshuttle</code>, which creates a VPN-like tunnel to your Chameleon network. You can also use a <a href="https://www.chameleoncloud.org/blog/2023/01/23/experiment-pattern-bastion-host/">bastion host pattern</a> to simplify access to multiple nodes. If you prefer the traditional approach, you can set up an SSH tunnel like this: <code>ssh -L 8080:localhost:8080 cc@&lt;floating-ip&gt;&lt;/floating-ip&gt;</code>. This lets you access the Spark UI at localhost:8080 on your local machine while keeping the port closed to the internet. For authentication between nodes, use SSH keys and configure your framework to use secure communication. Check out our <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/complex.html">documentation on complex appliances</a> for more details on multi-node setups.</p>

<p><strong>Ticket:</strong> You're trying to make a reservation using the CLI, but you're getting a flavor reservation error<br>
<strong>Solution:</strong> Flavor reservations are specific to KVM@TACC, and the key detail is that you must use the <strong>flavor ID</strong>, not the flavor name. You can list available flavors and their IDs with <code>openstack flavor list</code>. Once you have the correct flavor ID, you can create your lease using that ID in your reservation command. If you're still getting errors, check the <a href="https://chameleoncloud.org/user/discovery/">resource calendar</a> to confirm that the hardware you want is actually available during your desired time window. Make sure you're targeting KVM@TACC with your CLI environment variables. For detailed instructions on creating flavor-based leases, check out our <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/reservations/cli_reservations.html#creating-a-lease-for-a-flavor-on-kvm-tacc">CLI reservations documentation</a>.</p>

<p><strong>Ticket:</strong> You need to open specific ports for communication between instances in your project<br>
<strong>Solution:</strong> To allow communication between instances in the same project, you'll need to configure your firewall settings. For <strong>bare metal instances</strong>, you need to update the firewall rules on each instance using tools like <code>iptables</code> or <code>firewalld</code>. For <strong>KVM instances</strong>, you'll need to modify your security groups to allow the specific ports and protocols you need. By default, instances within the same project can communicate over the shared private network (typically 192.168.X.X addresses), but you need to explicitly allow the ports your applications use. For example, if you're running a database on port 5432, you'd need to allow incoming connections on that port. For detailed information on configuring security settings, check out our <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/networks/networks_basic.html#security">network security documentation</a>. Remember to only open the ports you actually need, and restrict access to specific IP ranges when possible to maintain security.</p>

<p><strong>Ticket:</strong> You're trying to extend your lease, but the system won't let you<br>
<strong>Solution:</strong> There are a few common reasons this happens. First, check if the resource you're trying to extend is already reserved by another user after your current lease ends—you can verify this on the <a href="https://chameleoncloud.org/user/discovery/">resource calendar</a>. If the hardware is available, the next thing to check is your allocation: your project allocation might have expired or be expiring during your desired extension period. You can check your allocation status under the <a href="https://chameleoncloud.org/user/projects/">project dashboard</a>. If your allocation has expired, your PI will need to request a renewal. Another possibility is that you've exhausted your Service Units (SUs)—if so, your PI can request a recharge.</p>

<p><strong>Ticket:</strong> You haven't logged into Chameleon in a while, and now your old credentials aren't working, or you're having trouble logging in<br>
<strong>Solution:</strong> If you haven't used Chameleon in some time, your account might need to be re-linked. Don't create a new account! Instead, submit a help desk ticket from the same email address associated with your old account, and our team can help reconnect it. If you want to use a different email address, you can <a href="https://chameleoncloud.readthedocs.io/en/latest/user/federation.html#account-linking">link multiple email addresses to your account through Globus</a>. Simply log into Globus, go to Account Settings, and add your new email under "Linked Identities." Then you can set it as your primary identity. If you're experiencing login issues specifically (like logins that hang), try clearing your browser cache and cookies, or try a different browser. Some users have found that browser extensions or VPNs can interfere with the authentication process.</p>

<p><strong>Ticket:</strong> You're trying to SSH into your instance, but the connection keeps failing or timing out<br>
<strong>Solution:</strong> SSH issues can have many causes, so here's a systematic troubleshooting approach. First, verify the basics: Did you associate a floating IP address to your instance? You can check this in the instance details page. Are you using the correct username? For most Chameleon-supported images, it's <code>cc</code>, not <code>root</code> or <code>ubuntu</code>. Are you specifying the correct SSH key file with the <code>-i</code> flag?</p>

<p>If those check out, verify your key file has the right permissions: <code>chmod 600 your_key.pem</code>. Next, check if your instance actually booted successfully—look at the web console (available in the GUI under your instance's Actions menu) to see if there were any boot errors. Sometimes instances show as "Active" but didn't complete the boot process.</p>

<p>For more detailed diagnosis, use verbose SSH output: <code>ssh -v cc@your-floating-ip</code>. This will show you exactly where the connection is failing. Common issues include: wrong key being offered, security group blocking port 22 (mainly an issue on KVM@TACC), or network connectivity problems.</p>

<p>If you're on a restrictive network (like a corporate or university network), try from a different network or ask your network administrator about SSH access. As a last resort, you can add your SSH public key through the web console if you can't connect—open the console and edit <code>~/.ssh/authorized_keys</code> to add your key.</p>

<h3>Happy Holidays!</h3>

<p>As these are some of the most common issues reported on Chameleon this year, we hope this blog helps you troubleshoot these problems if you encounter them! Remember, the <a href="https://www.chameleoncloud.org/user/help/">help desk</a> is always here if you need assistance. Have a great holiday season, and happy experimenting in 2025!</p>