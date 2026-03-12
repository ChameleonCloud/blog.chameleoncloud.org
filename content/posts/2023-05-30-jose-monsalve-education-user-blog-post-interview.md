---
abstract: <p>This month we present an interview with Jose Monsalve Diaz who is using
  Chameleon for HPC education. Jose and his colleagues developed an OpenMP tutorial
  that has been presented at multiple conferences, received an honorable mention by
  the Better Scientific Software Fellowship, and has lowered the barrier to participation
  in HPC for many who would not have had access to acquiring this type of knowledge
  otherwise. The blog discusses the challenges of teaching high-performance computing,
  explains how an open bare metal platform works to support it, and presents links
  to the tutorial materials on Chameleon that can help you develop your own tutorials!</p>
authors:
- Jose Manuel Monsalve Diaz
categories: []
date: '2023-05-30 21:28:38+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/f8/d3/f8d3639c-1e2a-4ac2-aeaf-213653b88998/jose.jpeg
related_posts: []
slug: jose-monsalve-education-user-blog-post-interview
subtitle: ''
title: 'Using Chameleon for HPC Education: an OpenMP Tutorial'
---

<h4><b id="docs-internal-guid-50ec4e4f-7fff-813b-d49b-d37d2d94c119">What areas of knowledge are you teaching using Chameleon?</b></h4>

<p>High Performance Computing (HPC) allows to push the limits of computation by using parallel CPUs, accelerator devices (e.g., GPUs) and multiple computing nodes (i.e., distributed computing). HPC is challenging in that it requires a large number of skill sets to be able to take the most advantage of the system. Several of these skills cannot be fully taught without hands-on experiences that accompany the theoretical sessions. To mention some examples an avid HPC user must know: parallel programming languages and frameworks, have a good understanding of computer architectures, know a large number of software tools for profiling and debugging, have a basic knowledge on how to use a linux-based terminal, etc. Our efforts focus on creating teaching materials for HPC. These products, such as our <a href="https://www.nic.uoregon.edu/pgas14/papers/pgas14_submission_11.pdf">OpenMP Tutorial</a>, are used to teach entry level students concepts of HPC. We have successfully used these tools in Tutorials at some conferences (e.g., <a href="http://carla2022.org/">CARLA2022</a>, and <a href="https://tapiaconference.cmd-it.org/">TAPIA2022</a>), summer schools (e.g., Cybercolombia’s <a href="https://cybercolombia.org/summer_school_5/">HPC summer school</a>), and in education of students in more personalized formats. This tutorial was also featured as an honorable mention by the Better Scientific Software Fellowship (<a href="https://bssw.io/pages/meet-our-fellows">BSSw</a>) presented by Jose M Monsalve Diaz in 2023.</p>

<h4 dir="ltr"><b id="docs-internal-guid-f62b8966-7fff-e145-dfea-cdfdea4fe1d5">What is the character of your educational project?</b></h4>

<p>The project's objective is to teach the fundamentals of parallel programming to people that already know how to program but that haven't had the chance to learn parallelization. We target education of undergraduate and graduate students, as well as post-graduates who are interested in extending their basic education. We have noticed that students do not have exposure to HPC either because they do not have access to a computer cluster and curriculum in their institution, or because they already work and didn't have the opportunity to learn these skills when they were students. After hosting these training sessions for almost 5 years, we have noticed an increased number of interested actors in students of STEM fields at the undergraduate or graduate level, as well as professionals in science and technology interested in harnessing the power of HPC in their work. One year we even had the chance to host a middle school student that was really interested in science. Some of the attendees have had the opportunity to learn some of the materials but not all of the necessary skills, and these trainings provide an excellent opportunity to solidify their knowledge. </p>

<p>The methodology used consists in a series of tutorials in the form of jupyter notebooks. The tutorials are presented in a hands-on workshop format, that can be followed either in person or remotely. At the moment we have opened our teaching material for OpenMP, as it is a powerful, yet simple enough framework for parallel programming. It also has capabilities to parallelize both on CPUs as well as GPUs. We are currently working on opening other courses. We are deploying these tutorials on a yearly event that we call simply HPC Summer School, and which takes place in Bogotá, Colombia.</p>

<h4 dir="ltr"><b id="docs-internal-guid-2751d44f-7fff-3c1c-7b53-d4a183d8c0ff">What made you select Chameleon for your class?</b></h4>

<p dir="ltr">There exists a large number of HPC systems that are open to the public. Open science projects can apply to application requests to obtain compute hours in HPC systems, for example in the laboratory of the Department of Energy. However, applicants who want to access these resources are expected to be at an advanced stage of development. These organizations also feature educational resources, but they are mostly targeted towards already existing users. Additionally, it is hard for these institutions to provide short-term access to external users as they must balance cybersecurity policies, internal bureaucratic procedures, and resource reservation for already existing users. Therefore, for newcomers, access to infrastructure is a daunting process, highly driven by availability in their local institutions. For underrepresented communities and institutions, it is not common to have these HPC resources on site, therefore there is a high barrier of entry into the world of HPC. On the other hand, for educators like us it is also important to have flexibility in our teaching infrastructure. Having full control over the system configuration in production systems is practically impossible.</p>

<p>Some solutions that we had explored in the past included hosting an educational system on site. However, this was extremely difficult given the complexity of hardware/software maintenance. Furthermore, these are expensive machines that are not worth having just for the use of education. Second, although we have maintained good relationships with institutions that are willing to provide training accounts in HPC systems, using their system requires large preparation times to guarantee availability together with navigation of complex internal politics. In contrast, Chameleon has been the perfect solution. First, it is easily adaptable to different group sizes thanks to flexibility in the reservation size. Second, there are a large number of different system types and configurations allowing for CPU, GPU and multi-node education. Third, deployment can be done in as little as 1 day thanks to DevOps automation tools (e.g., Ansible). Fourth, there is complete control over configuration parameters such as network, software system in each node, and number of users. Fifth, it allows us to be more neutral in the training process, reducing dependencies to a subset of institutions, therefore allowing us to expand to a larger number of users. </p>

<p>Not having Chameleon right now would require us to have more constraints in the times and dates that we can provide these training sessions. Furthermore, it would reduce the number of students that we target considerably, as there is a hard limit in the number of systems that can guarantee a given QoS. Finally, we would have to adapt the training material and infrastructure to whatever configuration is available in those institutions that may provide access to their systems.</p>

<h4 dir="ltr"><b id="docs-internal-guid-a18cbf18-7fff-f8d8-cc39-2e831f5defef">How are you using Chameleon to teach class?</b></h4>

<p>We use mainly the bare metal testbeds, as they allow us to create fully custom clusters with the hardware and software we need to run our tutorials. The complete software control means that we can deploy our systems with little to no modification to the training material. We commonly use the latest ubuntu LTS distribution installed on skylake nodes, and the Slurm works well as ad manager. We create a local network that connects the different nodes and allows for distributed computing. We create a network file system, usually through linux NFS, and add the user folders to it. For Jupyter support, we spawn Jupyerhub with multi-user support. We deploy the jupyter notebooks which compose the different tutorials.</p>

<p>Such infrastructure allows direct access to the cluster system through the web browser, requiring no installation whatsoever on the student’s system. </p>

<h4><strong>What are the most useful features of Chameleon for your education project and what would you like to see improved?</strong></h4>

<p>There are several features that have helped us in the development of our  educational project:<br>
 In our case, the most useful feature offered by Chameleon is the ease of granting students user accounts; this allows access across institutions and leads to democratization of HPC resources. Also important is availability of hardware, featuring different architectures. Second, it is accessing such hardware in bare-metal and with full control over the software and network stack. And third, it is the use of OpenStack for quick deployment of infrastructure in a cloud-like environment that is common in other systems.</p>

<h4><strong>Do you have any recommendations for professors using Chameleon to teach a class?</strong></h4>

<p>Our first recommendation would be to start simple. Creating single node infrastructures and using it in small groups first, such that errors can be detected before larger groups are involved. Frustration with the infrastructure can lead to early dropouts. Second, Jupyter notebooks are one of the best mechanisms to remove startup overhead and increase learning productivity. Not only are students familiar with them, but also, they are extremely easy to set up and use. Finally, as we observed during the <a href="https://chameleoncloud.org/chameleon-cloud-users-meeting/user-meeting-2023/">Chameleon User Meeting</a>, we are not the most advanced education infrastructure. We think it is very important to follow closely the work of others by being active actors in the Chameleon community: many of them have amazing ideas!</p>

<h4><strong>Can you point us to any virtual resources connected with your class that would be of interest to our readership?</strong></h4>

<p>Our community <a href="https://cybercolombia.org/">Cybercolombia</a> is always a point of contact for any of us. For now, our slides and tutorial for OpenMP are available on <a href="https://github.com/josemonsalve2/openmp_tutorial">GitHub</a>. The <a href="https://docs.google.com/document/d/1scycE7OAqwPJE8C6aFF0_3r8Zg8ttOptNopMzS_6djM/edit#heading=h.and9rv6uhj3d">syllabus</a> of this tutorial aims to cover most of the topics in OpenMP, starting with Part 1, that is an Introductory section where general concepts of parallelism and memory are explained. Following, Part 2 introduces multithreading, with an emphasis on traditional fork-join parallel models, as used by OpenMP. Part 3 (not yet released) extends the explanation to tasking. Part 4 is centered around OpenMP offloading, with an emphasis on general purpose GPUs. Finally Part 5 (Not yet released) discusses advanced topics in OpenMP offloading such as asynchronous offloading, declare mapper and declare variants. Each part has a collection of slides and its corresponding lab using Jupyter Notebooks. We believe that there is a lot of room for improvement, and welcome any external collaboration on extending, fixing or improving this material. We plan to continue creating materials on this topic as well as other multiple topics.</p>

<h3>Author Profile</h3>

<p><img src="https://chameleoncloud.org/media/filer_public/f8/d3/f8d3639c-1e2a-4ac2-aeaf-213653b88998/jose.jpeg" style="width: 640px; height: 480px;"></p>

<h4><strong>Tell us a little bit about yourself</strong></h4>

<p>Our group is <a href="https://cybercolombia.org/">Cybercolombia</a> a non-profit that is composed of researchers, academics, students and professionals that directly or indirectly work in the field of High Performance Computing. Our core members are: Jose M Monsalve Diaz, Postdoctoral Researcher at Argonne National Laboratory. Jose’s research focuses on programmability and usability of future computer architectures. Carlos Eduardo Alvarez Cabrera, professor with background in particle physics and high performance computing. Aurelio Antonio Vivas Meza, PhD student at the Universidad de los Andes in Bogotá, Colombia, and currently a student research assistant at Argonne National Laboratory. Aurelio focuses on in-situ workflows for scientific computation. And, Esteban Hernandez, PhD in Engineering with an emphasis in High Performance Computing. He is currently a Performance Engineer at Mercadolibre.</p>

<h4><strong>How do you keep students motivated through your educational projects?</strong></h4>

<p>Students are motivated by different things. Some are deeply interested in understanding the ins and outs of a process or system, but most are more easily motivated by pursuing specific, practical goals. When teaching a subject, particularly if it is a complex one, try to set up a study case with some practical goal at the end. This is not always easy, but if you manage it you might be able to engage a larger number of students.</p>