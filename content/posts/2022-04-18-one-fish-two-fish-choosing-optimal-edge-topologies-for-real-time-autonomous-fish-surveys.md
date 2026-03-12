---
abstract: "<p>Learn how researchers\_are pairing autonomous vehicles with\_Chameleon\
  \ to bridge edge to cloud computation to conduct marine\_surveys. Featuring work\
  \ presented at the 2021 Supercomputing conference, with a notebook available on\
  \ Trovi that you can reproduce yourself, and a YouTube video to accompany it!</p>"
authors:
- Jonathan Tsen
categories:
- User Experiments
date: '2022-04-18 23:12:55+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/c3/07/c30726cb-1231-4595-a800-03ee3c1558c3/screen_shot_2022-04-19_at_120550_am.png
related_posts: []
slug: one-fish-two-fish-choosing-optimal-edge-topologies-for-real-time-autonomous-fish-surveys
subtitle: ''
title: 'One Fish, Two Fish: Choosing Optimal Edge Topologies for Real-Time Autonomous
  Fish Surveys'
---

<p dir="ltr">Learn how researchers are pairing autonomous vehicles with Chameleon to bridge edge to cloud computation to conduct marine surveys. Featuring work presented at the 2021 Supercomputing conference, with a notebook available on Trovi that you can reproduce yourself, and a YouTube video to accompany it!</p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-fe0f46ec-7fff-1e31-0267-801daf13597a">What is the central challenge your experiment investigates?</b></p>

<p dir="ltr">The oceans make up more than seventy percent of the Earth’s surface and marine ecosystems are central to many global challenges. However, monitoring the environment and ensuring the sustainable use of marine resources presents unique challenges spanning spatial and temporal scales including socio-economic balances, technology development, and dynamic ecological processes. Technological advances in computer vision technology, artificial intelligence, and cloud computing allow marine scientists to collect and process data in greater volumes than ever before and offer promise for solutions that may improve the efficiency of real-time data acquisition and analysis to address complex biological and ecological questions.</p>

<p> </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-fe0f46ec-7fff-1e31-0267-801daf13597a"><img height="275" src="https://lh4.googleusercontent.com/3qjyYqaFtUryRM7LW7boHtn97V3H43emcgiublDFBNuy_fcv-Q0OzHFU9dSmrqgLlEaVJmHURJsOMwZ9A8jvQ_KkjoDxUU_tl0fdMg056MtLCx7IsC8QUmTjkiUPvskVeIYKh_Fn" width="488"></b></p>

<p> </p>

<p dir="ltr">We aim to better understand the Biscayne Bay ecosystem by improving survey efficiency by leveraging the capabilities of autonomous vehicles (AVs). To do this, we develop metrics of fish abundance and map the fish distributions of important habitats in the Biscayne Bay in real-time. To accomplish this goal, we need to ask two questions.</p>

<p dir="ltr"><b id="docs-internal-guid-fe0f46ec-7fff-1e31-0267-801daf13597a">1. </b>What is the best strategy for collecting and analyzing data from autonomous vehicles and can we leverage cloud computing resources to improve access to data products in real-time?</p>

<p dir="ltr"><b id="docs-internal-guid-fe0f46ec-7fff-1e31-0267-801daf13597a">2. </b>How does the resolution of video data and quality of network connection influence which strategy is best?</p>

<p><br>
 </p>

<p dir="ltr"><b id="docs-internal-guid-fe0f46ec-7fff-1e31-0267-801daf13597a">How is your research addressing this challenge? </b></p>

<p> </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-fe0f46ec-7fff-1e31-0267-801daf13597a"><img height="283" src="https://lh6.googleusercontent.com/wdjRCBAtL49dwgR6B6PUtgZTmhBxDj_xKb2LqPEIUS3ytbePdtw331ry3iI1RZoY7RFbPCF6o2tlLZKdPyh0maPMXvCVo6mkc-jWb4wEpmDCqV4JUMmZGuUkiQX6PXlhlw8y_3i3" width="519"></b></p>

<p> </p>

<p>The challenge in this work was to compare configurations in which the vehicle is equipped with CHI@Edge versus configurations that perform similar calculations in the cloud and find out which has the lowest latency time and the best cost benefit.</p>

<p dir="ltr">We measured response time in each configuration, defined as how long from the time of video frame capture until the result can be received from the AI model. We found that in the cloud configuration, runtime defined as the time it takes for the model to run in a frame was dominated by transfer time that is the time it takes for video to be uploaded and returned from IoT to Chameleon Cloud (for example, RTX 6000 could evaluate at 25 ms but it took 235 ms to transfer the data, for a total response time of 260 ms).</p>

<p> </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-fe0f46ec-7fff-1e31-0267-801daf13597a"><img height="427.9198723871032" src="https://lh6.googleusercontent.com/7EbNx8UvgNpTI1tSPmE8ZRD2a08aYo-0aV1vLgW2I7G5w6-KF7FXSSCn9nI6YHFGKg8AQMG7C5PpHD8tKSP45vlVfJbmlNjP5EEmuMvTEh5zs2y0ttP5F0Bbm-qm8a96qpmS6jZg" width="242"><img height="464.42172083712853" src="https://lh6.googleusercontent.com/6dqmRHu5Bncq9mFn9Wn5Fymiem3jmCAR7NX7anXadBGmFnars9_YfyBnXn4VlrSHz-zX6W7XQR1H2I8sBlxK2Hh41slRC6N2626KNQGrv64G3K3UjdQlaYCrZmmWeX1Oc70PSEkd" width="538.5"></b></p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-fe0f46ec-7fff-1e31-0267-801daf13597a">How do you structure your experiment on Chameleon? </b></p>

<p dir="ltr">For this experiment, we used Chameleon’s CHI@Edge, as well as provision cloud resources for our experiment. We were able to connect the devices to GPU nodes on Chameleon’s Cloud and thus answer the questions mentioned in the introduction. The experiments were implemented via a Jupyter notebook that provisioned the resources and ran the experiments.</p>

<p> </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-fe0f46ec-7fff-1e31-0267-801daf13597a"><img height="158.40404360626127" src="https://lh6.googleusercontent.com/ZgVzAl6XsmfzqpMkNmuk0_ZajB7RNbeHYvnj8rXN5i4qvUrDy8J9SSQh3I9su9ZmgkqNKWrikDa-JeDngew01akhkcJbY65Aq3L-kIUOC9KenHnRJq9HREueawR3_6Z1xQH35Wl-" width="380"></b></p>

<p dir="ltr">The prices of each GPU in dollars used to calculate the (price / performance) was collected in August 2021, where FPS is the reciprocal of response time: how many frames can be processed in a given second The Jetson Nano is almost 19 times cheaper per FPS than Edge/Cloud (V100). The cheaper RTX 6000 outperforms the more expensive V100 with this perspective.</p>

<p><br>
 </p>

<p dir="ltr"><b id="docs-internal-guid-fe0f46ec-7fff-1e31-0267-801daf13597a">Can you point us to artifacts connected with your experiment that would be of interest to our readership? </b></p>

<p>The Poster: <a href="https://sc21.supercomputing.org/presentation/?id=spostu110&amp;sess=sess241">https://sc21.supercomputing.org/presentation/?id=spostu110&amp;sess=sess241</a></p>

<p>SC21 Poster presentation: <a href="https://youtu.be/jpFun2AbxoY">https://youtu.be/jpFun2AbxoY</a> </p>

<p dir="ltr">To reproduce the experiment: <a href="https://www.chameleoncloud.org/experiment/share/58">https://www.chameleoncloud.org/experiment/share/58</a></p>

<p dir="ltr">YouTube video from September 2021 CHI@Edge Workshop: <a href="https://www.youtube.com/watch?v=YJ46wOgGC40&amp;t=4s">https://www.youtube.com/watch?v=YJ46wOgGC40&amp;t=4s</a></p>

<p> </p>

<p dir="ltr"><b>About the Authors</b></p>

<p> </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-fe0f46ec-7fff-1e31-0267-801daf13597a">Jonathan Tsen</b></p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-1e49d124-7fff-8f0e-64a6-2feb6bf1577a"><img height="434" src="https://lh6.googleusercontent.com/VYQKTtjFC98ZuHKRW7ypTeZ450QRqNn-flEWDrXAciTNydardsKgGOoE0sccJkUNiHKTh4smskqPemj4C5HMVUbKWvwTQCsNxjmrqEePfDxYAyAySzKjQbmpp45i7n8bFKjkJj5k" width="352"></b></p>

<p dir="ltr">My name is Jonathan Tsen, and I'm currently working as a data scientist at a startup in Brazil. I am interested in specializing in Artificial Intelligence and to accomplish this, I have just started a Master's degree at the Aeronautical Technological Institute (ITA) in São José dos Campos in Brazil. I hope in the future to work as a data scientist at a company in the US. My hobbies include traveling and playing soccer.</p>

<p dir="ltr">LinkedIn: <a href="https://www.linkedin.com/in/jonathan-tsen/">https://www.linkedin.com/in/jonathan-tsen/</a></p>

<p> </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-fe0f46ec-7fff-1e31-0267-801daf13597a">Leonardo Bobadilla</b></p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-fe0f46ec-7fff-1e31-0267-801daf13597a"><img height="294" src="https://lh6.googleusercontent.com/YBR1jNlNpeno6-RVRfRs3zxaeldQ0PShX5LYjCrUCPq1c-Dcdy6XSzxv9lOhRGkiPheloToC9kWZvG7XzJMg-S68_dBPzJW_LrtOtbIJcNlSbg01Xvb7VvACRp590Yt7c29IKWqP" width="202"></b></p>

<p> </p>

<p dir="ltr">Dr. Leonardo Bobadilla (FIU) is currently an Assistant Professor at the Knight Foundation School of Computing and Information Sciences at Florida International University. He received his Ph.D. degree in Computer Science from the University of Illinois at Urbana-Champaign. He has received several awards and has published 37 peer-reviewed journal articles and conference papers. His research articles have appeared in prestigious journals such as IEEE Journal of Automation Science and Engineering, IEEE Robotics and Automation Letters, and ACM Transactions on Sensor Networks. His research has been sponsored by the Army Research Office, Department of Homeland Security, NSF, and the Ware Foundation.</p>

<p> </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-fe0f46ec-7fff-1e31-0267-801daf13597a">Kevin Boswell</b></p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-fe0f46ec-7fff-1e31-0267-801daf13597a"><img height="246" src="https://lh5.googleusercontent.com/gL7SMbcUyomqDoN-m9ObGRJsN7LBz_-FpDUpudMmS0UtLcYKt45Rqo7c6rfaIGjG3Kwpt32tatkkI1gC0YWpv3z7kyWGWa3-OrP4UtYNSNHK6lxnb1WLw721k0PjSckleGOylLzR" width="246"></b></p>

<p dir="ltr">Kevin Boswell is a marine ecologist. His research program broadly focuses on the interacting factors that mediate the distributional patterns, behavior, habitat use, energetics and natural ecology of coastal and oceanic animals, including the implications of ecosystem variability, particularly for rapidly changing environments. To address many of these interests, his lab integrates advanced sampling techniques, such as active and passive underwater acoustics, with observations from autonomous aerial and aquatic platforms to collect high-resolution data to simultaneously describe spatial and temporal patterns of interest, ranging from individual-level interactions to broad ecosystem dynamics.</p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-fe0f46ec-7fff-1e31-0267-801daf13597a">Are there any researchers you admire? Can you describe why? </b></p>

<p dir="ltr">I admire Jason Anderson because he is an excellent mentor, and he took me in during my internship at the University of Chicago. </p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-fe0f46ec-7fff-1e31-0267-801daf13597a">What's your most powerful piece of advice for students beginning research or finding a new research project?</b></p>

<ul>
	<li dir="ltr">
	<p dir="ltr">Schedule!</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Start, don't end with Wikipedia.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Mine bibliographies. </p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Have a research question in mind. </p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Deal with one piece at a time.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Use a system.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Know your resources.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Ask for help.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Carry an idea book.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Bring it up to date.</p>
	</li>
</ul>

<p><br>
 </p>