---
abstract: <p>This blog post introduces the latest advancements in peripheral support
  for the CHI@Edge research testbed. It highlights the platform's holistic approach
  to integrating a wide range of sensors and cameras, opening up new possibilities
  for edge computing experiments. The post covers recent updates to documentation
  and tutorials, showcasing specific peripherals like the Waveshare Sense HAT-B and
  the Pi Camera Module 3. It also provides real-world examples of edge computing applications
  in fields such as precision agriculture and marine biology. Researchers are guided
  through the process of utilizing these new capabilities, with links to comprehensive
  tutorials on GPIO, sensors, and camera integration. This update represents a significant
  step forward in CHI@Edge's mission to facilitate cutting-edge research in edge computing
  and IoT applications.</p>
authors:
- Soufiane Jounaid
categories:
- Tips and Tricks
date: '2024-07-15 16:04:23+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/bd/7a/bd7aa209-1232-49a2-ad97-6639a255605f/for-beginners.png
related_posts:
- slug: seamless-ssh-container-access-with-chiedge
  title: Seamless SSH Container Access with CHI@Edge
- slug: chiedge-transitioning-from-successful-preview-to-full-production
  title: 'CHI@Edge: Transitioning from Successful Preview to Full Production'
- slug: driving-autonomous-cars-from-edge-to-cloud-with-chiedge
  title: Driving Autonomous Cars From Edge to Cloud with CHI@Edge
slug: expanding-horizons-with-chiedge-new-peripheral-support
subtitle: Enhancing Edge Computing Research with Advanced Sensors and Cameras
title: 'Expanding Horizons with CHI@Edge: New Peripheral Support'
---

<h1>Peripherals on CHI@Edge</h1>

<p>Peripherals are an essential part of edge computing. Facilitating the ability to add sensors and actuators that act on a device's environment was and remains one of the core ideas behind the CHI@Edge research testbed. To enhance the sensing on CHI@Edge, we have introduced support for a variety of new peripherals. This development opens up new avenues for experimentation and data collection, making it easier for researchers to integrate sensors, cameras, and other devices into their projects. Our recent CHI@Edge tutorials on Trovi can instruct you on leveraging these peripherals effectively (Check them out here!).</p>

<p>In this month's Tips and Tricks, we will go through the new peripherals we have introduced recently to CHI@Edge and show off their capabilities.</p>

<h2>Holistic approach to peripheral support</h2>

<p>We released an ambitious overhaul to our peripheral support structure. In contrast to our previous approach, where we maintained a limited subset of peripherals on a best-effort basis, we released an updated <a href="https://app.gitbook.com/o/Zkch89lL259lOhVcksT8/s/g88rFJkby8fmPSPBK6Ju/device-enrollment/peripherals-and-device-profiles">documentation</a> alongside multiple tutorials that not only showcase how to enable and operate certain peripherals on the platform, but overall present a holistic approach that paves the way for our users to contribute support for new and exciting peripherals to the platform. Visit the <a href="https://app.gitbook.com/o/Zkch89lL259lOhVcksT8/s/g88rFJkby8fmPSPBK6Ju/device-enrollment/peripherals-and-device-profiles">peripheral support documentation page</a> to learn more.</p>

<h2>Sensing the world around us</h2>

<p><img src="https://www.chameleoncloud.org/media/filer_public/2b/72/2b72873e-57ec-432c-8f7e-ab80ec501bef/sense-hat-c-1.png"></p>

<p>Using sensors on edge devices opens up a plethora of innovative applications, particularly in fields that require real-time data processing and local decision-making. One notable example is the <a href="https://www.waveshare.com/wiki/Sense_HAT_(B)">Waveshare Sense HAT-B</a>. This versatile board integrates a range of sensors, including temperature, humidity, pressure, and IMU (Inertial Measurement Unit) sensors. With such capabilities, you can deploy edge devices for environmental monitoring, where real-time data about weather conditions can help in various fields such as precision agriculture or disaster management.</p>

<p>A compelling example of using sensors on the edge is a project[1] at the Politecnic university of Valencia, Spain; which used wireless sensor networks (WSN) for precision agriculture. This project implemented low-cost, robust sensor nodes that measure soil moisture at various depths, enabling optimized irrigation processes for citrus trees.</p>

<p><img alt="Soil moisture sensor" src="https://www.chameleoncloud.org/media/filer_public/47/a0/47a0e08b-c5ec-4334-9559-8ea9110b5048/sensors-21-07243-g002.png"></p>

<p>In our <a href="https://www.chameleoncloud.org/experiment/share/1b8cdcba-e10c-4cae-8b1e-145037bc4cda">GPIO and Sensors Tutorial</a>, we walk you through the process of connecting and using various sensors with CHI@Edge. This tutorial covers:</p>

<ul>
	<li>Setting up your environment and connecting to CHI@Edge</li>
	<li>Reading data from different types of sensors</li>
	<li>Practical examples and use cases for sensor data</li>
</ul>

<p>It is a great starting point for working with sensor data on edge devices.</p>

<h2>Camera Tutorial</h2>

<p><img src="https://www.chameleoncloud.org/media/filer_public/bd/7a/bd7aa209-1232-49a2-ad97-6639a255605f/for-beginners.png"></p>

<p>One major peripheral that we have seen steady demand for is the camera. There is growing interest in the field of computer vision and its practical implementations on the edge. On Chi@Edge, we currently house a few of the <a href="https://www.raspberrypi.com/products/camera-module-3/">Pi Camera module 3</a>, a capable little sensor that can take high resolution pictures and videos. The examples of interesting projects using cameras on the edge are endless but our personal favorite is a homegrown project that had previously used a camera on CHI@Edge. A past <a href="https://www.chameleoncloud.org/blog/2022/04/18/one-fish-two-fish-choosing-optimal-edge-topologies-for-real-time-autonomous-fish-surveys/">blog post</a> of ours details how Jonathan Tsen (FATEC Shunji Nishimura), Leonardo Bobadilla (Florida International University), Kevin Boswell (Florida International University), and Jason Anderson (University of Chicago) used a camera coupled with a CHI@Edge device to develop metrics of fish abundance and map the fish distributions of important habitats in the Biscayne Bay in real-time.</p>

<p><img alt="Fish in the biscayne bay" src="https://lh4.googleusercontent.com/3qjyYqaFtUryRM7LW7boHtn97V3H43emcgiublDFBNuy_fcv-Q0OzHFU9dSmrqgLlEaVJmHURJsOMwZ9A8jvQ_KkjoDxUU_tl0fdMg056MtLCx7IsC8QUmTjkiUPvskVeIYKh_Fn"></p>

<p>Our <a href="https://www.chameleoncloud.org/experiment/share/7d35f884-68d8-4b91-b42b-207717c9b742">Camera Tutorial</a> demonstrates how to integrate and use cameras with CHI@Edge. This guide includes:</p>

<ul>
	<li>Connecting a camera to an edge device</li>
	<li>Capturing and processing images</li>
	<li>Streaming video from the edge device</li>
	<li>Analyzing image data with machine learning models</li>
	<li>Example projects that utilize camera data</li>
</ul>

<p>With this tutorial, you can experiment with computer vision applications, real-time video processing, and more, all within the CHI@Edge environment.</p>

<h1>Get Started with CHI@Edge</h1>

<p>Ready to dive into peripheral support on CHI@Edge? Here’s how you can get started:</p>

<ol>
	<li>Visit the <a href="https://www.chameleoncloud.org/experiment/chiedge/">CHI@Edge experiment page</a> to learn more about the platform and its capabilities.</li>
	<li>Reserve an edge device and set up your environment.</li>
	<li>Follow our GPIO and Sensors Tutorial and Camera Tutorial to start integrating peripherals into your projects.</li>
	<li>Share your experiments and findings with the community to inspire further innovation.</li>
</ol>

<p>We are thrilled to see what you will create with the newly expanded sensing capabilities of CHI@Edge. Stay tuned for more updates and tutorials as we continue to enhance our platform and support the growing needs of the research community. We look forward to seeing you at the edge!</p>

<p><strong>References</strong> [1] Lloret, J.; Sendra, S.; Garcia, L.; Jimenez, J.M. A Wireless Sensor Network Deployment for Soil Moisture Monitoring in Precision Agriculture. Sensors 2021, 21, 7243. https://doi.org/10.3390/s21217243</p>