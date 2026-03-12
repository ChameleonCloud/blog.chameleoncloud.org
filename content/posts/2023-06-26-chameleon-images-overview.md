---
abstract: "<p>This month's Tips &amp; Tricks\_blog is an overview of one of the most\
  \ critical components to experimentation on Chameleon: images! We explore everything\
  \ that makes a Chameleon image unique, and how you can build your own images!</p>"
authors:
- Adam Cooper
categories:
- Tips and Tricks
date: '2023-06-26 23:00:00+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/cf/d8/cfd8109c-8d5f-49b6-8f6e-598812560edb/cc-images.png
related_posts: []
slug: chameleon-images-overview
subtitle: ''
title: Chameleon Images Overview
---

<p><img src="https://chameleoncloud.org/media/filer_public/cf/d8/cfd8109c-8d5f-49b6-8f6e-598812560edb/cc-images.png" style="height: 375px; width: 538px;"></p>

<p>Besides our bare metal resources and networking infrastructure, one of the most defining features of experimentation on Chameleon are the images we provide: we maintain overall 12 images, located in our <a href="https://chameleoncloud.org/appliances/">Appliance Catalog</a> and directly in the GUI, so that you can get to the task at hand quickly. </p>

<p>Let’s start with base GNU/Linux distributions – Chameleon supports two: <strong>Ubuntu</strong> and <strong>CentOS</strong>.</p>

<h3>Ubuntu</h3>

<p><a href="https://chameleoncloud.org/appliances/108/">Ubuntu</a> is the most popular Linux distribution out there, so naturally we support it not only because it provides great familiarity to many of our users, but because all software maintainers support Ubuntu! This means that whatever you’re using is likely to work out of the box on Ubuntu, and is also likely to have a package which can be easily installed on Ubuntu. This is a benefit to users because there will be fewer software issues while trying to set up experiments, and to the Chameleon team because the software on our images remains well-supported over time. We recommend users start with the latest officially-supported Ubuntu images for these reasons.</p>

<h3>CentOS</h3>

<p><a href="https://chameleoncloud.org/appliances/112/">CentOS</a> is a liberally-licensed open distribution based on Red Hat Enterprise Linux, or RHEL. In that way, it is similar to the popular Fedora distribution, which is a testing distribution for RHEL, except CentOS is extremely stable. This is because the packages tested on Fedora are published downstream to RHEL and CentOS. For this reason, RHEL and CentOS often have the same versions of packages available, so things that work on RHEL typically work on CentOS. CentOS is very popular for scientific computing because of its stability, which enables experiments to be easier to reproduce over time. Unfortunately, Red Hat has officially deprecated CentOS, so there will be no further releases after CentOS 9. Chameleon currently supports CentOS 7, CentOS 8, and CentOS 9, but CentOS 8 is currently <a href="https://endoflife.software/operating-systems/linux/centos">end-of-life</a>, and CentOS 7 will become end-of-life next year after ten years of support. Because of this, we have begun supporting CentOS-Stream images, which are far less stable than the base images. We are looking at other RHEL-based operating systems to be an alternative to CentOS going forward.</p>

<h2>What makes Chameleon images unique?</h2>

<p>Chameleon images are based on popular Linux distributions, and use <a href="https://www.qemu.org/docs/master/system/images.html">standard QEMU image formats</a>. So, what ultimately makes them Chameleon images is the customization built into the images which allow them to function on our unique infrastructure – an image does not necessarily have to have this customization but having it will make your work a lot easier. Images are configured to set users up with a functioning environment no matter what hardware they are using (by the way, if you find this not to be the case, please <a href="https://chameleoncloud.org/user/help/">open a ticket</a> so we can fix it!).</p>

<h3>What's in a Chameleon image?</h3>

<p>Chameleon images come pre-configured with various software and configuration files that make experimentation and interaction with Chameleon infrastructure easy. To ensure that you’re always able to connect to your instance remotely, we also install an SSH configuration that is more secure than the default one shipped by OpenSSH, and we allow incoming SSH connections through the firewall. Like any other cloud, Chameleon installs all of your <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/gui.html?highlight=keypair#key-pairs">SSH keys</a> on every instance you launch, so you’ll be able to log into your instance from your laptop, your desktop, or wherever else you want to. We also configure the default cc (chameleon cloud) account such that it has easy root access, so that you can install packages or modify the system to your heart’s content. </p>

<p>In your home directory, you’ll find an <code>openrc</code> file which you can use to authenticate with the pre-installed Chameleon <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/cli.html">CLI</a>. You’ll also find your project’s object store mounted conveniently in a directory called my_mounting_point. This means you can remotely store and access files just like they were on the drive. </p>

<h4>Software</h4>

<p>Chameleon images come with a small collection of both mainstream and custom software packages. The mainstream software suite represents a basic, minimal collection of software of which we have observed very frequent use in modern computer science experiments on Chameleon. At the time of writing, this includes ansible, autoconf, curl, emacs, gcc, g++, gdb, git, jq, make, nfs, openssl, OpenStack CLI, python3, rcs, subversion, unzip, vim, and virtualenv.</p>

<p>We also provide some custom software which helps with managing your experiments on Chameleon. Specifically, <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/swift.html#mounting-object-store-as-a-file-system">cc-cloudfuse</a> allows you to mount the Chameleon object store as a directory on your instance’s filesystem. By default, instances will boot with the object store root mounted under my_mounting_point in the home directory using cc-cloudfuse.</p>

<p>Alongside cc-cloudfuse, we include the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images.html#the-cc-snapshot-utility">cc-snapshot</a> utility to save the state of your work. Running this tool creates a snapshot of the instance and uploads a new image which you can boot in the future to pick up where you left off. This is the best way to ensure you don’t have to reinstall all your software and configuration every time you boot a new instance. However, we don’t recommend using it to store large volumes of data used for experimentation, as bloated images are challenging to boot. For that, we always recommend backing the data up to the object store!</p>

<h2>Image Variants</h2>

<p>From our two base operating systems, we publish special image “variants” for multiple releases of those operating systems. </p>

<h3>Architectures</h3>

<p>Currently, Chameleon supports two different architectures: x86-64 and ARM64. The only images supported for ARM64 are CC-Ubuntu20.04-ARM64 and CC-Ubuntu22.04-ARM64. These images are exactly the same as their X86 equivalents, except they have ARM-compatible binaries installed. All other images are built exclusively for X86-64.</p>

<h3>CUDA</h3>

<p>For researchers looking to take advantage of our powerful GPU nodes, we recommend using our CUDA images. They come pre-installed with official Nvidia drivers, Nvidia CLI utilities, and the base CUDA development toolkit. These images will be the easiest to get up and running with popular libraries like Tensorflow and OpenCV. We currently support CUDA on both Ubuntu and CentOS, although the Ubuntu CUDA images are better maintained.</p>

<h3>FPGA</h3>

<p>For those experimenting with FPGAs, we provide official FPGA images based on CentOS7 with all the tools you’ll need to interface with these neat programmable chips. Compiling FPGA designs on Chameleon has a bit of a tricky workflow, which we’ve documented <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/fpga.html">here</a>.</p>

<h2>Extending our images</h2>

<p>If you want to create a new image for your project, you can do so by booting an official image, installing packages and making configuration changes, and then creating a snapshot using <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images.html#the-cc-snapshot-utility">cc-snapshot</a>. This image will be available for everyone in your project to use, and can be ported across different sites by <a href="https://chameleoncloud.org/blog/2023/05/01/how-to-port-your-experiments-between-chameleon-sites/">following our guide</a>. If you’d like to publish the image to all Chameleon users, you can do so via our <a href="https://chameleoncloud.org/appliances/">Appliance Catalog</a>, where you’ll find officially-supported images, community-contributed images, and hardware configurations. If you want to make your own Chameleon image from scratch, you should do so with the <a href="https://github.com/ChameleonCloud/CC-Images">cc-images</a> tool. This will allow you to include all of our configuration and software that we talked about above in your own image.</p>

<h2>Open for suggestions</h2>

<p>If you would like to see us support additional operating systems or software configurations on Chameleon, feel free to reach out to us via <a href="https://chameleoncloud.org/user/help/">the help desk</a> or @ChameleonCloud on social media!</p>