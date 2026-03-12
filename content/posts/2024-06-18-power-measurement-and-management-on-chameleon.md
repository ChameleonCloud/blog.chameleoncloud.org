---
abstract: <p>Monitoring power consumption is crucial for understanding the energy
  efficiency of your applications and systems. In this post, we explore various techniques
  for measuring power usage on Chameleon nodes, including leveraging Intel's RAPL
  interface for fine-grained CPU and memory power data, utilizing IPMI's DCMI commands
  for system-level power information, and employing the Scaphandre tool for detailed
  per-process power monitoring and visualization. We provide practical examples and
  step-by-step instructions to help you get started with power measurement on Chameleon,
  enabling you to gain valuable insights into the energy footprint of your workloads.</p>
authors:
- Michael Sherman
categories:
- Tips and Tricks
date: '2024-06-18 22:01:24+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/56/a2/56a23811-f1ea-4a7d-9edd-3b7aa4fe3fe0/power_grafana.png
related_posts:
- slug: maximizing-performance-distributed-system-power-budget
  title: Maximizing Performance in Distributed Systems with a Power Budget
- slug: monitoring-power-consumption-low-power-nodes
  title: 'Power to People: Monitoring Power Consumption of Low Power Nodes'
slug: power-measurement-and-management-on-chameleon
subtitle: Exploring Power Monitoring Techniques with RAPL, DCMI, and Scaphandre
title: Power Measurement and Management on Chameleon
---

<p><img height="auto" src="https://www.chameleoncloud.org/media/filer_public/56/a2/56a23811-f1ea-4a7d-9edd-3b7aa4fe3fe0/power_grafana.png" width="80%"></p>

<p>A common question we get is "how can I see how much power my node is using?" Because the node is sitting in one of Chameleon's Datacenters, we can't just plug it into a smart outlet and watch what it draws (There are smart PDUs on the market, we just don't have them right now).</p>

<p>However, all of our "server-class" nodes make this information available to the operating system, and we can get at this information in a few ways. The Intel RAPL (Running Average Power Limit Energy Reporting) framework has the CPU self-report information about the joules used by each processor, and by other subsystems, such as memory.</p>

<p>The "baseboard management controller (BMC)" on each system may also provide information from the power supplies, this can be useful for getting a total system level measurement including fans, cooling, and other overhead.</p>

<h2>Getting system-level power information from the BMC</h2>

<p>Most "normal" Chameleon bare metal nodes support IPMI and the "Data Center Manageability Interface (DCMI)". This includes all of the Intel and AMD based <code>compute_</code> and <code>gpu_</code> nodes. Some special case nodes like FPGAs and arm64 do not support this, as the vendor didn't implement the interface.</p>

<pre><code>sudo apt install freeipmi-tools
sudo ipmi-dcmi --get-system-power-statistics

</code></pre>

<pre><code>Current Power                        : 226 Watts
Minimum Power over sampling duration : 0 watts
Maximum Power over sampling duration : 650 watts
Average Power over sampling duration : 236 watts
Time Stamp                           : 06/18/2024 - 16:49:22
Statistics reporting time period     : 1000 milliseconds
Power Measurement                    : Active

</code></pre>

<p>This data is generally accurate, but doesn't update very frequently (usually several seconds at the fastest). It's most useful for logging power data over hours to days.</p>

<h2>RAPL: Getting information from the CPU</h2>

<p>Intel's RAPL makes information available via several registers, including <code>MSR_PKG_Energy_Status</code> and <code>MSR_PP0_Energy_Status</code>, which update on the order of milliseconds. This makes information available with a much finer time resolution than from the BMC, but it is not "complete", generally only including power usage from the CPU and Memory subsystems.</p>

<p>Rather than write code to query these interfaces directly, we'll leverage some existing tools to get at the data.</p>

<h3>A simple example with <code>Perf</code></h3>

<p>For more detailed and timely information, we can query the CPU using the RAPL interface. This information is updated on the order of milliseconds, although we are limited by the overhead of querying it.</p>

<p>First, for a simple example with "perf":</p>

<pre><code># install linux-tools for your running kernel, to get the `perf` tool
sudo apt-get install "linux-tools-$(uname -r)"

# Make sure intel rapl kernel module is loaded
sudo modprobe intel_rapl_msr

# Finally, we'll ask the kernel how many joules `sleep 1` used
sudo perf stat -e power/energy-pkg/,power/energy-ram/ sleep 1

</code></pre>

<p>Example Results:</p>

<pre><code>Performance counter stats for 'system wide':

             85.17 Joules power/energy-pkg/
             15.17 Joules power/energy-ram/

       1.001343899 seconds time elapsed

</code></pre>

<h3>Using <code>scaphandre</code> to get per-process information</h3>

<p>However, we can do better with the information available: Scaphandre is a powerful tool that combines this information from RAPL, as well as information about how much cpu time each process is using, to make good estimates of per-process power. <a href="https://hubblo-org.github.io/scaphandre-documentation/explanations/how-scaph-computes-per-process-power-consumption.html">For a comprehensive explanation of how/why it works, take a look at their docs</a>.</p>

<p><img alt="scaphandre_process.png" src="https://www.chameleoncloud.org/media/filer_public/04/6b/046b0551-ea1f-4b65-9c18-752516c02d2d/scaphandre_process.png" width="80%"></p>

<p>Scaphandre is built in rust, so we can either install the rust deps, or pull their docker container.</p>

<pre><code># install dependencies for building scaphandre
sudo apt-get install \\\\
    pkg-config \\\\
    cargo \\\\
    rustup \\\\
    libssl-dev

cargo install scaphandre

</code></pre>

<p>Now, we can run scaphandre and see what it shows us:</p>

<p><code>sudo ~/.cargo/bin/scaphandre stdout --timeout 10 --step 1</code></p>

<pre><code>...
------------------------------------------------------------

Host:	100.568017 W from
	package 	dram
Socket1	41.074833 W |	7.629241 W

Socket0	44.256115 W |	7.599235 W

Top 5 consumers:
Power		PID	Exe
0.6129861 W	130088	"/home/cc/.cargo/bin/scaphandre"
0.009577908 W	116790	"/usr/bin/containerd"
0 W	167	""
0 W	1139	""
0 W	117309	""
------------------------------------------------------------

</code></pre>

<p>Let's install a benchmarking tool, <code>stress-ng</code>, and run that while we monitor usage.</p>

<pre><code># install stress-ng
sudo apt install stress-ng

# run stress-ng for 60s, with parameters to:
# use a single thread to load the CPU
# pin the thread to only core ID 0
# and run in the background

stress-ng --taskset 0 --cpu 1 --timeout 60s &amp;

# run scaphandre again
sudo ~/.cargo/bin/scaphandre  stdout --timeout 10 --step 1

</code></pre>

<p>And the results:</p>

<pre><code>------------------------------------------------------------

Host:	105.828908 W from
	package 	dram
Socket1	41.515255 W |	7.549873 W

Socket0	49.148525 W |	7.582383 W

Top 5 consumers:
Power		PID	Exe
1.105572 W	130281	"/usr/bin/stress-ng"
0.720596 W	130284	"/home/cc/.cargo/bin/scaphandre"
0.009871177 W	116790	"/usr/bin/containerd"
0.009871177 W	94531	""
0 W	275	""

</code></pre>

<h2>Collecting longer term data and plotting it</h2>

<p>Both of these methods (<code>perf</code> and <code>scaphandre</code>) have just been printing human readable text. However, we can easily get machine readable output.</p>

<p>Scaphandre offers a bunch of helpful methods, like saving results to a json file. Or, for something fully integrated, you can run it as a prometheus exporter.</p>

<p>To try this out, we'll grab scaphandre's git repo, and use their example docker-compose file to run scaphandre to export the power data, prometheus to query it, and grafana to plot it.</p>

<ol>
	<li>
	<p>If your image doesn't have it, we'll need to install docker and docker-compose</p>

	<pre><code># Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL &lt;https: download.docker.com="" gpg="" linux="" ubuntu=""&gt; -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \\\\
"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] &lt;https: download.docker.com="" linux="" ubuntu=""&gt; \\\\
$(. /etc/os-release &amp;&amp; echo "$VERSION_CODENAME") stable" | \\\\
sudo tee /etc/apt/sources.list.d/docker.list &gt; /dev/null
sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

&lt;/https:&gt;&lt;/https:&gt;</code></pre>
	</li>
	<li>
	<p>grab the scaphandre git repo</p>

	<pre><code>git clone &lt;https: github.com="" hubblo-org="" scaphandre.git=""&gt;

&lt;/https:&gt;</code></pre>
	</li>
	<li>
	<p>for security, change prometheus and scaphandre to listen on localhost, and change the grafana password to <code>mysuperdemopassword</code></p>

	<pre><code>cd scaphandre/docker-compose/
sed -i 's/8080:8080/127.0.0.1:8080:8080/' docker-compose.yaml
sed -i 's/9090:9090/127.0.0.1:9090:9090/' docker-compose.yaml
sed -i 's/secret/mysuperdemopassword/' docker-compose.yaml

</code></pre>
	</li>
	<li>
	<p>check your public IP, and access grafana in your browser on port 3000, with credentials <code>admin/mysuperdemopassword</code></p>

	<p><img alt="grafana_scaphandre.png" src="https://www.chameleoncloud.org/media/filer_public/ba/32/ba32c803-9d13-4fc4-843a-4a08aa739c7e/grafana_scaphandre.png" width="100%"></p>
	</li>
	<li>
	<p>Finally, lets kick off a big stress test on all cpu cores:</p>

	<pre><code>stress-ng --cpu $(nproc) --timeout 60

</code></pre>

	<pre><code>stress-ng: info:  [133743] setting to a 60 second run per stressor
stress-ng: info:  [133743] dispatching hogs: 96 cpu

</code></pre>

	<p><img alt="scaph_grafana_stress.png" src="https://www.chameleoncloud.org/media/filer_public/91/c4/91c4dddd-0dfc-4974-8443-f76ad5de4edd/scaph_grafana_stress.png" width="100%"></p>
	</li>
</ol>

<p>Using this approach, you can use prometheus on one node to monitor power consumption of multiple others, as well as related metrics like cpu usage.</p>

<h2>Combining data from DCMI and RAPL</h2>

<p>For best results, you'll want both system-level power from DCMI, and cpu/memory/process level data from RAPL. To do this, with prometheus, you can run a combination of the scaphandre prometheus exporter, and the <a href="https://github.com/prometheus-community/ipmi_exporter">prometheus ipmi exporter</a> which calls the above <code>ipmi-dcmi</code> commands.</p>

<p>For a simple script, check out the <a href="https://boavizta.github.io/Energizta/intro.html">Energizta</a> project.</p>

<pre><code>wget &lt;https: boavizta="" energizta="" energizta.sh="" main="" raw.githubusercontent.com=""&gt;
chmod +x energizta.sh
sudo ./energizta.sh --interval 1 --duration 1 --once --energy-only | jq '.'
{
  "interval_us": 1066379,
  "duration_us": 1066379,
  "nb_states": 1,
  "powers": {
    "dcmi_cur_watt": 230,
    "rapl_dram_0_watt": 8,
    "rapl_dram_1_watt": 8,
    "rapl_package_0_watt": 44,
    "rapl_package_1_watt": 41,
    "rapl_total_watt": 101
  },
  "energizta_version": "0.5"
}

&lt;/https:&gt;</code></pre>

<h2>Further Reading</h2>

<p>For a much deeper dive into this, I can recommend the following readings:</p>

<ul>
	<li><a href="https://www.intel.com/content/www/us/en/developer/articles/technical/software-security-guidance/advisory-guidance/running-average-power-limit-energy-reporting.html">Intel RAPL details</a></li>
	<li><a href="https://hubblo-org.github.io/scaphandre-documentation/references/metrics.html">Scaphandre metric details</a></li>
	<li><a href="https://www.kernel.org/doc/html/next/power/powercap/powercap.html">Linux Powercap interface docs</a></li>
	<li><a href="https://www.cncf.io/blog/2023/10/11/the-road-to-scaphandre-v1-0-challenges-and-improvements-to-come-on-it-energy-consumption-evaluation/">https://www.cncf.io/blog/2023/10/11/the-road-to-scaphandre-v1-0-challenges-and-improvements-to-come-on-it-energy-consumption-evaluation/</a></li>
</ul>