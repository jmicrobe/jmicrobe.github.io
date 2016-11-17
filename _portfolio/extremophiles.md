---
layout: portfolio
title: "novel extremophiles: cladogram construction"
image_path: /public/images_portfolio/finaltree_forpaper.png
weight: 4
---

## Background

My first introduction to bioinformatics was during my undergraduate research thesis, and the experiences I had inspired me to pursue more computational work for my graduate studies. For my thesis I used traditional laboratory and genomic techniques to characterize a novel bacteria isolate.

This bacterium, referred to as Eh-2, was collected from the intersection of a hot spring and an alkaline lake in Ethiopia. While in the lab I was conducting growth rate studies, I also was interested in it's 16S rRNA phylogeny. Based on 75% coverage of the gene and a BLAST query, Eh-2 was only 95% similar to one other organism in culture.

Constructing the 16S rRNA phylogenetic tree was an interesting experience for me as a junior scientist. I was mentored by a post-doc in my lab and learned that there wasn't a single, standard way to create a tree, and that the process took a bit of careful pruning, preparation, and multiple programs to create.

## Methods

This tree was generated through *several* steps:

+ ARB was used to locate both similar as well as more "rooted" organisms (using the SILVA database)
+ 16S rRNA sequences of these organisms were gathered from the NCBI Database
+ RAxML was used to construct the newick-formatted tree
+ MEGA was used to image and design the tree
+ Additional formatting of species names was done using Inkscape

## Results

<img src="/public/images_portfolio/finaltree_forpaper.png" alt="16s rRNA phylogenetic tree" width="100%" />

The above cladogram was generated with my previously mentioned methods. It was included in my undergraduate honors thesis, and included in presentations for both the Oregon NASA Consortium and the Portland State University McNair Scholars Symposium.

## Future

I really enjoyed learning about the well-crafted art of phylogenetic tree construction, and have gone on to learn from other mentors that this is an often opinionated field of work. In the future I would use RAxML, but would probably seek out more up-to-date, open-source tools for the rest of the pipeline.
