---
abstract: <p>What's the secret ingredient that makes our new Chameleon images so much
  better? From automatic SSH configuration to built-in rclone support, these aren't
  your ordinary cloud images. Find out what makes them special.</p>
authors:
- Paul Marshall
categories:
- Tips and Tricks
date: '2025-05-19 16:02:19+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/00/51/0051406d-b53e-4289-b43b-03b908cc9fe4/chameleon-images-headline.png
related_posts:
- slug: chameleon-images-overview
  title: Chameleon Images Overview
slug: leveraging-new-and-improved-chameleon-images
subtitle: 'Less Setup, More Science: Streamlined Images with Built-in Tools and Drivers'
title: Leveraging New and Improved Chameleon Images
---

<p>We're happy to announce refreshed, improved, enhanced, and streamlined--pick your favorite adjective--images to support your experiments on Chameleon! The images can be found in the usual places: directly in the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images.html#managing-images-using-the-gui">Chameleon dashboard GUI</a> under Compute -&gt; Images, or listed in the <a href="https://chameleoncloud.org/appliances/">Appliance Catalog</a>. The Chameleon team supports 8 images (along with 2 OpenStack Heat templates), all of which are available in the Appliance Catalog.</p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/00/51/0051406d-b53e-4289-b43b-03b908cc9fe4/chameleon-images-headline.png"></p>

<h2>The Building Blocks</h2>

<p>Our images are based on two of the most popular Linux distributions, Ubuntu and CentOS. We include a number of drivers, tools, and helpful resources in our images to smooth the process of standing up experiments on Chameleon. We'll first discuss the operating systems we support and then we can dive into the recent enhancements we've made.</p>

<h3>Ubuntu</h3>

<p><a href="https://ubuntu.com/">Ubuntu</a> is not only the most popular distribution, but also one of the most widely supported. A majority of our images are based on Ubuntu Long Term Support (LTS) releases, which are released in April every two years. The LTS releases include 5 years of support and security updates and put an extra emphasis on stability. Long term support, reliability, and a rich ecosystem of packages make an ideal foundation for experiments on Chameleon. This makes Ubuntu LTS releases a great choice for most of our users.</p>

<p>We offer seven distinct Ubuntu images, each pre-configured for different architectures and GPU workloads:</p>

<ul>
	<li>CC-Ubuntu22.04</li>
	<li>CC-Ubuntu22.04-CUDA</li>
	<li>CC-Ubuntu22.04-ARM</li>
	<li>CC-Ubuntu24.04</li>
	<li>CC-Ubuntu24.04-CUDA</li>
	<li>CC-Ubuntu24.04-ROCm</li>
	<li>CC-Ubuntu24.04-ARM</li>
</ul>

<p>For x86 servers (without GPUs), choose either CC-Ubuntu<strong>22</strong>.04 or CC-Ubuntu<strong>24</strong>.04 depending on your needs. Though we still support Ubuntu 22, keep in mind it will be end-of-life 2 years earlier than Ubuntu 24. If you are just starting out, and don't need Ubuntu 22 for a specific reason, then we recommend going with Ubuntu 24.</p>

<p>If you're running on an NVIDIA GPU instance, grab one of the CUDA images to skip manual tool and driver installs.</p>

<p>For ARM instances, pick an ARM build, which shares the same setup as its x86 cousin.</p>

<p>Last but not least, for AMD GPU instances, use the ROCm image. Our ROCm image only includes the tooling for AMD GPUs, so you'll need to install the specific drivers you need.</p>

<p>We've recently deprecated Ubuntu 20.04 which is <a href="https://ubuntu.com/blog/ubuntu-20-04-lts-end-of-life-standard-support-is-coming-to-an-end-heres-how-to-prepare">end of life May 31, 2025</a>. It will no longer receive important software and security updates. <em>If you are selecting a new image, please don't select Ubuntu 20, and if you are still on Ubuntu 20 we encourage you to move to a newer version</em>. If for some reason you need to use an unsupported OS on Chameleon, please consider deploying a supported, and up-to-date, <a href="https://chameleoncloud.org/blog/2023/01/23/experiment-pattern-bastion-host/">bastion host</a> to connect through so your instance that is running an outdated and insecure OS is not directly exposed to the Internet.</p>

<h3>CentOS</h3>

<p>If you need a Red Hat–compatible alternative for a specific reason, check out CC-CentOS9-Stream. This rolling-release image brings you the latest CentOS Stream 9 packages and upstream updates, all with cloud-init enabled and standard CentOS repositories configured. It's ideal for development, testing, or production workloads on x86 when you need a CentOS environment that stays close to upstream RHEL.</p>

<h2>The Secret Ingredients</h2>

<p>These images may look like ordinary images, but under the hood, they come packaged with a few clever ingredients to make your life a little easier.</p>

<p>To start, a Chameleon user account, named cc, and your SSH key are configured at boot, so you can dive in without worrying about how to access your environment. You'll also find an openrc file pre-generated in the home directory of the cc user. The credentials stored in this file allow you to access the Chameleon OpenStack API for 24 hours. After that, you'll need to regenerate the file with the command <code>cc-generate-openrc</code> to get a fresh set of credentials. And then don't forget to source the openrc file again to pick up the new credentials!</p>

<p>When you log in, you'll be greeted with a friendly message of the day that offers pointers to docs, storage tips, and where to get help. Need to save your work? <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images.html#the-cc-snapshot-utility">cc-snapshot</a> makes it easy to capture your instance and turn it into a reusable image. For data storage off your instance, <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/swift.html#mounting-object-store-as-a-file-system">rclone</a> is ready to go in the image so you can mount object storage buckets directly into your environment. And thanks to cloud-init, your instance is automatically configured at boot—setting hostnames, attaching volumes, running user scripts, providing credentials, and more.</p>

<p>Finally, all the essential drivers are bundled into the image, so networking, GPUs, and other hardware work out of the box.</p>

<h2>Bring Your Own Images</h2>

<p>If you are not able to use a Chameleon-supported image, you can create your own. To do this we recommend using our <a href="https://github.com/ChameleonCloud/CC-Images">CC-Images tool</a> (it's what we use), based on <a href="https://docs.openstack.org/diskimage-builder/latest/index.html">OpenStack Diskimage-builder</a>.</p>

<p>The <a href="https://github.com/ChameleonCloud/CC-Images/blob/main/README.md">readme</a> of the CC-Images repo is up-to-date with instructions on how to use the tool. You can extend an image by changing or adding elements for your image.</p>

<p>If you don't use one of our images, or use CC-Images to build your image, you'll be missing out on many of the items highlighted in the previous section unless you add them manually. You'll want to pay special attention to the drivers you are including (e.g. network drivers) to make sure they work on hosts you plan to support. You'll also want to bundle cloud-init for proper setup and configuration at boot time on Chameleon. Finally, if you manually include cc-snapshot, we cannot guarantee it will work on images other than our own, so make sure to test it thoroughly if you choose to use it.</p>

<h2>Feedback</h2>

<p>There you have it — a quick tour through our new and improved Chameleon-supported images. We'd love to hear what you think about these images and what you'd like to see next. Please reach out to us on the <a href="https://forum.chameleoncloud.org">Chameleon Forum</a> and send us your thoughts.</p>