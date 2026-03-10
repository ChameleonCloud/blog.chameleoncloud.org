---
abstract: "<p>Interested in learning how you can save power in computer systems, especially\
  \ with latency critical applications? Learn more about how profile-guided frequency\
  \ scaling can help solve this problem, with research supervised by Assistant Professor\_\
  Vinicius Petrucci at the University of Pittsburgh and\_presented last month at IEEE/ACM\
  \ CCGrid!</p>"
authors:
- Vinicius Petrucci
categories:
- User Experiments
date: '2021-06-21 22:58:16+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/ff/a3/ffa359cb-3d44-4a1c-aceb-c5f56f8e45a3/screen_shot_2021-06-21_at_35708_pm.png
slug: profile-guided-frequency-scaling-latency-critical-search-workloads
subtitle: ''
title: Profile-Guided Frequency Scaling for Latency-Critical Search Workloads
---

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-a7977f5e-7fff-e146-ffbc-094e0c0c0c07"><img height="181" src="https://lh6.googleusercontent.com/CsSyk8xbfGl9Az4-Rx1jYryH2c4-LoL0zhjos-drWHRyWnzPyI0X28bLvBgr35fatTLYsrtFb4mORfEMrBRWYbMyx2e-9pvkWl0FF9DT6f05MnezopvPSwMgNNSlGSOWaOggoRi0" width="186"><img height="190" src="https://lh5.googleusercontent.com/oamKUGRF0mASkZywsEFrDvLX1ru77VK_IYXLyxeW1jA8C7nRX_etIaudlSHSXf4673nj7nn1uhXSuDn9-qf8BUTBXtsVjSna6CumNiBh_mfPmUEZGFFZbrY8eU9FuYVVLPU5nr8s" width="197"><img height="180" src="https://lh4.googleusercontent.com/C2uBO39O0-y2jxEN0U7ec8WjZExIVC9wL69LSotEW3yEA6I57zmBp40aIJLCI06XHEMzkQyPHFk8Z_wRb_gYNiggUadTfaaWr86z64Jlhl45bj10_ZZu2Hpck4bEK53kxk-lgXRc" width="223"></b></p>

<p dir="ltr" style="text-align: center;">Daniel Araujo-UFBA (left), Denilson Amorim-UFBA (center), Vinicius Petrucci-UFBA/Pitt (right)</p>

<p> </p>

<p>The experimental work described here was conducted by Masters student Daniel Araujo in collaboration with the undergraduate student Denilson Amorim, both affiliated with the Universidade Federal da Bahia, from Salvador, Bahia, Brazil. The students were supervised by Vinicius Petrucci (UFBA/Pitt).</p>

<p> </p>

<p dir="ltr"><b>On the current research:</b></p>

<p dir="ltr">Dynamic frequency scaling is a technique to reduce power consumption in computer systems. However, this technique poses challenges when adopted in latency-critical cloud applications, such as web search, because it does not take into account the latency requirements of the running application. Established work on dynamic frequency scaling at OS-level is application agnostic and coarse-granulated in the sense that it considers the entire application process utilization for decision making. </p>

<p>We hypothesize that we can better optimize such latency-critical applications by characterizing and identifying functions/threads that require distinct levels of performance and could then be optimized individually. In that sense, we should be running the CPU at a higher speed only during the activation of a function that requires such a higher performance.</p>

<p dir="ltr">Our experimental work introduces a new approach that combines profiling compute-intensive functions with code instrumentation for thread monitoring and core frequency scaling. Using the Chameleon testbed, we implemented and evaluated our proposal in a real multi-core system. We observed energy consumption savings up to 28% when compared to the recent Linux's Ondemand frequency scaling governor while attaining acceptable levels of performance/latency constraints for a web search application.</p>

<p> </p>

<p dir="ltr"><b>On approaching the research challenge:</b></p>

<p dir="ltr">Our experimental work, called Hurry-Up, proposes a finer-grained dynamic frequency scaling approach for multi-core processors that leverages information about the computational intensity of certain functions in latency-critical search applications. Our solution works by identifying that individual requests can demand distinct CPU processing time, thus the frequency can be adjusted to match the request's demand. The idea is to dynamically track the execution stage of the most compute-intensive threads and to adjust the associated CPU frequency based on the stage information. The execution stage is characterized by two information sources: (1) whether or not the thread is executing a particular “hot function”, and (2) for how long it has been running in the “hot function”.</p>

<p> </p>

<p>At a high level, as shown in the figure below, every thread entry and exit event on a hot function is intercepted at run-time by the Java Virtual Machine Tool Interface (JVMTI) agent (shown on the left). In the JVMTI agent, shown on the right-hand side figure, there is an Event Generator, which pushes the entry and exit events to the Event Queue; the Frequency Scheduler consumes the events from this queue and performs the CPU frequency changes using the cpufreq Linux interface.</p>

<p> </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-a7977f5e-7fff-e146-ffbc-094e0c0c0c07"><img height="188" src="https://lh4.googleusercontent.com/YVC3OUcedbXzVqxD0v0i591z_MbUK56RjYNVfZ1ckBUEFBta4jWeAJCT8BfzNuUh31ipUcR8fprx_5E8IzyFaPGG_nRwecXPMV1mTn__NbK9Hjk4AMBILgRwJZV8lH7tAw9YoUg2" width="681"></b></p>

<p><br>
 </p>

<p dir="ltr">We deployed Elasticsearch as our latency-critical benchmark. We identified Elasticsearch's hot function while running the benchmark with previous representative input traces. We generated a Flame Graph of Elasticsearch (see figure below) after running it using the Linux perf tool. We found that the method “org/elasticsearch/search/SearchService. executeQueryPhase” dominated about 81% of the search process. We selected this particular method as our “hot function” from the call stack since it is the top function in the stack from the search Java package.</p>

<p> </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-a7977f5e-7fff-e146-ffbc-094e0c0c0c07"><img height="437" src="https://lh5.googleusercontent.com/WsyESyd5lVoBKpojRdBkCnT9jt0wplE1nbywmnpwaAGKPRcZKrjO_cn_b5y7nebHqwjgH9SkKo1uX_z8NXnCTZNJMBXnuutAMiDxuNDCClGna3SZ1C33ZRUGa_YTTfNpbjZ13br1" width="624"></b></p>

<p> </p>

<p dir="ltr">During the search process, our frequency scaling solution works by reacting to hot function entry/exit events that are intercepted at run-time. A flowchart of the frequency scheduler logic is shown below. Recall that every thread entry/exit to/from the hot function generates an event that is pushed into the Event Queue that is consumed by the scheduler. Based on those events, the Scheduler is responsible for increasing or decreasing the CPU frequency running each thread based on the executing stage of these search threads. Each event has information about what core each thread is running at, a timestamp for detecting if this thread is over a particular time threshold, and status (e.g. either an entry or leave event).</p>

<p><br>
 </p>

<p dir="ltr" style="text-align: center;"><b id="docs-internal-guid-a7977f5e-7fff-e146-ffbc-094e0c0c0c07"><img height="396" src="https://lh3.googleusercontent.com/QceUkL_JJRXoG_2prKUwrtHdq_7awmfNIwwMSklQUmw_AWIKuZ8zGKWphr8J0dZ5jAeY_4VyJTgv1kYBdjd4EdKEJFbCne0PVt7GLygzPgumjH9IKlEsubRueJGwaVYGB9lbmSk2" width="465"></b><br>
 </p>

<p dir="ltr"><b id="docs-internal-guid-a7977f5e-7fff-e146-ffbc-094e0c0c0c07">On testbed needs: </b></p>

<p dir="ltr">The key feature from Chameleon was the access of bare-metal instances with root access to be able to control the voltage/frequency of individual CPU cores and to measure the CPU power consumption using Intel’s RAPL interface. In particular, this feature allowed us to choose our desired processor architecture (we used both Intel’s Skylake and Haswell, as they both had per-core dynamic frequency support) and also our OS-flavor, while letting us customize it. During the course of the research, we had to change the default kernel’s boot configuration (using ACPI energy driver instead of Intel’s pstate, for example) and even the kernel itself - and Chameleon did allow us to do it.  We also used Chameleon’s infrastructure for packing our modified OS into a snapshot, storing it in the cloud, and starting multiple instances with it. All we can say is that this kind of research would be a lot harder without Chameleon’s infrastructure. We are very thankful for this support!</p>

<p> </p>

<p dir="ltr"><b id="docs-internal-guid-a7977f5e-7fff-e146-ffbc-094e0c0c0c07">About the author:</b> </p>

<p dir="ltr">I am an Assistant (tenured) Professor (on leave) at UFBA, Brazil, and Assistant Teaching Professor at the University of Pittsburgh, USA. </p>

<p dir="ltr">My primary research interests concentrate on computer systems with an emphasis on improving resource efficiency while delivering real-time performance guarantees. I have focused on understanding the tradeoffs of energy (e.g. save energy by running a bit slower) and performance (e.g. need to meet user expectations, always!) and exploring this knowledge to design better dynamic resource management approaches.</p>

<p dir="ltr">Check out my <a href="https://scholar.google.com/citations?hl=en&amp;user=wjCINR8AAAAJ&amp;view_op=list_works&amp;sortby=pubdate">Google Scholar</a> for up-to-date publications and citations.</p>

<p dir="ltr"> </p>

<p dir="ltr"><b>On his most powerful piece of advice: </b></p>

<p dir="ltr">I believe an important step is to acknowledge that research is hard as you are required to pursue both high-quality work and novelty. If students are told that research is an easy and natural process, and in fact, they find that it is hard, which is, they won’t think "Oh! That was a lie", they will think "I'm not good at research and should quit."</p>

<p dir="ltr">My piece of advice is that students should not pay attention to thoughts like "I am not good enough to do research" or "I am dumb since I am struggling with my research". It is OK being “stuck” and sometimes not making any (visible) progress. Actually, in the long run, you just need to be comfortable with a certain level of ambiguity and uncertainty, and to be good at being "stuck" now and then. Research is a long-term process, and you should just keep it up, continue putting great effort into your work, and naturally, good stuff will come out from all this process.</p>

<p dir="ltr">Especially for new graduate students, I recommend watching “Graduate School: Keys To Success'' (<a href="https://www.youtube.com/watch?v=fqPSnjewkuA">link</a>) by Remzi Arpaci-Dusseau (Wisconsin). It was very inspiring to me!</p>

<p dir="ltr">From this presentation, I found the following quote impactful: “It’s hard to make something that’s interesting… Basically, anything that anyone makes… It’s like a law of nature, a law of aerodynamics, that anything that’s written or anything that’s created wants to be mediocre. It’s all tending toward mediocrity the way that all the atoms are dissipating out toward the expanse of the universe. Everything wants to be mediocre, so what it takes to make anything that is more than mediocre is an extreme act of will. You just have to exert so much will into something for it to be good.” - Ira Glass (This American Life)</p>

<p dir="ltr"> </p>

<p dir="ltr"><b>Additional reading: </b></p>

<p dir="ltr">This research work was accepted to be presented and appear at the IEEE/ACM 21st International Symposium on Cluster, Cloud and Internet Computing (CCGRID) on May 10-13, 2021. You can find a copy of the paper <a href="https://www.researchgate.net/publication/350470537_Profile-guided_Frequency_Scaling_for_Latency-Critical_Search_Workloads">here</a>.</p>

<p dir="ltr">The source code of our solution with instructions for reproducibility is open and available at <a href="https://github.com/raijenki/elastic-hurryup/">https://github.com/raijenki/elastic-hurryup/</a></p>