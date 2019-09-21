---
title: "A Two-Step Graph Convolutional Decoder for Molecule Generation"
authors:
- xavier.bresson
- "Thomas Laurent"
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
publication: "*arXiv preprint arXiv:1906.03412*"

abstract: "We propose a simple auto-encoder framework for molecule generation. The molecular graph is first encoded into a continuous latent representation , which is then decoded back to a molecule. The encoding process is easy, but the decoding process remains challenging. In this work, we introduce a simple two-step decoding process. In a first step, a fully connected neural network uses the latent vector  to produce a molecular formula, for example CO (one carbon and two oxygen atoms). In a second step, a graph convolutional neural network uses the same latent vector  to place bounds between the atoms that were produced in the first step (for example a double bound will be placed between the carbon and each of the oxygens). This two-step process, in which a bag of atoms is first generated, and then assembled, provides a simple framework that allows us to develop an efficient molecule auto-encoder. Numerical experiments on basic tasks such as novelty, uniqueness, validity and optimized chemical property for the 250k ZINC molecules demonstrate the performances of the proposed system. Particularly, we achieve the highest reconstruction rate of 90.5%, improving the previous rate of 76.7%. We also report the best property improvement results when optimization is constrained by the molecular distance between the original and generated molecules."

# Summary. An optional shortened abstract.
summary: ""

tags:
- Deep Learning
- Graph Neural Networks
- Chemistry
- Molecule Generation

featured: false

# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: https://arxiv.org/pdf/1906.03412
url_code: ''
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
- chemistry

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---
