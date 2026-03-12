---
abstract: "<p>Today we share\_a very unique user experience\_-- a conversation\_with\
  \ Rafael Tolosana Calasanz who is an\_Associate Professor in the Department of Informatics\
  \ of the University of Zaragoza, Spain and has participated in the reproducibility\
  \ initiative at SC. Rafael shares with us his experiences reproducing artifacts\
  \ on Chameleon and his insights on reproducibility and its importance to the modern\
  \ scientific process.\_</p>"
authors:
- Rafael Tolosana Calasanz
categories:
- User Experiments
date: '2023-02-20 23:48:04+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/9e/47/9e471916-cc70-4321-855a-281c3d468569/rafael.png
related_posts: []
slug: sc-the-largest-reproducibility-laboratory
subtitle: ''
title: 'SC: The largest Reproducibility Laboratory'
---

<p dir="ltr"><b id="docs-internal-guid-eb7862c9-7fff-c4b0-3f4d-bedfd0c0c097">Rafael, thank you for talking to us. Please, tell us about the SC22 reproducibility initiative – what are its goals and how is it structured? </b></p>

<p>Reproducibility is the ability to repeat the research experiments that appear as the validation of a scientific paper. When we can reproduce the experiments, we can confirm the validity of a scientific discovery. Therefore, reproducibility is the foundation of solid and trustworthy scientific and technical research. Furthermore, fostering reproducibility facilitates dissemination, comparison, and adoption of research. Therefore, it can also contribute to increasing the impact and enhancing the visibility of papers.</p>

<p>From my point of view, technology in the past did not allow researchers to make reproducibility easy, requiring titanic amounts of effort and time. However, recent advancements, such as the widespread usage of online software and data repositories (such as github, dataPort or Dryad), or virtualization and packaging technologies such as virtual machines or containers have increased the opportunities for enabling reproducibility and, in consequence, many computer science conferences are already considering it. </p>

<p>During the last few years, SC has been leading the reproducibility of experiments in computer science, not only from a fantastic technical perspective, but also from its commitment. The SC reproducibility initiative started in 2015, and since then it has been developing continuously. A significant milestone happened in 2019, since then, reproducibility is mandatory for all SC submissions. It is very interesting to see the evolution of the SC reproducibility initiative across the SC websites (there is also a summary each year at the SC reproducibility main website)</p>

<p>On the other hand, the conference has to provide new committees to handle the review of the reproducibility code and data artifacts and it requires an additional effort. In parallel with the Program Committee, in SC there is a Committee of Reproducibility, with different subareas, which include the review of reproducibility artifacts, the reproducibility challenge, and a special issue for reproducibility. </p>

<p>The reviewing process is similar to that of traditional research papers, but reviewers assess whether they can reproduce the experiments as depicted in the paper. As an output of the process, each paper can receive a badge that quantifies its degree of reproducibility, such as, no code available, code available or results reproduced. Besides, the reproducibility challenge consists of selecting a paper accepted at the previous conference to be used as the source of the Reproducibility Challenge in the Student Cluster Competition (SCC). Then, the critique reproducibility reports obtained are compiled and submitted as a special issue to a journal (typically IEEE TPDS).</p>

<p dir="ltr"><b id="docs-internal-guid-eb7862c9-7fff-c4b0-3f4d-bedfd0c0c097">What was your role in the reproducibility initiative? </b></p>

<p>In 2022, I was involved in the reproducibility initiative of the IEEE TPDS journal, which is one of the first IEEE journals piloting a reproducibility initiative. Along with the editor-in-chief, Prof. Manish Parashar, we believed that it could be interesting to get involved inside the SC reproducibility initiative to learn from their knowhow. Therefore, I participated in the SC22 reproducibility initiative as a reviewer and the experience was absolutely fascinating. </p>

<p>At SC22, each reviewer handled 1 or 2 software artifacts and the time required to reproduce the experiment varies depending on the type of artifact / experiment and its quality. If the artifact is provided with deployment / installation / execution scripts and it is very well documented, the reviewer may not find many barriers, and it is just letting the machine(s) execute the code. Sometimes, it can be really challenging and an anonymous interaction between the reviewers and the authors is required.</p>

<p>Based on my experience at SC22, I believe that a reproducibility reviewer faces two main challenges. First, to understand the reproducibility artifact description and, then, to obtain the computing resources, to configure them and to execute the experiments on the resources. The problem is that, as researchers, we learn how to structure and write papers as there is a standardized agreement about that in the community. However, reproducibility is something novel and both authors and reviewers need to deal with it. Currently, we are working from the TPDS journal and the SC23 and ICPP23 conferences to standardize the artifact descriptions</p>

<p>On the other hand, another aspect is the computing resources required, their access and their configuration. On this matter, SC is also absolutely fascinating because of the variety of experiment types that can be found, requiring different software and hardware dependencies. For example, one can find from a single computer as a requirement, or a specific supercomputer, or thousands of computing nodes. The configuration and management of software dependencies is another challenge. SC was aware of that and aimed their authors to wrap their artifacts into a container specification. However, not all the experiments can be wrapped in a container specification and still the configuration setup of the computing infrastructure to execute the artifact can be challenging. Again, I believe that a standard reproducibility platform, where authors can prepare all or some of their experiments so that reviewers and eventually the research community can reproduce them could be a solution. I can see that Chameleon Cloud has been working towards that direction.</p>

<p dir="ltr"><b id="docs-internal-guid-eb7862c9-7fff-c4b0-3f4d-bedfd0c0c097">How do you use Chameleon in this effort and what was your experience? </b></p>

<p>One of the artifacts I was reviewing at SC22 required a server with a specific GPU and a version of its OS and compilers. That’s quite difficult to find, unless you have full control of that machine in your lab. Then, I asked the SC reproducibility chair for help, to grant me access to a computing infrastructure and that is when I used Chameleon. I used the GUI interface to look for the hardware and reserve the machine. Then, I requested the installation of the OS and the network and once I had access to it, I executed the artifact directly in the bare metal machine with the command line interface via ssh. Although I did not require a complex experimental set up, I could observe that it can be easily done with current functionality provided in Chameleon.</p>

<p>My experience with Chameleon was absolutely great. I was impressed by the ease of usage, starting from the logging in Chameleon, to the usage of the catalog or the access to the machines. </p>

<p dir="ltr"><b id="docs-internal-guid-eb7862c9-7fff-c4b0-3f4d-bedfd0c0c097">What features of the testbed did you need in order to reproduce the evaluated experiments? </b></p>

<p dir="ltr">My assignments at SC just required a single computer to be executed. However, I could validate and review the experiments of the server with GPU thanks to Chameleon giving me access to the hardware, and then letting me install the required OS and compilers on it. Furthermore,  looking at other submissions, SC really requires many features that Chameleon can provide, such as Bring Your Own Device (BYOD), when authors have made use of very specific hardware that is very difficult to obtain, otherwise.</p>

<p dir="ltr"><b id="docs-internal-guid-eb7862c9-7fff-c4b0-3f4d-bedfd0c0c097">Can you point us to artifacts connected with your work that would be of interest to our readership? </b></p>

<p>I participated in the first artifact approved by the IEEE TPDS journal, a joint collaboration with Prof. Omer Rana and Prof. Manish Parashar. It can be found <a href="https://codeocean.com/capsule/3e800863-bb27-4c51-8758-34cb630a7643/tree/v1">here</a>. The artifact is about a reactive resource manager controller for streaming applications. At that time, IEEE was promoting the Codeocean platform, and we used it as the experimental platform. Codeocean is a very interesting reproducibility platform, but, unfortunately, it only supports containerized applications and that can be an important limitation for parallel and distributed systems. The code in Codeocean is a modified version of the one for the paper to let the controller work inside a container. Another more recent code artifact we developed can be found here. This is a simulator of a cloud / edge scenario.</p>

<p>Both artifacts follow the artifact description guidelines that are now at IEEE TPDS, SC23 and ICPP23.</p>

<p><b id="docs-internal-guid-eb7862c9-7fff-c4b0-3f4d-bedfd0c0c097">Tell us a little bit about yourself</b></p>

<p>I am currently associate Professor in the Department of Informatics of the University of Zaragoza, Spain. I have been teaching in the same university for the last 17 years, mostly introduction to programming courses, but, more recently, I am in charge of concurrent programming and distributed systems courses in undergraduate degrees. </p>

<p>I am also associate editor in chief for reproducibility at IEEE TPDS, and reproducibility co-chair in SC23 and ICPP23. I am really enjoying my current tenure position as a civil servant, because it allows me to assume more risks with research ideas and project proposals, with less bad consequences than in the past. Sometimes, the pressure for publishing of the system can bring more continuist research and “less adventurous” researchers. </p>

<p>Regarding my hobbies, I love music and nature, and my little girl. In the past, my spare time was for music and nature, now, it is only for her. I hope when she grows up a little more we can enjoy my hobbies together, if not, I can always find some other hobbies.</p>

<p dir="ltr"><b id="docs-internal-guid-eb7862c9-7fff-c4b0-3f4d-bedfd0c0c097">What is the most powerful piece of advice for students beginning research or finding a new research project?</b></p>

<p dir="ltr">I particularly like “Labor omnia vincit”, which means something like “work always brings you to success”. We can say just keep on trying and making the effort to do our best. To find research ideas, I think it is key to be very bored. A busy brain is not a good idea for freshness. </p>

<p dir="ltr"><b id="docs-internal-guid-eb7862c9-7fff-c4b0-3f4d-bedfd0c0c097">How do you stay motivated through a long research project?</b></p>

<p dir="ltr">Sometimes it is good to stop and have a break. It works for me to completely change the activity, for instance, to do sports, to read a book, to travel, or to spend good quality time with family and friends.</p>

<p dir="ltr"><b id="docs-internal-guid-eb7862c9-7fff-c4b0-3f4d-bedfd0c0c097">What has been a tough moment for you either in your life or throughout your career? How did you deal with it? How did it influence your future work direction?</b></p>

<p dir="ltr">It is fair to acknowledge and assume that learning is always a difficult process, especially during the PhD. It is good to remember that we need to enjoy every moment, tough moments will pass and good moments will come.</p>

<p dir="ltr"><b id="docs-internal-guid-eb7862c9-7fff-c4b0-3f4d-bedfd0c0c097">What drives your interest in reproducibility and how do you think it can change the way science is done?</b></p>

<p dir="ltr">I find it fascinating. On one hand, we really owe the society quality research that can be trusted. On the other hand, I believe that it can really boost the productivity of science globally, as it can foster the comparison and the integration of techniques and mechanisms. It is also another way of being organized with our own work.</p>

<p><b id="docs-internal-guid-eb7862c9-7fff-c4b0-3f4d-bedfd0c0c097">Thank you for taking the time to talk to us and thank you for sharing your experiences with the Chameleon community!</b></p>

<p><br>
 </p>