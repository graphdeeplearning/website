---
title: "An Experimental Study of Neural Networks for Variable Graphs"
authors:
- xavier.bresson
- "Thomas Laurent"
date: 2018-01-01
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: 2019-09-17T00:46:25.619962Z

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent; 9 = Workshop Paper
publication_types: ["3"]

# Publication name
publication: "*International Conference on Learning Representations (Workshop)*"

abstract: "Graph-structured data such as social networks, functional brain networks, chemical molecules have brought the interest in generalizing deep learning techniques to graph domains. In this work, we propose an empirical study of neural networks for graphs with variable size and connectivity. We rigorously compare several graph recurrent neural networks (RNNs) and graph convolutional neural networks (ConvNets) to solve two fundamental and representative graph problems, subgraph matching and graph clustering. Numerical results show that graph ConvNets are 3-17% more accurate and 1.5-4x faster than graph RNNs. Interestingly, graph ConvNets are also 36% more accurate than non-learning (variational) techniques. The benefit of such study is to show that complex architectures like LSTM is not useful in the context of graph neural networks, but one should favour architectures with minimal inner structures, such as locality, weight sharing, index invariance, multi-scale, gates and residuality, to design efficient novel neural network models for applications like drugs design, genes analysis and particle physics."

# Summary. An optional shortened abstract.
summary: ""

tags:
- Deep Learning
- Graph Neural Networks
- Spatial Graph ConvNets

featured: true

# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: https://openreview.net/pdf?id=SJexcZc8G
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
