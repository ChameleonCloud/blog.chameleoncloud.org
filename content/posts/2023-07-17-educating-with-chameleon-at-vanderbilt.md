---
abstract: <p>This month we present an interview with Aniruddha Gokhale, Full Professor
  of Computer Science and Engineering at Vanderbilt University who is using Chameleon
  to teach classes on cloud computing, computer networks, and distributed systems.
  Professor Gokhale discusses the challenges of teaching with testbeds, explains how
  he managed to overcome it in his own teaching, and shares recommendations on how
  to best leverage the power of testbeds in the classroom.</p>
authors:
- Aniruddha Gokhale
categories:
- User Experiments
- Education
date: '2023-07-17 17:00:00+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/3d/3d/3d3dc1aa-7791-41ce-a621-31389d46ea12/lecture.png
related_posts: []
slug: educating-with-chameleon-at-vanderbilt
subtitle: ''
title: Educating with Chameleon at Vanderbilt
---

<p>This month we present an interview with Aniruddha Gokhale, Full Professor of Computer Science and Engineering at Vanderbilt University who is using Chameleon to teach classes on cloud computing, computer networks, and distributed systems. Professor Gokhale discusses the challenges of teaching with testbeds, explains how he managed to overcome it in his own teaching, and shares recommendations on how to best leverage the power of testbeds in the classroom. </p>

<h4><strong>What areas of knowledge are you teaching using Chameleon?</strong></h4>

<p> have been teaching three different but related systems courses, one course a semester. These courses are <a href="https://www.vanderbilt.edu/catalogs/kuali/undergraduate-22-23.php/index.php#/courses/B144ur6hnO?group=Computer%20Science&amp;bc=true&amp;bcCurrent=Computer%20Science&amp;bcItemType=courses&amp;bc=true&amp;bcCurrent=CS4287%20-%20Principles%20of%20Cloud%20Computing&amp;bcGroup=Computer%20Science&amp;bcItemType=courses">CS4287/5287: Principles of Cloud Computing</a>, <a href="https://www.vanderbilt.edu/catalogs/kuali/undergraduate-22-23.php/index.php#/courses/r1bwBw62nu?group=Computer%20Science&amp;bc=true&amp;bcCurrent=Computer%20Science&amp;bcItemType=courses&amp;bc=true&amp;bcCurrent=CS4383%20-%20Computer%20Networks&amp;bcGroup=Computer%20Science&amp;bcItemType=courses">CS/ECE 4383/5383: Computer Networks</a> and <a href="https://www.vanderbilt.edu/catalogs/kuali/graduate-22-23.php#/courses/HkbxBvThnd?bc=true&amp;bcCurrent=CS6381%20-%20Distributed%20Systems%20Principles&amp;bcGroup=Computer%20Science&amp;bcItemType=courses">CS 6381: Distributed Systems Principles</a>. Of these, the course on distributed systems is primarily a graduate-level course though undergrads in senior standing can take instructor’s permission to register for the course. This summer I intend to get my class material on Chameleon Trovi.</p>

<p>I teach these courses since they are directly aligned with my research interests. All of these courses could be taught as just a theory course. However, without a practical, hands-on and immersive experience, there is simply no way for a student to appreciate and understand the fundamental challenges, the solutions to these challenges and the impact of these solutions on the performance, reliability, scalability and security of the applications that rely on these systems. Consequently, my approach to teaching these courses has always relied on a mix of theory and empirical approach, where the theory behind one or more specific concepts is taught followed by a programming assignment that reifies those concepts.</p>

<p>The most significant challenges in empirically teaching such courses are (a) having a testbed to experiment with the ideas, (b) the steep learning curve in understanding to use the testbeds, when one is available, and (c) dealing and keeping up with the pace at which technology improves and/or changes.</p>

<h4><strong>What is the character of your educational project?</strong></h4>

<p>All of my courses are of moderate size ranging from 30-40 students. As mentioned earlier, the Cloud and Computer Networking courses are cross-listed between undergraduates and graduate students while the Distributed systems course is primarily a graduate-level course. Since Vanderbilt University’s CS department also runs an online Masters program for students from industry, the same course may be offered in two sections, one for the in-person students on campus and one for the online students. The assessments I have created for my courses are predominantly programming assignments. I usually have 4-5 assignments per semester. Most of these assignments build off on the previous one where more requirements get added based on the concept that gets taught.</p>

<p>I have been using the Chameleon for over four years quite heavily for these classes. To help students overcome the learning curve, I have also created video lectures and powerpoint slides with a sufficient number of screenshots that provide an easier approach for a student to get up to speed with the testbed. Yet, as new features get added to the testbed, it is hard for me to keep up. Summer is the time when I try to revamp some of the material.</p>

<p>I have a total of three projects allocated to me in Chameleon. Of this, two projects are used for teaching and a third one is for research, where my graduate students use Chameleon for testing their hypotheses. For the teaching-related projects, every semester, I add students to the project and at the end of the semester, I remove them from the project.</p>

<h4><strong>What made you select Chameleon for your class?</strong></h4>

<p>I have been using Chameleon for more than four years. Prior to that, I had just developed a new course in Cloud Computing where I wanted to mix theory with hands-on activities. For the first couple of years or so, I was using our in-house facilities to teach Cloud Computing. We had developed an OpenStack-based small cloud cluster for a DARPA project that was then repurposed for research and education. Moreover, although commercial platforms such as AWS, Azure and GCP, to name a few, were available in some form for educational purposes, there still were many limitations in using them. For example, I had to apply for educational credits every semester to use these platforms. AWS’ educational platform called AWS Educate also underwent multiple changes, and keeping up with these changes was difficult. Finally, these commercial platforms come with a limited number of credits after which we will have to pay. My concern was that when a student is learning the nuts and bolts of Cloud Computing, they are likely to make mistakes, such as forgetting to terminate VMs after use, and such mistakes could end up costing that student their credits.</p>

<p>Thus, I was looking for some platform that was available exclusively for research and education, was either very low cost or even free to use, had a long-term path to remain sustainable and where students could immerse themselves in their learning endeavors without having to worry about making mistakes. It was during this time that I heard of Chameleon. I cannot remember from what source I got to know of Chameleon but it certainly seemed very appealing to me, and that is when I decided to give it a try.</p>

<p>Since my syllabus was teaching virtualization both via VMs and containers, concepts such as software-defined networking, and techniques for application hosting, etc, I was looking primarily for something that would provide me and my students with virtual machines. Thus, the KVM OpenStack feature of Chameleon became my most used functionality. As I make changes to my syllabus to include recent advances, and also increasingly use it to teach my Distributed Systems and Computer Networking courses, I will be needing to use the bare metal and networking features of Chameleon. The CHI@Edge is also going to be an important functionality that I will need in the near future.</p>

<p>More recently, there have been many other NSF-funded projects that are available for research and teaching, such as CloudLab, FABRIC, etc. But before that there was no platform similar to Chameleon. Without Chameleon, it would have been very hard for me to have taught Cloud Computing unless I was ready to live with the constraints of the commercial platforms, their changing feature set, and changing policies.</p>

<h4><strong>How are you using Chameleon to teach class?</strong></h4>

<p>As mentioned above, the most used feature of Chameleon so far has been the KVM@TACC. In the Cloud Computing course, students are required to create their VMs/containers, security groups, etc. But for the Distributed Systems and Computer Networking courses, I create most of the platform for the students. I use Chameleon both in-class for hands-on demo and for programming assignments.</p>

<p>For the Computer Networking class in Fall 2023, I am looking into using the integration of Chameleon with FABRIC.</p>

<h4><strong>What are the most useful features of Chameleon for your educational project and what would you like to see improved?</strong></h4>

<p>Currently I have been making heavy use of KVM@TACC. This summer, I am making an effort to learn some of the new features, particularly the networking features and the integration with FABRIC. I want to use these capabilities in the Computer Networking course. Since my research focuses on Edge/Cloud computing, I also want to leverage CHI@Edge.</p>

<p>Integrating Chameleon with other projects is something I am interested in, and also happy to provide any help in this area. I am also studying how to use FABRIC and its integration with Chameleon. I have found this part somewhat complicated and am looking for ways to simplify it. Currently, I am also beta testing the ARA Wireless testbed. There are efforts to integrate that with Chameleon. When these testbeds are federated, then we would be able to expand both our research and teaching.</p>

<p>As for feature changes, I think that once the FABRIC-Chameleon and similar other testbed integrations are well-tested, their documentations and the process explaining these can be simplified.</p>

<h4><strong>Do you have any recommendations for professors using Chameleon to teach a class?</strong></h4>

<p>Chameleon is very easy to use. I will suggest starting with KVM@TACC or even better, start with the Chameleon Jupyter notebooks. Then, slowly transition to KVM@TACC and then as the need arises for your respective courses, use bare metal, GPUs etc. Professors should note that the use of baremetal, GPUs, and similar high-demand resources need reservations and are available for a limited time period only. However, one need not worry about reservations and limited time that VMs can be up and running on KVM@TACC.</p>

<p>Professors will need to create a project for their use. Thereafter, they should ask their class to create accounts on Chameleon. These days, students can use their school credentials to create accounts. At the start of the semester, the professor will need to add the students using their emails to the project. At the end of the semester, the professor can then remove these students and clean up any resources so that the same project can be repurposed for the subsequent semester. Please also note that every project has a time limit, and will need to be renewed periodically. The Chameleon team is very helpful and will renew the project as long as it is being used for the purposes that it is meant to be used.</p>

<h4><strong>Can you point us to any virtual resources connected with your class that would be of interest to our readership?</strong></h4>

<p>Most of my class material in the form of scaffolding code and starter code for programming assignments for all my three classes is available on <a href="https://github.com/asgokhale">my GitHub</a>. The three courses have their individual projects under this link. Due to some overlap between these courses, I want to modify the structure of these projects bringing some of the common scaffolding needs into a separate project.</p>

<p>At this time, my programming assignment descriptions etc are in a Box folder that is available internally to students. I plan to make these available also in my github repository.</p>

<h2>Profile</h2>

<p><b id="docs-internal-guid-b114e584-7fff-de8e-e528-f7e203317086"><img src="https://chameleoncloud.org/media/filer_public/1b/0a/1b0aa28b-52ca-49d8-84cd-67aaff6cc7b0/aniruddha.png" style="width: 800px; height: 418px;"></b></p>

<p><strong>Tell us a little bit about yourself.</strong></p>

<p>I am a Full Professor of Computer Science and Engineering at Vanderbilt University with a primary appointment in Computer Science and a secondary appointment in Electrical and Computer Engineering. My university is supporting my teaching efforts. My use of testbeds like Chameleon are possible due to the support provided by NSF and other sponsors to the designers and maintainers of Chameleon and similar testbeds. We are very thankful to both the funding agencies that have funded these testbeds, and the teams that manage these testbeds.</p>

<p>My research interests are in addressing a range of challenges in distributed systems in general, and cloud/edge computing in particular. Since all of these systems are inherently networked, I also conduct some research in Computer Networking, primarily in software-defined networking and more recently in 5G network slice management. Since we develop reusable solutions, our focus is on developing open-source middleware and tools, and make them available to the scientific community.</p>

<p><b id="docs-internal-guid-645e1118-7fff-fd8b-ec0b-aaa62a3579ab"><img src="https://chameleoncloud.org/media/filer_public/3d/3d/3d3dc1aa-7791-41ce-a621-31389d46ea12/lecture.png" style="width: 800px; height: 408px;"></b></p>

<h4><strong>Most powerful piece of advice for teachers, especially young educators, just starting out in their careers?</strong></h4>

<p>I feel that one can learn some concept or a subject in its depth only when one gets to self-experience that subject and not by someone else or a book telling them so. That has been my emphasis in all the courses that I teach. This is more so the case for systems courses, which require hands-on experimentation, and fortunately, I have been teaching all systems courses.</p>

<h4><strong>How do you keep students motivated through your educational projects?</strong></h4>

<p>By having hands-on projects, lively discussions over Slack channels, and end-of-semester projects by teams that brings out the creativity in the students.</p>

<h4><strong>Are there any researchers or teachers you particularly admire? Can you describe why?</strong></h4>

<p>There have been many teachers over the years right from school through college as well as keynote speakers in conferences and several YouTube lectures that have helped me. It is hard to pinpoint a single individual. I am grateful to all these people. I am always learning something and also learning some effective mechanism to teach when I hear these talks.</p>

<h4><strong>Has there been a tough moment for you either in your life or throughout your teaching career? How did you deal with it? How did it influence your future work direction or how you teach?</strong></h4>

<p>When I first became a tenure track faculty member, my teaching evaluations were very bad. This happened because although I had the hands-on approach in mind right from then, I did not do a good job of creating the scaffolding needed by the students. At Vanderbilt University, we have a Center for Teaching. Through their help, I started to improve things. This process never ends. The subjects I teach are such that there is significant churn in the technologies and concepts. So I have to keep up with the trends and keep modifying and adding more scaffolding.</p>

<p>Yoga/meditation/exercising and maintaining additional interests like learning Indian classical music etc have also helped me over the years.</p>

<h4><strong>Why did you choose to teach this subject?</strong></h4>

<p>My research centers around solving systems challenges in the general area of distributed systems with a focus on cloud and edge computing. Hence, the three courses: Cloud Computing, Distributed Systems, and Computer Networks are aligned with my interests.</p>

<h4>Thank you for sharing your knowledge with the Chameleon community!</h4>