---
abstract: <p>Teaching cloud computing effectively requires hands-on experience, but
  establishing local datacenters or using commercial cloud providers presents significant
  barriers for students. Chameleon Cloud provides the perfect solution, offering real
  cloud infrastructure experience without access limitations or costs, enabling comprehensive
  cloud computing education across European universities.</p>
authors:
- Massimo Canonico
categories:
- User Experiments
- Education
date: '2025-05-27 16:55:40+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/e3/79/e3795ae1-7bf6-43a7-abba-9eb15d9db8da/coruna2025.png
slug: teaching-cloud-computing-with-chameleon-making-complex-concepts-accessible
subtitle: How Chameleon Cloud Transforms Computer Science Education Across Europe
title: 'Teaching Cloud Computing with Chameleon: Making Complex Concepts Accessible'
---

<div style="background-color: #f8f9fa; border-left: 4px solid #007bff; padding: 15px; margin-bottom: 20px; font-style: italic;">
<h3 style="margin-top: 0; color: #007bff;">Note</h3>

<p>Chameleon Cloud serves a vibrant community of educators across US universities who are transforming how computer science is taught through hands-on cloud computing experiences. The international collaborations highlighted in this story represent the kind of academic knowledge sharing that strengthens educational practices globally. Through our <a href="https://www.chameleoncloud.org/chameleon-cloud-users-meeting/user-meeting-2023/">user community meetings focused on educational applications</a>—including our 2023 User Meeting's education mini-symposium with its theme of "teaching with testbeds"—we've seen how best practices developed on Chameleon inspire educators worldwide. Researchers like Massimo Canonico, who has <a href="https://www.chameleoncloud.org/blog/2019/09/18/teaching-high-performance-computing-with-chameleon/">shared educational slide decks</a> and teaching resources with the Chameleon community, exemplify how knowledge flows bidirectionally: international partnerships enhance educational methodologies that benefit classrooms both abroad and here in the United States.</p>
</div>

<p><img src="https://www.chameleoncloud.org/media/filer_public/e3/79/e3795ae1-7bf6-43a7-abba-9eb15d9db8da/coruna2025.png"></p>

<p><small>3rd year Software Architecture class 24/25, Universidade da Coruña</small></p>

<p>Being a computer science professor, I've consistently stressed the importance of practical exercises in my lessons. Explaining the workings of cloud computing proved to be a very complex challenge from the outset due to several factors. Establishing a local datacenter is far from straightforward, and the initial cloud service providers (like Amazon and Google) mainly offered paid access (you needed to provide your credit card details) or highly limited access (those famous free tiers are essentially machines where you can't run much of practical value). And this is where the Chameleon Cloud project steps in, like the superhero in movies who saves the day.</p>

<h3>Research Overview</h3>

<p>The Chameleon Cloud project has given me the possibility to offer my students a real hands-on experience of interacting with a cloud platform, free from access limitations and even using hardware that is often unavailable even in university science departments. While the course naturally starts with a theoretical introduction to cloud computing, the practical aspect is crucial for addressing the challenges that are merely outlined in the theoretical part.</p>

<p>Cloud computing represents a fundamental shift in how we think about computing resources, moving from ownership to service-based models. For students to truly understand concepts like elasticity, scalability, and distributed systems, they need to experience these concepts firsthand rather than just reading about them in textbooks.</p>

<h3>Educational Activities on Chameleon</h3>

<p>The learning process starts with the straightforward task of launching a simple virtual machine through the <a href="https://chameleoncloud.org/learn/frequently-asked-questions/#toc-horizon-gui">Horizon web interface</a>. From there, embracing their roles as computer scientists, students move on to using the terminal to automate tasks, leveraging Python libraries like Libcloud or Python-Chi. This empowers them to build sophisticated scenarios.</p>

<p>For example, they can create a setup where, if a virtual machine's CPU load surpasses a defined limit, a new, more robust VM is automatically created, and data is transferred using volumes or snapshots (the storage provided by OpenStack) to continue the computation seamlessly. Despite the limited time (24 hours of direct instruction), my aim is to expose the students to almost all the functionalities provided by Chameleon Cloud, including: VM management, volume and snapshot management, security groups, load balancers, User Data, floating IPs, and the utilization of <a href="https://chameleoncloud.org/learn/frequently-asked-questions/#toc-bare-metal-machines">bare metal instances</a>.</p>

<p>The <a href="https://chameleoncloud.org/hardware/">hardware catalog</a> and <a href="https://chi.uc.chameleoncloud.org/project/leases/calendar/host/">host availability browser</a> are particularly useful features that allow students to understand the physical infrastructure underlying cloud services, something impossible with traditional commercial cloud providers.</p>

<h3>Educational Artifacts</h3>

<p>I've always been a firm believer in the power of shared knowledge. Being aware of my own limitations, and knowing that teaching Cloud Computing involves so many different facets, I realize I can't be an expert in everything, even with the best intentions. That's why I created a website (<a href="http://tcc.uniupo.it">tcc.uniupo.it</a>) where I share all my teaching materials – slides, scripts, and tutorials – and I've also written a free ebook.</p>

<p>I love to teach, and thanks to Chameleon Cloud and the Erasmus+ project, I'm now sharing my knowledge of cloud computing not only here in Italy but also throughout Europe. In recent years, Chameleon Cloud has been a significant part of the computer science departments at universities in Malta, Norway (in Gjøvik), and Spain (in A Coruña). I'm currently planning the next leg of my 'Chameleon Cloud around the world' tour in France (Nantes).</p>

<h3>User Interview</h3>

<p><strong>Tell us a little bit about yourself</strong></p>

<p>I'm an associate professor of computer science at the University of Eastern Piedmont, Italy. My background includes studying and doing research in Aberdeen, Scotland, and at the University of California, Santa Barbara. I teach computer networks, mobile app development, and, naturally, cloud computing – a topic I'm particularly passionate about making accessible to everyone. My vision is for everyone to understand the fundamental importance of this technology, not just those in the field of computer science. When I'm not engaged in research and teaching, you'll find me playing soccer, working in my home garden and vegetable patch, or organizing cultural events with the association I'm part of.</p>

<p><strong>Most powerful piece of advice for students beginning research or finding a new research project?</strong></p>

<p>Maintain the curiosity of a child: approach things with the same enthusiasm and sense of wonder.</p>

<p><strong>How do you stay motivated through a long research project?</strong></p>

<p>Cloud computing is something that changes every year if you plan to keep up-to-date on your course. You never get bored.</p>

<p><strong>Have you ever been in a situation where you couldn't do an experiment that you wanted to do? What prevented you from doing it?</strong></p>

<p>In cloud computing, you're not in direct control of the hardware or the network, so it's pretty common to run into situations where you can't do what you wanted. You just have to get used to it and deal with it calmly, always having a plan B ready to go.</p>