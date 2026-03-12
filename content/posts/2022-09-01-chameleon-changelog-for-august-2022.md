---
abstract: "<p>We hope everybody has had a great vacation \u2013 \_welcome back, we\
  \ are glad to see you again! In this month\u2019s changelog, we bring you groundbreaking\
  \ composable Liqid hardware at CHI@TACC, updated categorization for projects, appliance\
  \ news, and Xena upgrade at CHI@NU. Additionally, we have a reminder for a scheduled\
  \ outage of our authentication service, and important notes on using our A100 hardware.<br>\n\
  \_</p>"
authors:
- Mark Powers
categories:
- Chameleon Changelog
date: '2022-09-01 22:47:56+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/65/24/6524b800-9c28-4516-8059-eee2bf91d6ee/liqid1.png
related_posts: []
slug: chameleon-changelog-for-august-2022
subtitle: ''
title: Chameleon Changelog for August 2022
---

<p dir="ltr" style="text-align: center;"> </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-2f269cba-7fff-84d7-3817-03b6c484e649"><img height="377" src="https://lh6.googleusercontent.com/SKBhAGtg_c7RUBd9fR5i-0BhtJl86b_uMHlXc32lbZTUFR6Rnf_GgTXfx0WzM9ToIPsrY4KFQY4g3lGb-19TvdxWuN4rIwtkHzgBclyVWo4IW5G0DDSTjEGZC0-9vOpQF-kKufuIcxqpJuKQt4ZTig" width="521"></b></p>

<p>Dear Chameleon users,</p>

<p>Welcome back – we hope everybody has had a great summer and is coming back with fresh energy to tackle important research problems – we are so looking forward to see what cool discoveries you make this year! Don’t forget to share them with us – your tests and triumphs is what makes us roll out of bed every day – if you have an exciting experiment or result you’d like to share via <a href="https://chameleoncloud.org/blog/category/user-experiments/">our blog</a> please <a href="https://chameleoncloud.org/user/help/ticket/new/">contact us</a>, we will be happy to help you share your experiences with others. </p>

<p>A quick reminder to all that we have a long <a href="https://chameleoncloud.org/user/outages/scheduled-downtime-for-authentication-systems/">planned authentication outage scheduled</a> on September 6 at 11:00 AM CT to deploy necessary upgrades. We estimate that the outage will take only an hour but during that time you won’t be able to log into Chameleon – though you will be able to work on deployed instances – please, plan accordingly and renew any leases ahead of time. On a more cheerful note, we also bring you the following: </p>

<p><strong>Composable Hardware at CHI@TACC!</strong> The big news this month is the <a href="https://www.liqid.com/">composable Liqid hardware</a>. What makes this composable hardware special is that it disaggregates memory, GPU, and storage, making it possible to detach and attach these resources between Liqid nodes via software. At this time, Liqid nodes are available as a set of static configurations:</p>

<table>
	<colgroup>
		<col>
		<col>
		<col>
		<col>
	</colgroup>
	<tbody>
		<tr>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">Machine</b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25"># CPU</b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25"># GPU</b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25"># NVMe SSD</b></p>
			</td>
		</tr>
		<tr>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">liqid01</b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">1</b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">2</b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">2</b></p>
			</td>
		</tr>
		<tr>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">liqid02</b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">1</b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">2</b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">2</b></p>
			</td>
		</tr>
		<tr>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">liqid03</b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">1</b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">1</b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">3</b></p>
			</td>
		</tr>
		<tr>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">liqid04</b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">1</b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">1</b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">3</b></p>
			</td>
		</tr>
		<tr>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">liqid05</b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">1</b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">1</b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">2</b></p>
			</td>
		</tr>
		<tr>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">liqid06</b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">1</b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">1</b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">2</b></p>
			</td>
		</tr>
		<tr>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">liqid07</b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">1</b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">1</b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">1</b></p>
			</td>
		</tr>
		<tr>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">liqid08</b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">1</b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">1</b></p>
			</td>
			<td>
			<p dir="ltr"><b id="docs-internal-guid-e5c50c26-7fff-dfbe-8b1c-7d5c0da92a25">1</b></p>
			</td>
		</tr>
	</tbody>
</table>

<p>You can reference these names with the CPU information on our <a href="https://chameleoncloud.org/hardware/">hardware discovery page</a> under the node number “compute_liqid.” Due to the reconfigurable nature of this hardware, we are still working through some issues getting it to work correctly on the hardware page, but for reference, the NVMe SSDs are 3841GB SAMSUNG MZ1LB3T8HMLA-00007 and the GPUs are 40GB A100s. If you wish to reconfigure Liqid nodes to explore different configurations, please reserve the nodes, and <a href="https://chameleoncloud.org/user/help/">submit a help ticket</a> for us to do the reconfiguration for you as it is not yet supported programmatically. Another way you can experiment with disaggregated hardware on the testbed is with the Haswell InfiniBand nodes at TACC.<br>
<br>
<strong>New Project Categorization</strong>. We are always trying to better understand what our users are working on so that we may make better prioritization and purchasing decisions. To help us develop that understanding, when you make a new project you will be asked to select a project “tag” from a list of Computer Science research fields. You can also update the tag for your existing projects on <a href="https://chameleoncloud.org/user/projects/">your project’s page</a>. If you don’t do this by 09/16 we will propose a tag for you, but if you don’t like it, you are free to update it yourself, or contact us at help@chameleoncloud.org.</p>

<p><strong>Appliance news</strong>. We have several changes on the appliance front this month. First, we have a <a href="https://www.chameleoncloud.org/experiment/share/6a30d3fb-8c8a-49b1-a415-cd9c7fc0a6e3?">JupyterHub Trovi artifact</a> that allows you to create your own standalone JupyterHub on  Chameleon resources. While we also used to have a JupyterHub appliance in Appliance Catalog, the users voted with their feet and we are now officially stopping support for the appliance in favor of the Trovi artifact. Second, if you ever had trouble ssh-ing to Ubuntu  instances with two networks attached, you will be glad to know that we’ve fixed this issue and released a new version of Chameleon-supported Ubuntu images, including ARM and CUDA images. In addition, we no longer support Ubuntu16.04 and CentOS8 images as these systems are no longer supported; please, use Ubuntu18.04, Ubuntu20.04, and CentOS8-stream instead. Last but not least, Chameleon has started using customized <a href="https://docs.openstack.org/ironic/latest/admin/drivers/ipa.html">Ironic Python Agent</a> images to better serve all node types of both core sites and associate sites. Please see <a href="https://chameleoncloud.gitbook.io/chi-in-a-box/operations/chameleon-tools/image-tools#ipa-image-tester">CHI-in-a-Box documentation</a> for details. </p>

<p><strong>CHI@NU Xena upgrade</strong>. The <a href="https://www.chameleoncloud.org/blog/2021/02/19/setting-associate-site-interview-northwestern-university/">CHI@NU</a> site has been upgraded to a newer version of OpenStack, Xena. CHI@NU has nodes with Mellanox ConnectX-5 100GE cards, making it the ideal site for 100G networking experiments.</p>

<p><strong>Heads up on A100 hardware problem</strong>. Last month we announced nodes with <a href="https://chameleoncloud.org/hardware/">multiple A100 GPUs</a> at CHI@UC. We are happy to see that our users are excited to use this new hardware, however we’ve discovered that it comes with a problem: when using it with Ubuntu 20.04, due to an operating system issue, not all the GPUs will appear. We are actively pursuing a resolution of this problem with Dell but for the time being we’ve found a workaround for you in <a href="https://www.dell.com/community/PowerEdge-Hardware-General/NVIDIA-A100-in-Dell-Poweredge-R750-with-Ubuntu-20-04/td-p/8136431">this support article</a>. Alternatively, you may use a CentOS CUDA image which does not have this problem.</p>

<p>Enjoy the last days of summer – though don’t forget to enjoy the new hardware too! <br>
 </p>