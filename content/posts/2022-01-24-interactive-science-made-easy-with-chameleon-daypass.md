---
abstract: "<p>Check out Chameleon Daypass! Enable Daypass for your Chameleon experiment,\
  \ and let any user, including those without a Chameleon allocation, try running\
  \ your experiment! You can even include a QR code which links to your experiment\
  \ in your paper or on a poster. Learn about the latest innovation in reproducibility\
  \ and how to make it work for you in this blog.\_</p>"
authors:
- Mark Powers
categories:
- Tips and Tricks
date: '2022-01-24 23:59:06+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/a1/c6/a1c6e033-0490-4beb-be57-a55d36d45edf/screen_shot_2022-01-24_at_34736_pm.png
related_posts: []
slug: interactive-science-made-easy-with-chameleon-daypass
subtitle: ''
title: Interactive Science Made Easy with Chameleon  Daypass
---

<h2 dir="ltr"><b id="docs-internal-guid-8fd4a53f-7fff-5e2a-3ef6-a529564369e1">What is Daypass?</b></h2>

<p dir="ltr">Chameleon offers many tools for reproducibility. You may be familiar with <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/jupyter.html">Jupyter Notebooks</a> that integrate into the testbed, allowing you to set up nodes, run code, and gather results in one place. These notebooks can be <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/sharing.html">packaged into artifacts</a>, and published to Chameleon’s sharing portal, <a href="https://chameleoncloud.org/experiment/share/">Trovi</a>, allowing others to launch a copy of the experiment and reproduce it in the same environment. Trovi is proving to be a popular way to share research: one such artifact is <a href="https://chameleoncloud.org/experiment/share/15">LinnOS</a>, which has been launched over 435 times since it was published in September 2020!</p>

<p> </p>

<p dir="ltr">However, only Chameleon users with an active allocation are able to launch these notebooks, which can be a hurdle for new users, since using the system requires an allocation, allocation requires PI eligibility – and as a new user it is hard to know if you are entitled to use the system, how to get an allocation, etc.. As a solution to this problem, we’ve created Chameleon daypass.</p>

<p> </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-8fd4a53f-7fff-5e2a-3ef6-a529564369e1"><img height="348" src="https://lh5.googleusercontent.com/ZbUzN46SDe4rtdCizM_I3zpe2VNLS-l_AMmeKQnAVCoZ4HLMAFscdNi1iIDYEuK92DdCa9c596m955SuSRuWruOz4gPrHZzZXbnROD-c_ycsqLdzJM7L8sK_3E7L3TUIfwExI0hQ" width="624"></b></p>

<p dir="ltr" style="text-align: center;">An artifact from the view of someone without an active allocation. Notice there is no way to launch the artifact.</p>

<p> </p>

<p dir="ltr">Imagine a scenario where someone is reading a research paper, and comes up with their own questions about the work. The reader will need access to the Jupyter notebook and any other code used in the experiment, but also the resources needed to reenact the experiment. Chameleon daypass makes it easy for anyone in the world to access resources on the testbed for a limited period of time for the purpose of reproducing the experiment. Check out <a href="https://www.youtube.com/watch?v=E2NCgIyatoo">this video</a> to see it in action, or continue reading to learn more.</p>

<p> </p>

<p>Requests for a daypass can be made by users without allocations, or users who don’t want to reproduce an experiment on their main allocation. Daypass has the potential to increase the number of people who interact with your experiment and boost your work’s impact.</p>

<h2 dir="ltr"> </h2>

<h2 dir="ltr"><b id="docs-internal-guid-8fd4a53f-7fff-5e2a-3ef6-a529564369e1">Daypass for Experiment Authors</b></h2>

<p dir="ltr">You’ve finished running your experiment and are ready to share your work with the world. Daypass can make this easier. To start this, <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/sharing.html#allowing-reproducibility-requests">follow these instructions</a> to enable daypass in the artifact’s sharing settings. Now that daypass is enabled, you can share a link to the artifact, either directly in a paper, or embedded as a QR code.</p>

<p> </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-8fd4a53f-7fff-5e2a-3ef6-a529564369e1"><img height="385" src="https://lh5.googleusercontent.com/idvEZQ-o6bzDA1NhAZHqk6fFMv3uuE89h0LmZPqE6SiEI0as0SyUbrfukC5RIYP7MOo0SNKiHt8F3wSqRV87rCi4N8kVLfgyvpc3nR2lKQY_iuazglnFqyJgZ0S3f2jdNMONuR_v" width="624"></b></p>

<p dir="ltr" style="text-align: center;">An example QR code, linking to a daypass artifact, from “<a href="https://chameleoncloud.org/about/papers-and-tech-reports/#:~:text=Yin%20and%20Yang%3A%20Balancing%20Cloud%20Computing%20and%20HTC%20Workloads">Yin and Yang: Balancing Cloud Computing and HTC Workloads</a>”.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-8fd4a53f-7fff-5e2a-3ef6-a529564369e1">Optimizing Daypass Artifacts for Users:</b></p>

<p dir="ltr">To help users get the most out of the experiment, there are a few things you, as an author, can do: </p>

<ol>
	<li dir="ltr">
	<p dir="ltr">Follow <a href="https://www.chameleoncloud.org/blog/2020/10/20/tips-and-tricks-packaging-experiments-reproducibility/">Chameleon Best Practices</a> for packaging experiments with reproducibility in mind.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Limit default reservation length: As a courtesy to other users, limit the default reservation length on your artifact to the length a daypass is configured for (e.g. 6 hours). This also maximizes the chance that requested resources are available. </p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Configure the notebook to use the Daypass Project ID: After enabling daypass, the experiment’s project PI will be added to a project titled “Reproducing ‘Artifact Title’”. This is the project daypass users will be using, and so it is helpful to configure the notebook to use this project’s ID by default.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Include detailed information: Daypass users might not have any prior experience with Chameleon! Please include any extra explanation or links that may help ensure users can successfully run the notebook.</p>
	</li>
</ol>

<h2 dir="ltr"> </h2>

<h2 dir="ltr"><b id="docs-internal-guid-8fd4a53f-7fff-5e2a-3ef6-a529564369e1">Daypass for Chameleon Project PIs</b></h2>

<p dir="ltr">Project PIs are responsible for reviewing daypass requests. Our documentation explains the review process <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/sharing.html#reviewing-a-daypass-request">here</a>. We understand that many PIs are busy, and may not have time to review requests, and encourage the use of <a href="https://chameleoncloud.readthedocs.io/en/latest/user/project.html#manage-user-roles-pi-delegate">PI delegate</a> to designate requests to the artifact author, if they are not a PI.</p>

<h2 dir="ltr"> </h2>

<h2 dir="ltr"><b id="docs-internal-guid-8fd4a53f-7fff-5e2a-3ef6-a529564369e1">Daypass for Users Interested in Experiments</b></h2>

<p dir="ltr">If a user navigates to a daypass-enabled artifact, they will see a button labeled “Request daypass”. Clicking on this button will guide the user through the process of requesting a daypass, and we explain it also <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/sharing.html#requesting-a-daypass">here in our documentation</a>. Once the request is approved, an email will notify the requestor, which we describe further <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/sharing.html#using-an-invitation">here</a>.</p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-8fd4a53f-7fff-5e2a-3ef6-a529564369e1"><img height="324" src="https://lh5.googleusercontent.com/gDMRqFMsxzcCSCDcBAUW2hje0mn6DSo6CXPjNGzxSKYvmpmtPTMI5Z81OI0ErapsnVHXiOeRUp0Kjr97pMMfMwd7rk9N-3eYDr1CXD58qJSrQ2mcqmlTJ61eLY1ik578SUm-XvS9" width="624"></b></p>

<p dir="ltr" style="text-align: center;">An artifact showing the “Request daypass” button.</p>

<p> </p>

<p dir="ltr">Public experimental testbeds provide a necessary condition for repeating experiments because they ensure that everybody has access to the same resources. With daypass, we are making it easier for everyone to have access to Chameleon for the purposes of reproducing an experiment, increasing the impact your artifacts can have. If you are interested, our <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/sharing.html#using-day-passes">daypass documentation</a> contains step by step instructions for users with more information.</p>

<p><br>
Want to try it out yourself? We’ve created <a href="https://chameleoncloud.org/experiment/share/70">this artifact</a> just for that purpose. Have feedback? Send us an email! We’d love to hear about how daypass helps with your experiments and what else can be done to improve access to the testbed.</p>