---
title: "Residual Gated Graph ConvNets"
authors:
- xavier-bresson
- "Thomas Laurent"
date: 2017-01-01
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: 2019-09-17T00:46:25.620574Z

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent; 9 = Workshop Paper
publication_types: ["3"]

# Publication name
publication: "*arXiv preprint arXiv:1711.07553*"

abstract: "Graph-structured data such as social networks, functional brain networks, gene regulatory networks, communications networks have brought the interest in generalizing deep learning techniques to graph domains. In this paper, we are interested to design neural networks for graphs with variable length in order to solve learning problems such as vertex classification, graph classification, graph regression, and graph generative tasks. Most existing works have focused on recurrent neural networks (RNNs) to learn meaningful representations of graphs, and more recently new convolutional neural networks (ConvNets) have been introduced. In this work, we want to compare rigorously these two fundamental families of architectures to solve graph learning tasks. We review existing graph RNN and ConvNet architectures, and propose natural extension of LSTM and ConvNet to graphs with arbitrary size. Then, we design a set of analytically controlled experiments on two basic graph problems, ie subgraph matching and graph clustering, to test the different architectures. Numerical results show that the proposed graph ConvNets are 3-17% more accurate and 1.5-4x faster than graph RNNs. Graph ConvNets are also 36% more accurate than variational (non-learning) techniques. Finally, the most effective graph ConvNet architecture uses gated edges and residuality. Residuality plays an essential role to learn multi-layer architectures as they provide a 10% gain of performance."

# Summary. An optional shortened abstract.
summary: ""

tags:
- Deep Learning
- Graph Neural Networks
- Spatial Graph ConvNets

featured: false

# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: https://arxiv.org/pdf/1711.07553
url_code: https://github.com/xbresson/spatial_graph_convnets
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: 'http://helper.ipam.ucla.edu/publications/dlt2018/dlt2018_14506.pdf'
url_source: ''
url_video: 'https://www.youtube.com/watch?v=v3jZRkvIOIM'

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects:
- spatial-convnets

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---
