---
abstract: "<p style=\"line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;\" dir=\"\
  ltr\"><span id=\"docs-internal-guid-5e339c20-1d07-e22d-f1e2-dad07d601e9d\"><span\
  \ style=\"font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color:\
  \ transparent; font-weight: 700; vertical-align: baseline; white-space: pre-wrap;\"\
  >Great news in Chameleon-land!</span></span></p>\n\n<p style=\"line-height: 1.38;\
  \ margin-top: 0pt; margin-bottom: 0pt;\" dir=\"ltr\">\_</p>\n\n<p style=\"line-height:\
  \ 1.38; margin-top: 0pt; margin-bottom: 0pt;\" dir=\"ltr\"><span id=\"docs-internal-guid-5e339c20-1d07-e22d-f1e2-dad07d601e9d\"\
  ><span style=\"font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color:\
  \ transparent; vertical-align: baseline; white-space: pre-wrap;\">Here are the most\
  \ important features we added since the public release of our new hardware in mid-March:</span></span></p>"
authors:
- Kate Keahey
categories:
- Chameleon Changelog
date: '2018-05-01 18:47:02+00:00'
featured: false
hide_image: true
image: ''
related_posts: []
slug: chameleon-changelog-april-2018
subtitle: ''
title: Chameleon Changelog for April 2018
---

<p style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;" dir="ltr"><span id="docs-internal-guid-5e339c20-1d07-e22d-f1e2-dad07d601e9d"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">Great news in Chameleon-land!</span></span></p>

<p style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;" dir="ltr"> </p>

<p style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;" dir="ltr"><span id="docs-internal-guid-5e339c20-1d07-e22d-f1e2-dad07d601e9d"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Here are the most important features we added since the public release of our new hardware in mid-March:</span></span></p>

<p style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;" dir="ltr"> </p>

<p style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;" dir="ltr"><span id="docs-internal-guid-5e339c20-1d07-e22d-f1e2-dad07d601e9d"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">Pre-defined network connection for high-bandwidth (up to 100 Gbps) wide-area networking experiments </span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">between Chameleon’s Chicago and TACC sites (beta level). We deployed a new shared network (“sharedwan1”) enabling high-bandwidth network traffic to flow between the sites over an isolated layer 2 network. By default, sharedwan1 is limited to 40 Gbps, however, we can lift the limitation and provide assistance for experiments that can show need for higher bandwidth. If you are interested in being a beta user of this new high-bandwidth WAN connection, please send email to Paul Ruth (pruth@renci.org) with the subject line “100G beta testers”.</span></span></p>

<p> </p>

<p style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;" dir="ltr"><span id="docs-internal-guid-5e339c20-1d07-e22d-f1e2-dad07d601e9d"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">Documentation overhaul. </span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Our documentation grew organically from contributions by many individuals as the system developed -- and as you probably noticed it suffered from inconsistencies in content, terminology, and structure. </span><a style="text-decoration: none;" href="https://www.chameleoncloud.org/blog/2018/03/29/major-documentation-update/"><span style="">We refactored it to make it easier to find things</span></a><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"> and put it in a documentation management system to ensure that it will be easier to maintain in the future. The new documentation is linked off of the home page and all the main links have been updated -- however, for the next couple of months you can also access the old documentation (there is a link on top of the new docs) and all your “tried and true” bookmarks should work for that time. </span></span></p>

<p> </p>

<p style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;" dir="ltr"><span id="docs-internal-guid-5e339c20-1d07-e22d-f1e2-dad07d601e9d"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; font-weight: 700; vertical-align: baseline; white-space: pre-wrap;">Appliances.</span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; font-weight: 700; font-style: italic; vertical-align: baseline; white-space: pre-wrap;"> </span><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">We made several improvements to appliances — in particular, every Chameleon appliance has now a FUSE module that you can use to access our object store. We also updated the snapshot program on the appliances to allow you to exclude some directories, and warn you when creating large snapshots which could take a long time to deploy. If you are using an older appliance, you can follow </span><a style="text-decoration: none;" href="https://chameleoncloud.readthedocs.io/en/latest/technical/images.html#updating-snapshot"><span style="">our instructions to update cc-snapshot</span></a><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">.</span></span></p>

<p> </p>

<p style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;" dir="ltr"><span id="docs-internal-guid-5e339c20-1d07-e22d-f1e2-dad07d601e9d"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">There are some things that have not been resolved yet: in particular, we are aware that many of you experienced problems when launching many instances at a time on our bare-metal clouds. This problem is caused by reengineering of the Nova service in OpenStack Ocata; we have identified a fix, tested a solution, and will be deploying it next week at University of Chicago and the following week at TACC. In the meantime, for those of you who need to launch many instances, a quick fix is to batch them into multiple smaller groups -- we are very sorry for any trouble this may have caused to your experimentation. </span></span></p>

<p> </p>

<p style="line-height: 1.38; margin-top: 0pt; margin-bottom: 0pt;" dir="ltr"><span id="docs-internal-guid-5e339c20-1d07-e22d-f1e2-dad07d601e9d"><span style="font-size: 11pt; font-family: Arial; color: rgb(0, 0, 0); background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">What do you think of the new changes? If you have any comments or suggestions, please leave us a comment! </span></span></p>

<div> </div>
