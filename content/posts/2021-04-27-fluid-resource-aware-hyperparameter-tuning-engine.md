---
abstract: "<p dir=\"ltr\">This blog feature\_explores 4th year University of Michigan\
  \ PhD student Peifeng Yu\u2019s research on hyperparameter tuning, <a href=\"https://www.mosharaf.com/wp-content/uploads/fluid-mlsys21.pdf\"\
  >presented earlier this month at MLSys21</a>. Learn more about Yu, the hyperparameter\
  \ tuning engine, and how it can improve your deep learning model training process.</p>"
authors:
- Peifeng Yu
categories:
- User Experiments
date: '2021-04-27 02:59:36+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/13/63/13638c3f-c6c5-430f-b7ae-d7281f1769df/screen_shot_2021-04-26_at_75843_pm.png
slug: fluid-resource-aware-hyperparameter-tuning-engine
subtitle: ''
title: 'Fluid: Resource-Aware Hyperparameter Tuning Engine'
---

<p dir="ltr">This blog feature explores 4th year University of Michigan PhD student Peifeng Yu’s research on hyperparameter tuning, <a href="https://www.mosharaf.com/wp-content/uploads/fluid-mlsys21.pdf">presented earlier this month at MLSys21</a>. Learn more about Yu, the hyperparameter tuning engine, and how it can improve your deep learning model training process.</p>

<p> </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-85a94d65-7fff-c349-6dcc-9986919db200"><img height="415" src="https://lh5.googleusercontent.com/bJIZLDMO5tu_KcYmpjYDnH6ms9FW91nmSfz6dxV0N0icMe9K6QuIviaZTa8Rk1weIjvW6H7rB1wgAbMpMkPLyidE3iIY_jb21Zl7JLGpixfn5YTfNT8Omd6LtutG3xtlSDPFGqq2" width="624"></b></p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-85a94d65-7fff-c349-6dcc-9986919db200">On the current research:</b></p>

<p dir="ltr">Hyperparameters (HP) are parameters that govern the entire deep learning model training process, e.g. the number of layers, learning rates, or other parameters controlling the model architecture and/or training process. The effectiveness of deep learning models is highly sensitive to hyperparameters. For example, if the learning rate is too large, the model may converge too quickly to a suboptimal solution, whereas a learning rate that is too small can cause the process to get stuck.</p>

<p dir="ltr">Hyperparameter tuning is an optimization technique whereby we look for the best set of hyperparameters that are likely to produce the highest validation accuracy. This can be slow, as one tuning job contains a large group of training trials, each with its own hyperparameter configuration. Each of these configurations is evaluated by training the model.  Distributed computation is commonly used to speed up the tuning process.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-85a94d65-7fff-c349-6dcc-9986919db200"><img height="255" src="https://lh5.googleusercontent.com/W4-_f7Lu8I-RpRoHEifZp2VgLBn_veYGxTGTRZID7voYrcpAkOpNgRW9WbeNc2VLKSx98UQ9C7t5fgPw4PHlrmJOAH5-DQkPqtNd9ABkVE7ER2ZxebnNwu8vPR_fOSaAbtzFHL0A" width="624"></b></p>

<p dir="ltr">Hyperparameter tuning algorithms today usually consist of two components: config generation and evaluation strategies. The algorithm directly interacts with the cluster and the execution logic is implicitly defined by the evaluation strategy.</p>

<p dir="ltr">During a tuning job:</p>

<ol>
	<li dir="ltr">
	<p dir="ltr">A<b> </b>set of hyperparameter configurations are generated</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Each configuration, submitted to the cluster as a training trial, are evaluated</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">The cluster reports back the results</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">The generation process is updated with the results to guide the future config generation</p>
	</li>
</ol>

<p> </p>

<p dir="ltr">This method creates unnecessary slowdowns in the tuning process. It lacks complementary execution engines to efficiently leverage distributed computation in the cluster during the evaluation step. While there are recent attempts in individual HP tuning algorithms to better utilize resources, they have their own drawbacks and can not be easily generalized to the whole ecosystem.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-85a94d65-7fff-c349-6dcc-9986919db200">On approaching the research challenge:</b></p>

<p dir="ltr">The trial execution strategy greatly affects the resource efficiency in hyperparameter tuning solutions. Current strategies can result in suboptimal utilization or can be tricky to parallelize on distributed hardware.</p>

<p dir="ltr">We therefore propose to decouple the execution strategy from hyperparameter tuning algorithms into a separate execution engine. This has the following advantages: </p>

<ol>
	<li dir="ltr">
	<p dir="ltr">By separating the concern between tuning algorithms and execution engines, we allow both components to  evolve independently</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Resource usage can be optimized, which results in faster tuning speed for any tuning algorithms, benefiting a wider range of applications.</p>
	</li>
</ol>

<p> </p>

<p dir="ltr">Our proposed execution engine, Fluid, is algorithm- and resource-aware. It coordinates between the cluster and hyperparameter tuning algorithms. By abstracting hyperparameter tuning jobs as a sequence of TrialGroups, Fluid provides a generic high-level interface for hyperparameter tuning algorithms to express their execution requests for training trials. Fluid then automatically schedules the trials considering both the current workload and available resources to improve utilization and speed up the tuning process.</p>

<p> </p>

<p dir="ltr">Fluid models the problem as a strip packing problem where each rectangle has different shapes and the goal is to minimize the height of the strip. The intuition behind Fluid is to grant more resources to more demanding or promising configurations, such as those with larger training budgets, higher resource requirements, or higher priority. By combining techniques like elastic training and GPU multiplexing, Fluid is able to change the trial size including scaling out and in a trial across many GPUs and within one respectively. We also propose heuristics to solve the strip packing problem efficiently and prove that their performance is bounded within 2x of the optimal.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-85a94d65-7fff-c349-6dcc-9986919db200"><img height="251" src="https://lh6.googleusercontent.com/NiiAnHGcfH1IhORRFC93zOdYseJn2HILNvHOo7jnDvOjkRPv_dc8r-ndPdG2SySBKo293Sdp1G4XbsDB_l1ijDhS_P-YCv7BqpI7D0mywN0n_4BjlEPI-d50srOhRzych1qcBy7S" width="624"></b></p>

<p dir="ltr">With Fluid, the tuning algorithm submits TrialGroup according to its evaluation strategy and gets feedback back anytime they are available. Fluid itself manages the job execution and handles resource changing events from the cluster.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-85a94d65-7fff-c349-6dcc-9986919db200">On testbed needs: </b></p>

<p dir="ltr">GPU clusters of decent size (e.g. at least 4-8 nodes with multiple GPUs on each node to provide some room for the cluster scheduler to act on) are necessary for evaluating both the baseline and our system. Thankfully, Chameleon has various GPU nodes for us to carry out our experiments.</p>

<p dir="ltr">If Chameleon was not available (which actually happened a few times before due to limited number of GPU nodes), we would have to find other providers for GPU clusters, which isn’t easy or may incur large costs.</p>

<p dir="ltr">On one hand, VM-based solutions like AWS may potentially impact the experiment, as we care about performance measurement and there is no interference with bare metal access provided by Chameleon. On the other hand, it isn’t easy to customize the OS and drivers to the exact software environment we want in traditional HPC clusters, which often do not grant users full control over the system.<br>
 </p>

<p dir="ltr"><b id="docs-internal-guid-85a94d65-7fff-c349-6dcc-9986919db200">On himself: </b></p>

<p dir="ltr">I’m a 4th year PhD student at the University of Michigan, working with <a href="https://www.mosharaf.com/">Prof. Mosharaf Chowdhury</a> on interesting problems in systems and networking. I’m especially excited about improving the system infrastructure for deep learning applications. I hope to build software with practical usage and thus I’d prefer to work in the industry after graduation. </p>

<p dir="ltr">During quarantine and working from home, I spend most of my free time on open source projects and playing video games. </p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-85a94d65-7fff-c349-6dcc-9986919db200">On staying motivated through a long research project: </b></p>

<p dir="ltr">Actually I don’t. I think it’s completely normal to have negative thoughts now and then, especially when there are challenges seemingly unsolvable. But they will be overcomed eventually, just as a matter of how. For me, it’s important to have detailed plans beforehand, so during the depressed time, I just stick to the plan without thinking, basically trusting myself from the earlier. By definition there won’t be negative thoughts if you don’t think about it :) Things will eventually work out and I can find the motivation again afterwards.</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-85a94d65-7fff-c349-6dcc-9986919db200">On choosing his research direction:</b> </p>

<p dir="ltr">I enjoy coding and building tools. So systems research feels like a natural fit for me.</p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-85a94d65-7fff-c349-6dcc-9986919db200">On his most powerful piece of advice: </b></p>

<p dir="ltr">Try to be organized about your code. While we all write “research quality” code all the time, taking the effort to improve the engineering side of things can help your code have a real impact in the world.</p>

<p dir="ltr"> </p>

<p dir="ltr"><b id="docs-internal-guid-add448e5-7fff-26c8-41ee-25ce8319744f">On related artifacts that will be available for interested users to interact with:</b> </p>

<p dir="ltr">Our paper <a href="https://www.mosharaf.com/wp-content/uploads/fluid-mlsys21.pdf">“Fluid: Resource-Aware Hyperparameter Tuning Engine”</a> is published as part of MLSys21. Related materials (slides, poster, videos) can be found on our <a href="https://symbioticlab.org/publications/#/venue:MLSys">group website</a>. Fluid itself is open sourced on our <a href="https://github.com/SymbioticLab/fluid">group Github</a>, and can be used to reproduce experiment results. We will also update the repo to include detailed instructions about the experiments soon.</p>