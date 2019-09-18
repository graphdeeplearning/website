---
title: "Convolutional Neural Networks on Graphs with Fast Localized Spectral Filtering"
authors: ["Michaël Defferrard", xavier.bresson, "Pierre Vandergheynst"]
date: 2016-01-01
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

abstract: "In this work, we are interested in generalizing convolutional neural networks (CNNs) from low-dimensional regular grids, where image, video and speech are represented, to high-dimensional irregular domains, such as social networks, brain connectomes or words’ embedding, represented by graphs. We present a formulation of CNNs in the context of spectral graph theory, which provides the necessary mathematical background and efficient numerical schemes to design fast localized convolutional filters on graphs. Importantly, the proposed technique offers the same linear computational complexity and constant learning complexity as classical CNNs, while being universal to any graph structure. Experiments on MNIST and 20NEWS demonstrate the ability of this novel deep learning system to learn local, stationary, and compositional features on graphs."

# Summary. An optional shortened abstract.
summary: ""

tags:
- Deep Learning
- Graph Neural Networks
- Spectral Graph ConvNets

featured: true

# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: http://papers.nips.cc/paper/6081-convolutional-neural-networks-on-graphs-with-fast-localized-spectral-filtering.pdf
url_code: https://github.com/xbresson/spectral_graph_convnets
url_video: https://www.youtube.com/watch?v=cIA_m7vwOVQ
url_slides: https://doi.org/10.5281/zenodo.1318411
url_poster: https://zenodo.org/record/1318420

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
- spectral-convnets

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---
