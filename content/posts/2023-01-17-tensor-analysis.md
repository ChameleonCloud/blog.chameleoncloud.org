---
abstract: <p>This month's user experiment blog covers some interesting work on tensor
  analysis from researchers at Arizona State University.</p>
authors:
- Mao-Lin Li
categories:
- User Experiments
date: '2023-01-17 20:40:10+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/6a/b6/6ab6d758-6499-4509-9546-a45e475527be/mao-lin-li.png
slug: tensor-analysis
subtitle: ''
title: Tensor Analysis
---

<h3><strong>What is the central challenge/hypothesis your experiment investigates?</strong></h3>

<p>Tensor representation is commonly used for multi-modal and multi-dimensional data sets. For example, in order to understand the shopping behavior of Amazon’s consumers, we can analyze the transaction data. We can extract “consumer” and “item” from the transaction data as a 2-D zero-one matrix (if the consumer purchased the item, mark <code>[i,j]=1</code> in the matrix; otherwise, <code>[i,j]=0</code>). We can also include the transaction time and make it a 3-D matrix. Those matrices are called tensors, and the attributes of the matrix (in our case, consumer, item, and transaction time) are called tensor mode. Tensor decomposition is any scheme for expressing a tensor as a sequence of elementary operations acting on others and thus helping extract important information from a tensor. There are a lot of tensor decomposition algorithms and Tucker is one of the most commonly used algorithms. The disadvantage of the Tucker algorithm is that memory and computation effort grows exponentially with the number of tensor modes.  The tensor train (TT) algorithm solves the problem by using an approximated representation which requires lesser space and decomposition time. TT-decomposition has been widely used in deep learning, crowdsourcing, and recommendation systems. However, finding an optimal sequence for TT decomposition is not trivial. For a 4-mode tensor, there are 4!=24 possible decomposition sequences and it’s impractical to enumerate all of them to choose the best sequence. Therefore, identifying the best decomposition sequence efficiently and effectively becomes important.</p>

<p style="text-align: start;"><b id="docs-internal-guid-ba0c1647-7fff-bb94-3fe9-e1ce720f9da2"><img src="https://chameleoncloud.org/media/filer_public/c4/8c/c48cf263-8fb3-4ba7-8ed3-203215b1f857/tensor-analysis.png" style="width: 512px; height: 105px;"></b></p>

<h3 style="text-align: start;"><strong>How is your research addressing this challenge?</strong></h3>

<p>In order to identify an optimal decomposition sequence, we developed an algorithm called Guiding the Tensor Train (GTT). GTT leverages various data characteristics, such as the number of modes, length of the individual modes, density, distribution of mutual information, and distribution of entropy, to pick a decomposition sequence.</p>

<h3><strong>How do you structure your experiment on Chameleon?</strong></h3>

<p>We used KVM@TACC for our experiments with the GUI interface and OpenStack APIs. We used the GUI interface for initial setups and package installations. We “saved” our manual setups by taking a snapshot and creating a customized image. Then, this customized image was used for creating multiple instances - each of the instances was responsible for calculating one metric described in the previous question. We also enabled an SFTP port for each instance for data loading and communications. There was a special instance called aggregation instance which was responsible for collecting results from all metric calculating instances and outputting the final result.</p>

<h3><strong>What features of the testbed do you need in order to implement your experiment?</strong></h3>

<p>We rely on the GUI interface which allows us to easily set up our experiment with the desired number of CPUs, size of memory and storage, and third-party packages.</p>

<h3><strong>Why did you choose this direction of research?</strong></h3>

<p>I was interested in social network analysis and recommendation systems before I joined ASU, since I wanted  to know how people interact with each other and how  I could know what people like. These topics motivated me to seek more fundamental knowledge during my PhD. I am focusing more on the hidden semantics in the data, which we try to extract the most significant information from high-dimensional data in the real world and further analyze it to achieve effective decision-making.</p>

<h3><strong>Most powerful piece of advice for students beginning research or finding a new research project?</strong></h3>

<ul>
	<li>Plan ahead even though life is so unpredictable.</li>
	<li>Believe in yourself.</li>
</ul>

<h3><strong>Are there any researchers you admire? Can you describe why?</strong></h3>

<p>I was lucky enough to get supervision from Dr. Candan when I joined ASU, and had the opportunity to dig into the fundamental areas for my research. Dr. Candan is an enthusiastic researcher and willing to devote a lot of time to his students, and always gives insightful advice for our research.  He is really a nice supervisor to teach me  how to do decent research.</p>

<h3><strong>Can you point us to artifacts connected with your experiment that would be of interest to our readership?</strong></h3>

<ul>
	<li>Mao-Lin Li, K. Selçuk Candan, Maria Luisa Sapino. GTT: Leveraging data characteristics for guiding the tensor train decomposition, Information Systems, Volume 108, 2022, ISSN 0306-4379, <a href="https://doi.org/10.1016/j.is.2022.102047">https://doi.org/10.1016/j.is.2022.102047</a>. <a href="https://www.sciencedirect.com/science/article/pii/S0306437922000424">https://www.sciencedirect.com/science/article/pii/S0306437922000424</a></li>
	<li>Youtube video for GTT presentation in SISAP 2020 [Best Paper Candidate]: <a href="https://youtu.be/lxy1rbK3sv8">https://youtu.be/lxy1rbK3sv8</a></li>
</ul>

<h2>Authors</h2>

<p><b id="docs-internal-guid-ba0c1647-7fff-bb94-3fe9-e1ce720f9da2"><img src="https://chameleoncloud.org/media/filer_public/6a/b6/6ab6d758-6499-4509-9546-a45e475527be/mao-lin-li.png" style="width: 387px; height: 418px;"></b></p>

<p><u><strong>Mao-Lin Li</strong></u> is a PhD candidate at the School of Computing and Augmented Intelligence (SCAI) at Arizona State University. His research interests include management and analysis of imprecise, high-dimensional data, with applications including collaborative filtering and predictive analysis.</p>

<p><b id="docs-internal-guid-ba0c1647-7fff-bb94-3fe9-e1ce720f9da2"><img src="https://chameleoncloud.org/media/filer_public/87/ee/87ee4fe6-14bf-4501-b3c7-4ce83f21e528/k-selcuc-candan.png" style="width: 208px; height: 206px;"></b></p>

<p><u><strong>K. Selcuk Candan</strong></u> is a professor of computer science and engineering at Arizona State University (ASU) and the director of ASU’s Center for Assured and Scalable Data Engineering (CASCADE). His primary research interest is in the area of decision making through efficient and trusted management and analysis of non-traditional, heterogeneous, and imprecise (such as multimedia, web, and scientific) data, with applications in human centered complex systems, such as pandemics and disaster preparedness and response, building energy systems, and sustainability.</p>

<p><b id="docs-internal-guid-ba0c1647-7fff-bb94-3fe9-e1ce720f9da2"><img src="https://chameleoncloud.org/media/filer_public/ce/7c/ce7c1fce-56a4-4730-acd8-0e0e0025b6a5/hans-behrens.png" style="width: 391px; height: 391px;"></b></p>

<p><u><strong>Hans Behrens</strong></u> is a PhD Candidate at the School of Computing and Augmented Intelligence (SCAI) at Arizona State University. His research focuses on the intersection of data science, distributed computing, network security, and resilient design.</p>

<p><b id="docs-internal-guid-ba0c1647-7fff-bb94-3fe9-e1ce720f9da2"><img src="https://chameleoncloud.org/media/filer_public/95/27/95278e10-2e97-4f05-b24d-a61338365a7f/maria-luisa-sapino.png" style="width: 396px; height: 512px;"></b></p>

<p><u><strong>Maria Luisa Sapino</strong></u> is a Professor of Computer Science at University of Turin and an Adjunct Professor at Arizona State University. Her major research interests are in the area of Heterogeneous and Multimedia Data management, with strong emphasis on tackling the so called "Big Data challenges", including aspects related to the development of efficient techniques for tensor based big data analysis, and on various aspects related to indexing, classification and querying of (possibly multivariate) time series. Maria Luisa Sapino is active in multiple interdisciplinary projects, in which different domains and disciplines, apparently far from each other (such as Building Energy Consumption Analysis and Study of the Infectious Disease Propagation) can benefit from "smart data oriented" fundamental technological innovations.</p>

<p><b id="docs-internal-guid-ba0c1647-7fff-bb94-3fe9-e1ce720f9da2"><img src="https://chameleoncloud.org/media/filer_public/77/25/77250195-a1ba-4f7a-bd3d-e0e65e61b9e3/fateh-singh.png" style="width: 216px; height: 300px;"></b></p>

<p><u><strong>Fateh Singh</strong></u> is a Computer Science Master’s student and a graduate research assistant at Arizona State University. My interest area is in the field of highly scalable and performant distributed systems. I wish to start a tech startup and carry out philanthropic activities sometime in the future. My hobbies include playing basketball and traveling.   <br>
<strong>LinkedIn:</strong> <a href="https://www.linkedin.com/in/singh-fateh/">https://www.linkedin.com/in/singh-fateh/</a></p>

<p><strong>Acknowledgments:</strong> We like to acknowledge the contributions of numerous other team members, including Javier Redondo Antón, Fahim Tasneema Azad, Xilun Chen, Gerardo Chowell-Puente, Ashish Gadkari, Yash Garg, Xinsheng Li, Sicong Liu, Giulia Pedrielli, Silvestro Roberto Poccia, Md Shadab, Dalton Turner, Magesh Vijayakumaren.</p>