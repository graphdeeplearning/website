---
title: "Learning TSP Requires Rethinking Generalization"
authors:
- chaitanya-joshi
- "Quentin Cappart"
- "Louis-Martin Rousseau"
- "Thomas Laurent"
- xavier-bresson
date: 2020-06-12
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: 2020-06-17T00:46:25.621256Z

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent; 9 = Workshop Paper
publication_types: ["3"]

# Publication name
publication: "*arXiv preprint arXiv:2006.07054*"

abstract: "End-to-end training of neural network solvers for combinatorial problems such as the Travelling Salesman Problem is intractable and inefficient beyond a few hundreds of nodes. While state-of-the-art Machine Learning approaches perform closely to classical solvers for trivially small sizes, they are unable to generalize the learnt policy to larger instances of practical scales. Towards leveraging transfer learning to solve large-scale TSPs, this paper identifies inductive biases, model architectures and learning algorithms that promote generalization to instances larger than those seen in training. Our controlled experiments provide the first principled investigation into such zero-shot generalization, revealing that extrapolating beyond training data requires rethinking the entire neural combinatorial optimization pipeline, from network layers and learning paradigms to evaluation protocols."

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

url_pdf: https://arxiv.org/pdf/2006.07054.pdf
url_code: https://github.com/chaitjo/learning-tsp
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: ''

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
