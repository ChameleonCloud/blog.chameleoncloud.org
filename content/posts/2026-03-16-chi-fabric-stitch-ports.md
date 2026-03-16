---
abstract: '<p>Chameleon''s stitch port feature lets you connect bare-metal GPU servers
  directly to FABRIC''s network fabric — no public IP required. This post walks through
  a Trovi artifact that provisions a Chameleon GPU node, links it to a FABRIC slice
  over fabnet, and runs LLM inference across the stitched network. Grab the notebook
  and adapt it to your own cross-testbed workflows.</p>'
authors:
- Ganesh C. Sankaran
categories:
- Tips and Tricks
- Featured
date: '2026-03-16 00:00:00+00:00'
featured: true
image: 'https://chameleoncloud.org/media/filer_public/80/48/8048c9bf-a0f6-4362-9dfd-4d420f9232f2/chameleon_fabric.png'
related_posts:
- slug: fabric-updated-trovi-example-for-using-fabric-with-chameleon
  title: FABRIC - Updated Trovi Example for using FABRIC with Chameleon
slug: chi-fabric-stitch-ports
subtitle: A Trovi artifact for cross-testbed GPU workflows using Chameleon and FABRIC
title: 'Running LLMs on Chameleon GPUs from FABRIC via Stitch Ports'
---

<p>What if you could combine Chameleon's bare-metal GPU servers with FABRIC's programmable network fabric — and access the GPU over a private network without ever assigning a public IP? That's exactly what Chameleon's <strong>stitch port</strong> feature enables, and we've published a Trovi artifact that demonstrates the full workflow end to end.</p>

<p>The artifact provisions an RTX 6000 GPU server on Chameleon, connects it to a FABRIC slice over <code>fabnetv4</code>, installs Ollama with a DeepSeek-R1 model on the GPU, and queries the LLM from a FABRIC node — all through the private stitched network. You can use it as-is to run LLM inference, or adapt it as a starting point for your own cross-testbed experiments.</p>

<h2>Why Stitch Ports?</h2>

<p>Normally, accessing a Chameleon server from an external network requires a floating IP and exposing the server to the public internet. Stitch ports change that equation: when you reserve a Chameleon node with FABRIC as the stitch-port provider, the server gets a private IP on FABRIC's <code>fabnetv4</code> network. A FABRIC node on the same network can then reach the Chameleon server directly — no public exposure, no firewall gymnastics for the network path between them.</p>

<p>This is especially valuable for GPU workloads. You get Chameleon's bare-metal GPU performance with FABRIC's network programmability, and you can orchestrate both sides from a single notebook.</p>

<h2>What the Artifact Does</h2>

<p>The notebook walks through five stages:</p>

<ol>
<li><strong>Reserve a Chameleon GPU node</strong> with FABRIC as the stitch-port provider, selecting a GPU type (e.g., <code>gpu_rtx_6000</code>) and scheduling the lease.</li>
<li><strong>Create the Chameleon server</strong> on the reserved node, connected to the <code>fabnetv4</code> network and booting a <code>CC-Ubuntu20.04</code> image.</li>
<li><strong>Create a FABRIC slice</strong> with a compute node at the same site (TACC), attached to <code>fabnetv4</code>.</li>
<li><strong>Install GPU drivers and Ollama</strong> on the Chameleon server — the notebook SSHs from the FABRIC node to the Chameleon server over the private network to run the setup scripts.</li>
<li><strong>Query the LLM</strong> from the FABRIC node by POSTing to Ollama's HTTP API on the Chameleon server's private IP.</li>
</ol>

<p>Here's what the final query looks like — a simple curl from the FABRIC node to the Chameleon GPU server:</p>

<pre><code>curl -X POST http://10.191.131.85:11434/api/generate \
  -H "Content-Type: application/json" \
  -d '{
    "model": "deepseek-r1:8b",
    "prompt": "Tell me a joke about computer networks.",
    "stream": false
  }'</code></pre>

<p>And it works — the response comes back over the private fabnet link with sub-millisecond ping latency between the two nodes:</p>

<pre><code>PING 10.191.131.85 (10.191.131.85) 56(84) bytes of data.
64 bytes from 10.191.131.85: icmp_seq=1 ttl=63 time=0.121 ms
64 bytes from 10.191.131.85: icmp_seq=2 ttl=63 time=0.105 ms
64 bytes from 10.191.131.85: icmp_seq=3 ttl=63 time=0.110 ms</code></pre>

<h2>Prerequisites</h2>

<p>Before running the notebook, you'll need accounts and credentials on both testbeds:</p>

<h3>Chameleon Setup</h3>
<ul>
<li>A <a href="https://chameleoncloud.org/user/dashboard/">Chameleon Cloud account</a> with an active project.</li>
<li>A <strong>key pair</strong> created at your experiment site (e.g., CHI@TACC) under Project &gt; Compute &gt; Key Pairs. Download the private key — you'll need it in the notebook.</li>
<li>A <strong>GPU lease reservation</strong> with FABRIC selected as the stitch-port provider. Check the host calendar for GPU availability and note the reservation ID.</li>
</ul>

<h3>FABRIC Setup</h3>
<ul>
<li>A <a href="https://portal.fabric-testbed.net/">FABRIC account</a> with portal access.</li>
<li>FABRIC credential files in your config directory: bastion keys, slice keys, <code>fabric_rc</code>, and <code>ssh_config</code>.</li>
<li>A fresh token from the FABRIC Credential Manager (Experiments &gt; Manage Tokens), saved as <code>id_token.json</code>.</li>
</ul>

<div class="alert alert-block alert-info">
<b>Important:</b> Chameleon monitors server utilization and reclaims idle servers. Plan to start using your reserved resources as soon as the lease begins.
</div>

<h2>Key Steps in the Notebook</h2>

<h3>Provisioning the Chameleon Server</h3>

<p>The notebook uses Chameleon's <code>chi</code> Python bindings to create a bare-metal GPU server on the reserved lease, connected to the <code>fabnetv4</code> network:</p>

<pre><code>chi.server.create_server(
    server_name,
    reservation_id=chi_reservation_id,
    network_name='fabnetv4',
    image_name='CC-Ubuntu20.04',
    key_name=chi_key_file)

chi.server.wait_for_active(server.id)
chi_server = chi.server.get_server('chi_fab_gpu_1')
fixed_ip = chi_server.addresses['fabnetv4'][0]['addr']</code></pre>

<p>The server's IP on <code>fabnetv4</code> is a private address — not reachable from the public internet, but directly accessible from any FABRIC node on the same network.</p>

<h3>Creating the FABRIC Slice</h3>

<p>On the FABRIC side, the notebook uses <code>fablib</code> to create a slice with a single node attached to <code>fabnetv4</code>:</p>

<pre><code>slice = fablib.new_slice(name='My-Fabric-Chameleon-GPU')
node = slice.add_node(name='node1', site='TACC')
node.add_fabnet()
slice.submit()</code></pre>

<p>Once both sides are up, the FABRIC node can reach the Chameleon server over the private network. The notebook uploads the Chameleon SSH key to the FABRIC node and uses it as a jump host to install software and run commands on the GPU server.</p>

<h3>Running LLM Inference</h3>

<p>After installing NVIDIA drivers and Ollama on the Chameleon GPU server, the notebook pulls a model (<code>deepseek-r1:8b</code>) and configures Ollama to listen on all interfaces. From there, the FABRIC node can query the model directly over HTTP through the private fabnet link.</p>

<h2>Adapting the Artifact</h2>

<p>The notebook is designed as a starting point. Here are a few ways you might adapt it:</p>

<ul>
<li><strong>Swap the GPU type:</strong> Change the reservation to a different GPU (e.g., A100, V100) depending on your workload and availability.</li>
<li><strong>Run a different model:</strong> Replace <code>deepseek-r1:8b</code> with any model Ollama supports — or skip Ollama entirely and install your own inference framework.</li>
<li><strong>Add more FABRIC nodes:</strong> Scale the slice to multiple nodes that all query the same GPU server, useful for benchmarking or distributed workloads.</li>
<li><strong>Change the site:</strong> The artifact uses TACC, but you can target any Chameleon site that supports FABRIC stitch ports.</li>
<li><strong>Build on the cross-testbed pattern:</strong> The general approach — Chameleon for compute, FABRIC for network — applies beyond LLMs. Any workload that benefits from bare-metal GPU access and programmable networking can use this same stitch-port setup.</li>
</ul>

<h2>Tips and Gotchas</h2>

<ul>
<li><strong>Reservation timing:</strong> GPU resources are in high demand. Check the host calendar and reserve ahead of time. Once your lease starts, begin using the resources promptly to avoid reclamation.</li>
<li><strong>Driver and model installs take time:</strong> CUDA drivers and large model downloads can take many minutes on bare-metal. Plan for this in your workflow.</li>
<li><strong>Key management:</strong> The notebook uploads a Chameleon private key to the FABRIC node for SSH access. This is convenient for experimentation but should be handled carefully — consider ephemeral keys for longer-running or shared experiments.</li>
<li><strong>Chi library versions:</strong> The <code>chi</code> Python bindings evolve across versions. If you encounter missing methods (e.g., <code>interface_list</code>), use the server's <code>addresses</code> attribute directly as shown in the notebook.</li>
<li><strong>Firewall configuration:</strong> To expose Ollama's API port on the Chameleon server, the notebook opens TCP port 11434 via <code>firewalld</code>. Adjust this if your application uses different ports.</li>
</ul>

<h2>Get Started</h2>

<p>The full notebook is available as a Trovi artifact. Clone it, fill in your credentials and reservation details, and run through the cells to have a GPU-backed LLM endpoint accessible from FABRIC's network — all without a single public IP address.</p>
