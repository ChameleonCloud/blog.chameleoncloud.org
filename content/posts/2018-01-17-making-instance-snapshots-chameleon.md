---
abstract: '<p><span id="docs-internal-guid-f2429221-05f4-3c30-e4ac-8931119f45be"><span
  style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color:
  transparent; vertical-align: baseline; white-space: pre-wrap;">Now that you have
  successfully launched a Chameleon instance, you may want to take a snapshot of it.
  Snapshots are a great way of saving your work in progress, especially if you have
  done a lot of configuration to your bare metal instance and you need to preserve
  the work beyond your lease.</span></span></p>'
authors:
- Joon Yee Chuah
categories:
- Tips and Tricks
date: '2018-01-17 21:12:13+00:00'
featured: false
hide_image: true
image: ''
related_posts: []
slug: making-instance-snapshots-chameleon
subtitle: ''
title: Making Instance Snapshots on Chameleon
---

<p><strong>Saving Your Work!</strong></p>

<p><span id="docs-internal-guid-f2429221-05f6-4942-9649-0e90a1dfd0ed"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">One of Chameleon’s features is the Glance image repository. If you’ve ever launched an instance, you have already used Glance without realizing it. Your project has access to all of Chameleon’s public </span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; font-style: italic; vertical-align: baseline; white-space: pre-wrap;">Simple Appliances</span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">, which are machine images. In addition, each project keeps its own private set of images. This is handy when you want to build your own image. In this blog post, we are going to cover how to take an image snapshot using the </span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; font-style: italic; vertical-align: baseline; white-space: pre-wrap;">cc-snapshot</span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"> utility. </span></span></p>

<p><span style="color: rgb(0, 0, 0); font-family: Arial; font-size: 14.6667px; white-space: pre-wrap;">Something to note - the image snapshot feature is appropriate for saving system images when you have done certain tasks like compiling libraries or installing software. Due to the limit of system image sizes, it is less appropriate for storing user data such as your giant neural network weight file</span><span style="color: rgb(0, 0, 0); font-family: Arial; font-size: 14.6667px; white-space: pre-wrap;">. For storing user data, you have the Swift object store functionality which we will cover in a subsequent post.</span></p>

<p> </p>

<p style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;" dir="ltr"><span id="docs-internal-guid-f2429221-05f6-4942-9649-0e90a1dfd0ed"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">Downloading cc-snapshot</span></span></p>

<p style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;" dir="ltr"> </p>

<p style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;" dir="ltr"><span id="docs-internal-guid-f2429221-05f6-4942-9649-0e90a1dfd0ed"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">First, you need to be logged in to your running instance. Next, we need to make sure that you have the latest version of the </span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; font-style: italic; vertical-align: baseline; white-space: pre-wrap;">cc-snapshot</span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"> utility. Images built from either the </span><a style="" href="https://www.chameleoncloud.org/appliances/1/"><span style="font-size: 11pt; font-family: Arial; color: rgb(17, 85, 204); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">CC-Centos7</span></a><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"> or </span><a style="" href="https://www.chameleoncloud.org/appliances/19/"><span style="font-size: 11pt; font-family: Arial; color: rgb(17, 85, 204); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">CC-Ubuntu16.04</span></a><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"> simple appliances should have this installed. You may need to update </span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; font-style: italic; vertical-align: baseline; white-space: pre-wrap;">cc-snapshot</span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"> if you get the following error while following the steps in this blog post:</span></span></p>

<p style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;" dir="ltr"> </p>

<p style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;" dir="ltr"><span style="color: rgb(33, 33, 33); font-family: monospace; font-size: 15.3333px; white-space: pre-wrap;"><code>public endpoint for image service in regionOne not found Unable to contact Glance, check username and password</code></span></p>

<p style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;" dir="ltr"> </p>

<p style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;" dir="ltr"><span id="docs-internal-guid-f2429221-05f6-4942-9649-0e90a1dfd0ed"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">To download </span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; font-style: italic; vertical-align: baseline; white-space: pre-wrap;">cc-snapshot</span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">, type in the following commands:</span></span></p>

<p style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;" dir="ltr"> </p>

<p style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;" dir="ltr"><span style="color: rgb(33, 33, 33); font-family: monospace; font-size: 15.3333px; white-space: pre-wrap;"><code>curl -O https://raw.githubusercontent.com/ChameleonCloud/cc-snapshot/master/cc-snapshot</code></span></p>

<p style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;" dir="ltr"><span style="color: rgb(33, 33, 33); font-family: monospace; font-size: 15.3333px; white-space: pre-wrap;"><code>sudo mv cc-snapshot /usr/bin/</code></span></p>

<p style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;" dir="ltr"><span style="color: rgb(33, 33, 33); font-family: monospace; font-size: 15.3333px; white-space: pre-wrap;"><code>sudo chmod +x /usr/bin/cc-snapshot</code></span></p>

<p> </p>

<p><span id="docs-internal-guid-f2429221-05f6-4942-9649-0e90a1dfd0ed"><span style="font-size: 11.5pt; font-family: Arial; color: rgb(33, 33, 33); background-color: transparent; font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">Taking a Snapshot</span></span></p>

<p><span id="docs-internal-guid-f2429221-05f6-4942-9649-0e90a1dfd0ed"><span style="font-size: 11.5pt; font-family: Arial; color: rgb(33, 33, 33); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Taking a snapshot of your instance is very easy. Just type:</span></span></p>

<p><span><span style="font-size: 11.5pt; font-family: Arial; color: rgb(33, 33, 33); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"><code>sudo cc-snapshot</code></span></span></p>

<p><span id="docs-internal-guid-f2429221-05f6-4942-9649-0e90a1dfd0ed"><span style="font-size: 11.5pt; font-family: Arial; color: rgb(33, 33, 33); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">...and enter in your username and password. By default, your instance image will be saved as the instance’s name, followed by a UUID. If you would like to name your image something specific, you can type:</span></span></p>

<p><span style="font-size: 11.5pt; font-family: Arial; color: rgb(33, 33, 33); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"><code>sudo cc-snapshot <em>my_image_name</em></code></span></p>

<p style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;" dir="ltr"><span id="docs-internal-guid-f2429221-05f6-4942-9649-0e90a1dfd0ed"><span style="font-size: 11.5pt; font-family: Arial; color: rgb(33, 33, 33); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">If you use an image name that has already been used, cc-snapshot will simply store this as a new image with the same name and a UUID. As a result, your old image will not be lost.</span></span></p>

<p> </p>

<p style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;" dir="ltr"><span id="docs-internal-guid-f2429221-05f6-4942-9649-0e90a1dfd0ed"><span style="font-size: 11.5pt; font-family: Arial; color: rgb(33, 33, 33); background-color: transparent; font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">Viewing Your Images</span></span></p>

<p><span id="docs-internal-guid-f2429221-05f6-4942-9649-0e90a1dfd0ed"><span style="font-size: 11.5pt; font-family: Arial; color: rgb(33, 33, 33); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Now that we’ve taken a snapshot, let’s look at the images in your project. Log in to the CHI portal where you launched your instance. In the left navigation panel, click </span><span style="font-size: 11.5pt; font-family: Arial; color: rgb(33, 33, 33); background-color: transparent; font-style: italic; vertical-align: baseline; white-space: pre-wrap;">Project &gt; Compute &gt; Images</span><span style="font-size: 11.5pt; font-family: Arial; color: rgb(33, 33, 33); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"> to see all images that are available to your project.</span></span></p>

<p> </p>

<p><img width="800px" src="https://www.chameleoncloud.org/media/filer_public/32/80/3280106c-f4f3-435f-8583-ea5a57e07fbe/snapshot-all_images.png"></p>

<p> </p>

<p><span id="docs-internal-guid-f2429221-0601-9c77-fbfd-6ebf8f8fba28"><span style="font-size: 11.5pt; font-family: Arial; color: rgb(33, 33, 33); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">This list includes all public images. You can filter for images by name or by visibility. By default, the new image that you have created will be private. Click on the text input bar that says “Click here for filters”. Select </span><span style="font-size: 11.5pt; font-family: Arial; color: rgb(33, 33, 33); background-color: transparent; font-style: italic; vertical-align: baseline; white-space: pre-wrap;">Visibility</span><span style="font-size: 11.5pt; font-family: Arial; color: rgb(33, 33, 33); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"> and then </span><span style="font-size: 11.5pt; font-family: Arial; color: rgb(33, 33, 33); background-color: transparent; font-style: italic; vertical-align: baseline; white-space: pre-wrap;">Shared with Project.</span></span></p>

<p> </p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/a2/19/a2194629-2b5f-41a7-9526-9fba52b986ca/snapshot-visibility.png"> <img src="https://www.chameleoncloud.org/media/filer_public/13/37/1337a21f-2099-4f19-98bb-882a87d390d0/snapshot-visibility_shared.png"></p>

<p> </p>

<p><span id="docs-internal-guid-f2429221-0603-590d-29f3-b9dc1917ff33"><span style="font-size: 11.5pt; font-family: Arial; color: rgb(33, 33, 33); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">The image list will repopulate with only images that are shared with other users in your project, including the one you just made.</span></span></p>

<p> </p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/85/ab/85ab2b00-50c8-4446-9116-0274fa19ed68/snapshot-shared_images.png"></p>

<p> </p>

<p><span id="docs-internal-guid-f2429221-0604-2198-d299-13a978446da8"><span style="font-size: 11.5pt; font-family: Arial; color: rgb(33, 33, 33); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">At this point, you can re-launch the image from this snapshot or edit details such as the image name. Check back in two weeks to see how you can work with images on Chameleon Cloud from your local computer using the Glance client!</span></span></p>
