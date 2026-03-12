---
abstract: "<p>University of Texas, San Antonio\_Professor Wei Wang and PhD student\
  \ Sen He investigate performance testing for cloud computing research to help make\
  \ your research more efficient\_and cost effective. Learn about their research,\
  \ which won the ACM SIGSOFT Distinguished Paper award in 2019, experience on Chameleon\
  \ and AWS, and life philosophies.</p>"
authors:
- Wei Wang
categories:
- User Experiments
date: '2021-09-20 17:27:55+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/82/a8/82a84a26-7598-4312-91ae-bf7a45b0dd9f/screen_shot_2021-09-20_at_70906_pm.png
related_posts: []
slug: a-statistics-based-performance-testing-methodology-for-cloud-applications
subtitle: ''
title: A Statistics-Based Performance Testing Methodology for Cloud Applications
---

<p dir="ltr">University of Texas, San Antonio Professor Wei Wang and PhD student Sen He investigate performance testing for cloud computing research to help make your research more efficient and cost effective. Learn about their research, which won the ACM SIGSOFT Distinguished Paper award in 2019, experience on Chameleon and AWS, and life philosophies.</p>

<p dir="ltr"> </p>

<p dir="ltr"><b>On the current research: </b></p>

<p dir="ltr">Cloud computing has become the major computing infrastructure of our society. The average annual investment on cloud computing per organization is about  $73.8 million, according to IDG’s 2020 cloud survey. To effectively utilize cloud resources, especially for planning resource allocation and autoscaling, users need to accurately measure the performance of their applications through performance testing. Without accurate performance information, a cloud user may spend more than 10 times on cloud resources than they actually need. However, applications’ performance in the cloud usually fluctuates randomly due to resource contention caused by multi-tenancy. This fluctuation makes it very difficult to accurately determine the performance of cloud applications. </p>

<p dir="ltr">The following figure shows the performance distributions of a cloud application obtained from two separate performance tests. The large difference between the two tests illustrates the difficulty of performance testing in the cloud -- at least one of them is inaccurate -- maybe both!</p>

<p dir="ltr" style="text-align: center;"><br>
<br>
<b><img height="168" src="https://lh3.googleusercontent.com/3FpRDXnEC2nw7AZPtHc3aZCC124Ph9bojhio3xjyw2LRyxa04A65FtqcqJoLuJO4M2sA_2OvJPE3dfZyINnPaZNQpjIjuae1lnpyef2CvWDPJ4m4Xz6hGRkILivHgcnDPdYkOtyA=s0" width="524"></b><br>
Figure 1. Example of Performance Tests Result Variations. This figure shows the performance distributions (probability density function, PDF) of the two performance tests.</p>

<p dir="ltr"><br>
In short, cloud application performance is a fundamental requirement for efficient and effective cloud practice. This requirement applies to any cloud application scenarios, such as commercial software, web services and scientific computing. However, how to accurately obtain this performance is still an open research question.</p>

<p dir="ltr">We are building reliable performance testing methodologies that can provide accurate performance results while also maintaining low testing costs. Performance testing is essentially executing the application-under-test (AUT) repeatedly until accurate results are obtained. Therefore, the main research question is “how can we reliably know if the data from performance tests is accurate enough so that we can stop the test?”</p>

<p dir="ltr">This project is a collaboration project with Dr. Lori Pollock from University of Delaware and Dr. Mary Lou Soffa from University of Virginia.</p>

<p> </p>

<p dir="ltr">On approaching the research challenge: The basic idea is statistical stability -- when the performance distribution calculated from the performance testing data is stable (does not change), then we know the performance distribution is most likely to be accurate, and the test can be stopped.</p>

<p dir="ltr">However, the real challenge is to determine when the performance distribution is stable. We need an approach that can quantitatively describe this stability, and we need to be able to handle the non-typical types of cloud performance distributions.</p>

<p dir="ltr">We relied on advanced statistical tools to aid the performance testing processing. More specially, we use nonparametric statistical tools --  we use multinomial likelihood to compute the probability that the performance distribution is stable, and we use bootstrapping to handle the non-typical distributions.<br>
<br>
 </p>

<p dir="ltr" style="text-align: center;"><b><img height="223" src="https://lh4.googleusercontent.com/n91NlbljLM11Xv9K1sPpeV_y4tjZDG8LTOg6OFWVt8O4wabDLZhhJAnV4Txuu54sTt94QcTf9415-CVZS3BLfVDB2qqmZQgiATiyncdUQR_lpPCNQwVycIvzC-HTj481rZoo4sL1=s0" width="506"><br>
                            </b>Figure 2. The overall flow of PT4Cloud<br>
<br>
 </p>

<p dir="ltr">With the above ideas, the methodology we developed is called PT4Cloud. PT4Cloud conducts performance tests in multiple time periods of test runs. The application is executed repeatedly to collect n performance samples within each time period. Then, PT4Cloud calculates and determines if adding newly obtained n samples from the current time period significantly changes the performance distribution generated from previous periods. If the change is significant, more test runs of another time period are required. Otherwise, the performance distribution is considered stable and can be used to represent the actual performance distribution of the application on the cloud.</p>

<p dir="ltr" style="text-align: center;"><br>
<br>
<b><img height="397" src="https://lh5.googleusercontent.com/S6WZUpaAsDMY7ajtXeAr3b_gOu99qvml5i6ShiHUAC-VdVSGDf8gotGmxe3VfQFMpwGnVcO0Lir3aLhcURfuf5fA70582numlhtYNZpn67kHNqes11I6OiHiCVuOIq6eRnYGRDA9=s0" width="615"></b><br>
Figure 3. An example of PT4Cloud obtaining performance results with 92% stable probability after three weeks of performance tests. <br>
<br>
 </p>

<p dir="ltr">The above figure shows how PT4Cloud is used to obtain the performance results with 92% stable probability after three weeks of performance tests. In the figure, the first two weeks of tests have a stable probability of 56%. However, adding the third week increases the stable probability to 92%.<br>
 </p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-7d073243-7fff-47a3-bc81-e09307c75ea5">On testbed needs: </b></p>

<p dir="ltr">We mainly used Chameleon to validate our performance testing methodologies. We are probably in the rare group of users who rely more on the KVM setups than the bare-metal setups, although we do use bare-metal setups as benchmarking clients.  The main benefits of Chameleon we appreciate are its scalability, free, and direct access. //On Chameleon, we tested 15 benchmark configurations consecutively executed for more than two months. Over 40 KVM instances of different VM flavors and over 20 bare-metal instances were simultaneously used. Without the large scalability from Chameleon, it is basically impossible for us to finish that many experiments within six months. Chameleon is a well-maintained cloud platform with a large user base, and therefore performance testing on Chameleon can represent the complicated random resource contentions of most cloud environments.</p>

<p dir="ltr">The second benefit is direct availability at no cost to the researcher. Chameleon is free for research. We actually conducted the experiments on both AWS and Chameleon to verify the effectiveness and efficiency of our methodology. The experiments on AWS cost us about $10,000, which was paid through our NSF grant. Besides the high cost, estimating AWS expense is more difficult because of the “hidden costs”, such as network usage and storage cost. These hidden costs are more difficult to accurately estimate the expense before experimentation. We are currently working on serverless performance testing, where the cost model is even more complex and difficult to plan with.  Moreover, most of the cost on AWS was used to collect ground truth for evaluating PT4Cloud, which also shows the importance of inventing low-cost and accurate cloud performance testing methodologies.</p>

<p><br>
 </p>

<p dir="ltr"><b id="docs-internal-guid-7d073243-7fff-47a3-bc81-e09307c75ea5">On the authors:</b></p>

<p dir="ltr" style="text-align: center;"><br>
<b id="docs-internal-guid-7d073243-7fff-47a3-bc81-e09307c75ea5"><img height="167" src="https://lh3.googleusercontent.com/GxSFgzIV-Oj7chJ-cbT_CfTxMy0YrwykOgmF0ESPfrBxgREZ4P5Upj9vVYRGAKDvs09io2XiLm3eZMPOOKiV02_MmgYLGwI5LT-5bKBMciPBkg8DLEW-a1J7wYhKdotzsQTZGLDA=s0" width="126"></b><br>
 </p>

<p dir="ltr">Sen He is a Ph.D. student in the Department of Computer Science at the University of Texas at San Antonio. He has been working with Dr. Wei Wang since 2016. Sen He’s research interests include the areas of cloud computing, software engineering, and software testing. More specifically, his research is about using statistical tools to develop performance testing methodologies to obtain accurate performance results at reduced testing costs.</p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-7d073243-7fff-47a3-bc81-e09307c75ea5"><img height="168" src="https://lh3.googleusercontent.com/1RTdp9P6wthgHTWCSk5Ah3dIZvh2QT7rYBdj_rzL0L46Iyuh3NFHJvJ_af8ivekUMRtzVoCDvVdc--cVydbgnAyhBeZOZVIZLaf6rPoPbspxl2HhZnc_EZNEsWggOFOIrnlUs1cg=s0" width="159"></b></p>

<p dir="ltr">Wei Wang is an assistant professor in the Department of Computer Science at the University of Texas at San Antonio. He received his Ph.D. from University of Virginia in 2015. His research falls in the intersection of computer systems, cloud computing, computer architecture, and software engineering. His current projects mainly focus on cloud system designs, cloud native applications, and cloud performance engineering. His work was published in top CS conferences, including HPCA, MICRO, ASPLOS, PLDI, ICS, and FSE.</p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-7d073243-7fff-47a3-bc81-e09307c75ea5">On staying motivated through a long research project: </b></p>

<p dir="ltr">Through a long research project, I don’t always stay motivated. I usually itemize the tasks and keep working. After each task is done, the sense of fulfillment will naturally motivate me through the next one. </p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-7d073243-7fff-47a3-bc81-e09307c75ea5">On choosing his research direction: </b></p>

<p dir="ltr">Performance is one of the most important things users care about. I want to help users to easily and reliably obtain the performance without too much testing cost.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-7d073243-7fff-47a3-bc81-e09307c75ea5">On his most powerful piece of advice: </b></p>

<p dir="ltr">I think it is important to work in an area that has direct and clear social impact. The project itself can start small, but it is important to think about how your future research can benefit society. </p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-7d073243-7fff-47a3-bc81-e09307c75ea5">Interested readers can explore the following resources for more information:</b></p>

<p dir="ltr"><b id="docs-internal-guid-7d073243-7fff-47a3-bc81-e09307c75ea5">Paper: </b></p>

<ul dir="ltr">
	<li><b id="docs-internal-guid-7d073243-7fff-47a3-bc81-e09307c75ea5"><a href="https://dl.acm.org/doi/10.1145/3338906.3338912">https://dl.acm.org/doi/10.1145/3338906.3338912</a></b></li>
	<li><b id="docs-internal-guid-7d073243-7fff-47a3-bc81-e09307c75ea5"><a href="https://wwang.github.io/papers/PT4Cloud.pdf">https://wwang.github.io/papers/PT4Cloud.pdf</a></b></li>
</ul>

<p><b id="docs-internal-guid-7d073243-7fff-47a3-bc81-e09307c75ea5">Software and Data: </b></p>

<ul dir="ltr">
	<li><b id="docs-internal-guid-7d073243-7fff-47a3-bc81-e09307c75ea5"><a href="https://figshare.com/articles/conference_contribution/ESEC_FSE_2019_-_A_Statistics-based_Performance_Testing_Methodology_for_Cloud_Applications/7749356">https://figshare.com/articles/conference_contribution/ESEC_FSE_2019_-_A_Statistics-based_Performance_Testing_Methodology_for_Cloud_Applications/7749356</a></b></li>
</ul>

<p dir="ltr"><b id="docs-internal-guid-7d073243-7fff-47a3-bc81-e09307c75ea5">Awards:</b></p>

<ul dir="ltr">
	<li><b id="docs-internal-guid-7d073243-7fff-47a3-bc81-e09307c75ea5">ACM SIGSOFT Distinguished Paper Award</b></li>
</ul>