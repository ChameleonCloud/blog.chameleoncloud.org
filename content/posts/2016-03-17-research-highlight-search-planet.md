---
abstract: <p><em>CyVerse computer science class allows students to develop a solution
  to a real-world science problem using Chameleon</em></p>
authors:
- Makeda Easter
categories:
- User Experiments
- Announcements
date: '2016-03-17 17:01:31+00:00'
featured: false
hide_image: true
image: ''
slug: research-highlight-search-planet
subtitle: ''
title: 'RESEARCH HIGHLIGHT: IN SEARCH OF A PLANET'
---

<p><img alt="" src="https://www.chameleoncloud.org/media/uploads/2016/10/18/new-nirav-merchant-image.png"></p>

<article>
<section>
<p>Four years ago, <a href="http://www.bio5.org/about/scientists/nirav-merchant">Nirav Merchant</a> and <a href="https://cals.arizona.edu/spls/content/eric">Eric Lyons</a> noticed that many domain scientists were actively avoiding advanced computing for their research projects because they viewed it as inflexible, complicated, frustrating, and time-consuming. The two co-principal investigators of <a href="http://www.cyverse.org/">CyVerse</a>, a NSF-funded Cyberinfrastructure project that offers researchers access to a integrated platform of powerful computational  resources, wanted to address this issue by developing an educational initiative that intervened early in the pipeline.</p>

<p> </p>

<p>Through their annual upper division and graduate course, <a href="https://pods.iplantcollaborative.org/wiki/display/ACIC2015/Class+Schedule"><em>Applied Concepts in Cyberinfrastructure</em></a> at the University of Arizona, students learn fundamental concepts, tools and resources for effectively managing common tasks associated with analyzing real-world science problems. But more than a typical computer science class, the students take theoretical concepts and put them into practice using <a href="https://www.chameleoncloud.org/">Chameleon</a>, the nation’s first configurable experimental environment for large-scale cloud and computer science research, to build a specialized system to solve a real-world domain science problem.</p>

<p> </p>

<p>“The inspiration for the course came from what’s popularly called project-based learning, where you take a real question from a domain scientist and help them solve it,” Merchant said. “This is not just about teaching students what real data looks like, because in standard courses you give the students pre-cooked data — it’s pristine, it’s clean and real science is never that way.”</p>

<p> </p>

<p>From calculating energy mass transfer through ecosystems to analyzing rice genomes, a mix of undergraduate and graduate students worked on varying issues throughout the course’s history. Last fall’s class was tasked with addressing a computational bottleneck for astronomer <a href="http://makana.as.arizona.edu/">Jared Males</a> as he searches for <a href="https://en.wikipedia.org/wiki/Exoplanet">exoplanets</a>. Mapping exoplanets, or those that orbit a star other than the Sun, is an essential step toward the goal of finding other Earth-like planets.</p>

<p> </p>

<p>A <a href="http://nexsci.caltech.edu/sagan/">NASA Sagan Fellow</a> at <a href="https://www.as.arizona.edu/">Steward Observatory</a> at the <a href="http://www.arizona.edu/">University of Arizona</a>, Males builds and designs instrumentation inserted on telescopes to observe inactive objects. These telescopes are operated for a period of several months in Chile, so that other astronomers can use the equipment for their research.</p>

<p> </p>

<p>The instrumentation generates up to hundreds of thousands of images for a single star over the course of several hours. Males then processes direct images of the star in attempts to identify a cluster of pixels that have the signature of being a planet. To analyze these data, researchers use computation to filter the images for noise, and rotate and position the images so they are oriented the same way, as the earth is constantly rotating.</p>

<p> </p>

<p>Typically, analyzing these data in hopes of finding a unique set of pixels takes several months. Over the course of the semester, the students learned about concepts in computer science including virtualization, automation, web APIs, distributed and data visualization. They then worked with Males to apply these concepts and drastically reduce the time it takes to process image data and statistics to less than two days.</p>

<p> </p>

<p>Students learned about the numerous advanced computing technologies available to them to address this challenge, including Google’s cloud and their own campus resources. But for this real-world problem, the students tur</p>

<p>ned to <a href="https://www.chameleoncloud.org/">Chameleon</a>, hosted by the University of Chicago and the Texas Advanced Computing Center (TACC). CyVerse’s <a href="http://www.cyverse.org/discovery-environment">Discovery Environment</a> and Data Store were also used to transfer and share data between the class and Males.</p>

<p><img alt="" src="/media/uploads/2016/03/17/nirav-and-eric.png"></p>

<p> </p>

<p>“They learned about traditional HPC, they learned about cloud, and they gravitated towards Chameleon to design their solution because they had the required flexibility and fine grain control,” Merchant said. “They could control much more of how many hours something ran, how it ran, and the version of operating system on the virtual machine.”</p>
 

<p> </p>

<p>The Chameleon system also helped the researchers address time-sensitivity in analyzing star images. Oftentimes, astronomers need data processed in a single night, and also need to be able to do the analysis from anywhere. Chameleon allowed students to develop a virtual appliance that can be used by astronomers on multiple cloud platforms.</p>

<p> </p>

<p>“If it wasn’t for Chameleon, which provided a fertile training ground for students to really hammer on expensive virtual machines at once, we would have never been able to get this project done,” Lyons said.</p>

<p> </p>

<p>“It was fantastic to have access to [Chameleon] because of the complexity and amount of resources these students needed, which equated to about 100,000 CPU hours per run. They could get all those computing tasks done within a 24 to 48-hour time period,” he continued.</p>

<p> </p>

<p>By working on a real-world problem, the students were also forced to navigate the real-world kinks that challenge scientists using advanced computing, such as finding creative solutions during system outages.</p>

<p> </p>

<p>“We create a pressure cooker situation for the students where they’re not comfortable,” Lyons said. “This means we set up courses where we know students are going to fail, then we give them the space to fail, catch them, and let them succeed. This sets them up for handling failure in a real sense and how to get through it.”</p>

<p> </p>

<p><img alt="" src="/media/uploads/2016/03/17/mirrorlabsmall.png">In spite of these challenges, the students applied the skills they learned to develop a specialized research appliance, <a href="https://github.com/acic2015/findr">Find-R</a>, which is an analytical software package required to simultaneously  manage multiple virtualized computational appliances. The tool provides the analytical software required to process image files and ensures that everything is initialized and configured for the user. The tool also divides and coordinates the analytical tasks using open source distributed computing and workflow management tools from the <a href="http://ccl.cse.nd.edu/software/">Cooperative Computing Lab</a> at University of Notre Dame. The appliance is available on GitHub and includes documentation that explains how to run and install the software. Using this appliance, Males could run his analyses in one to two days instead of four months, a breakthrough for the astronomer.</p>

<p> </p>

<p>“We want to make sure this becomes a reusable appliance so other astronomers that have similar kinds of data can use the system as it is or be able to swap out core algorithms,” Lyons said.</p>

<p> </p>

<p>The course ended last December and will begin again in fall 2016.  In the meanwhile, Merchant, Lyons, and former students are expanding the capabilities of the appliance to make it available to the larger astronomy community, and helping Males get much closer to exoplanet discovery. This work is being presented at the upcoming <a href="http://spie.org/conferences-and-exhibitions/astronomical-telescopes-and-instrumentation">SPIE Astronomical Telescope and Instrumentation conference</a> in Edinburgh UK, June 2016.</p>
</section>
</article>