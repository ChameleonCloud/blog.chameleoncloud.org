---
abstract: "<p>The <code>history</code>\_command available in Bash is a useful tool,\
  \ and you probably use it frequently in your daily routine jobs to check the history\
  \ of the commands executed by the user. In this blog, we will see how an equivalent\
  \ tool in Chameleon can help you check the experiment setup events you performed\
  \ on Chameleon.\_</p>"
authors:
- Zhuo Zhen
categories:
- Tips and Tricks
date: '2019-12-23 19:52:59+00:00'
featured: false
hide_image: true
image: ''
related_posts: []
slug: implementing-chameleons-history-command
subtitle: ''
title: "The \u201CHistory Command\u201D of Chameleon"
---

<p dir="ltr">The <code>history</code> command available in Bash is a useful tool, and you probably use it frequently in your daily routine jobs to check the history of the commands executed by the user. In this blog, we will see how an equivalent tool in Chameleon can help you check the experiment setup events you performed on Chameleon. </p>

<h4 dir="ltr">Experiment Précis</h4>

<p dir="ltr">Chameleon helps you record your experiment setup events performed on the testbed, such as creating leases, creating instances, and setting up networks. Like the <code>history</code> command, you can request your experiment records from Chameleon using your Chameleon credentials and the <code>cep client</code> tool. A report on those experiment records is known as the Experiment Précis. But there is more than that. Chameleon Experiment Précis also includes the detailed information of the hardware you use for your experiment, as well as the quality metrics collected from our <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/metrics.html">monitoring service</a>.</p>

<h4 dir="ltr">To Avoid the “Command Not Found” Error</h4>

<p dir="ltr">You might never see “command not found” when running the <code>history</code> command on Linux systems because most of the Linux distributions have <code>bash</code> installed. To be able to retrieve your experiment setup history from Chameleon, you need to install the <code>cep client</code> tool by running <code>pip install cepclient</code>, and to set up the <code>cep client</code> by sourcing <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/cli.html#the-openstack-rc-script">the OpenStack RC file</a>. </p>

<h4 dir="ltr">Print History</h4>

<div dir="ltr" style="background: #eeeeee; border: 1px solid #cccccc; padding: 5px 10px;"><samp>$ history</samp></div>

<p><br>
Simply running <code>history</code> will print out the bash commands executed by the current user. To print out the experiment précis, you can use the following command:</p>

<div dir="ltr" style="background: #eeeeee; border: 1px solid #cccccc; padding: 5px 10px;"><samp>$ cep print &lt;ep_id or ep_name&gt;</samp></div>

<p dir="ltr"><br>
To find the <code>ep_id</code> and <code>ep_name</code>, which are the ID and name of the experiment précis, run </p>

<div style="background: #eeeeee; border: 1px solid #cccccc; padding: 5px 10px;"><samp>$ cep list</samp></div>

<p dir="ltr"><br>
Initially, Chameleon sets the name of an experiment précis the same as its ID. However, you can rename it for the convenience of future retrieving. To rename an experiment précis, run the following command:</p>

<div dir="ltr" style="background: #eeeeee; border: 1px solid #cccccc; padding: 5px 10px;"><samp>$ cep rename --name &lt;new_name&gt; &lt;ep_id or ep_name&gt;</samp></div>

<h4 dir="ltr"> </h4>

<h4 dir="ltr">A Lot More You Can Do</h4>

<p dir="ltr">We know that there’s a lot more you can do with the <code>history</code> command, such as filtering commands, excluding commands, setting the number of commands to print out, etc. With the <code>cep client</code>, you can do the similar as well.  </p>

<h5 dir="ltr">Pagination</h5>

<p dir="ltr">The <code>history</code> command allows you to print the most recent 3 commands by running <code>history 3</code>. You can also tell <code>history</code> how many commands to store and how many commands to print by setting “HISTFILESIZE” and “HISTSIZE” environment variables. The <code>cep client</code> achieves the same goal with pagination parameters, including the page size and the page number. For example, if you’d like to show the first 3 events of your experiment, simply run the following command:</p>

<div dir="ltr" style="background: #eeeeee; border: 1px solid #cccccc; padding: 5px 10px;"><samp>$ cep print &lt;ep_id or ep_name&gt; --event-page-size 3 --event-page-number 1</samp></div>

<p dir="ltr"> </p>

<h5 dir="ltr">Filter</h5>

<p dir="ltr">By piping <code>history</code> with <code>history | grep systemctl</code>, you can filter the commands that contains “systemctl”. You can also ignore commands by setting up the “HISTIGNORE” environment variable. The <code>cep client</code> also provide filter parameters, so you can focus on the information you care about. For example, you can exclude quality metrics from your experiment précis by adding <code>--exclude-metric</code> to the <code>cep print</code> command. The <code>cep client</code> also allows you to filter events by OpenStack services and time period. <br>
 </p>

<h4 dir="ltr">And More To Come</h4>

<p dir="ltr">With the <code>history</code> command printout, you can quickly repeat any of the line by copying and pasting or by using a special syntax (!). Using the following as an example.</p>

<div style="background: #eeeeee; border: 1px solid #cccccc; padding: 5px 10px;"><samp>[user@centos7 ~]$ history 3<br>
16  passwd<br>
17  getenforce<br>
18  history 3</samp></div>

<p dir="ltr"><br>
Running <code>!16</code> will repeat command <code>passwd</code>. Running <code>!-2</code> will repeat <code>getenforce</code>. Running <code>!!</code> means running the most recent command, in our case,  <code>history 3</code>.</p>

<p><br>
With your experiment précis, you can create a <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/complex.html">complex appliance</a> or a <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/jupyter.html">Jupyter Notebook</a>, which allows you to easily repeat your experiment setup steps on Chameleon. In the near future, we will develop a Chameleon “!” tool to help you easily convert your experiment précis to a shareable artifact.<br>
 </p>

<h4 dir="ltr">At the End</h4>

<p dir="ltr">For any discipline, the abilities of keeping records of, sharing and repeating experiments are critical. To reduce the burden of the researchers when preparing experiments on Chameleon, we developed the Chameleon Experiment Précis framework to record testbed events, hardware information, and quality metrics for you and to allow you to retrieve the records via the <code>cep client</code> tool. From there, you can create your experiment artifact, such as <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/complex.html">complex appliance</a> or <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/jupyter.html">Jupyter Notebook</a>, from your experiment précis and share it on the Chameleon <a href="https://www.chameleoncloud.org/appliances/">Appliance Catalog</a> or the <a href="https://www.chameleoncloud.org/experiment/share/">Sharing Portal</a>. </p>

<p><br>
In this blog, we showed you how to generate an experiment précis and what you can do with it. If you are interested, please read our <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/ep.html">documentation</a> for more details. You can leave a comment about this framework or <a href="https://www.chameleoncloud.org/user/help/">submit a ticket</a> to us if you have any questions.</p>