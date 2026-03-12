---
abstract: "<p>This changelog is packed! The Chameleon User Meeting Call for Presentations\
  \ is out, and we have new storage FAST\u201923 experiment artifacts. We finally\
  \ have an Ubuntu 22 appliance, and many upgrades to the images in general, more\
  \ GUI improvements, a faster portal, and CHI-in-a-box is easier to get started with.</p>"
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2023-03-01 22:41:57+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/17/e2/17e29bf9-4b67-4f72-bfaf-185322ea1415/juan-carlos-fernandez-rodriguez-lidrieeo4d0-unsplash.jpg
related_posts: []
slug: chameleon-changelog-for-february-2023
subtitle: ''
title: Chameleon Changelog for February 2023
---

<p> </p>

<p style="text-align: center;"><b id="docs-internal-guid-c54f510d-7fff-47b6-790a-c66f3b5e2622"><img height="416" src="https://lh3.googleusercontent.com/Bp1GdoECv4SQcGs7YZA6HOBcWV4upDt9rRRa-ZgBUHJQ9Ma8irAAjqQKTaHZOczvGcP-lQ5GNE2L7weGyi0AMTxxUAl5Wz2yNd-pNFPWFVLSbJU0RqNOWekaaetTp_gPuGgR61Cmpo0-VRZMFReM05k" width="624"></b></p>

<p>Dear Chameleon Users,</p>

<p>We just got back from the USENIX <a href="https://www.usenix.org/conference/fast23">FAST'23</a> conference, where we had a great time meeting current and future Chameleon users. While there, <a href="https://chameleoncloud.org/blog/2023/02/20/chameleon-at-fast/">we held two BOF discussions</a> on packaging reproducible experiments. If you are interested in learning more, you can <a href="https://chameleoncloud.org/experiment/share/?filter=tag%3Astorage">browse the Trovi experiments</a> tagged with “storage”, which are excellent examples of Chameleon <a href="https://www.chameleoncloud.org/blog/2022/09/26/experiment-patterns-making-complex-experiments-easy/">experiment patterns</a>, making it easier to get started writing your own artifacts.</p>

<p><strong>Chameleon User Meeting Call for Presentations.</strong> You might’ve seen our announcement earlier that the Call for Presentations for the upcoming Chameleon User Meeting is out! The deadline to submit is April 3. Registration for the user meeting is also open, with early registration ending April 1. For more information, see the <a href="https://chameleoncloud.org/chameleon-cloud-users-meeting/user-meeting-2023/">Call for Presentations tab</a> on the web page.</p>

<p><strong>New and Improved Appliances! </strong>To run experiments on Chameleon, you’ll need some base OS image to boot on a node, known as “appliances” on the testbed. You can browse the list of supported appliances in our <a href="https://chameleoncloud.org/appliances/">catalog</a>. We are excited to bring you a new Ubuntu 22.04 appliance (and one with Cuda). Our appliances for both Ubuntu and CentOS now use chrony instead of ntp by default, which should make time synchronization more reliable. CUDA should now load with fewer issues on Ubuntu 20 and 22. Also on Ubuntu, we fixed a missing dependency issue with <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images.html#the-cc-snapshot-utility">cc-snapshot</a>, and a bug where the Nvidia driver would fail to load on our A100 nodes. We’d like to mention that while the Ubuntu 18 images will remain available for reproducibility purposes, they will no longer be updated or officially supported. If you need to use Ubuntu 18 or other out of date image, consider running them behind a <a href="https://chameleoncloud.org/blog/2023/01/23/experiment-pattern-bastion-host/">bastion host</a> on a private network. Additionally, due to software compatibility issues, the utility cc-checks will no longer be installed on new images going forward, and now is only available on CentOS7 images. As always, please let us know if you have any questions via the help desk.</p>

<p><strong>GUI Usability Improvements.</strong> For most users, Horizon, the web dashboard for Chameleon sites, is the first interface used. However, we’ve gotten feedback that it is overwhelming, especially to new users, who may not know which parts of creating an instance are required. Last month, we <a href="https://chameleoncloud.org/blog/2023/02/02/2023-january-changelog/">announced</a> some improvements to the interface, where we streamlined the interface for baremetal usage, and made it so you can sort by Chameleon supported images when launching instances. This month, we released a few more changes. Now the “Launch Instance” has an advanced section for configuration options that are unused by the vast majority of users. You can get these options back with the “Show Advanced'' button at the bottom. Additionally, there is a “Created By” column when viewing instances and leases to help differentiate who created each resource.</p>

<p style="text-align: center;"><b id="docs-internal-guid-4189539a-7fff-0247-7e5f-9b8d0d86898b"><img height="359" src="https://lh6.googleusercontent.com/Pe_UjkbvF6KalUuGFiTCgTdMBJo0Qd_GSY7YYSQ5XCGDxcqy_4ymAjioNu6jdn047xXhe5Ja5SP9KHIGYLTrGpZSMscQFCsU9dP-xltCnyTX7My-8jpoLYaIqsvtok9mZLRVi6VOP8VFq5QbrKFDMeQ" width="624"></b></p>

<p><br>
<strong>Portal Improvements.</strong> As you might have seen in the outage, we’ve migrated our main portal to a faster server and did other general maintenance to improve its performance. We hope this will give you better load times when managing projects and allocations – but as always, do not hesitate to let us know if you experience any problems. </p>

<p><strong>Chi-in-a-Box updates.</strong> <a href="https://chameleoncloud.gitbook.io/chi-in-a-box/">CHI-in-a-box</a>, the packaging of CHameleon Infrastructure, is what allows volunteer operators to run Chameleon associate sites, the latest being <a href="https://chameleon.cs.iit.edu/project/">CHI@IIT</a>, where 80 of Chameleon’s legacy Haswell nodes can still be used. We’ve made it easier to understand and get started with a “Before you begin” section in the documentation, <a href="https://chameleoncloud.gitbook.io/chi-in-a-box/before-you-begin/upstream-docs">covering necessary background knowledge</a> and a <a href="https://chameleoncloud.gitbook.io/chi-in-a-box/before-you-begin/openstack-architecture">detailed overview of the networking requirements and potential configurations</a>. If you are interested in getting involved setting up a Chameleon site, please <a href="https://chameleoncloud.org/user/help/ticket/new/">reach out</a> and we’d be happy to help! Additionally, site operators will have some improved tooling to sync the updated images to their associate sites. The existing tooling required some manual action, especially in the case where multiple images had the same “name”, while the new distribution mechanism will handle this automatically. In addition, we’re working to ensure the UUIDs for supported images are consistent across all sites.</p>

<p>Until next month!<br>
 </p>