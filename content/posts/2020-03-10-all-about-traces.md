---
abstract: "<p>The workload traces from data centers facilitate research on the design\
  \ of computer systems, job scheduling, and resource management.\_ Researchers can\
  \ analyze the traces and replicate real-life workloads for their experiments. In\
  \ this blog, we will briefly review some major released traces and introduce the\
  \ benefits of using a Chameleon-developed trace generator for easily creating traces\
  \ from cloud providers who use OpenStack.\_</p>"
authors:
- Zhuo Zhen
categories:
- Tips and Tricks
date: '2020-03-10 04:10:16+00:00'
featured: false
hide_image: true
image: ''
slug: all-about-traces
subtitle: ''
title: All About Traces
---

<p>The characterization of workloads in data centers is critical for resource management systems. To assist resource management studies, several traces and cluster data logs were released. The following table lists several major workloads that have been released and available today.</p>

<p> </p>

<table align="center" border="1">
	<colgroup>
		<col width="94">
		<col width="152">
		<col width="225">
		<col width="71">
		<col width="81">
	</colgroup>
	<tbody>
		<tr>
			<td>
			<p dir="ltr" style="text-align: center;">Source Type</p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">Name</p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">Owner Organization</p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">Latest Version</p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">First Release Year</p>
			</td>
		</tr>
		<tr>
			<td rowspan="3">
			<p dir="ltr" style="text-align: center;">Commercial Cloud</p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;"><a href="https://github.com/alibaba/clusterdata">Alibaba Cluster Trace</a></p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">Alibaba</p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">v2018</p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">2017</p>
			</td>
		</tr>
		<tr>
			<td>
			<p dir="ltr" style="text-align: center;"><a href="https://github.com/Azure/AzurePublicDataset">Azure VM Workload</a></p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">Microsoft</p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">v2</p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">2017</p>
			</td>
		</tr>
		<tr>
			<td>
			<p dir="ltr" style="text-align: center;"><a href="https://github.com/google/cluster-data">Google Cluster Workload Traces</a></p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">Google</p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">--</p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">2011</p>
			</td>
		</tr>
		<tr>
			<td rowspan="4">
			<p dir="ltr" style="text-align: center;">HPC</p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;"><a href="https://www.cse.huji.ac.il/labs/parallel/workload/">Parallel Workloads</a></p>

			<p dir="ltr" style="text-align: center;"><a href="https://www.cse.huji.ac.il/labs/parallel/workload/">Archive (PWA)</a></p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">The Hebrew University of Jerusalem (Israel)</p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">--</p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">2014</p>
			</td>
		</tr>
		<tr>
			<td>
			<p dir="ltr" style="text-align: center;"><a href="http://gwa.ewi.tudelft.nl/">Grid Workloads Archive (GWA)</a></p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">Delft University of Technology (TU Delft) (Netherlands)</p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">--</p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">2007</p>
			</td>
		</tr>
		<tr>
			<td>
			<p dir="ltr" style="text-align: center;"><a href="https://ftp.pdl.cmu.edu/pub/datasets/ATLAS/">LANL Mustang Cluster</a></p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">ATLAS project at Carnegie Mellon University and Los Alamos National Laboratory (LANL)</p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">--</p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">2018</p>
			</td>
		</tr>
		<tr>
			<td>
			<p dir="ltr" style="text-align: center;"><a href="https://ftp.pdl.cmu.edu/pub/datasets/ATLAS/">LANL Trinity Cluster</a></p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">ATLAS project at Carnegie Mellon University and Los Alamos National Laboratory (LANL)</p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">--</p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">2018</p>
			</td>
		</tr>
		<tr>
			<td rowspan="2">
			<p dir="ltr" style="text-align: center;">Private Cloud</p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;"><a href="https://ftp.pdl.cmu.edu/pub/datasets/ATLAS/index.html">Two Sigma</a></p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">Two Sigma</p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">--</p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">TBD</p>
			</td>
		</tr>
		<tr>
			<td>
			<p dir="ltr" style="text-align: center;"><a href="https://github.com/SWIMProjectUCB/SWIM/wiki">Statistical Workload Injector for MapReduce (SWIM)</a> </p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">The University of California Berkeley</p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">--</p>
			</td>
			<td>
			<p dir="ltr" style="text-align: center;">2011</p>
			</td>
		</tr>
	</tbody>
</table>

<p> </p>

<p dir="ltr">Publicly available cluster workload traces remain scarce for the increasing number of studies on scheduling and resource management research. </p>

<p dir="ltr">Chameleon has been configured using an adaptation of a mainstream open source infrastructure cloud system called <a href="https://www.openstack.org/">OpenStack</a>. OpenStack has been widely used by other testbeds, such as <a href="https://jetstream-cloud.org/">JetStream</a>, as well as academic/research/government organizations around the world. Developing a trace generator tool for OpenStack would encourage the OpenStack users to share their traces and, therefore, benefits various researches which require real-life workload traces. There are two major concerns when sharing traces -- one from the trace provider and one from the trace user. The researchers who use the traces usually ask -- “is this trace usable?” or “does it contain enough information for my experiment?”, while the trace providers would concern if they exclude or hide confidential information from the shared trace. To address the concerns for both the users and the providers, we developed a <a href="https://github.com/ChameleonCloud/starcompactor">trace generator tool</a> to extract the appropriate data from the OpenStack databases and also to anonymize certain fields. In addition, Chameleon has released both virtual machine and bare-metal traces generated using the trace generator and published the traces at <a href="https://press3.mcs.anl.gov/scienceclouds/cloud-traces/">sciencecloud.org</a>. </p>

<h4 dir="ltr">What’s Included?</h4>

<p dir="ltr">You can generate two tables with the trace generator -- machine events and instance events. The machine events table contains information about the physical hosts. The script captures 5 types of events of a machine, including when the machine is created, enabled, updated, disabled, and deleted. Along with the event type and timestamp, the machine events table also contains the name of the machine and the machine properties. The instance events table includes information about user-created instances (virtual machines or bare-metals). The event column of the table is extracted directly from the event column of the instance_actions_events table of the OpenStack Nova database. The events indicate when an instance gets started, terminated, rebuilt, paused, suspended, etc. For each instance event, we extract two timestamps -- the event start time and the event end time, along with the result of the event (succeeded or failed). Other information includes the name/ID of the instance, the instance owner (user and project), and the instance properties. Two tables can reference each other by the physical host column. To find the detailed column lists of the tables, visit <a href="https://scienceclouds.org/cloud-traces/cloud-trace-format/">cloud trace format page</a> at <a href="https://scienceclouds.org">sciencecloud.org</a>.  </p>

<h4 dir="ltr">What’s Hidden?</h4>

<p dir="ltr">For confidentiality reasons, trace providers may not want to expose information like user/project IDs or physical host names. When using the trace, the users might not need to know the actual IDs but they might want to know which instances belong to one user when running their simulations. The trace generator allows you to anonymize certain fields using different anonymization techniques. For fields like instance id, instance name, user id, project id and physical host name, keyed cryptographic hash technique is applied. We also mask the rack information of a physical host using the ordering technique. The list of observed unique rack values is sorted. Then, we assigned sequential numbers starting with 0 to the items of the rack list, and the observed values are mapped onto these numbers.</p>

<p> </p>

<h4 dir="ltr">About Usage</h4>

<h5 dir="ltr">How to use the Chameleon traces?</h5>

<p dir="ltr">The Chameleon traces can be downloaded from <a href="https://scienceclouds.org/cloud-traces/">sciencecloud.org.</a> For a quick start on downloading and using our cloud traces, we provided a <a href="https://github.com/ChameleonCloud/starcompactor/blob/master/ChameleonKVMCloudTraces.ipynb">Jupyter Notebook example</a>, which you can upload to <a href="https://jupyter.chameleoncloud.org/">Chameleon Jupyter server</a>. </p>

<h5 dir="ltr">How to use the trace generator?</h5>

<p dir="ltr">Generating traces using our trace generator tool is easy if you use OpenStack compute service (Nova). Simply download the scripts from our <a href="https://github.com/ChameleonCloud/starcompactor">GitHub repository</a> and follow the <a href="https://github.com/ChameleonCloud/starcompactor/blob/master/README.md">instructions</a> for setup, configuration and execution.  </p>

<p>It would be a huge encouragement to us to see your work using our cloud traces, and we also encourage research groups and cloud testbed providers to share their cloud traces with us. You can find more information about the Chameleon traces and how to share your traces with us at <a href="https://press3.mcs.anl.gov/scienceclouds/cloud-traces/">sciencecloud.org</a>. We look forward to hearing from you!</p>