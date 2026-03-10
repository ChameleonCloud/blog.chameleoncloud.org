---
abstract: <p>New H100 hardware on KVM@TACC, and good news about KVM lease limits,
  quotas, and SU cost. Additionally, we have SU changes for baremetal, an improved
  the resource browser, and are announcing the deprecation of TACC login.</p>
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2025-09-03 21:05:17+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/d7/09/d709d2c4-8974-42f4-a5fa-f12b34a4dfa3/54565034108_0f4f215511_w.jpg
slug: chameleon-changelog-for-august-2025
subtitle: ''
title: Chameleon Changelog for August 2025
---

<p style="text-align: center;"><img media="" src="https://chameleoncloud.org/media/filer_public/d7/09/d709d2c4-8974-42f4-a5fa-f12b34a4dfa3/54565034108_0f4f215511_w.jpg"></p>

<p style="text-align: center;"><a href="https://www.flickr.com/photos/kitmasterbloke/54565034108/in/photolist-2r8J4C9-2r7SSq3-2r5JBQA-2r5HNKY-2qzKyRT-2r3ozWA-2r33xhd-2r2ja8b-2r27cwB-2r1qEyP-2r1vxHW-2r1bB5c-2r1hnpa-2r1hnpk-2qZrxNe-2qZs28w-2qZrcVp-2qYpZG9-2qYjqTi-2qXGRh5-2qWKkvW-2qWKYtW-2qWJ4sy-2qWKkog-2qWrJk8-2qVGvqf-2qTAyZQ-2qTsitA-2qTqfKA-2qTfmcj-2qS838v-2qRCvKv-2qRfHND-2qQQD9X-2qQiXQV-2qPGwm6-2qPGqqj-2qPBR6v-2qPm35c-2qKDMps-2qKDMok-2qKyD7q-2qKuPmb-2qKpZgM-2qJfS3s-2qCRKVv-2qCK4FS-2qCPDNF-2qCPDMP-2qBVYTw">Steve Knight via Flickr</a></p>

<p>Dear Chameleon users,</p>

<p data-end="578" data-start="106">Whether you’ve been experimenting all summer or are just returning after a break, there is plenty of exciting updates on Chameleon this month: from new H100 GPUs and changes to KVM leases, to updated SU pricing and improvements to the hardware browser. </p>

<p><b>More hardware! More H100 GPUs!</b> This month, we’ve added <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/index.html#hardware">4 additional H100 nodes</a> to the site, now supporting a total 24 H100 instances on KVM@TACC. All the new nodes are part of our KVM partition so you can use them through <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/index.html#hardware">g1.h100.pci.1 instances</a>. However – if you need bare metal access to H100s please let us know via the <a href="https://www.chameleoncloud.org/user/help/ticket/new/guest/">helpdesk</a> – eventually these nodes will be switched between bare metal and virtualized availability but we are considering potentially making some of them statically configured for bare metal reconfiguration now.  </p>

<p><b>More good news about KVM.</b> First, we relaxed the lease duration limits on leases for non-GPU KVM flavors: you can now make a lease for up to 6 months, or the end of your allocation (whichever is earlier). Those leases <a href="https://chameleoncloud.org/learn/frequently-asked-questions/?edit_off=true#toc-how-can-i-extend-a-chameleon-lease-">can be extended</a> just like the ones on bare metal nodes, which means that pending availability your lease could be indefinite in practice. Also, we adjusted the SU cost for these VMs so that it is now slightly less than the equivalent baremetal node which makes them a really good deal! And even better, given that we now have bounded leases and are charging SUs for them, we are relaxing quotas, but will carefully watch utilization. There were a bunch of other tweaks and improvements, including a better KVM@TACC <a href="https://kvm.tacc.chameleoncloud.org/project/leases/calendar/flavor/">availability calendar</a> – and of course as we add new KVM hosts, you’ll notice  availability changes. Lastly, we updated <a href="https://chameleoncloud.org/learn/frequently-asked-questions/?edit_off=true#toc-how-are-kvm-instances-virtual-machines-charged-">our FAQs regarding KVM</a> so you can read about all these changes in one place!</p>

<p><b>Changes to SU pricing</b>. Over the last decade, as the project grew so did the diversity of our resources – but the SUs we charge for them did not. To better reflect the more differentiated makeup of our resources, and ensure fairness to all our users, we overhauled the SU cost of bare metal nodes. We hope that the new SU pricing will encourage everybody to take no more resources than their experiment requires. Updated SUs rates for all allocatable resources on Chameleon (including reservable IPs and VLANs) can always be found <a href="https://chameleoncloud.org/learn/frequently-asked-questions/?edit_off=true#toc-what-are-the-units-of-an-allocation-and-how-am-i-charged-">in our FAQ</a>, or at time of writing our SU rates as as follows:</p>

<p> </p>

<table border="1" cellpadding="1" cellspacing="1" style="width: 500px;">
	<thead>
		<tr>
			<th scope="col">Resource</th>
			<th scope="col">Charge rate (per hour)</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>Base Bare Metal</td>
			<td>1 SU</td>
		</tr>
		<tr>
			<td>Specialized (FPGAs, Storage, High RAM, GPUs before A100)</td>
			<td>2 SUs</td>
		</tr>
		<tr>
			<td>Bare Metal A100 GPU</td>
			<td>4 SUs</td>
		</tr>
		<tr>
			<td>4x Bare Metal A100 GPU</td>
			<td>16 SUs</td>
		</tr>
		<tr>
			<td>Reservable VLAN</td>
			<td>1 SU</td>
		</tr>
		<tr>
			<td>Reservable Stitchable VLAN</td>
			<td>2 SUs</td>
		</tr>
	</tbody>
</table>

<p>Similarly, <a href="https://chameleoncloud.org/learn/frequently-asked-questions/?edit_off=true#toc-how-are-kvm-instances-virtual-machines-charged-">for KVM instances</a>, our SU rates as as follows:</p>

<table border="1" cellpadding="1" cellspacing="1" style="width: 500px;">
	<thead>
		<tr>
			<th scope="col">Flavor</th>
			<th scope="col">Charge rate (per hour)</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>m1.tiny</td>
			<td>0.01 SUs</td>
		</tr>
		<tr>
			<td>m1.small</td>
			<td>0.02 SUs</td>
		</tr>
		<tr>
			<td>m1.medium</td>
			<td>0.04 SUs</td>
		</tr>
		<tr>
			<td>m1.large</td>
			<td>0.08 SUs</td>
		</tr>
		<tr>
			<td>m1.xlarge</td>
			<td>0.15 SUs</td>
		</tr>
		<tr>
			<td>m1.xxlarge</td>
			<td>0.3 SUs</td>
		</tr>
		<tr>
			<td>g1.h100.pci.1</td>
			<td>0.5 SUs</td>
		</tr>
	</tbody>
</table>

<p><b>Resource browser updates. </b>The <a href="https://chameleoncloud.org/hardware/">Chameleon hardware browser</a> allows you to see details for all of the hardware across Chameleon sites. However, it dates back to the beginning of the project, and is starting to show its age. This month, we started the process of improving the interface by cleaning up some of the hardware filters. We’ve also made improvements to how the data is imported, so that it is consistent and easy to understand while still being detailed. Stay tuned for more improvements over the next few months – we’re hoping to make it easier than ever to find resources on Chameleon – and if you have requests or suggestions, as always, please contact us via the <a href="https://www.chameleoncloud.org/user/help/ticket/new/guest/">help desk</a>. </p>

<p><b>Wrapping up KVM migration</b>. In case you have been away all summer, KVM now has <a href="https://chameleoncloud.org/blog/2025/06/02/chameleon-changelog-for-may-2025/">GPU instances</a> and, to support that, we rolled out changes to <a href="https://chameleoncloud.org/blog/2025/08/04/chameleon-changelog-for-july-2025/">require leases for all VMs</a>. Today we shut down old VMs that are not tied to a reservation <a href="https://chameleoncloud.org/blog/2025/08/04/chameleon-changelog-for-july-2025/">as per our earlier announcement</a>. But never fear – if you just came back from vacation and found that your VM has been shut down  and want it back <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_instance_migration.html#restoring-from-a-snapshot">see this documentation for how to restore your instance</a>.</p>

<p><b>TACC login deprecation. </b>Back in October 2020, <a href="https://chameleoncloud.org/blog/2020/10/05/chameleon-access-federated-login-coming-soon/">Chameleon added support for federated identity</a>. This enabled users to login using  their existing institutional credentials – but we still kept the old login, via the TACC account system (TAS), available to provide backwards compatibility. However, five years is a long time to allow everyone to move to the federated identity login and so we are preparing to drop the support for login via TAS. This is currently scheduled for January 2026: we hope that this will give everybody plenty of time to plan around and <a href="https://chameleoncloud.readthedocs.io/en/latest/user/federation.html#account-linking">link their existing account</a> to a Globus identity (and you will still be able to do it after the deadline though it may be a little bit more of a todo). As always, please let us know <a href="https://www.chameleoncloud.org/user/help/ticket/new/guest/">via the help desk</a> if you have any issues or questions about this process.</p>

<p>Happy experimenting!</p>