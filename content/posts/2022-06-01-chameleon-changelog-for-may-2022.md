---
abstract: "<p>This month, we\u2019re excited to announce some great usability improvements\
  \ to Chameleon, new features on CHI@Edge, and some fixes for CHI-in-a-Box. We also\
  \ have some great papers in PEARC! Don\u2019t forget about the <a href=\"https://chameleoncloud.org/blog/2022/05/09/summer-with-chameleon/\"\
  >Summer with Chameleon</a> webinar series too!</p>"
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2022-06-01 20:23:44+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/7d/78/7d781769-1682-4b70-b444-697d18b85b76/2901697741_f5165919c4_c.jpg
related_posts: []
slug: chameleon-changelog-for-may-2022
subtitle: ''
title: Chameleon Changelog for May 2022
---

<p style="text-align: center;"><br>
<b id="docs-internal-guid-1bb71d8c-7fff-2db4-cc7d-ecd97624570a"><img height="800" src="https://lh6.googleusercontent.com/wHcWxKO_SOPJZgBl6TZs61F5PXGi1eiM3G16ST9EaqkliPaXP-QteuGShLo8TcO39FDnjsobJO0Ddxi0cSnBRGbME8zMOHsSt1VBvBJmRG-28swHNRPqb7bywlcKmHQWTRp8gUWIpF33nETEpw" width="531"></b><br>
<strong>Image Copyright <a href="https://www.flickr.com/photos/nickwebb/2901697741/in/photolist-5qpXDp-e38bkd-oC8FYS-L35zAr-69BArN-5bJoLN-6tYKiC-cnNzmY-4vYrQu-eo3LJg-2XFL4B-cVfTyd-MXPAa-621VUD-dwc66-2A5wdh-5ipNbH-2ie1zFB-3f4W-obCa47-fehSP-qKqbrF-aertBi-aeuk2J-aeuiy7-bdF7ZD-KnkUPn-aeuie3-29vvWnD-br3D6A-dZKxm-9YRYUU-dhcbJq-cs9SZm-RkWG5g-cs9Smu-2kReASY-PgWRjp-SJrbsx-Ru5tDH-eTSCFG-27V686q-SG6ths-2mk6TZd-2avtYtT-tzvS6-SVMtat-4QpSNz-9RVhXG-9Ejo5W">Nick Webb</a></strong></p>

<p style="text-align: center;"> </p>

<p>Dear Chameleon users,</p>

<p>This month at Chameleon, we’ve been preparing things behind the scenes for some big changes next month. Like always, we have some exciting announcements this month too. </p>

<p><strong>CHI@Edge Private Registries and Improved Reservations!</strong> Our Edge testbed, CHI@Edge received a lot of work in the past few months. In the last changelog, we announced its official release to version 2.0. Most importantly in the new version was the support for open device enrollment, allowing everyone to add their devices to CHI@Edge. With the architecture change required for version 2.0, users were no longer able to use Glance images when launching a container. As a replacement, we’ve added private registry support which allows containers to be launched from images that are not public. To get started, check out our <a href="https://www.google.com/url?q=https://chameleoncloud.gitbook.io/chi-edge/getting-started/using-private-registries&amp;sa=D&amp;source=editors&amp;ust=1654115736623487&amp;usg=AOvVaw102yC6TipR7d3M2cJqedW6">documentation</a> on configuring a registry for your project. Additionally, we’ve worked on automatically detecting peripherals on a device. This information is now stored in the reservation service, meaning that you’ll be able to reserve a device based on its peripherals. For example, when creating a lease, you can specify `pi_camera=True` to filter your reservation to only devices with a camera module.</p>

<p><strong>Summer with Chameleon:</strong> Please, do not forget that next week we have <a href="https://www.google.com/url?q=https://chameleoncloud.org/blog/2022/05/09/summer-with-chameleon/&amp;sa=D&amp;source=editors&amp;ust=1654115736624216&amp;usg=AOvVaw2ASmipNT397V-QsGamt8dF">our summer with Chameleon webinars</a>! They will provide a fresh take on getting started with the system, give overview of resources for a variety of data science projects, provide an update on facilities for reproducibility and give an overview of all those new and improved CHI@Edge features you’ve been hearing about. To reserve your spot in any or all of them, see the registration links <a href="https://www.google.com/url?q=https://chameleoncloud.org/blog/2022/05/09/summer-with-chameleon/&amp;sa=D&amp;source=editors&amp;ust=1654115736624587&amp;usg=AOvVaw2kPtQ6reLP267y0YHvAXzw">next to each session</a>.</p>

<p><strong>New Chameleon Papers:</strong> If you are interested in the workings of the system, we recently had two papers accepted to the <a href="https://www.google.com/url?q=https://pearc.acm.org/pearc22/&amp;sa=D&amp;source=editors&amp;ust=1654115736625112&amp;usg=AOvVaw3VKeFyML2wXP4ruesWD8iO">PEARC’22</a> conference: one about <a href="https://www.google.com/url?q=https://chameleoncloud.org/media/filer_public/cb/a0/cba02f95-3697-450f-b3a3-f6e43666e13a/paper_3530770.pdf&amp;sa=D&amp;source=editors&amp;ust=1654115736625499&amp;usg=AOvVaw0fO3heZUsvk8br9HoAE0P-">our migration to single sign on and federated identity</a>, and the other about <a href="https://www.google.com/url?q=https://chameleoncloud.org/media/filer_public/cb/0a/cb0a0c57-0371-4163-9941-b7b037b3b099/paper_3530768.pdf&amp;sa=D&amp;source=editors&amp;ust=1654115736625802&amp;usg=AOvVaw2EbCJojk3UH2JAQA0U7jKa">CHI-in-a-Box</a>. They will be presented at the conference this July – a good opportunity to catch up with Chameleon personnel if you happen to be headed there.</p>

<p><strong>Usability Improvements:</strong> We’ve gotten some great feedback from our users about what Chameleon does well, and where it has some shortcomings. Based on this feedback, we worked on some usability improvements to the testbed. The first of these improvements is to the <a href="https://www.google.com/url?q=https://chameleoncloud.org/hardware/&amp;sa=D&amp;source=editors&amp;ust=1654115736626335&amp;usg=AOvVaw30DhUGBh0MGTq_kyN9azQv">Hardware Discovery</a> page. The biggest changes are the big node filter buttons now show the same node type you’ll see when making a lease. When viewing specific nodes, now you’ll see the node name and type, instead of the UUID, which is the same name used in the calendar.<img alt="" src="images/image1.png" title=""></p>

<p style="text-align: center;"><b id="docs-internal-guid-cd5aa597-7fff-d448-2efe-095b1aa4b40f"><img height="316" src="https://lh5.googleusercontent.com/peCK6kq-rSZzb3jiIcAWi0NPuQdGWhUIMdrTF5DyvnZjVTgbdVyfwiG78p2-xC4B3OaZI0cyzJ_LaYUreGiCwvERJIHSiVcUNWewbUt2aFFpzRQpmpkN0e59y5Jcaegz6R4Cab-Vdp2iEvkhfw" width="624"></b></p>

<p>The next usability improvement is to project management. Last year, we added email invitations, which made it so you could invite people who are not yet Chameleon users to your project. Now, you can add many users to your project at once.</p>

<p style="text-align: center;"><b id="docs-internal-guid-bce4e48a-7fff-aac2-e2c0-e6acf9e98af8"><img height="275" src="https://lh4.googleusercontent.com/tLBBDF0NvMeC8RGjwfYxB5Ak9BqwhGcwv6rcFGvK-e3PvTgtW-9mCXPznD980kS6_2FqvqXoD7eN2oJKPyViYbi9m0_DM_3NVXMsryAr3tFJAfXtuB56HYeVeSlP8JtAz7npIFfVXxDSzclr1g" width="624"></b></p>

<p>Our <a href="https://www.google.com/url?q=https://chameleoncloud.org/experiment/share/&amp;sa=D&amp;source=editors&amp;ust=1654115736626997&amp;usg=AOvVaw38kqqiPSaGQmV6E9yZrIaA">Trovi portal</a> received updates too. The search is more robust, and now lets you find artifacts by author name. In addition to launching artifacts on <a href="https://www.google.com/url?q=https://jupyter.chameleoncloud.org/&amp;sa=D&amp;source=editors&amp;ust=1654115736627306&amp;usg=AOvVaw2WBWDulqYsiSEBHEi2UDCf">JupyterHub</a>, there now is an option to download it as an archive, making it incredibly easy to get a local copy of its files.<img alt="" src="images/image2.png" title=""></p>

<p style="text-align: center;"><b id="docs-internal-guid-e05ff490-7fff-6e16-2b87-c5f79e692e03"><img height="292" src="https://lh4.googleusercontent.com/dtv-mhp8PPLNr39NwYdCGuE-xwoNJTVbRsHzkp46L9zjxnb9n_LApsfuaKghc0k2EjIMvpyy1XJBIC4LHjT5GDuMIhC9EA-kcGFkr5SDaN8WXvtNC5tljckk6oTKeAovoAwUQXxvJATQ6r_mgw" width="624"></b></p>

<p>Additionally, we’ve gotten feedback about how much our <a href="https://www.google.com/url?q=https://chameleoncloud.org/user/help/&amp;sa=D&amp;source=editors&amp;ust=1654115736627772&amp;usg=AOvVaw3EsZK_C5WuYCcZxPSMCCYk">Help Desk</a> is appreciated. In an effort to make the Help Desk even better, we’ve added a section above the ticket form where we plan to share information about common ticket types. This will firstly help our users by suggesting typical fixes and guidance based on the issue type, and will help our support staff, by describing what information assists us in helping you, ensuring we can resolve issues quickly.</p>

<p>Lastly, we’ve squashed some annoying bugs. Occasionally, some of our pages (e.g. the <a href="https://www.google.com/url?q=https://chameleoncloud.org/appliances/&amp;sa=D&amp;source=editors&amp;ust=1654115736628272&amp;usg=AOvVaw0bkLd4HKr0c4BBPjzcpl9M">Appliance Catalog</a>) wouldn’t load correctly unless you logged out and in again, but this issue should be resolved. For <a href="https://www.google.com/url?q=https://python-chi.readthedocs.io/en/latest/index.html&amp;sa=D&amp;source=editors&amp;ust=1654115736628538&amp;usg=AOvVaw0v1bkAOI9hH2Mei0UNjUYb">python-chi</a> users, we fixed a bug where the `wait_for_tcp` would timeout long after the connection was ready.</p>

<p><strong>CHI-in-a-Box Upgrades:</strong> Lastly, we bring a few minor fixes to <a href="https://www.google.com/url?q=https://chameleoncloud.gitbook.io/chi-in-a-box/&amp;sa=D&amp;source=editors&amp;ust=1654115736629076&amp;usg=AOvVaw2AUgC2MYjDJY7h-TDH1jRR">CHI-in-a-Box</a>, the tooling that packages Chameleon’s infrastructure together and allows us to add so many associate sites to the testbed. We’ve fixed issues generating the `admin-openrc` when setting up. Additionally, issues with prometheus while running `cc-ansible deploy` should be resolved.</p>