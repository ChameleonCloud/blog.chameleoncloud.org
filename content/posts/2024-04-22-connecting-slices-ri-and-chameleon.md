---
abstract: "<div class=\"flex flex-grow flex-col max-w-full\">\n<div class=\"min-h-[20px]\
  \ text-message flex flex-col items-start gap-3 whitespace-pre-wrap break-words [.text-message+&amp;]:mt-5\
  \ overflow-x-auto\" data-message-author-role=\"assistant\" data-message-id=\"2dd61384-6c24-4a27-adc8-dffab7738e1f\"\
  \ dir=\"auto\">\n<div class=\"markdown prose w-full break-words dark:prose-invert\
  \ dark\">\n<p>\"Connecting SLICES-RI and Chameleon: An Approach towards Portable,\
  \ Reproducible Experiments\" explores the creation of replicable scientific experiments\
  \ through 'pos', a novel tool and methodology. Integrated with Chameleon and other\
  \ public research infrastructure, 'pos' allows researchers to replicate experiments\
  \ reliably across shared infrastructures. This collaboration aligns with the SLICES-RI\
  \ initiative to enhance research portability. Authors Henning Stubbe, Sebastian\
  \ Gallenm\xFCller, and Georg Carle also share insights into maintaining adaptability\
  \ and variety in long-term research projects, crucial for advancing experimental\
  \ reproducibility and collaboration.</p>\n</div>\n</div>\n</div>"
authors: []
categories:
- User Experiments
date: '2024-04-22 21:59:54+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/db/1d/db1d009c-7123-49f0-acc6-8474af53c132/pos-slide.png
related_posts: []
slug: connecting-slices-ri-and-chameleon
subtitle: An Approach towards Portable, Reproducible Experiments
title: Connecting SLICES-RI and Chameleon
---

<p>Experiments are a cornerstone of modern science. Through experiments, we discover and experience the properties of our world. Results from experiments enable researchers to reason about what is. Nevertheless, for this reasoning to be sound, solid data and, thus, experiments are essential. One way to ensure valid data is repeating experiments multiple times: if results are repeatable, we can rely on them. However, relying on the results of other researchers requires trust. And building trust is a challenging endeavor. Reproducible experiments are an approach to ensure trust in experimental results. If we can reproduce the results of fellow researchers in their setup, there is no need to just trust the words of the researchers; we can verify the results by comparison! Despite a globalized world, accessing others’ experimental setups is not always feasible. Thus, researchers started to replicate experiments and results in their setups. Depending on the research domain, repeating, reproducing, or replicating experiments can be challenging. A common challenge is the influence of allegedly immaterial factors, e.g., the exact CPU type for an experiment focusing on networking behavior. The goal of our work is to assist researchers in creating replicable experiments. For this, we extend the researcher's toolkit with <em>the Plain Orchestrating System (pos</em>), both a tool and methodology, designed for this purpose.</p>

<h1>Our Research Findings</h1>

<p>As introduced, our work aims to assist researchers in creating replicable experiments. Creating replicable experiments is tedious, as experiments tend to have many hidden factors. In previous work, we introduced <em>pos</em>, a tool and a methodology helping to create reproducible experiments. In other words, <em>pos</em> describes a sequence of steps and guidelines to follow and adhering to this workflow leads to reproducible experiments.</p>

<p>To validate this claim, we implemented a tool that follows this methodology and is used at our labs to conduct experiments. This situation, however, raises two related research questions:</p>

<ul>
	<li><strong>(R1) How can we, as a community, move from reproducible to replicable experiments?</strong></li>
	<li><strong>(R2) How can we best enable external research to conduct <em>pos</em> experiments?</strong></li>
</ul>

<p><img height="auto" src="https://chameleoncloud.org/media/filer_public/fb/25/fb252b1a-54e1-472e-a739-158e63b651fb/pos-diagram.png" width="80%"></p>

<p><small><strong>Figure 1:</strong> Diagram of the <em>pos </em>methodology.</small></p>

<p>Given the availability of public research infrastructure, such as Chameleon and <a href="https://www.cloudlab.us/">CloudLab</a>, we decided to integrate the <em>pos</em> methodology into these existing environments. As depicted in <strong>Figure 1</strong>, we distinguish a hosting testbed providing crucial resources from a hosted testbed focusing on executing structured experiments. With this approach, researchers reserve infrastructure in one of the supported testbeds, deploy <em>pos</em> as a testbed environment onto their infrastructure, and, ultimately, conduct their experiments inside <em>pos</em>. This approach enabled researchers, regardless of their access to private infrastructure, to conduct <em>pos</em> experiments and, hence, fulfill (R2). Moreover, as the conducted <em>pos</em> experiments can be performed in either Chameleon, CloudLab, or local deployments, published experiments can be tested for replicability by other researchers. As a result, this solution solves (R1), enabling any researcher to package an experiment to be replicable, i.e., understandable, by all.</p>

<h1>Running the Experiment on Chameleon</h1>

<p>To implement and test our approach, we rely on several features provided by Chameleon. Our work includes an example experiment to highlight that no changes to the experiment are required when moving across the infrastructure. <a href="http://chameleoncloud.org/experiment/share/0eae10cc-fd90-4583-8965-77989dfe4e69">This experiment</a> uses <a href="http://chameleoncloud.org/experiment/share">Trovi</a> to share experiments easily and the <a href="https://chameleoncloud.org/blog/2023/08/29/running-experiments-inside-a-jupyter-notebook/">Jupyter Interface</a> provided by Chameleon for seamless interaction with the experiment environment. Additionally, we used the virtual machines available through <a href="https://chameleoncloud.org/experiment/sites/kvm/">KVM@TACC</a> to evaluate our approach. There, we used the Python OpenStack API (<a href="https://chameleoncloud.org/blog/2021/03/15/cloud-wrangling-chameleons-python-library/">python-chi</a>) to automate interactions, such as host creation and configuration.</p>

<p>The extension to <em>pos</em> made as part of this work interacts with Chameleon. For this interaction, we rely on the availability of an API to express our intent. Here, we found the OpenStack API provided by Chameleon particularly helpful. Though OpenStack is a well-known and proven software, to our knowledge, Chameleon is the sole testbed employing it. Yet, the mentioned OpenStack properties make for a pleasant user experience. A description that also fits the Jupyter Interface was used, as mentioned, to structure our sample experiment. Though other testbeds allow installing Jupyter instances, from our experience, only a few do. While not integrated into this work, we are interested in the long-term durability of experiments and reducing the overhead associated with replicating them. Trovi provides a valuable approach that we look forward to integrating into future work.</p>

<h1>Experiment Artifacts</h1>

<p><img height="auto" src="https://chameleoncloud.org/media/filer_public/db/1d/db1d009c-7123-49f0-acc6-8474af53c132/pos-slide.png" width="80%"></p>

<p><small><strong>Figure 2:</strong> Slide from a presentation on <em>pos</em></small></p>

<p>Our paper on the <em>pos </em>tool and methodology is available <a href="https://doi.org/10.23919/WONS60642.2024.10449532">here</a>.</p>

<p>Digital artifacts are available on both <a href="https://github.com/hstubbe/wons2024">GitHub</a> and <a href="https://chameleoncloud.org/experiment/share/0eae10cc-fd90-4583-8965-77989dfe4e69">Chameleon Trovi</a>.</p>

<p>The <em>pos</em> framework will become a component of the <a href="https://www.slices-ri.eu">European SLICES-RI initiative</a>. SLICES-RI is in the process of creating a European Research Infrastructure consisting of testbeds distributed across multiple sites. The implementation of <em>pos</em>’ portability feature will help creating experiments that can be run on testbeds like Chameleon or on testbeds part of SLICES-RI.</p>

<h1>User Interview</h1>

<p><strong>Tell us a little bit about yourself.</strong></p>

<p><em>Henning Stubbe</em> received a B.Sc. in computer science from the University of Rostock, Germany, in 2015 and an M.Sc. degree in computer science from the Technical University of Munich (TUM), Germany, in 2018. He is currently pursuing a Ph.D. degree in computer science at TUM at the Chair of Network Architectures and Services with chairholder Prof. Dr.-Ing. Georg Carle. Since 2019, he has been a Research Associate with TUM at the chair mentioned above. His research interests include software-defined, programmable networking with a particular focus on high-performance benchmarking. Moreover, he investigates the creation of reproducible experiments and the development of the methodology and tools to make them portable between different testbeds.</p>

<p><em>Sebastian Gallenmüller</em> received his Ph.D. in 2021 from the Technical University of Munich. He currently works as a PostDoc at the Chair of Network Architectures<br>
and Services led by Prof. Georg Carle at the Technical University of Munich. His main research interests are programmable packet processing systems and testbeds for<br>
network experiments with a focus on performance analysis and modeling of packet processing systems.</p>

<p><em>Georg Carle</em> is professor at the Technical University of Munich, holding the Chair of Network Architectures and Services. He studied at University of Stuttgart, Brunel<br>
University, London, and Ecole Nationale Superieure des Telecommunications, Paris. He did his Ph.D. in Computer Science at University of Karlsruhe, and worked as postdoctoral scientist at Institut Eurecom, Sophia Antipolis, France, at the Fraunhofer Institute for Open Communication Systems, Berlin, and as professor at the University of Tübingen.</p>

<p><strong>How do you stay motivated through a long research project?</strong></p>

<p>As with food, too much of the same stops tasting good. Variety helps. Or a break.</p>

<p><strong>Why did you choose this direction of research?</strong></p>

<p>“One cannot not communicate” stated Paul Watzlawick. As a computer scientist with a networking background, the goal is to assist people in doing so.</p>

<p><strong>Have you ever been in a situation where you couldn't do an experiment that you wanted to do? What prevented you from doing it?</strong></p>

<p>Once in a while experiment attempts are impeded by bottlenecks in the experiment setup. For example, calculations requiring more compute resources than are available. Luckily projects such as Chameleon now enable switching to more powerful machines. However, I find it important to now and then take a step back and reconsider if changing the approach would suffice as well.</p>

<p><strong>Thank you for sharing your knowledge with the Chameleon community!</strong></p>