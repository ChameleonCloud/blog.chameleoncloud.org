---
abstract: "<p>This year Chameleon hosted the IndySCC competition, analogous to the\
  \ in-person Student Cluster Competition (SCC) of Supercomputing. Teams use cloud/shared\
  \ resources to\_optimize a variety of HPC workloads in order to complete the most\
  \ computations during a 48 hour final, all while staying below a strict power cap.\
  \ Learn more about the compettion, Chameleon's support, and where you can\_see the\
  \ results.\_</p>"
authors:
- Michael Sherman
categories:
- Announcements
date: '2021-11-12 17:19:11+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/9b/37/9b375f59-cc2d-4cff-8397-37abe719e233/screen_shot_2021-11-12_at_61810_pm.png
related_posts: []
slug: summary-of-indyscc-2021-chameleon-usage
subtitle: ''
title: IndySCC 2021 on Chameleon
---

<p dir="ltr">This year Chameleon hosted the IndySCC competition, in which teams optimize a variety of HPC workloads in order to complete the most computations during a 48 hour final, all while staying below a strict power cap. Each year Supercomputing hosts the Student Cluster Competition (SCC), drawing teams from around the world to push HPC software and hardware to, and sometimes beyond, its limits. IndySCC is meant to be analogous to the in-person SCC, but uses cloud/shared resources so that more teams can participate. In the months leading up to the competition, the teams participate in a “Virtual Course”, completing assignments to familiarize themselves with cloud computing concepts, as well as the HPC workloads. 5 teams participated in IndySCC 2021, each consisting of up to 6 students plus an advisor. The teams were from UIUC, Monash University, Australia,  ETH Zurich, Switzerland, Texas A&amp;M, and Sun Yat-sen University, China.</p>

<p dir="ltr"> </p>

<p dir="ltr">Starting in July, the teams made short term leases on Chameleon to complete each assignment, as well as a lease well in advance for the 48 hour competition run on November 6-7. Each team reserved 2 P100 nodes on CHI@TACC, in rack 11 to ensure no bandwidth restrictions. The SCC committee also reserved 2 nodes as “spares”, to be used in the case of hardware issues.</p>

<p dir="ltr"> </p>

<p dir="ltr">In addition to Chameleon hardware, NCAR contributed 5 ARM Thunder X2 machines, operating as a Chameleon Associate site. Each team was allowed to reserve one of these for use in the competition, with the intent to make the site generally available to the community after SC21.</p>

<p dir="ltr"> </p>

<p dir="ltr">Before the 48 hour final competition, teams selected the specific nodes they planned to use; this could be any subset of 2x P100 and 1x ARM. The teams were required to submit results from 4 applications, HPCG, GROMACS, John the Ripper, each of which they had previously completed an assignment and benchmark for. At the beginning of the competition itself, Devito: Fast Stencil Computation from Symbolic Specification was announced as the “Mystery Application”. Teams were judged privately based on how many correct answers they submitted from each application, with a penalty applied if they exceeded the 1100 watt power cap.</p>

<p dir="ltr"> </p>

<p dir="ltr">The Chameleon team made available power monitoring Grafana displays for CHI@TACC , and CHI@NCAR resources. CHI@TACC information was obtained from the DCMI interface of each node’s BMC) and CHI@NCAR by querying smart PDUs, as nodes lacked DCMI support. In both cases, the information was aggregated by a Prometheus instance on the CHI@NCAR site, then made available to the teams and the public via Grafana, using Chameleon’s keycloak instance for single-sign-on. The power usage during the competition is shown on the attached graph, but winners are yet to be announced.</p>

<p dir="ltr"> </p>

<p dir="ltr">This effort will be presented as a talk at the HPCSYSPROS workshop during SC21, on Sunday November 14th. </p>

<p dir="ltr"><b id="docs-internal-guid-647a7749-7fff-5362-07f2-be9d2526f0d5"><img height="315" src="https://lh3.googleusercontent.com/zpIbOg4tneHTmEvaTbsMQAVIiTqW54oSDvu_0zGXefx3H5S1pUmnLlhFlaW8rWUPF9buTNX1ixGWKFBbpm5KAnJooEQgsi4zeQEXj9pCrYddK05BCMk1vAStlnngfilcG-Uen4Az" width="624"></b></p>