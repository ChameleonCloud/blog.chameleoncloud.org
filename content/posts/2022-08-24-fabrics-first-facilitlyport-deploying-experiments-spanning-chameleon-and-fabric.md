---
abstract: "<p>We are excited to announce the first FABRIC facility port at Chameleon\u2019\
  s University of Chicago site. \_With this facility port, users can deploy experiments\
  \ that span Chameleon and FABRIC.</p>"
authors:
- Paul Ruth
categories:
- Tips and Tricks
date: '2022-08-24 19:57:51+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/6b/4e/6b4e4a6f-4d52-41e6-a0c2-fca880f79561/fabric-map.png
related_posts:
- slug: managing-multiple-external-links-stitched-single-chameleon-network
  title: Managing Multiple External Links Stitched to a Single Chameleon Network
slug: fabrics-first-facilitlyport-deploying-experiments-spanning-chameleon-and-fabric
subtitle: ''
title: "FABRIC\u2019s First FacilitlyPort: Deploying Experiments Spanning Chameleon\
  \ and FABRIC"
---

<p><strong>FABRIC.</strong> The <a href="https://fabric-testbed.net/">FABRIC</a> testbed, along with its <a href="https://fabric-testbed.net/about/fab">FABRIC Across Borders (FAB)</a> extension, is an international infrastructure that enables cutting-edge experimentation and research at-scale in the areas of networking, cybersecurity, distributed computing, storage, virtual reality, 5G, machine learning, and science applications.</p>

<p>The FABRIC infrastructure is a distributed set of equipment at commercial collocation spaces, national labs and campuses. Each of the 33 FABRIC/FAB sites has large amounts of compute and storage, interconnected by high speed (100 Gbps+), dedicated optical links. In addition to traditional compute and storage, each FABRIC site provides access to programmable smart NICs, GPUs, NVMe drives, FPGAs, and programmable switches.</p>

<p>Unprecedented access to modern hardware in the core of an interconnected high-performance, low-level networking testbed enables researchers to deploy geographically distributed experiments at scale with novel protocols and algorithms in ways that are not possible with the commodity Internet. Combining this power with large-scale, deeply reconfigurable experimental platforms, such as Chameleon, enables end-to-end experiments at-scale with novel Internet technologies connected to realistic data center and edge compute systems.</p>

<p style="text-align: center;"><b id="docs-internal-guid-3c8f57ad-7fff-9f2d-055a-8d5ff5ff689f"><img src="https://chameleoncloud.org/media/filer_public/6b/4e/6b4e4a6f-4d52-41e6-a0c2-fca880f79561/fabric-map.png" style="width: 519px; height: 317px;"></b></p>

<p style="color: rgb(170, 170, 170); font-style: italic; text-align: center;">Figure 1: FABRIC’s full deployment of U.S. sites, circuits, and initial facility partners. FAB sites include U. Bristol, U. Amsterdam, CERN, and U. Tokyo.. Full deployment is expected by September 2023.</p>

<p><br>
<strong>Testbed-of-testbeds</strong>: Although a powerful testbed on its own, the full potential of FABRIC is only achieved through its philosophy of being a testbed-of-testbeds.   You can think of FABRIC as the programmable networking glue that connects experiments spanning your favorite testbeds and computing facilities. Towards this goal, FABRIC enables low-level networking connections to other specialized testbeds (5G/IoT PAWR, NSF Clouds), high-performance computing facilities (TACC, MGHPCC, NCSA, SDSC, PSC, LBNL, etc.),  public clouds (AWS, Google Cloud, Microsoft Azure), and even facilities in your institution*. </p>

<p>Direct connections between FABRIC and partner facilities are achieved through <strong>facility ports</strong>.  Each partner facility can have one or more facility ports that users can include in their FABRIC experiment topology.  Upon deployment, a facility port will create a layer 2 network circuit between FABRIC and the specified facility.  The circuit may or may not be logically connected to FABRIC’s layer 3 (IPv4 or IPv6) services.  If it is not connected to FABRIC’s layer 3 services, it will be a raw layer 2 circuit configured by the user.  Supporting both layer 2 and layer 3 facility ports allows them to be easily used to connect applications deployed across facilities while also allowing connections to low-level custom routing and switching protocols designed by the user. </p>

<p><strong>Chameleon’s Facility Port</strong> :  We are excited to announce the first FABRIC facility port at Chameleon’s University of Chicago site.  With this facility port, users can deploy experiments that span Chameleon and FABRIC. </p>

<p>Using Chameleon’s facility port requires using both the Chameleon and FABRIC testbeds.  On Chameleon you can reserve a private VLAN network on the stitch_provider labeled “fabric”.  The resulting network will use a VLAN that is connected to the FABRIC site at Starlight (Chicago).  Then on the FABRIC testbed, you can create an experiment that includes a circuit connecting to the Chameleon facility port.  The Chameleon servers added to the private VLAN can now send traffic directly to the FABRIC over the dedicated VLAN (i.e. not using the Internet).    </p>

<p>Managing experiments that span testbeds requires some form of federation between the testbeds.  Both Chameleon and FABRIC use Incommon but do not, yet, fully federate using user identities. For now, Chameleon and FABRIC are using what we are calling “tool based federation”. This means that the Chameleon and FABRIC tools can be simultaneously installed in a user’s environment.  In fact, the suggested way to use Chameleon and FABRIC are through the JupyterHubs provided by each testbed.  The FABRIC JupyterHub comes preconfigured with the Chameleon API and <a href="https://github.com/fabric-testbed/jupyter-examples/blob/master/start_here.ipynb">example Jupyter notebooks</a> that deploy experiments across both testbeds from a single notebook.  Similarly, there is a <a href="https://www.chameleoncloud.org/experiment/share/9284120f-3436-41f3-9e82-238e0628ec6c">Trovi artifact</a> that can be deployed on Chameleon that has similar notebooks that run in Chameleon.  Both the Chameleon and FABRIC JuptyerHub environments will be updated as more sophisticated federation features are added.</p>

<p dir="ltr"><b id="docs-internal-guid-62e6d025-7fff-f377-017c-ad81ce4b7808">Interested in using FABRIC and Chameleon?</b></p>

<p>FABRIC is similar to Chameleon in that a project is owned by a  professor or senior researcher and other users can only access the testbed after being added to a project. .</p>

<p>If you are already a user of FABRIC or Chameleon, but not both, you will need to create an account on the other testbed.  Instructions for signing up for <a href="https://fabric-testbed.net/">FABRIC</a> or <a href="https://www.chameleoncloud.org/">Chameleon</a> can be found on their respective web sites.  </p>

<p>Please contact us for help creating the necessary accounts and projects.<br>
 </p>