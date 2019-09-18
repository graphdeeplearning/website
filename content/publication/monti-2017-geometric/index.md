---
title: "Geometric Matrix Completion with Recurrent Multi-Graph Neural Networks"
authors: ["Federico Monti", "Michael Bronstein", xavier.bresson]
date: 2017-01-01
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: 2019-09-17T00:46:25.621256Z

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent; 9 = Workshop Paper
publication_types: ["1"]

# Publication name
publication: "*Advances in Neural Information Processing Systems*"

abstract: "Matrix completion models are among the most common formulations of recommender systems. Recent works have showed a boost of performance of these techniques when introducing the pairwise relationships between users/items in the form of graphs, and imposing smoothness priors on these graphs. However, such techniques do not fully exploit the local stationary structures on user/item graphs, and the number of parameters to learn is linear wrt the number of users and items. We propose a novel approach to overcome these limitations by using geometric deep learning on graphs. Our matrix completion architecture combines a novel multi-graph convolutional neural network that can learn meaningful statistical graph-structured patterns from users and items, and a recurrent neural network that applies a learnable diffusion on the score matrix. Our neural network system is computationally attractive as it requires a constant number of parameters independent of the matrix size. We apply our method on several standard datasets, showing that it outperforms state-of-the-art matrix completion techniques."

# Summary. An optional shortened abstract.
summary: ""

tags:
- Deep Learning
- Graph Neural Networks
- Recommender Systems

featured: true

# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: https://papers.nips.cc/paper/6960-geometric-matrix-completion-with-recurrent-multi-graph-neural-networks.pdf
url_code: https://github.com/fmonti/mgcnn
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
- recommender-systems

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



