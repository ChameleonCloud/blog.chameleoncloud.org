---
abstract: '<p><span style="font-size: 11.0pt;"><span style=''font-family: "Calibri",sans-serif;''><span
  style="color: black;">This blog discusses a new experiment deployed on Chameleon
  called CIEF, a Cyber Infrastructure for Ecological Forecasting </span></span></span><span
  style="font-size: 11.0pt;"><span style=''font-family: "Calibri",sans-serif;''><span
  style="color: black;">(Dietz &amp; Matta, 2018)</span></span></span><span style="font-size:
  11.0pt;"><span style=''font-family: "Calibri",sans-serif;''><span style="color:
  black;">. CIEF supports data-driven research in ecological forecasting to understand
  our ecosystem and drive policy. Examples include predicting environmental changes,
  corn production in the near to medium term, types of disease-carrying mosquitos,
  based on data related to air, land, and water. </span></span></span></p>'
authors:
- Ibrahim Matta
categories:
- User Experiments
date: '2020-04-23 20:55:40+00:00'
featured: false
hide_image: true
image: ''
slug: scalable-cyberinfrastructure-repeatable-ecological-research
subtitle: ''
title: A Scalable Cyberinfrastructure for Repeatable Ecological Research
---

<p style=""><span style="font-size: 12pt;"><span style="font-family: Calibri,sans-serif;"><span style="font-size: 11.0pt;"><span style="color: black;">This blog discusses a new experiment deployed on Chameleon called CIEF, a Cyber Infrastructure for Ecological Forecasting </span></span><span style="font-size: 11.0pt;"><span style="color: black;">(Dietz &amp; Matta, 2018)</span></span><span style="font-size: 11.0pt;"><span style="color: black;">. CIEF supports data-driven research in ecological forecasting to understand our ecosystem and drive policy. Examples include predicting environmental changes, corn production in the near to medium term, types of disease-carrying mosquitos, based on data related to air, land, and water.  The goal is to provide a platform where ecologists submit their forecasting model code, run these forecasts and update models whenever new data becomes available, and analyze and visualize results. </span></span></span></span></p>

<p style=""> </p>

<p style=""><span style="font-size: 12pt;"><span style="font-family: Calibri,sans-serif;"><span style="font-size: 11.0pt;"><span style="color: black;">CIEF raises the level of abstraction by leveraging the “serverless computing” model </span></span><span style="font-size: 11.0pt;"><span style="color: black;">(Paul Castro et al., 2019)</span></span><span style="font-size: 11.0pt;"><span style="color: black;"> where users worry only about their application code but not its deployment. This makes it much easier for domain scientists (users) to advance their research in a scalable, automated, secure, and reproducible way.</span></span></span></span></p>

<p style=""><span style="font-size: 12pt;"><span style="font-family: Calibri,sans-serif;"><i></i></span></span></p>

<p style=""><span style="font-size: 12pt;"><span style="font-family: Calibri,sans-serif;"><span style="font-size: 11.0pt;"><span style="color: black;">We developed the CIEF hybrid edge-cloud middleware architecture to automate the process of iterative eco-forecasting </span></span><span style="font-size: 11.0pt;"><span style="color: black;">(<i>Ecological Forecasting Initiative</i>, 2020)</span></span><span style="font-size: 11.0pt;"><span style="color: black;"> for authorized researchers, standardize data formats and interfaces, develop front-ends that support decision making, and allow forecasting models to ‘compete’ and perhaps aggregate their predictions.</span></span></span></span></p>

<p style=""> </p>

<p style=""><span style="font-size: 12pt;"><span style="font-family: Calibri,sans-serif;"><span style="font-size: 11.0pt;"><span style="color: black;">To test our CIEF architecture, we used Chameleon as a back-end core cloud (datacenter), and GENI </span></span><span style="font-size: 11.0pt;"><span style="color: black;">(Elliott, 2008)</span></span><span style="font-size: 11.0pt;"><span style="color: black;"> as a distributed system of edge servers. The system then runs a forecasting code submitted by the user near the data source, or data store, or the user. Figure 1 illustrates the workflow supported by CIEF:</span></span></span></span></p>

<p style=""> </p>

<ol>
	<li style=""><span style="font-size: 12pt;"><span style="font-family: Calibri,sans-serif;"><span style="font-size: 11.0pt;"><span style="color: black;">The user submits her function code, along with dependencies / libraries.</span></span></span></span></li>
	<li style=""><span style="font-size: 12pt;"><span style="font-family: Calibri,sans-serif;"><span style="font-size: 11.0pt;"><span style="color: black;">An ‘orchestrator’ analyzes that submitted code, installs code dependencies, and configures the container in which the code will run.</span></span></span></span></li>
	<li style=""><span style="font-size: 12pt;"><span style="font-family: Calibri,sans-serif;"><span style="font-size: 11.0pt;"><span style="color: black;">We use OpenWhisk </span></span><span style="font-size: 11.0pt;"><span style="color: black;">(<i>Apache OpenWhisk</i>, 2020)</span></span><span style="font-size: 11.0pt;"><span style="color: black;"> as the serverless platform to run the forecasting function.</span></span></span></span></li>
	<li style=""><span style="font-size: 12pt;"><span style="font-family: Calibri,sans-serif;"><span style="font-size: 11.0pt;"><span style="color: black;">Especially with huge amounts of data, it is important for the orchestrator to strategically place the forecasting function, for example, close to where the source data is generated or where the result data is stored.</span></span></span></span></li>
	<li style=""><span style="font-size: 12pt;"><span style="font-family: Calibri,sans-serif;"><span style="font-size: 11.0pt;"><span style="color: black;">The user interface allows the user to authenticate and register, start an experiment, access the logs and results, visualize results and compare or validate models.</span></span></span></span></li>
</ol>

<p style=""> </p>

<p style="text-align: center;"><img src="https://www.chameleoncloud.org/media/filer_public/39/df/39df02e2-a2fe-4dfc-8a97-0d4f801b9ae3/image1.png"></p>

<p align="center" class="MsoCaption" style="text-align: center; margin: 0in 0in 10pt;"><span style="font-size: 9pt;"><span style="font-family: Calibri,sans-serif;"><span style="color: #44546a;"><span style="font-style: italic;">Figure 1: High-level view of the CIEF prototype</span></span></span></span></p>

<p style=""><span style="font-size: 12pt;"><span style="font-family: Calibri,sans-serif;"><span style="font-size: 11.0pt;"><span style="color: black;">Figure 2 shows the user’s view of CIEF: user submits her code (e.g., written in the R programming language), accesses logs, and views results (e.g., comparing different prediction models).</span></span></span></span></p>

<p style="text-align: center;"><img src="https://www.chameleoncloud.org/media/filer_public/2b/d9/2bd9fe8b-9e99-499d-a971-b3a0c056d17b/image2.png"></p>

<p align="center" class="MsoCaption" style="text-align: center; margin: 0in 0in 10pt;"><span style="font-size: 9pt;"><span style="font-family: Calibri,sans-serif;"><span style="color: #44546a;"><span style="font-style: italic;">Figure 2: Screenshots showing the user interface of CIEF.</span></span></span></span></p>

<p style=""><span style="font-size: 12pt;"><span style="font-family: Calibri,sans-serif;"><span style="font-size: 11.0pt;"><span style="color: black;">Chameleon has proven to be a critical infrastructure over which CIEF has been tested and used by our ecology collaborators. Chameleon resources, however, need to be reserved in advance and are only available until the reservation expires. We are investigating ways to dynamically reserve and elastically manage Chameleon resources so CIEF can operate more reliably.</span></span></span></span></p>

<p style=""> </p>

<p style=""><span style="font-size: 12pt;"><span style="font-family: Calibri,sans-serif;"><span style="font-size: 11.0pt;"><span style="color: black;">The vision is for CIEF to also support other applications (with different demands on resources) and to broker services provided by any number of cloud providers, including commercial offerings, as shown in Figure 3.</span></span></span></span></p>

<p style=""> </p>

<p style=""> </p>

<p style="text-align: center;"><img src="https://www.chameleoncloud.org/media/filer_public/ef/07/ef075e9d-fce0-4a33-ae06-da927db282fd/image3.png"></p>

<p align="center" class="MsoCaption" style="text-align: center; margin: 0in 0in 10pt;"><span style="font-size: 9pt;"><span style="font-family: Calibri,sans-serif;"><span style="color: #44546a;"><span style="font-style: italic;">Figure 3: CIEF's general architecture.</span></span></span></span></p>

<p><span style="font-size: 12pt;"><span style="font-family: Calibri,sans-serif;"><span style="font-size: 11.0pt;"><span style="color: black;"><strong>References:</strong><br>
Apache OpenWhisk. (2020). http://openwhisk.apache.org/<br>
Dietz, M., &amp; Matta, A. (2018). EFCI. A Scalable and Secure Cyberinfrastructure for the Repeatability of Ecological Research. https://www.bu.edu/hic/2018/02/01/a-scalable-and-secure-cyberinfrastructure-for-the-repeatability-of-ecological-research/<br>
Ecological Forecasting Initiative. (2020). https://ecoforecast.org/<br>
Elliott, C. (2008). GENI (Global Environment for Network Innovations). 33rd IEEE Conference on Local Computer Networks (LCN). https://doi.org/10.1109/lcn.2008.4664143<br>
Paul Castro, Ishakian, V., Muthusamy, V., &amp; Slominski, A. (2019). The Rise of Serverless Computing. Communications of the ACM, 62(12), 44–54.</span></span></span></span></p>