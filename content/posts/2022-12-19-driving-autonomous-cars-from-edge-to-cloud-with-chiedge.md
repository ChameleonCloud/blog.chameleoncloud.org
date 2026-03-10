---
abstract: <p>This month, we talk to Rick Anderson from Rutgers University about his
  experience using Chameleon to experiment with autonomous vehicles!</p>
authors:
- Richard Anderson
categories:
- User Experiments
date: '2022-12-19 17:32:56+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/3e/e4/3ee49cf3-d554-4e12-ada6-3c363f8c3b73/image3.png
slug: driving-autonomous-cars-from-edge-to-cloud-with-chiedge
subtitle: ''
title: Driving Autonomous Cars From Edge to Cloud with CHI@Edge
---

<h1><b id="docs-internal-guid-5e67be08-7fff-0519-678d-44d13373b60f">Experiment</b></h1>

<h3><strong>What is the central challenge you address in your work?</strong></h3>

<p>As more remotely- or self- driven devices take to the streets, we need to be able to optimize how the devices interact in an environment full of real world challenges. Those challenges can be addressed by  the machine learning models – but how do we teach humans to develop in this type of environment? As students and researchers, we need a testbed to test our assumptions, explore and overcome the limitations of the machine learning models, and experiment with new ideas. While there are lots of resources for general machine learning training, there aren't many platforms that allow for evaluation with physical sensors, microcontrollers, and edge computing devices – in other words, the physical hardware on the edge of the network. This is why we created and use an autonomous remote-controlled car platform: an environment, in which students can explore how machine learning can influence the physical world in a very real way. It’s a reasonable intersection between human interaction, remote devices, and virtual decision making on remote hardware. One challenge we attempt to solve is how students or researchers are able to collect data and test models for self driving cars without in-person access. We seek to understand how a car can be driven remotely and the various tradeoffs between hosting the model on the cloud or locally.</p>

<h3><strong>How does your work  address this challenge?</strong></h3>

<p>Our approach is to make available a set of cars and tracks in an integrated learning environment. Tracks are defined by orange cones that you see in the figure below – this allows us to easily reconfigure them to represent differently shaped tracks and test how different learning algorithms adapt to different conditions. The cars are autonomous vehicle platforms composed of a camera, a steering system, a throttle, an inertial measurement unit, and a Raspberry Pi. They can collect steering, throttle, vehicle position, image, and speed data. It is possible to drive them manually (remotely) along the track to collect data that can be then used in training models – or autonomously based on inferences from the model. The Raspberry Pi on each vehicle is enrolled as a device on CHI@Edge, which means that students and researchers can reserve the vehicles for use as needed. From then on, they can use the Jupyter notebook preloaded with each vehicle as a tutorial, explaining how to get started and begin remotely operating it. Since both CHI@Edge and the Chameleon datacenter resources can be accessed from the same Jupyter notebook session the learning data can easily be sent to Chameleon cloud for training and testing – and the the new model or new weights and biases are returned from cloud to edge and updated on that vehicle. It is important that this configuration provides a complete training loop. The complete loop allows a full round trip of collecting, training, and deploying to and from the real world. This is modeled as an efficient and robust framework for us to know that we can perform continuous learning and upgrading the capabilities of our devices. Together we can now try, test, fail, and learn.</p>

<h3><strong>How do you structure your work on Chameleon?</strong></h3>

<p> </p>

<p style="text-align: start;"><b id="docs-internal-guid-ba0c1647-7fff-bb94-3fe9-e1ce720f9da2"><img src="https://chameleoncloud.org/media/filer_public/0c/bb/0cbb292e-0f83-492b-a440-32cca5b07e82/rickblogcover.png" style="width: 400px; height: 294px;"></b></p>

<p style="text-align: start;">We’re using a combination of all three Chameleon access options - GUI, Jupyter and command line. Previously we had to configure each car in step by step detail. This would take up 6 hours to get the cars ready to use. With CHI@Edge, we’re preparing a system image, which is essentially the boot hard drive, on an SD card for the Raspberry PI and the Jetson Nano. With this set-up, it now takes a few minutes per car to configure, which is a huge time saver. Additionally, this technique works on multiple architectures so we can compare how different architectures perform compared to each other. The system image we use is edited in such a way that it registers itself with CHI@Edge and the vehicle is now available/visible in the GUI. The project is housed in GitHub, where it’s possible to edit the machine learning code, the system images, the machine learning environment, and the car interfaces. There is a general purpose “Hello World” Jupyter notebook to get people started with the vehicle and the training environment. Since there are a limited number of physical devices we need a reservation system. Fortunately, CHI@Edge allows us to reserve vehicles and helps us manage the machine learning training process.</p>

<h3 style="text-align: start;"><strong>What features of the testbed do you need in order to implement your experiment?</strong></h3>

<p>The most important feature is of course the Chameleon’s CHI@Edge platform that allows us to launch containers onboard small, remote-control cars – and the fact that it supports advance reservations so that the availability can be managed. We developed base containers with libraries for access to the car's interfaces, a Python framework for data collection, training, and testing, and a set of Jupyter notebooks to orchestrate the above and allow the use of cloud resources. Another important aspect is that we get access to both edge and cloud GPU resources via consistent interfaces and within the same session – this makes programming edge to cloud interactions really easy. </p>

<p>If Chameleon’s CHI@Edge was not available, the central control, reservation system, and machine learning training loop would have to be handled by dedicated equipment. This would make continuous learning difficult. Another problem is that the preparation of the vehicles involves a long process. That starts with preparing each system OS SD card by configuring the code by hand and then burning a new custom image. CHI@Edge is so much more convenient and helps the students or experimenters focus on their machine learning projects.</p>

<h3><strong>Can you point us to artifacts connected with your experiment that would be of interest to our readership?</strong></h3>

<p>An early version of the project on a Blue Ribbon and Milwaukee Makerfaire. It’s been used in several workshops internationally and throughout New Jersey.</p>

<p><b id="docs-internal-guid-ba0c1647-7fff-bb94-3fe9-e1ce720f9da2"><img src="https://chameleoncloud.org/media/filer_public/c9/b3/c9b31db1-da42-41f2-844a-adbd1f53af42/image2.png" style="width: 960px; height: 720px;"></b></p>

<h1><strong>Author Profile</strong></h1>

<p><b id="docs-internal-guid-ba0c1647-7fff-bb94-3fe9-e1ce720f9da2"><img src="https://chameleoncloud.org/media/filer_public/46/2d/462de221-856c-453a-bae5-e6f698fcd788/image1.png" style="width: 813px; height: 579px;"></b></p>

<h3><strong>Tell us a little bit about yourself</strong></h3>

<p>I’m the Director of Virtual Worlds at Rutgers University and have led the Game Research and Immersive Design group for almost 15 years. A couple of my achievements are creating the framework for Arduino to support multiple families of microcontrollers. I co-authored Pro Arduino to help beginner embedded programmers try more advanced projects, consider how to develop, build a community and launch a product. I got my start in self-driving car projects when my team created a car racing game in Unity where you raced car algorithms instead of driving them. My virtual car racing moved into real life by building $500.00 human-driven electric race cars that I eventually made autonomous.</p>

<h3><strong>What are your interests?</strong></h3>

<p>I’m interested in connecting students emotionally with the learning they are undertaking.</p>

<h3><strong>What are your future hopes, dreams, and aspirations? (grad school, positions, etc.) What are your hobbies?</strong></h3>

<p>I’m co-founder of Fair Use Building and Research Labs. We recently got evicted from our location with 30 days notice. The city of New Brunswick, NJ decided to demolish the building and develop our location.  It’s been tough but we have a new location and we’re building a larger wood and metal shop. This will be used for more of our robot and machine learning projects amongst the classic makerspace projects. We could always use more help and support. What we’ve done in the last 11 years has inspired me every day in my day job at Rutgers University.</p>

<h3><strong>How do you stay motivated through a long research project?</strong></h3>

<p>I try to have partners in my projects and those partners help keep the motivation going. </p>

<p>When I got stuck and was having difficulty figuring out my career path I co-founded the FUBAR Labs makerspace. There I was able to combine my love of people,  games, making, and machines. It was a real reboot. I got to remember the things I was interested in when I was younger and discover that it was affordable and possible to do. That experience was super inspiring and I’ve been working with this new motivation ever since.</p>

<h3><strong>Most powerful piece of advice for students beginning research or finding a new research project?</strong></h3>

<p>A new project should be “about” something. What specifically will it do, what change or piece of knowledge is it about? A project that is for everyone, everywhere, for all time is an impossible design goal.</p>