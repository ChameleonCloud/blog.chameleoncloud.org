---
abstract: "<p style=\"text-align: justify;\">Our friends at FABRIC have recently updated\
  \ their FABRIC/Chameleon Trovi artifact. It's\_<em>full</em>\_of interesting examples\
  \ to check out.</p>"
authors:
- Paul Ruth
categories:
- Announcements
date: '2023-05-22 18:26:57+00:00'
featured: false
hide_image: true
image: https://chameleoncloud.org/media/filer_public/ed/8d/ed8d4ca8-b883-4f39-a87d-1d43d449c68c/fabric.png
related_posts:
- slug: fabrics-first-facilitlyport-deploying-experiments-spanning-chameleon-and-fabric
  title: "FABRIC\u2019s First FacilitlyPort: Deploying Experiments Spanning Chameleon\
    \ and FABRIC"
slug: fabric-updated-trovi-example-for-using-fabric-with-chameleon
subtitle: ''
title: 'FABRIC: Updated Trovi Example for using FABRIC with Chameleon'
---

<p>The <a href="https://fabric-testbed.net/">FABRIC</a> testbed, along with its <a href="https://fabric-testbed.net/about/fab">FABRIC Across Borders (FAB)</a> extension, is an international infrastructure that enables cutting-edge experimentation and research at-scale in the areas of networking, cybersecurity, distributed computing, storage, 5G networking, machine learning, and science applications.</p>

<p> The FABRIC infrastructure is a distributed set of equipment at commercial collocation spaces, national labs and campuses. Each of the 33 FABRIC/FAB sites has large amounts of compute and storage, interconnected by high speed (100 Gbps+), dedicated optical links. In addition to traditional compute and storage, each FABRIC site provides access to programmable smart NICs, GPUs, NVMe drives, FPGAs, and programmable switches.</p>

<p><b id="docs-internal-guid-a665bbab-7fff-9f6f-657d-c071fcb3cc80"><img src="https://chameleoncloud.org/media/filer_public/ed/8d/ed8d4ca8-b883-4f39-a87d-1d43d449c68c/fabric.png" style="width: 624px; height: 319px;"></b></p>

<h3>Tying Testbeds together with FABRIC</h3>

<p>A central goal of FABRIC is to enable realistic wide-area networking experimentation at-scale in ways that are not possible with the commodity Internet.  Toward this goal, FABRIC focuses on connections to the external facilities that researchers already use.  These facilities include campus infrastructure, high performance computing centers, and other NSF testbeds, such as Chameleon.   Combining FABRIC’s power core networking power with large-scale, deeply reconfigurable experimental edge platforms, such as Chameleon, enables end-to-end experiments at-scale with novel Internet technologies connected to realistic data center and edge compute systems.  The example depicted in the figure below shows a theoretical experimental topology spanning FABRIC, Chameleon, Cloudlab, OCT, public clouds, and research institutions. </p>

<p><b id="docs-internal-guid-2fad82d4-7fff-f8a7-8a0e-79cab2b9e8b5"><img src="https://chameleoncloud.org/media/filer_public/58/86/5886243e-85ba-4f14-a504-bda348763492/untitled_presentation_4.png" style="width: 624px; height: 351px;"></b></p>

<h3>Connecting Chameleon to FABRIC with Facility Ports </h3>

<p>Last fall Chameleon became the first external facility connected to FABRIC. More recently, we have added a dedicated 100 Gbps connection between FABRIC and Chameleon’s TACC site. With this new facility port, users can deploy experiments that span both Chameleon sites using isolated programmable networks across FABRIC.</p>

<p>The suggested way to use Chameleon and FABRIC are through the JupyterHubs provided by each testbed.  The FABRIC JupyterHub comes preconfigured with the Chameleon API and <a href="https://github.com/fabric-testbed/jupyter-examples/blob/master/start_here.ipynb">example Jupyter notebooks</a> that deploy experiments across both testbeds from a single notebook.  This blog announces an updated FABRIC Trovi artifact that includes the full array of FABRIC capabilities including examples of how to deploy experiments across Chameleon and FABRIC.  If you are interested in learning more, please see the “<a href="https://www.chameleoncloud.org/experiment/share/9a63884a-5a89-46d6-9149-63946f45e2b1">FABRIC Networking Testbed Examples</a>'' artifact and navigate to the complex recipe called “Chameleon Facility Ports”. </p>

<h3>Interested in using FABRIC and Chameleon?</h3>

<p>FABRIC is similar to Chameleon in that a project is owned by a  professor or senior researcher and other users can only access the testbed after being added to a project. .</p>

<p>If you are already a user of <a href="https://fabric-testbed.net/">FABRIC</a> or <a href="https://www.chameleoncloud.org/">Chameleon</a>, but not both, you will need to create an account on the other testbed.  Instructions for signing up for FABRIC or Chameleon can be found on their respective web sites.  </p>

<p>Please contact us for help creating the necessary accounts and projects.</p>