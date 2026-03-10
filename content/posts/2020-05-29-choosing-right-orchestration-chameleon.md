---
abstract: "<p>As with many projects and programming languages, there is more than\
  \ one way to achieve a task when orchestrating Chameleon computing and network resources.\
  \ As a result, experimenters may feel overwhelmed and choose to stick to the orchestration\
  \ method they are familiar with even when another method might be more effective\
  \ for the task in hand.\_</p>"
authors:
- Mauricio Tavares
categories:
- Tips and Tricks
date: '2020-05-29 13:56:00+00:00'
featured: false
hide_image: true
image: ''
slug: choosing-right-orchestration-chameleon
subtitle: ''
title: Choosing the right orchestration in Chameleon
---

<p style="text-align: right;"><b><img src="https://lh3.googleusercontent.com/2V5myR-iHlFUfIozinaGx48fdGSPhIunUyLKZidkE9Pt7B4PbDU3MOxTE4J4lj9lFcWMsWpj5Vd7VO_fc5qxMOiJEwO8mklXo22LRLP0tmdmPLFIyNqIVFW_hnqeN9bO3q-YJ73y" height="20"></b></p>

<p style="text-align: right;" dir="ltr"><b>A frog in a well cannot conceive of the ocean.</b></p>

<p style="text-align: right;" dir="ltr"><b>Zhuangzi</b></p>

<p> </p>

<p dir="ltr">As with many projects and programming languages, there is more than one way to achieve a task when orchestrating Chameleon computing and network resources. As a result, experimenters may feel overwhelmed and choose to stick to the orchestration method they are familiar with even when another method might be more effective for the task in hand. </p>

<p dir="ltr">In this article, we will take a quick look at the orchestration methods most commonly used in Chameleon and then we will compare them in two ways:</p>

<ul>
	<li dir="ltr">
	<p dir="ltr"><b>Interactiveness:</b> how easy to change its parameters. If you control each step separately, you can adjust the lab to deal with experiment variations and even unexpected issues.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr"><b>Automation:</b> how little user intervention is required for it to run. The more automated it is, the faster you can set the experiment up. An added bonus is you minimize the amount of user-induced mistakes.</p>
	</li>
</ul>

<p dir="ltr"> </p>

<h3 dir="ltr">The Players</h3>

<p dir="ltr">Within this article, four different methods for orchestration will be explored: </p>

<ol dir="ltr">
	<li><a href="#webinterface">Web Interface</a></li>
	<li><a href="#vanillajupyter">"Vanilla" Jupyter</a></li>
	<li><a href="#jupyteransible">Jupyter + Ansible</a></li>
	<li><a href="#heattemplate">Heat Templates</a></li>
</ol>

<p dir="ltr">There are pros and cons for each method, depending on your goals. Continue reading to better understand the different values and how to narrow down which will work best for your experience.</p>

<p dir="ltr"> </p>

<h4 dir="ltr"><a name="webinterface">#1 Web Interface</a></h4>

<p dir="ltr">Web Interface is the method users encounter by default when logging into <a href="https://www.chameleoncloud.org/">https://www.chameleoncloud.org/</a>, watching the <a href="https://www.chameleoncloud.org/news/introduction-chameleon-april-2020">Intro to Chameleon</a> webinar, and reading the <a href="https://chameleoncloud.readthedocs.io/en/latest/getting-started/index.html">getting started documentation</a>. From this web interface, you can visually explore the available and used resources, examine the network(s) associated with the experiment and how they relate with themselves and the servers (a.k.a. instances), add (or remove) public floating IPs to instances, and restart and have console access to these instances.</p>

<p style="text-align: center;" dir="ltr"><img src="https://www.chameleoncloud.org/media/filer_public/99/9e/999e4548-8730-4772-8a9c-9c3d84bb7e7e/image1.png" style="width: 533px; height: 268px;"></p>

<p dir="ltr"><b>Pros</b></p>

<ul>
	<li>Easiest to learn.</li>
	<li>No programming or scripting skills required. Identifying which OS images are available, visualizing which resources our virtual lab uses, or selecting a public key is but a mouse click away.</li>
	<li>Can see how each step is doing in real time.</li>
	<li>Great for a quick test without having to write a bunch of lines of code first. </li>
	<li>Most interactive. It can modify the lab infrastructure on the fly in ways that are not available to other methods. Specifically, it allows us to have console access to the instances we created.<img src="https://www.chameleoncloud.org/media/filer_public/4e/83/4e8323cc-cff4-4857-979b-d793d34fb697/image2.png" style="width: 477px; height: 328px;"></li>
	<li>Having console access allows investigating network issues from within the instance.</li>
</ul>

<p dir="ltr"><b>Cons</b></p>

<ul>
	<li>Slow.</li>
	<li>Labor-intensive.</li>
	<li>Manual, least automated.</li>
	<li>Easy to miss one step.</li>
</ul>

<p> </p>

<h4 dir="ltr"><a name="vanillajupyter">#2 “Vanilla” Jupyter </a></h4>

<p dir="ltr">A Jupyter Notebook is a great way to combine documentation and executable code in a single entity. Learn more about this method by watching  the<a href="https://youtu.be/I9VyL9A0PLk"> Orchestration with Jupyter Notebooks  webinar</a> and reviewing the online <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/jupyter.html">documentation</a>.</p>

<p style="text-align: center;" dir="ltr"><img src="https://www.chameleoncloud.org/media/filer_public/18/84/1884e339-5a0d-44cb-9086-68e681399bfd/image3.png" style="width: 560px; height: 462px;"></p>

<p dir="ltr"><b>Pros</b></p>

<ul>
	<li>Reproducible. Repeating  the entire experiment is just a matter of restarting the notebook.</li>
	<li>Can see the output inside the Jupyter Notebook be it graphics or text.</li>
	<li>Great as Textbook/lab manual.
	<ul>
		<li>Diagrams.</li>
		<li>Interactive: If an user wants to make a change to run a what-if-scenario (great for those who learn better by changing parameters to see the outcome), editing the right field and running it again is all that is required.</li>
		<li>Text with code you can run! Notebooks show which step was executed in which order, and with supporting documentation including links right with the step being executed.</li>
		<li>Users/Students can follow each step and see the outcome without worrying about typos.</li>
	</ul>
	</li>
	<li>Linking to other notebooks will launch them.</li>
	<li>Once you have a good notebook, you can build a new one by duplicating it and then editing. Or copying the good bits from other notebooks. You do not need to reinvent the wheel.</li>
	<li>What you tell the instances to do is limited to your ability to describe it using the command line. For instance, why not connect from your Notebook to a node and then tell it to check out a git repo and then build that package? </li>
</ul>

<p dir="ltr"><b>Cons</b></p>

<ul>
	<li>Some programming or scripting skills required. Youtalk to openstack with scripts written in Bash to orchestrate the networks and instances, but can also use Python. Therefore, you need to know how to talk to openstack from the command line in either of those scripting languages.</li>
	<li>Unless you also write a script to verify if required intermediate steps are successfully executed before continuing, you may end up in a broken state without knowing which step caused the problem. You would then need to manually issue the command line to delete enough resources to get to a state you can continue. Notebooks students are supposed to run (class exercises and labs) should be able to decide when to continue and when to safely abort.</li>
</ul>

<p> </p>

<h4 dir="ltr"><a name="jupyteransible">#3 Jupyter + Ansible</a></h4>

<p dir="ltr">Use Jupyter Notebook to spool up the instances with only the OS. Install ansible (also applicable to puppet/salt) and its playbooks (in the following image we are getting them from a git repo), and then run the playbooks.</p>

<p style="text-align: center;" dir="ltr"><img src="https://www.chameleoncloud.org/media/filer_public/f8/cd/f8cd2334-a973-4296-b4f3-aaf77f9b6880/image4.png" style="width: 624px; height: 308px;"></p>

<p dir="ltr"><b>Pros</b></p>

<ul>
	<li>Can automate many steps in the experiment setup that needs to be documented. In fact, the ansible playbook can be part of the documentation.</li>
	<li>Steps -- detecting the operating system, updating a configuration file, installing packages, starting services -- that would need to be spelled out (and are slightly different for distinct Linux distributions) in the normal Jupyter Notebooks are well-defined in Ansible; no need to write functions to perform those tasks.</li>
	<li>Ansible playbooks can be constructed to run on different platforms such as baremetal instance, a virtual computer (say, KVM or VirtualBox), or kubernetes. Clever coding can make it adjust itself to work in the environment. Case in point, in our Jupiter + Ansible notebook, the two servers running the experiment are running different Linux distributions -- Ubuntu and CentOS -- and the playbook not only adapts to that but uses that to make decisions. That also means playbook can be developed and tested somewhere else and then run on Chameleon… or the other way around. Or, if experiment uses Chameleon and other resources which are linked together, they can be configured using one single playbook.</li>
	<li>To change the experiment parameters on specific hosts one needs only to edit the configuration file for that host.</li>
	<li>If you love Python, you will be happy here as Ansible is python based.</li>
</ul>

<p dir="ltr"><b>Cons</b></p>

<ul>
	<li>Much more programmatically intensive. If you do not know how to program in Python, you may struggle here (Ansible is python based).</li>
	<li>One of the most time consuming steps -- creating the instances -- is still being done explicitly in the Jupyter Notebook (you have to run every single step in order).</li>
</ul>

<p> </p>

<h4 dir="ltr"><a name="heattemplate">#4 Heat Templates</a></h4>

<p dir="ltr">This is how Chameleon generates its complex appliances. Customize a few parameters, launch it, and then come back when the entire lab is set up; no user interaction from starting until it is complete. As shown in its <a href="https://youtu.be/YnrGNehNBcY">webinar</a>, we can execute it from the command line (which means it can be done from within Jupyter Notebooks) or Web GUI.</p>

<p style="text-align: center;" dir="ltr"><img src="https://www.chameleoncloud.org/media/filer_public/c0/dc/c0dcd14b-f2cc-43c5-a208-1b6fe2d01f7f/image5.png" style="width: 624px; height: 283px;"></p>

<p dir="ltr"><b>Pros</b></p>

<ul>
	<li>You no longer need to interactively make reservations and allocate resources. The heat template can do that for you and then configure them, even calling, say, ansible playbooks as needed. </li>
	<li>Can create a somewhat generic one so you can select network, ssh keys, OS images and so on before unleashing it.</li>
	<li>Destroying the entire experiment is done with one single command. Chameleon then works the heat template backwards.</li>
	<li>Of the 4 orchestration methods presented, it is the most automated.</li>
	<li>Can run scripts during the installation that checks repos out, compiles code, moves files and so on. If that becomes too long, just have it use ansible.</li>
</ul>

<p dir="ltr"><b>Cons</b></p>

<ul>
	<li>Least Interactive of the list.</li>
	<li>Heat templates can become complex rather quickly and are a new “language” to master.</li>
	<li>Cannot easily reconfigure a server. it would require recreating the instance. The work around is for the heat template install and run ansible so you can push updates later on.</li>
</ul>

<p> </p>

<h3 dir="ltr">Comparing Methods</h3>

<p dir="ltr">The following table shows how the orchestration systems mentioned here are distributed in an Interactiveness vs Automation matrix. As expected, while heat templates are very automated, they are not very interactive. The web GUI is very interactive but not automated. The other two techniques are somewhere in the middle.</p>

<p style="text-align: center;" dir="ltr"><a href="https://www.draw.io/?page-id=bvfYJYZktL-f1EnLbFGk&amp;scale=auto#G1Eu9fVka5HyUsFRLvVRzp_KeB1Nei70wq"><img src="https://www.chameleoncloud.org/media/filer_public/69/66/6966840e-c636-4ae4-923d-c391d5dd76b1/image6.png" style="width: 408px; height: 332px;"></a></p>

<p dir="ltr"> </p>

<p dir="ltr">In the above graph, Jupyter Notebook + Ansible is a bit more interactive and distinctively more automated than plain Jupyter. That is to emphasize the effect of adding Ansible to the equation - it cuts down the number of steps required to accomplish a task and simplifies running them in complex/mixed environments. If a given set of tasks defined in ansible have to be rerun across all the instances, we just need to go to the notebook step where the variables are defined, rerun it with updated variables, and then rerun the step that executes the ansible playbook. </p>

<p dir="ltr"> </p>

<h3 dir="ltr">Choosing a Method</h3>

<p dir="ltr">Which one should you pick? It depends on where in the interactiveness vs automation graph you want to be. </p>

<ul>
	<li>If introducing someone to Chameleon, the Web GUI is the best method. </li>
	<li dir="ltr">
	<p dir="ltr">If creating lab assignments for students, the Jupyter Notebooks by themselves or with Ansible provide a balance of automation while providing real time/interactive training.</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">If setting up a complex experiment in a repetitive and automated fashion, heat templates would be the best choices.</p>
	</li>
</ul>

<p dir="ltr">With that said, once you have enough experience with those orchestration methods, the next step is mixing and matching them: creating a Jupyter notebook (keeping notes in a single location) that runs a fully automated orchestration, like heat template, to do the basic building of the lab (instances, networks, floating IPs, etc). Then it installs and runs something like ansible to deploy the required packages and files that will perform the experiments. But, that will be for another article...</p>