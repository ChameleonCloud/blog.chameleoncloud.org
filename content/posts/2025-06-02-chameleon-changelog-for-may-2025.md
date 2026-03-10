---
abstract: "<p>This month, we have new H100 GPU nodes on KVM@TACC! Today, you can launch\
  \ VM instances with 1 full H100 GPU. This hardware comes with a brand new workflow\
  \ for reserving VMs. It\u2019s important to note that this reservation workflow\
  \ will be rolled out to the rest of KVM later in the summer. Additionally, we have\
  \ refreshed our documentation. Lastly, CHI-in-a-box comes with a new image deploy\
  \ tool for associate sites.<br>\n\_</p>"
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2025-06-02 21:31:51+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/ac/ff/acffdfec-55d3-4036-aded-85a2332fd811/54511643985_3e38c03a32_w.jpg
slug: chameleon-changelog-for-may-2025
subtitle: ''
title: Chameleon Changelog for May 2025
---

<p style="text-align: center;"><img media="" src="https://chameleoncloud.org/media/filer_public/ac/ff/acffdfec-55d3-4036-aded-85a2332fd811/54511643985_3e38c03a32_w.jpg"></p>

<p style="text-align: center;"><a href="https://www.flickr.com/photos/berniedup/54511643985/in/photolist-2r41qAM-2qzKyRT-2r3ozWA-2r33xhd-2r2ja8b-2r27cwB-2r1qEyP-2r1vxHW-2r1bB5c-2r1hnpa-2r1hnpk-2qZs2ak-2qZrxNe-2qZs28w-2qZrcVp-2qYpZG9-2qYjqTi-2qXGRh5-2qWKktG-2qWKYtW-2qWJ4sy-2qWDEYQ-2qWKkog-2qWrJk8-2qVGvqf-2qVj6oo-2qTAyZQ-2qTsitA-2qTqfKA-2qTfmcj-2qS838v-2qRCvKv-2qRfHND-2qQQD9X-2qQJfif-2qPGwm6-2qPGqLp-2qPGqqj-2qPBR6v-2qPm35c-2qMLPjH-2qKDMps-2qKDMok-2qKyD7q-2qKuPmb-2qKpZgM-2qJfS3s-2qCRKVv-2qCK4FS-2qCPDNF">Bernard DUPONT via Flickr</a></p>

<p>Dear Chameleon users,</p>

<p>It’s a big month on the testbed, so best jump right into the new features.</p>

<p><b>New hardware – GPUs on KVM@TACC! </b>We are thrilled to announce preview availability of new hardware: two new nodes, each a Dell PowerEdge XE9640 equipped with Intel Xeon Platinum processor with 4 NVIDIA HGX H100 GPUs, 1 TB DDR5-4800 RAM, 2x 447.13 GB PCIe NVMe and 1x 3.84 TB PCIe NVMe. The nodes are connected with 1x 25 GbE Ethernet – and four more are  coming soon! We haven’t updated our hardware browser in our hurry to give you access to those new nodes so the information above is all you get for now – but of course let us know anytime if you need more detail! </p>

<p>The big innovation is that those nodes are available via KVM, significantly extended to support advance reservations and fractional GPU leases. The KVM@TACC you know and love runs on older Haswell series compute nodes, and its flavors let you launch basic compute VMs. Now, if you use a special new flavor, you’ll be able to launch a VM with a H100 GPU slice. At the moment, each slice is 1/4th of the node (meaning 1 full H100 GPU per instance), but soon we will make available instances tied to a fraction of the GPU which means that we will be able to map many instances to one node. This division will make our GPUs more accessible than with bare metal, where the entire node can only be used by one lease at a time.</p>

<p>To ensure that these GPUs can be efficiently shared between users, before you get access to this special GPU flavor you’ll have to create an advance reservation, similar to the workflow for using our bare metal nodes. However, unlike in the bare metal reservations, you’ll reserve a flavor instead of a specific node. Once your lease is active, you can start launching an instance as normal but when selecting the flavor, you’ll see a new option based on the reservation. There is also an <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_gui.html#checking-gpu-availability">availability calendar</a> which lets you see availability of these new nodes over time. For more information about this process, see our <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/index.html">KVM documentation</a>. For now, the use of reservations is only possible on this new GPU hardware; the, existing workflows on KVM@TACC still work as they always have (but read below). Since the GPU nodes and flavor reservations on KVM@TACC are very new (and as we explained, we still did not enter them into the resource discovery service), this release should be considered a preview – please, let us know if you have any questions or problems via the <a href="https://chameleoncloud.org/user/help/">Help Desk</a>. Enjoy! </p>

<p><b>Upcoming KVM@TACC reservations. </b>As per above, for now the older parts of KVM@TACC still work as before, meaning you can launch compute instances using the old flavors. This is going to change later this summer, when we will enable advance reservations for all KVM instances. We announced these plans <a href="https://chameleoncloud.org/blog/2025/02/04/chameleon-changelog-for-january-2025/">back in February</a>, but postponed the work to so as not to introduce disruptive changes during the Spring semester. We are making this change for a few reasons. Firstly, we want to ensure consistent workflows between Chameleon sites. KVM@TACC was the only site that didn’t require reservations, while baremetal sites and CHI@Edge did. In addition, “forgotten” KVM instances pose security risks if they are left running without security patches. You still will be able to have long running instances under these changes, but they will be tied to a lease, ensuring that you must renew it periodically and stay an active user. We’ll have more details in next month’s changelog about what exactly these changes will mean to you, but we are expecting that it may require you to relaunch your instances. Stay tuned for more information.</p>

<p><b>Better docs!</b> Last year, we revamped our <a href="https://chameleoncloud.org/blog/2024/08/02/chameleon-changelog-for-july-2024/">Getting Started </a>documentation, and this month we’ve refreshed <a href="https://chameleoncloud.readthedocs.io/en/latest/contents.html">the rest of the documentation</a> too! Most of the content is the same, but we’ve cleaned up references to old and outdated systems, rearranged sections for clarity, and fixed typos and other issues. Additionally, we’ve added feedback buttons, allowing you to rate the documentation pages. This information will help us guide future documentation work, ensuring we give attention to pages that are confusing users. We’ve also added a button to the bottom of each page which creates a GitHub issue, letting you comment on any specific problem that comes up. If you have any feedback or issues with Chameleon, you are welcome as always to contact us via our <a href="https://chameleoncloud.org/user/help/">Help Desk</a> or the <a href="https://forum.chameleoncloud.org/">Chameleon Forum</a>.</p>

<p><b>CHI-in-a-box updates for image deployment</b>. <a href="https://github.com/ChameleonCloud/chi-in-a-box">CHI-in-a-box</a> is the software that packages the Chameleon infrastructure, which in turn makes Chameleon’s associate sites like CHI@EVL and CHI@NU possible. Last month, we <a href="https://chameleoncloud.org/blog/2025/05/01/chameleon-changelog-for-april-2025/">released brand new OS images</a>, for ARM and AMD ROCm, but since Chameleon sites are federated, we can’t simply “push” these new images to all sites. To solve this problem, we’ve released an <a href="https://github.com/ChameleonCloud/chi-in-a-box/blob/stable/2023.1/docs/operations/chameleon-tools/image-tools.md">image-deployer tool</a> as a part of CHI-in-a-box that associate site operators can run to fetch updated images from our flagship sites, which can manually pull in image updates, or automatically manage image versions in the background. For more information, site operators can see <a href="https://github.com/ChameleonCloud/chi-in-a-box/blob/stable/2023.1/docs/operations/chameleon-tools/image-tools.md">the CHI-in-a-box documentation</a> for how to configure and run this tool.</p>

<p>Happy experimenting!</p>