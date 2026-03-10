---
abstract: "<p>Happy Birthday to Chameleon \u2013 and many happy returns of the day!\
  \ It is hard to believe it has been 8 years working with our amazing user community,\
  \ hearing about your research, reading your papers, and generally watching amazing\
  \ science being done every day. In this month\u2019s blog we have a cake, candles,\
  \ silly hats, balloons \u2013 and a tiny little gift. Welcome to the REPETO project\
  \ that will help us foster practical reproducibility and interactive science \u2013\
  \ read the changelog to find out more.</p>"
authors: []
categories:
- Chameleon Changelog
date: '2023-08-01 22:29:36+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/76/ad/76ad6fde-1a8f-4941-9c92-d8127fc39341/chameleon_2.png
slug: chameleon-changelog-for-july-2023
subtitle: ''
title: Chameleon Changelog for July 2023
---

<p style="text-align: center;"><img media="" src="https://chameleoncloud.org/media/filer_public/76/ad/76ad6fde-1a8f-4941-9c92-d8127fc39341/chameleon_2.png" style=""></p>

<p>Dear Chameleon users, Happy Birthday to Chameleon – and many happy returns of the day! It is hard to believe it has been 8 years working with our amazing user community, hearing about your research, reading your papers, and generally watching amazing science being done every day. In this month’s blog we have a cake, candles, silly hats, balloons – and a tiny little gift.</p>

<p style="text-align: center;"><img media="" src="https://chameleoncloud.org/media/filer_public/94/b3/94b3682b-36ae-43a2-9617-9a6f62781d7a/repeto_logo_background_transparent.png" style=""></p>

<p><b>The REPETO Project.</b> We know that increasingly more of you are using Chameleon as a reproducibility platform and would like to draw your attention to the <a href="https://repeto.cs.uchicago.edu/">REPETO project</a> that fosters practical reproducibility of  computer science experiments on open platforms. What is practical reproducibility you ask – it is a <a href="https://chameleoncloud.org/blog/2023/03/20/the-practical-reproducibility-opportunity/">way of making your experiments available in a way that makes reproducing them cost-effective enough to be part of mainstream scientific exploration</a>. The <a href="https://repeto.cs.uchicago.edu/">REPETO project website</a> is well worth visiting: you will find announcements of upcoming hackathons where you can either reproduce experiments on Chameleon or package your own, as well as calls for the <a href="https://repeto.cs.uchicago.edu/sor/">Summer of Reproducibility</a> internship opportunities that could give you – or your students – funding to package your experiments or other computer science experiments for teaching, sharing, or scientific exploration. You can also join the <a href="https://groups.google.com/g/repeto">REPETO mailing list</a> and follow on social media (<a href="https://twitter.com/PracticalRepro">Twitter</a> and <a href="https://www.linkedin.com/company/practicalrepro">LinkedIn</a>), which provide a discussion forum for all things reproducibility on open platforms. Please, take a look and tell us what you think!</p>

<p><b>Trovi Reproducibility badge and experiments.</b> But wait, there’s more! It turns out that some of our users have already packaged experiments for practical reproducibility and put them on Trovi – how’s that for party favors! This means you can find and reproduce those experiments easily – you may be interested in their experiments, or their data analysis method, or experimental methodology, or want to “<a href="https://www.chameleoncloud.org/blog/2022/09/26/experiment-patterns-making-complex-experiments-easy/">steal</a>” their recipe for creating an experimental environment on Chameleon – it doesn’t matter what aspect of their experiment you want to interact with, it is there for you to play with. To make it easier to find these experiments we created a new badge – the repeat sign from sheet music that is also part of the REPETO logo. And the best part – if you are interested in packaging your experiments on Chameleon for practical reproducibility, you can <a href="https://forms.gle/i1cnJoNeETafesdF9">apply for the badge</a> quite easily (a link to the application is also on the sidebar on the <a href="https://www.chameleoncloud.org/experiment/share/">main Trovi page</a> by the badge explanation). As we reported in <a href="https://www.chameleoncloud.org/blog/2022/10/04/chameleon-changelog-for-september-2022/">last September’s changelog</a> we keep track of views and executions of the Trovi artifacts – we are looking forward to seeing how many of you will repeat the available experiments – and to seeing more experiments with the reproducible badge! </p>

<p style="text-align: center;"><img src="https://chameleoncloud.org/media/filer_public/ed/b5/edb5cc13-4192-46d4-b51b-b10fd211d4d6/repeto_twitter_3.jpg" style="width: 300px;"></p>

<p style="text-align: center;">REPETO BADGE </p>

<p><b>New Ice Lake nodes at CHI@TACC! </b>More presents for our wonderful user community! We are excited to announce 20 new Ice Lake nodes available this month at CHI@TACC. These nodes are Dell R750 servers, each with 2x <a href="https://www.intel.com/content/www/us/en/products/sku/212287/intel-xeon-platinum-8380-processor-60m-cache-2-30-ghz/specifications.html">Intel Platinum 8380 CPUs</a>, for a total of 80 cores and 160 threads, as well as 256GB of ram. They’re configured with 2x 25G ethernet interfaces, and a 480GB SATA SSD for the boot drive. </p>

<p><b>Reservation bug fixes. </b>This month, we fixed some minor bugs with the reservation service. Some of you reported that the system got a bit huffy with allocation and lease extensions so that if you extended your lease beyond our 7 day limit, it would turn its status to “ERROR” and if you tried to create a lease that would exceed the balance or duration of your allocation, the system would spit out a very cryptic message – it now got a good talking to so it became a bit more articulate and urbane. </p>

<p><b>Contribute support for new device types in CHI@Edge. </b>Some of you have asked for new device types to be supported in CHI@Edge. Depending on the device, and its kernel, this can be more or less work. To assist in this effort, we’ve published a “template” repository of sorts: <a href="https://github.com/ChameleonCloud/chi-edge-coral">https://github.com/ChameleonCloud/chi-edge-coral</a><br>
If deployed on your own <a href="https://www.balena.io/">Balena</a> account, this repository will download and build the relevant kernel modules to get the google coral dev board working for CHI@Edge, and run the validation scripts from the K3s and Calico projects to verify this. If you’d like a different device supported, swap out the kernel and build options until it works, then send us a PR!</p>

<p>Happy experimenting!</p>