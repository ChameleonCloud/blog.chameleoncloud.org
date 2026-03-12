---
abstract: "<p>Interested in using Chameleon for education? Illinois Institute of Technology\u2019\
  s TA and PhD candidate Melanie Cornelius and Dr. Zhiling Lan use Chameleon for undergraduate\
  \ and graduate students in their Intro to Parallel Programming and Parallel and\
  \ Distributed Processing classes. Learn all about how the course is structured,\
  \ incorporating Chameleon into assignments, and tips for using Chameleon for education.</p>"
authors:
- Melanie Cornelius
categories:
- Tips and Tricks
- Education
date: '2021-08-23 19:12:40+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/d6/04/d6040e76-56b6-4bab-a223-207a42378395/screen_shot_2021-02-09_at_102934_am.png
related_posts: []
slug: chameleon-education-iits-intro-parallel-programming
subtitle: ''
title: "Chameleon for Education: IIT\u2019s Intro to Parallel Programming"
---

<p dir="ltr">Interested in using Chameleon for education? Illinois Institute of Technology’s TA and PhD candidate Melanie Cornelius and Dr. Zhiling Lan use Chameleon for undergraduate and graduate students in their Intro to Parallel Programming and Parallel and Distributed Processing classes. Learn all about how the course is structured, incorporating Chameleon into assignments, and tips for using Chameleon for education.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-95c44635-7fff-6f2d-d061-94a8f256be0c">Other resources the Chameleon team has created for those interested in using Chameleon for educational purposes or just beginning to explore Chameleon can be found here: </b></p>

<ul>
	<li dir="ltr">
	<p dir="ltr"><a href="https://bit.ly/3xdjXHf">A blog post</a> to help you or your students get started using Chameleon: how to launch artifacts on Trovi (perfect for classes!), where to find pre-packaged experiments by the Chameleon team on basic topics - orchestration, machine learning, setting up Chameleon resources, networking - and ~5 min YouTube videos for select packaged experiments.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr"><a href="https://bit.ly/3sXQ3FU">An older blog post</a> with similar information as the previous link, enumerating each of the pre-packaged experiments and getting started tutorials available on Trovi.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">An <a href="https://youtu.be/xun-aT1T6mA">Introduction to Chameleon YouTube video</a>: For students just learning how to use Chameleon, this video walks through making a reservation, setting up keys and logging in.</p>
	</li>
</ul>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-95c44635-7fff-6f2d-d061-94a8f256be0c">On the classes using Chameleon: </b></p>

<p dir="ltr">We’re using Chameleon for an Intro to Parallel Programming course (graduate and undergraduate students) and the CS546 Parallel and Distributing Processing class (graduate students) at the Illinois Institute of Technology. </p>

<p dir="ltr" style="text-align: center;">Prior to taking the CS546 course, students have some familiarity with programming in C/C++, linux tools and the development environment and basic concepts of computer architecture. Students design and code a CUDA-C/C++ version of a matrix normalization algorithm. The sequential version of this code is provided, and students must use CUDA-C/C++ to complete the program, then compare results between their parallelized version and the provided sequential code.<br>
<b><img height="421" src="https://lh6.googleusercontent.com/rk_-RjnQ8qkjo7GcI-LCaFp5D7YlhLe3U_5d5P7Uag0A3R7ME9hIzCrgYz5U3OWlP2DSdW7aARaJSpwGXwOy8T-GpPo0GDPq0qmLTxLdAW59xjygmVhjESyIs0Z3JlLWCJOYw8YW=s0" width="624"></b></p>

<p dir="ltr"> </p>

<p dir="ltr">Additionally, students complete a term project along similar lines. Here, students implement 2D matrix convolution using MPI send/recv, MPI collectives, and task/data parallelism. The point here is to compare parallelization techniques and communication strategies - with the hope that this will give students a practical understanding of the tradeoffs with each.<br>
In both the assignment and project, students use Chameleon resources to run their tests (so the graders can compare results directly).</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-95c44635-7fff-6f2d-d061-94a8f256be0c">On how long Chameleon has been used:</b></p>

<p dir="ltr">We use Chameleon for the two classes mentioned above and have used it for 3 semesters now.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-95c44635-7fff-6f2d-d061-94a8f256be0c">On recommendations for professors using Chameleon to teach a class: </b></p>

<p dir="ltr">There are a couple of things, some maybe sound negative but aren’t intended so - they’re just good to keep in mind when using this for teaching:</p>

<ol>
	<li dir="ltr">
	<p dir="ltr">If your students need a specific resource (like a GPU) there will be resource contention, especially if students procrastinate, consider encouraging students to plan in advance or creating a schedule for student time on the machines. </p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Consider a pre-assignment that just has students make a reservation and log in, this can present several hurdles for students who have never used remote machines or schedulers before.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Consider walking through making a reservation, setting up keys, and logging in while in class, or doing so in a recording. Chameleon offers <a href="https://youtu.be/xun-aT1T6mA">various videos</a> on the <a href="https://www.youtube.com/channel/UCVP_TxAjuCiMoQRxC68Pt_A">Chameleon YouTube channel</a> which students can follow to get started.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Link students to the extensive Chameleon docs, they can be hard to reach from the Chameleon website.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Make known the differences between the different kinds of allocations with Chameleon (bare metal, virtual machines, etc) if they exist.</p>
	</li>
</ol>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-95c44635-7fff-6f2d-d061-94a8f256be0c">On testbed needs for class instruction:</b></p>

<p dir="ltr">Here, we mostly make use of the <a href="https://chi.uc.chameleoncloud.org/project/leases/calendar/host/">visual resource scheduling system</a> (so students can see when they will have a machine available) and the GPU nodes.</p>

<p dir="ltr"> </p>

<ul dir="ltr">
</ul>

<p dir="ltr"> </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-95c44635-7fff-6f2d-d061-94a8f256be0c"><img height="151" src="https://lh4.googleusercontent.com/WAZCpHZ5zMF0rVWODIfJ6mpR4M5AfsF-MRRtg920B9dGZCL2hanuYNG3Was0CMxEq-LgV5S9rE6ifyep_tZRMnLRE-b1l4diS1-CvVaUkRbePwiOQlT3izABdBxW2JVIizcZIkHE=s0" width="121"> <img height="148" src="https://lh6.googleusercontent.com/WA47ARefOPBi7iD1iW2kbTX5glsXwYpZ-mOS4Ofr6G-QLtU3drr9wrCr7ShKd_n1CZxWeVKmevmoAsoW27oSI_Lt8Y-9Kb8eoDwJpguQfgkN2_g1LH1zl_x2bG9Ylt8D7Ecbt3gO=s0" width="148"></b></p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-95c44635-7fff-6f2d-d061-94a8f256be0c">Dr. Zhiling Lan &amp; TA Melanie Cornelius</b></p>

<p dir="ltr"><b id="docs-internal-guid-95c44635-7fff-6f2d-d061-94a8f256be0c">On herself:</b></p>

<p dir="ltr">I’m a PhD candidate at the Illinois Institute of Technology going for a doctorate in computer science / computer architecture. I’ve been at this stage for 2 years now following an undergraduate (in physics) and a MS in computer science. I took a small amount of time during the MS degree to work in two different corners of industry, one a very standard startup and the other a hemorrhaging-edge tech company. But by far, my favorite part of my job is teaching college students and doing research. I did it voluntarily as an undergrad, teaching fellow physics majors to use python, linux, and git. And now, I get to work with Dr. Lan’s classes as her lab instructor and TA. I love it! I enjoy working hard to make information accessible to a range of learning styles and backgrounds, and it’s challenging to find the right balance of provided material and experience-driven work. It’s fascinating to me. So, I went back for the PhD in the hopes I can successfully earn it and become a professor of CS doing research.</p>

<p dir="ltr">My hobbies are pretty simple, as I have kids - the tiny people are pretty much all of my hobbies. I garden a lot, and I sometimes sew or crochet. Mostly, I work and hang out with my kids, who are very little and full of wonder. I’m very, very fortunate to be doing what I love, all while having a family, under a wonderful adviser, Dr. Zhiling Lan. She’s a fascinating woman who is endlessly supportive, endlessly knowledgeable and invested in the field, and a stellar editor of papers.</p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-95c44635-7fff-6f2d-d061-94a8f256be0c">On staying motivated through a long project:</b></p>

<p dir="ltr">I stay motivated by not relying on motivation, honestly. Motivation, for me, is very short-lived. Like many people drawn to research, I’m very able to get excited and into a new topic - but that wave of interest is often short-lived. I’m learning all the time about discipline and how to be better at it.</p>

<p dir="ltr">I keep a planner, and I try to be diligent about it. I try to forgive a “bad day”, where I don’t get much done or get discouraged about research, and just move on - dwelling only makes another bad day happen. Mostly, I set hard lines around my work schedule and try not to go outside those lines more than 2 times a week. If it’s a Sunday, unless something really, really needs to get done, it gets put off to Monday. And if I take a day off, I take it off. I also do a lot of exercise. I’m an awful athlete, but being disciplined about doing a yoga class or something 5 times a week is like a training regime for being disciplined about working hard while working from home.</p>

<p dir="ltr">But it’s a struggle to remain disciplined, and I think it’s normal for it to be.</p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-95c44635-7fff-6f2d-d061-94a8f256be0c">On researchers she admires: </b></p>

<p dir="ltr">My adviser, Dr. Zhiling Lan, is someone I admire. She reads papers constantly, so she’s always up to date on which journals are focused on what, which formats like this or that styling or phrasing, and she’s one heck of an editor. She has a laser-focused eye for concise detail, and I’ve learned so much about writing papers for publication under her. And she’s so disciplined about her work - she works at specific times like clockwork, and I’ve learned so much from her about how to balance a schedule and not take on too much while still being challenged. Dr. Lan is a mom, a married partner, a successful academic, and an attentive, compassionate instructor. I look up to her enormously and try to learn from her all the time.</p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-95c44635-7fff-6f2d-d061-94a8f256be0c">On her most powerful piece of advice: </b></p>

<p dir="ltr">Anything worth doing is worth half-assing.</p>

<p dir="ltr">Seriously. Perfection is the enemy. Just get it done, and learn when to let go of perfection (and when to insist on it) - there’s almost always time to make it perfect later.</p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-95c44635-7fff-6f2d-d061-94a8f256be0c">Interested readers can explore the following class resources: </b></p>

<p dir="ltr">The <a href="https://drive.google.com/file/d/1_My2w9-QyyDDaqjZbpTrZGYIZ5KirEWu/view?usp=sharing">project</a> and <a href="https://drive.google.com/file/d/1fo74zzl3o0xkI0Wg9OYrKBwWyxj3OdzW/view?usp=sharing">assignment</a> done on Chameleon for the graduate student class are linked and the course websites are as follows: </p>

<ul dir="ltr">
	<li>Undergrad and grad class: <a href="http://www.cs.iit.edu/~lan/cs451/">http://www.cs.iit.edu/~lan/cs451/</a></li>
	<li>Grad class: <a href="http://www.cs.iit.edu/~lan/cs546/">http://www.cs.iit.edu/~lan/cs546/</a> </li>
</ul>