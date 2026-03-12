---
abstract: "<p>Modern computational science depends on many complex, compute, and data-intensive\
  \ applications operating on distributed datasets that originate from a variety of\
  \ scientific instruments and data repositories. Two major challenges for these applications\
  \ are: (1) the provisioning of compute resources and (2) the integration of data\
  \ into the scientists\u2019 workflow.</p>"
authors:
- Georgios Papadimitriou
categories:
- User Experiments
date: '2019-11-13 20:11:29+00:00'
featured: false
hide_image: true
image: ''
related_posts: []
slug: dynamo-and-chameleon
subtitle: ''
title: Dynamo and Chameleon Aid Weather Scientists
---

<hr>
<p dir="ltr"><em>This work was part of the first ever SCinet Technology Challenge at Supercomputing 2019 in Denver, CO. <br>
The Dynamo team won two awards: "Most Diverse Resource Set" and "Most Original Technical Approach."<br>
<a href="https://isi.edu/news/story/394">Read more about the Challenge and the awards</a>.</em></p>

<hr>
<p dir="ltr" id="docs-internal-guid-4e41cfb7-7fff-8280-95b7-1be331aff910">Modern computational science depends on many complex, compute, and data-intensive applications operating on distributed datasets that originate from a variety of scientific instruments and data repositories. Two major challenges for these applications are: (1) the provisioning of compute resources and (2) the integration of data into the scientists’ workflow.</p>

<h3 dir="ltr">DyNamo and CASA</h3>

<p dir="ltr">DyNamo [7] is a project funded under the NSF Campus Cyberinfrastructure program, which aims to enable high-performance, adaptive, and performance-isolated data-flows across a federation of distributed cloud resources (e.g, ExoGENI, Chameleon, OSG, XSEDE Jetstream) [1, 2, 3, 4] and community data repositories.</p>

<p dir="ltr">Advances in network hardware and software defined networks have enabled high-performance, dynamically-provisioned networks. This functionality has been implemented on the ExoGENI testbed (<a href="http://www.exogeni.net">http://www.exogeni.net</a>) [2], and in addition to “stitching” ExoGENI sites together, it can also “stitch” external resources to the testbed (e.g., NSF Chameleon Cloud [1]) using a network artifact called “stitchport” [7].</p>

<p dir="ltr">Dynamo relies on the stitching capabilities of ExoGENI and by using the Mobius platform [8], it facilitates the provisioning of appropriate compute and storage resources for observational science workflows from diverse, national-scale cyberinfrastructure (CI). Efforts to use, configure, and reconfigure resources are significantly simplified by this approach. Additionally, through integration with the Pegasus Workflow Management System [6], DyNamo offers automation and orchestration of data-driven workflows on the provisioned infrastructure.</p>

<p dir="ltr"><img src="https://www.chameleoncloud.org/media/filer_public/fc/a1/fca126b6-bcf4-4af5-9066-ba7a34100e4c/image1.png"></p>

<p dir="ltr">The NSF Engineering Research Center for Collaborative and Adaptive Sensing of the Atmosphere (CASA) [5] aims to improve our ability to observe, understand, predict, and respond to hazardous weather events. Because of its data movement challenges and its need to elastically scale resources on demand, CASA is one of many applications that stands to benefit from the DyNamo project. Moment data from a network of seven weather radars located in Dallas/Fort Worth (DFW) flow continuously to CASA’s data repository, triggering new processing tasks on the arrival of new data. With increase in severity of the weather comes increased processing times (severe weather often means significantly more data to process). Thus, additional resources have to be provisioned dynamically to assure that the processing is not delayed and warning and forecast information can be provided on time.</p>

<h3 dir="ltr">CASA Workflows</h3>

<p dir="ltr">The Wind Speed pipeline (Figure 1) ingests radar moment data on radial velocity, but other variables are collected for noise reduction purposes as well. The first step in the process is the merging of an arbitrary number of individual radar data files. The wind speed algorithm attempts to create a grid of the maximum observed velocity, corrected for the height of the observation. The output is a single grid representing the estimate of the wind speed near the ground (Figure 2).</p>

<table align="center">
	<tbody align="center">
		<tr align="center">
			<td><img src="https://www.chameleoncloud.org/media/filer_public/27/5a/275a7b53-8f88-4e6c-8e5b-0960371ae239/image2.png" style="width: 90%;"></td>
			<td><img src="https://www.chameleoncloud.org/media/filer_public/27/6e/276e7d01-97ad-492b-9844-cc226c474416/image3.gif" style="width: 90%;"></td>
		</tr>
		<tr align="center">
			<td><em>Figure 1</em></td>
			<td><em>Figure 2</em></td>
		</tr>
	</tbody>
</table>

<p dir="ltr"> </p>

<p dir="ltr">The Nowcast pipeline (Figure 3) ingests asynchronous individual radar data that have previously been combined into a merged grid. These gridded data are accumulated over time for a certain initialization period and then used as input to the nowcast algorithm. In its current version, the algorithm is processing data every minute and produces a series of gridded reflectivity data, where each grid corresponds to the projected conditions of each minute within the span of the next 30 minutes into the future. An example of the calculated reflectivity is presented in Figure 4.</p>

<table align="center">
	<tbody>
		<tr align="center">
			<td><img src="https://www.chameleoncloud.org/media/filer_public/4d/fb/4dfbf8c5-99c0-4722-8d70-fae5693d97f0/image4.png" style="width: 90%;"></td>
			<td><img src="https://www.chameleoncloud.org/media/filer_public/fc/1c/fc1c7c51-0e1c-48b0-a439-e96dfcf29aa9/image5.png" style="width: 90%;"></td>
		</tr>
		<tr align="center">
			<td><em>Figure 3</em></td>
			<td><em>Figure 4</em></td>
		</tr>
	</tbody>
</table>

<p dir="ltr"> </p>

<h3 dir="ltr">Dynamo and Chameleon</h3>

<p dir="ltr"><br>
Chameleon is playing a key role in CASA’s workflow executions. Weather is changing constantly and as a result computation requirements change too. By taking advantage of Chameleon's direct stitching capabilities to ExoGENI [9], we can reliably connect Chameleon resources with CASA’s data repositories and scale up the available computing resources for its workflow executions, as seen in Figure 5. Due to the more powerful hardware available on Chameleon, CASA can scale up its computations faster than just using ExoGENI, by acquiring fewer physical nodes. However, this has the side effect of creating IO pressure on the Chameleon nodes, since multiple (over 24) tasks are getting executed simultaneously on the same node, and all of them have to stage-in, stage-out, read and write data. To mitigate any IO bottlenecks observed, CASA is using Storage node appliances to share data between the Chameleon workers, prefers nodes with SSDs (if available) and uses the shared network between TACC and the University of Chicago, to connect chameleon resources between them.</p>

<p> </p>

<table style="width: 100%;">
	<tbody>
		<tr align="center">
			<td><img src="https://www.chameleoncloud.org/media/filer_public/bf/77/bf7714f0-eb62-4455-9b73-dccd411028e7/image6.png" style="width: 100%;"></td>
		</tr>
		<tr align="center">
			<td><em>Figure 5</em></td>
		</tr>
	</tbody>
</table>

<p> </p>

<p dir="ltr"><strong><em>Acknowledgements: DyNamo is supported by the National Science Foundation, award number #1826997. </em></strong></p>

<h3 dir="ltr">References</h3>

<p dir="ltr">[1] NSF Chameleon Cloud. <a href="https://chameleoncloud.org/">https://chameleoncloud.org/</a></p>

<p dir="ltr">[2] I. Baldin, J. Chase, Y. Xin, A. Mandal, P. Ruth, C. Castillo, V. Orlikowski, C. Heermann, J. Mills. “ExoGENI: A Multi-Domain Infrastructure-as-a-Service Testbed.” The GENI Book, pp. 279--315, 2016.</p>

<p dir="ltr">[3] R. Pordes, D. Petravick, B. Kramer, D. Olson, M. Livny, A. Roy, P. Avery, K. Blackburn, T. Wenaus, F. Wurthwein, I. Foster, R. Gardner, M. Wilde, A. Blatecky, J. McGee, R. Quick, The open science grid, Journal of Physics:</p>

<p dir="ltr">Conference Series 78 (2007) 012057. doi:10.1088/1742-6596/78/1/012057. URL https://doi.org/10.1088%2F1742-6596%2F78%2F1% 2F012057</p>

<p dir="ltr">[4] J. Towns, T. Cockerill, M. Dahan, I. Foster, K. Gaither, A. Grimshaw, V. Hazlewood, S. Lathrop, D. Lifka, G. D. Peterson, R. Roskies, J. Scott, N. Wilkins-Diehr, Xsede: Accelerating scientific discovery, Computing in Science &amp; Engineering 16 (05) (2014) 62–74. doi:10.1109/MCSE. 2014.80.</p>

<p dir="ltr">[5] B. Philips, D. Pepyne, D. Westbrook, E. Bass, J. Brotzge, W. Diaz, K. Kloesel, J. Kurose, D. McLaughlin, H. Rodriguez, and M. Zink. “Integrating End User Needs into System Design and Operation: The Center for Collaborative Adaptive Sensing of the Atmosphere (CASA).” In Proceedings of Applied Climatol., American Meteorological Society Annual Meeting, San Antonio, TX, USA, 2007.</p>

<p dir="ltr">[6] E. Deelman, K. Vahi, G. Juve, M. Rynge, S. Callaghan, P. J. Maechling, R. Mayani, W. Chen, R. Ferreira da Silva, M. Livny, and K. Wenger, “Pegasus: a workflow management system for science automation.” Future Generation Computer Systems, vol. 46, pp. 17–35, 2015.</p>

<p dir="ltr">[7] E. Lyons, G. Papadimitriou, C. Wang, K. Thareja, P. Ruth, J. J. Villalobos, I. Rodero, E. Deelman, M. Zink, and A. Mandal, “Toward a Dynamic Network-centric Distributed Cloud Platform for Scientific Workflows: A Case Study for Adaptive Weather Sensing,” in 15th eScience Conference, 2019.</p>

<p dir="ltr">[8] Mobius. <a href="https://github.com/RENCI-NRIG/Mobius">https://github.com/RENCI-NRIG/Mobius</a></p>

<p dir="ltr">[9] Chameleon Direct Stitching. <a href="https://www.chameleoncloud.org/blog/2019/06/21/isolating-wide-area-networking-and-distributed-computing-experiments/">https://www.chameleoncloud.org/blog/2019/06/21/isolating-wide-area-networking-and-distributed-computing-experiments/</a></p>