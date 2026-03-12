---
abstract: <p>This month, we bring to you the much awaited filesystem preview, and
  a massive Openstack upgrade. We also have a new CHI-in-a-Box version to go along
  with the upgrade, and some reservation usability improvements.</p>
authors:
- Zhuo Zhen
categories:
- Chameleon Changelog
date: '2022-07-01 14:17:51+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/a3/14/a314189a-1c07-43ae-b473-a93e21e8f0a4/july_chameleon.png
related_posts: []
slug: chameleon-changelog-for-june-2022
subtitle: ''
title: Chameleon Changelog for June 2022
---

<p style="text-align: center;"><br>
<img src="https://www.chameleoncloud.org/media/filer_public/48/d8/48d8d2e6-6547-4dd4-87bd-9094a1cda072/july_chameleon_1.gif" width="70%"></p>

<p> </p>

<p>Dear Chameleon users,</p>

<p>We’ve had a busy month with Chameleon, and have a few big changes to announce. But first, a reminder that to kick off the summer, we held the Summer with Chameleon webinar series, covering an introduction to Chameleon, data science and best practices, CHI@Edge, and reproducibility on Chameleon. In case you missed it, the recordings and slides for these are now posted on our <a href="https://www.youtube.com/user/ChameleonCloud/videos">YouTube channel</a>. In a few weeks, we are presenting two papers at <a href="https://pearc.acm.org/pearc22/">PEARC22</a>: one on CHI-in-a-Box, and one on Migrating to Federated Identity, which won <a href="https://chameleoncloud.org/blog/2022/06/28/chameleon-wins-best-paper-award-at-pearc-22/">Best Paper</a>! If you are there, please stop by!</p>

<p><strong>Filesystem Preview!</strong> A shared filesystem has been a much requested and long desired feature for our users: storage tied to cloud instances is ephemeral (i.e., disappears once you terminate your instance/experiment) and while you could store data persistently in the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/swift.html">object store</a> and mount it via FUSE, this tends to be brittle and involve extra overhead on either the system or the experimenter (or both!). We are delighted to announce that at long last, Chameleon has a network filesystem that you can mount on your baremetal servers! For the time being, this feature is available in preview and at our UC site only – support at TACC is coming soon, pending feedback from users like you, so please share with us your thoughts on any adjustments that you would like to see in either functionality or interface. To learn more, please read <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/shares.html">our user documentation</a>. </p>

<p><strong>Openstack Xena Upgrade:</strong> As most of you are aware, Chameleon is built on a mainstream cloud implementation called <a href="https://www.openstack.org/">OpenStack</a>, which helps us keep it up to date as it integrates contributions from a large development community. A large amount of our effort  this month went into upgrading to the Xena version of Openstack on our bare metal offering at UC and TACC. Most of the changes are behind the scenes helping operators keep things running, but it also brings many improvements to reliability and performance, in particular launching new instances should get faster, as well as  improved error messages. It also provides a baseline for integrating improvements in the future.</p>

<p><strong>New reservation interface:</strong> Some of you have pointed out that it would be useful to swap out a node in your lease – for example, when one of your nodes is experiencing hardware failure. To provide this feature we’ve updated our reservation service, Blazar, so that you now can reallocate nodes in your lease – though we hope that you will still <a href="https://chameleoncloud.org/user/help/">contact the help desk</a> if you have issues with something on the testbed: if you see something, say something. But now, while waiting for our reply, rather than having to make a whole new lease to get a new node, you’ll be able to swap out the one having issues. For more information, see the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/reservations.html#reallocating-a-node-in-your-lease">docs</a>.</p>

<p><strong>CHI-in-a-Box Release:</strong> Last but not least, for those of you who are operating other Chameleon sites or thinking about it, we also made considerable upgrades to <a href="https://github.com/chameleoncloud/chi-in-a-box">CHI-in-a-Box</a> the packaging of  CHameleon Infrastructure (CHI). If you want to learn more about it we have a good summary of the progress in the last year in this month’s tips&amp;tricks <a href="https://chameleoncloud.org/blog/2022/06/28/chi-in-a-box-update/">blog</a>, and our <a href="https://chameleoncloud.org/media/filer_public/69/2a/692a6558-eeba-4a7f-a729-33e22eefccc8/ciab-pearc22-23-final.pdf">paper</a> on it will be presented at the PEARC on July 12th! A quick summary of this month’s features is the  Xena upgrade which brings new operator features such as burn-in hardware testing, container health checks, and. With feedback from our developing adopter community, we’ve also put lots of work into bug fixes, documentation, and general polish, making CHI-in-a-Box deployment quicker and more streamlined. Our favorite new feature: you can now set up a minimal site with 3 lines of configuration, and add features (and complexity) as needed.</p>

<p>Have a happy Independence Day weekend from the Chameleon team!</p>