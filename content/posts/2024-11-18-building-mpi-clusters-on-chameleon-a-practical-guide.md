---
abstract: <p>Running distributed applications across multiple nodes is a common need
  in scientific computing, but setting up MPI clusters can be challenging, especially
  in cloud environments. In this post, we'll explore a template for creating MPI clusters
  on Chameleon that handles the key configuration steps automatically, letting you
  focus on your research rather than infrastructure setup.</p>
authors:
- Michael Sherman
categories:
- Tips and Tricks
date: '2024-11-18 20:34:58+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/6f/f0/6ff0d773-8864-48f9-9fbc-d5ce1f5be834/open-mpi-logo.png
slug: building-mpi-clusters-on-chameleon-a-practical-guide
subtitle: Simplifying Distributed Computing Setup with Jupyter, Ansible, and Python
title: 'Building MPI Clusters on Chameleon: A Practical Guide'
---

<p><img src="https://www.chameleoncloud.org/media/filer_public/6f/f0/6ff0d773-8864-48f9-9fbc-d5ce1f5be834/open-mpi-logo.png"></p>

<p>Running distributed applications across multiple nodes is a common need in scientific computing, but setting up MPI clusters can be challenging, especially in cloud environments. In this post, we'll explore a <a href="https://www.chameleoncloud.org/experiment/share/bee0e61d-b272-487f-b2c6-e7455f4b4474">template for creating MPI clusters</a> on Chameleon that handles the key configuration steps automatically, letting you focus on your research rather than infrastructure setup.</p>

<h3>Why Use This Pattern?</h3>

<p>When researchers need to run parallel applications, they often face several hurdles:</p>

<p>First, there's the challenge of configuring network connectivity between nodes and ensuring proper security settings. Then comes the task of setting up SSH access and installing MPI consistently across all nodes. Finally, researchers need to manage multiple nodes effectively while maintaining their synchronization. Our template addresses these challenges using a combination of Jupyter notebooks, Ansible automation, and Chameleon's Python SDK (<a href="https://python-chi.readthedocs.io/en/latest/">python-chi</a>) to create a repeatable process.</p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/bc/2b/bc2bce1d-c921-4763-aba2-cc4c4a73c932/screenshot_2024-11-27_at_23125pm.png"></p>

<h3>The Building Blocks</h3>

<p>The template consists of three main components that work together to create a fully functional MPI cluster:</p>

<p>1. A simple MPI "Hello World" application that demonstrates basic cluster functionality by having each node report its hostname and rank within the cluster.</p>

<p>2. Comprehensive Jupyter notebooks for orchestrating the setup, with versions available for both bare metal and KVM environments. These notebooks guide you through the process step-by-step while providing the flexibility to modify parameters as needed.</p>

<p>3. Ansible playbooks that handle node configuration automatically, ensuring consistent setup across all cluster nodes.</p>

<p><img src="https://www.chameleoncloud.org/media/filer_public/ef/92/ef925435-e2fc-4644-b0cd-5d0086ea5476/screenshot_2024-11-27_at_23726pm.png"></p>

<h3>How It Works</h3>

<h4>1. Infrastructure Setup</h4>

<p>The template leverages python-chi to handle all the initial infrastructure creation:</p>

<p>First, it creates a reservation for compute nodes if you're using bare metal resources. Then it launches instances for both the master and worker nodes, configuring networking and security groups along the way. Finally, it sets up SSH access through the master node, which acts as a gateway to the worker nodes.</p>

<h4>2. Cluster Configuration</h4>

<p>Once the nodes are running, Ansible takes over to configure the software environment:</p>

<p>The automation configures hostnames and /etc/hosts entries to ensure nodes can communicate by name. It handles distribution of SSH keys for passwordless access between nodes - a critical requirement for MPI operations. The playbook then installs OpenMPI and related packages, and sets up the clustershell utility for simplified cluster management.</p>

<h4>3. Application Deployment</h4>

<p>With the infrastructure and configuration in place, the template demonstrates application deployment:</p>

<p>It compiles the MPI application on the master node, distributes the resulting binary to all worker nodes using clustershell, and shows how to run the application across the entire cluster using mpirun.</p>

<h3>Tips for Success</h3>

<p>To make the most of this template, keep these key points in mind:</p>

<p>When using bare metal nodes, ensure you request enough nodes in your reservation before starting - you can't add more nodes to a running cluster without reconfiguration. The master node serves as your gateway to the cluster, so keep track of its floating IP address. For initial testing and development, consider using the KVM version of the template before scaling to bare metal resources. And remember to clean up your instances when finished to free up resources for other users.</p>

<h3>Customizing the Template</h3>

<p>Ready to run your own MPI applications? Here's how to adapt the template:</p>

<p>Simply replace hello.c with your application code. If your application requires additional packages, adjust the ansible playbook accordingly. You can modify the node count and instance types based on your computational needs. For applications with special requirements, you can add custom configuration steps to the ansible playbook.</p>

<h3>Getting Started</h3>

<p>Getting up and running with the template is straightforward:</p>

<p>1. Find the "MPI Cluster" artifact in <a href="https://www.chameleoncloud.org/experiment/share/">Trovi</a>, Chameleon's sharing portal.<br>
2. Launch it directly in Chameleon's Jupyter environment.<br>
3. Update the project name in the notebook to match your project.<br>
4. Follow the step-by-step execution process in the notebook.</p>

<h3>Conclusion</h3>

<p>This template demonstrates how Chameleon's tools can streamline the deployment of complex infrastructure. Whether you're teaching parallel computing concepts or conducting distributed systems research, having a reliable way to create MPI clusters lets you focus on what matters most - your science.</p>

<p>The combination of Jupyter notebooks for orchestration, Ansible for configuration, and python-chi for infrastructure management creates a powerful and flexible foundation for your distributed computing experiments. By providing this template, we hope to accelerate your research by eliminating common setup hurdles.</p>