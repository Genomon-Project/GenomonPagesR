---
layout: splash
author_profile: true

header:
  overlay_color: "#5e616c"
  overlay_image: /assets/images/genomon-8fps-1100px-once.gif
  cta_label: "<i class='fa fa-download'></i> Install Now"
  cta_url: "/docs/quick-start-guide/"
  caption:
excerpt: 'The Zen of Cancer Genome Sequence Analysis'
feature_row:
  - image_path: /assets/images/iconmonstr-laptop-4-96.png
    alt: "easy"
    title: "Easy to use!"
    excerpt: '{::nomarkdown}Genomon is now easier than ever to use.<br />You just need to prepare list of input sequence data paths and just type:<pre style="margin: 15px; padding: 5px; background-color: #FFFFFF;">genomon_pipeline dna input.csv output_dir</pre>{:/nomarkdown}'
    url: 
    btn_label: 
  
  - image_path: /assets/images/iconmonstr-server-7-96.png
    alt: "large"
    title: "Large scale!"
    excerpt: '{::nomarkdown}Genomon is now highly optimized and efficiently utilizes ruffus package for job scheduling. <br />You can analyze several hundreds of genomic and transcriptome sequencing data simultaneously.{:/nomarkdown}'
    url: 
    btn_label: 
  
  - image_path: /assets/images/iconmonstr-control-panel-11-96.png
    alt: "flexible"
    title: "Flexible!"
    excerpt: '{::nomarkdown}Genomon is extensible. So you can easily incorporate your favorite modules into Genomon. <br />Also you can easily deploy Genomon to your own cluster other than HGC supercomputer.{:/nomarkdown}'
    url: 
    btn_label: 
github:
  
  - excerpt: '{::nomarkdown}<iframe style="display: inline-block;" src="https://ghbtns.com/github-btn.html?user=aokad&repo=fungi&type=star&count=true&size=large" frameborder="0" scrolling="0" width="160px" height="30px"></iframe> <iframe style="display: inline-block;" src="https://ghbtns.com/github-btn.html?user=aokad&repo=fungi&type=fork&count=true&size=large" frameborder="0" scrolling="0" width="158px" height="30px"></iframe>{:/nomarkdown}'

---

{% include feature_row %}

# Overview

Genomon enables us to perform sensitive and accurate detection of most types of genomic variants
(single nucleotide variants, short indels, mid-size (20bp - 300bp) indels and large scale structural variations),
and transcriptomic changes (gene fusions, aberrant splicing patterns),
and fairly good performance is demonstrated 
through [a large number of important cancer genome projects](http://www.ncbi.nlm.nih.gov/pubmed?term=(Ogawa%2C%20Seishi%5BAuthor%5D)%20AND%20Miyano%2C%20Satoru%5BAuthor%5D).


Genomon adopts efficient job scheduling framework that enables us easily analyzing several hundreds of 
genome and transcriptome sequencing data simultaneously.
Genomon is easy to install and after installing, 
users can start analysis just preparing simple sample configuration files.

Also, Genomon can be easily extensible and developers can freely re-distribute throught GPLv3 license.
