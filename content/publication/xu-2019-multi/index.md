---
title: "Multi-Graph Transformer for Free-Hand Sketch Recognition"
authors: [peng.xu, chaitanya.joshi, xavier.bresson]
date: 2019-12-24
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: 2020-01-14T16:08:24+08:00

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["3"]

# Publication name
publication: "*arXiv preprint arXiv:1912.11258*"

abstract: "Learning meaningful representations of free-hand sketches remains a challenging task given the signal sparsity and the high-level abstraction of sketches. Existing techniques have focused on exploiting either the static nature of sketches with Convolutional Neural Networks (CNNs) or the temporal sequential property with Recurrent Neural Networks (RNNs). In this work, we propose a new representation of sketches as multiple sparsely connected graphs. We design a novel Graph Neural Network (GNN), the Multi-Graph Transformer (MGT), for learning representations of sketches from multiple graphs which simultaneously capture global and local geometric stroke structures, as well as temporal information. We report extensive numerical experiments on a sketch recognition task to demonstrate the performance of the proposed approach. Particularly, MGT applied on 414k sketches from Google QuickDraw: (i) achieves small recognition gap to the CNN-based performance upper bound (72.80% vs. 74.22%), and (ii) outperforms all RNN-based models by a significant margin. To the best of our knowledge, this is the first work proposing to represent sketches as graphs and apply GNNs for sketch recognition."

# Summary. An optional shortened abstract.
summary: ""

tags:
- Deep Learning
- Computer Vision
- Graph Neural Networks
- Sketches
- Transformer

featured: false

links:
# - name: Blog
#   url: 

url_pdf: https://arxiv.org/pdf/1912.11258.pdf
url_code: https://github.com/PengBoXiangShang/multigraph_transformer
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: ''


# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects:
- sketches

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---
