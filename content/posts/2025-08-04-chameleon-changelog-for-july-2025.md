---
abstract: "<p>This month, we have a significant change to KVM@TACC: <a href=\"https://chameleoncloud.org/blog/2025/07/01/chameleon-changelog-for-june-2025/\"\
  >as per our announcement last month</a>, all KVM instance launches will now require\
  \ an advance reservation step in the allocation workflow (with the \u201Cadvance\u201D\
  \ potentially being once second from now, i.e., on demand). Also, we have cool new\
  \ hardware on CHI@Edge, and improvements to the \u201Cmessage of the day\u201D on\
  \ Chameleon-supported base images</p>"
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2025-08-04 14:32:26+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/bc/54/bc54607f-0d5e-4060-996c-087b2da5ef86/54680578838_af0a05f319_w.jpg
slug: chameleon-changelog-for-july-2025
subtitle: ''
title: Chameleon Changelog for July 2025
---

<p style="text-align: center;"><img media="" src="https://chameleoncloud.org/media/filer_public/bc/54/bc54607f-0d5e-4060-996c-087b2da5ef86/54680578838_af0a05f319_w.jpg"></p>

<p style="text-align: center;"><a href="https://www.flickr.com/photos/tambako/54680578838/in/photolist-2riWg3E-2riCnqG-2ri8kjg-2rhBgbD-2rhGGCB-2rhGGBV-2rhkv1x-2rhiTQy-2qMLPjH-2reCxPT-2rectQE-2re6X54-2re6X4N-2recynz-2rectMt-2recYPH-2re6WZp-2re9YKv-2rdZe9c-2re5Mm5-2rdZe8f-2re5Rrt-2re4L8x-2re5Mhn-2re6igS-2re6igr-2rdZp3c-2rc6nHM-2r9r2AC-2r99iZy-2r8J4Ff-2r8J4C9-2r7SSq3-2r5RSVZ-2r5JBQA-2r5HNKY-2r5HNKh-2r5nS2o-2r4Qi8D-2r4AJt2-2qzKyRT-2r3ozWA-2r33xhd-2r2ja8b-2r27cwB-2r1VQwU-2r1qEyP-2r1vxHW-2r1bB5c-2r1hnpa/">Tambako The Jaguar via Flickr</a></p>

<p>Dear Chameleon users,</p>

<p>This is one of the more important changelog blogs you are going to read. </p>

<p><b>KVM Changes</b>. As we announced <a href="https://chameleoncloud.org/blog/2025/07/01/chameleon-changelog-for-june-2025/">last month</a>, starting this month all KVM instance launches will now require an advance reservation step in the allocation workflow (with the “advance” potentially being once second from now, i.e., on demand). In other words, in order to launch VMs, you will first need to <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_gui.html#creating-leases-for-vms">create a flavor lease</a>, similar to the allocation step you are required to do for baremetal instances; this lease will have a well-defined beginning and end so that your VM instances will no longer run indefinitely as an unbounded instance. Currently running unbounded VMs will stay running until September 1st, at which point we will snapshot and terminate them. This means that if one of your VM instances is not tied to a reservation by then, it will be deleted. You can avoid this unavoidable fate! We recommend that before September 1 you <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_instance_migration.html#migrating-an-ad-hoc-kvm-instance-to-a-reservation">follow our process</a> to migrate on-demand instances to a reservable flavor to avoid any interruption in your experiment. If you miss this deadline – but send us a sufficiently unhealthy amounts of chocolates – we will let you <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_instance_migration.html#restoring-from-a-snapshot">restore your instance</a> from the snapshot ;-). </p>

<p>Also, where before all VM instances were “for free” we now got serious about charging you – in SUs, similar to on baremetal reservations.  The charge cost is based on the proportion of node hours that your VMs use. For example, our KVM GPU nodes support 4 g1.h100.pci1 instances per host. If you make a 1 hour lease, for 1 instance of this flavor, you’ll be charged 1/4th of what you would be charged for the g1.h100.pci1 bare metal node. For more information, <a href="https://chameleoncloud.org/learn/frequently-asked-questions/#toc-what-are-the-units-of-an-allocation-and-how-am-i-charged-">see our FAQs</a>. Please keep in mind that these details are subject to change as we adjust to this new usage pattern. For any questions about this, please feel free to contact us <a href="https://chameleoncloud.org/user/help/">via the Help Desk</a>. The bright side of these changes is that you can now use VMs with GPUs on those H100 instances – and there will be more of them coming – they are necessary to ensure fair sharing of those super expensive instances between all users! </p>

<p><b>Pilot: New Python-chi Widgets.</b> We are trying out some usability improvements to help you create your experiments faster! This month we are trying a new idea: we’ve updated our programmable interface to the testbed, <a href="https://python-chi.readthedocs.io/">python-chi</a>, with new Jupyter widgets. The chi.hardware module now includes <a href="https://python-chi.readthedocs.io/en/latest/modules/hardware.html#chi.hardware.show_nodes">show_nodes</a> which will display a sortable table table of hosts, so that you can easily compare different nodes. To see this widget in action, see our updated <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/50692573-4094-466c-b4fe-0ed3471f8993">Bare Metal Experiment artifact</a>. Similarly, we’ve added chi.lease.show_leases which lets you compare all of the leases you have made, which we hope will improve the experience of using python-chi for reservations made in advance. These widgets are currently in the pilot stage: we have more widget features planned soon, but there is a catch: we need to hear from you on how you like this new feature, whether we should keep investing in it, and if so, how we should evolve it – we look <a href="https://chameleoncloud.org/user/help/">forward to your feedback</a>.</p>

<p><b>New devices on CHI@Edge</b>. This month we added 5 cool new CHI@Edge devices with sense hats and cameras! <a href="https://chameleoncloud.org/experiment/chiedge/">CHI@Edge is our Edge computing site</a> that allows you to run containerized experiments on Raspberry Pis and Nvidia Jetsons. Previously,  the Chameleon team operated 25 Raspberry Pi 4s, and 11 Jetson Nanos. To that list, we’ve now added the following new devices, which each have interesting peripherals to play around with:</p>

<ul>
	<li>iot-jetson11 - with a <a href="https://chameleoncloud.org/blog/2022/12/19/driving-autonomous-cars-from-edge-to-cloud-with-chiedge/">Waveshare PiRacer pro board</a> and wide angle camera (OV5647)</li>
	<li>iot-rpi4-picam2 - with a sense hat and Pi camera 2.1</li>
	<li>iot-rpi4-picam3 - with a sense hat and Pi camera 3</li>
	<li>iot-rpi4-ov5647 - with wide angle camera (OV5647)</li>
	<li>iot-rpi5-nvme-01 - with a 1tb PCIe NVMe drive and Pi camera 3</li>
</ul>

<p>For now, those cameras are not pointed at anything in particular but we look forward to your ideas on this! (you know the drill: let us know via <a href="mailto:helpdesk@chameleoncloud.org">help@chameleoncloud.org</a>). Stay tuned for more hardware coming soon, as we get time to configure and enroll new devices. In addition to the hardware that we operate, users like you have contributed devices via the Bring Your Own Device capability of CHI@Edge. Along with these devices, we also have example Jupyter notebooks that showcase how to use these peripherals and cameras in <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/7d35f884-68d8-4b91-b42b-207717c9b742">this Trovi artifact</a>.</p>

<p><b>Image updates. </b>This month, we’ve published updated versions of our Chameleon support OS images at CHI@UC and CHI@TACC. These updates include patches to the preinstalled software dependencies. Additionally, we brought back the message of the day (MOTD) that shows information about your node and lease expiration on SSH login; it has all the goodness without any adverse effects that plagued it on first launch <a href="https://chameleoncloud.org/blog/2025/05/01/chameleon-changelog-for-april-2025/">in April</a>. </p>

<p>Happy experimenting!</p>