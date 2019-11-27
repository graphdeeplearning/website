---
title: "An Efficient Graph Convolutional Network Technique for the Travelling Salesman Problem"
authors:
- chaitanya.joshi
- "Thomas Laurent"
- xavier.bresson
date: 2019-01-01
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: 2019-09-17T00:46:25.621256Z

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent; 9 = Workshop Paper
publication_types: ["3"]

# Publication name
publication: "*arXiv preprint arXiv:1906.01227*"

abstract: "This paper introduces a new learning-based approach for approximately solving the Travelling Salesman Problem on 2D Euclidean graphs. We use deep Graph Convolutional Networks to build efficient TSP graph representations and output tours in a non-autoregressive manner via highly parallelized beam search. Our approach outperforms all recently proposed autoregressive deep learning techniques in terms of solution quality, inference speed and sample efficiency for problem instances of fixed graph sizes. In particular, we reduce the average optimality gap from 0.52% to 0.01% for 50 nodes, and from 2.26% to 1.39% for 100 nodes. Finally, despite improving upon other learning-based approaches for TSP, our approach falls short of standard Operations Research solvers."

# Summary. An optional shortened abstract.
summary: ""

tags:
- Deep Learning
- Graph Neural Networks
- Operations Research
- Combinatorial Optimization
- Travelling Salesman Problem

featured: false

# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: https://arxiv.org/pdf/1906.01227
url_code: https://github.com/chaitjo/graph-convnet-tsp
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: 'http://helper.ipam.ucla.edu/publications/glws4/glws4_16076.pdf'
url_source: ''
url_video: 'http://www.ipam.ucla.edu/abstract/?tid=16076&pcode=GLWS4'

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
- combinatorial-optimization

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---

