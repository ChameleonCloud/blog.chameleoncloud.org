---
abstract: "<p dir=\"ltr\">The Chameleon Tickets of the Year blog returns for a second\
  \ time! To close out the year, we\u2019ve gathered and answered some of the most\
  \ commonly seen user problems brought to the Help Desk\u2019s attention in 2021.\
  \ As always, <a href=\"https://www.chameleoncloud.org/user/help/\">creating a helpdesk\
  \ ticket</a> is the fastest way to <a href=\"https://www.chameleoncloud.org/user/help/\"\
  >reach the Chameleon support team</a> and get help, though it doesn\u2019t hurt\
  \ to check <a href=\"https://chameleoncloud.readthedocs.io/en/latest/\">our documentation</a>\
  \ and the <a href=\"https://chameleoncloud.org/learn/frequently-asked-questions/\"\
  >Chameleon FAQ</a> as well!</p>"
authors:
- Isabel Brunkan
categories:
- Tips and Tricks
date: '2021-12-14 20:32:39+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/eb/0a/eb0a9c1a-018f-4216-a782-01c121822711/screen_shot_2021-12-14_at_122654_pm.png
slug: tickets-of-the-year-2021-edition
subtitle: ''
title: 'Tickets of the Year: 2021 Edition'
---

<p dir="ltr">The Chameleon Tickets of the Year blog returns for a second time! To close out the year, we’ve gathered and answered some of the most commonly seen user problems brought to the Help Desk’s attention in 2021. As always, <a href="https://www.chameleoncloud.org/user/help/">creating a helpdesk ticket</a> is the fastest way to <a href="https://www.chameleoncloud.org/user/help/">reach the Chameleon support team</a> and get help, though it doesn’t hurt to check <a href="https://chameleoncloud.readthedocs.io/en/latest/">our documentation</a> and the <a href="https://chameleoncloud.org/learn/frequently-asked-questions/">Chameleon FAQ</a> as well! </p>

<p>If you want to learn about more, check out our <a href="https://chameleoncloud.org/blog/2020/12/21/tickets-year-solutions-your-2020-ticket-problems/">last December’s blog post about 2020’s most frequent Chameleon errors</a>  – and if there are common problems that you’ve been seeing lately and that you’d like to share with others, please leave a comment on this blog. And dare we say it again – you can always reach out to the <a href="https://www.chameleoncloud.org/user/help/">Help Desk team</a> for white-glove troubleshooting help.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-520cb39b-7fff-b44d-e72b-cdab99cb8569">Commonly Encountered Problems</b></p>

<p dir="ltr"><b id="docs-internal-guid-520cb39b-7fff-b44d-e72b-cdab99cb8569">Problem: </b>Let’s say you are trying to log into Chameleon to conduct game-changing research but you get an “Email address is already in use” error message – that must be a bit deflating... </p>

<p dir="ltr"><b id="docs-internal-guid-520cb39b-7fff-b44d-e72b-cdab99cb8569">Solution: </b>There are two possible reasons why this might happen. </p>

<p dir="ltr"><strong>If you already migrated to a federated account</strong>, it’s likely that you linked your Chameleon access to one federated ID, and then tried to log in with a different one! For example, if you used your ORCID account to log into Chameleon in the past, and are now trying to log in using your Google account, Chameleon won’t know that you are the same person. To resolve this, go to the <a href="https://app.globus.org/account/identities">Globus</a> App managing those accounts and link them there. That way, Globus will tell Chameleon about both accounts, and you’ll be able to log in with either. </p>

<p>Another reason for why this might happen is that <strong>you haven’t logged into Chameleon since the transition to federated accounts in 2020</strong>. If this is the case, welcome back! You’ll need to <a>contact the Help Desk</a> to help you migrate your old account; please, include your old account’s username, as well as the new one you’d like linked.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-520cb39b-7fff-b44d-e72b-cdab99cb8569">Problem: </b>Let’s say you’re a Chameleon project PI and are trying to add users to your project – but instead of seeing them on your project immediately you get an “Invitation Sent!” message.</p>

<p dir="ltr"><b id="docs-internal-guid-520cb39b-7fff-b44d-e72b-cdab99cb8569">Solution:</b> Good news, everything is alright! When you add a username to a project, we check for a matching user in our system. If you submit an email that is not tied to a current user, we send a message to that email address with an invitation link. After the user clicks this link, they will be asked to sign up or log into Chameleon, and then they are automatically added to the project, regardless of the email their account is tied to. This means as long as the invite is sent to any email for the user, they can use it to join the project. </p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-520cb39b-7fff-b44d-e72b-cdab99cb8569">Problem: </b>Let’s say you’ve run close to the end of your lease but still had research to conduct – what now?</p>

<p dir="ltr"><b id="docs-internal-guid-520cb39b-7fff-b44d-e72b-cdab99cb8569">Solution: </b>One fix for that is to <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/reservations.html?highlight=extend%20lease#id3">extend your lease</a>. However, it sometimes happens that someone has made a reservation for the node you have leased to begin immediately after your lease stops. If this is the case, you won’t be able to extend your lease. But you can take a snapshot of your host using <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images.html#the-cc-snapshot-utility">cc-snapshot</a>, which creates an image of the current instance. This can be used later when launching a new instance to restore the state of the original instance.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-520cb39b-7fff-b44d-e72b-cdab99cb8569">Problem: </b>Getting a “no active reservations” error message when launching a new instance despite being sure that you made a lease? You might need to make a host reservation! </p>

<p dir="ltr"><b id="docs-internal-guid-520cb39b-7fff-b44d-e72b-cdab99cb8569">Solution: </b>If your reservation does not appear in the drop down menu when launching a new instance, make sure that you actually <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/reservations.html?highlight=reserve%20a%20host#creating-a-lease-to-reserve-physical-hosts">reserved a host</a>! Your lease should contain reservations, which can be for various types of resources including hosts, networks or floating IPs. It is possible to create leases that contain only a network or floating ip reservation, but only host reservations will appear in the ‘Launch Instance’ menu. To create a host reservation, select the ‘Hosts’ tab in the ’Create Lease’ window.</p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-520cb39b-7fff-b44d-e72b-cdab99cb8569"><img height="237" src="https://lh4.googleusercontent.com/S2aD0v3C69t-KV_TKE3jnTjchc39jIuqjNPZIfUnupeTbejDjhFSV08R6GFI_Vhi9noAwNVB80548h5okfAbwK-PoIytAxWPBNz9-uWF3Y4HXSjAAPyeOPDGwIr3zQp5WcIG7XNy" width="624"></b></p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-520cb39b-7fff-b44d-e72b-cdab99cb8569">Problem: </b>Let’s say you are having trouble pinging or ssh-ing into your KVM instance and suspect that some ports may not be open.</p>

<p dir="ltr"><b id="docs-internal-guid-520cb39b-7fff-b44d-e72b-cdab99cb8569">Solution: </b>We have some default firewall rules set up when you’re using the Chameleon-supported images. To check the firewall rules, please use our preconfigured ufw tool and run  “sudo ufw status”. To open a port, update the firewall rules using the ufw tool. To learn more, you can read our <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/networks/networks_basic.html#firewall">user documentation</a>.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-520cb39b-7fff-b44d-e72b-cdab99cb8569">Problem: </b>Let’s say you are trying to extend your lease to nodes that you see are available in the <a href="https://chi.tacc.chameleoncloud.org/project/leases/calendar/">host calendar</a> but running into an error while updating the lease. You might be seeing this error message: “Floating IP reservation cannot be updated with requested parameters. Cannot remove allocations from an active reservation. Please try again”.</p>

<p dir="ltr"><b id="docs-internal-guid-520cb39b-7fff-b44d-e72b-cdab99cb8569">Solution: </b>If you have reserved floating IPs along with the nodes, the above error occurs when one or more floating IPs you reserved are no longer available during your extended time. If you see the error, please <a href="https://www.chameleoncloud.org/user/help/">submit a ticket to the help desk</a>, and we can help you remove the floating IP reservation from your lease, so that you can extend your node reservation. </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-520cb39b-7fff-b44d-e72b-cdab99cb8569"><img height="331" src="https://lh4.googleusercontent.com/vPpPq9Ikl7oz3BwMR00OTCmvROTaLUaZgqhtP-_3mlFLlfVBeTRHp8ix70_4jK1BRFNLRkby2quWXJqcgShsiChB7pfp1hrFcJg9OgEqCcfaMc9vorH8Y2zBGLKPXi3ySVmuA8UD" width="624"></b></p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-520cb39b-7fff-b44d-e72b-cdab99cb8569">Problem: </b>Running out of floating IPs?</p>

<p dir="ltr"><b id="docs-internal-guid-520cb39b-7fff-b44d-e72b-cdab99cb8569">Solution: </b>This error often shows up when users want to connect an IP to every single node in a large-scale deployment – the  good news is that you only need one! If you have multiple instances, you don’t need to connect a unique floating IP to each and every one. You can connect to all of your instances with just one floating IP address using “bastion host”. To learn more, please read our <a href="https://chameleoncloud.org/blog/2019/02/27/save-planet-use-fewer-ips/">blog post</a> which describes the process in more detail.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-520cb39b-7fff-b44d-e72b-cdab99cb8569">Problem: </b>Not sure what to include in a help desk ticket? We’ve got you covered. Here’s everything you can include to help us resolve your problem faster and get you back to experimenting. </p>

<p dir="ltr"><b id="docs-internal-guid-520cb39b-7fff-b44d-e72b-cdab99cb8569">Solution: </b>More information is always better! Attachments, error messages, outputs - include it all. That being said, here are some key points to make sure to include: </p>

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

<p dir="ltr">We hope this helps answer some of the Chameleon errors you’re running into! Feel free to reach out to the Help Desk at any point - no ticket is too small, no problem too complicated, and now you have everything you need to write the perfect <a href="https://www.chameleoncloud.org/user/help/">Help Desk ticket</a>. </p>

<p> </p>

<p dir="ltr">From all of us at Chameleon, Happy Holidays!</p>