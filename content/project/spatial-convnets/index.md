---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Spatial Graph ConvNets"

summary: "Graph Neural Network architectures for inductive representation learning on arbitrary graphs."

authors: [vijay.dwivedi, chaitanya.joshi, xavier.bresson]

tags: [Deep Learning, Graph Neural Networks, Models, Spatial Graph ConvNets]

categories: [Models]

date: 2019-09-17T22:20:35+08:00

# Optional external URL for project (replaces project detail page).
external_link: ""

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Custom links (optional).
#   Uncomment and edit lines below to show custom links.
# links:
# - name: Follow
#   url: https://twitter.com
#   icon_pack: fab
#   icon: twitter

url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---

## Non-Euclidean and Graph-structured Data

Classic deep learning architectures such as [Convolutional Neural Networks (CNNs)](http://yann.lecun.com/exdb/publis/pdf/lecun-01a.pdf) and [Recurrent Neural Networks (RNNs)](https://www.bioinf.jku.at/publications/older/2604.pdf) require the input data domain to be regular, such as 2D or 3D Euclidean grids for Computer Vision and 1D lines for Natural Language Processing. 

However, most real-world data beyond images and language has an underlying structure that is **non-Euclidean**.
Such complex data commonly occurs in science and engineering, and can be modelled by heterogeneous graphs.
Examples include chemical graphs, computer graphics, social networks, genetics, neuroscience, and sensor networks.

![Graph structured data](graph-data.png)

---

## Graph Neural Networks

Graph-structured data can be large and complex (in the case of social networks, on the scale of billions), and is a natural target for machine learning applications. 
However, designing models for learning from non-Euclidean data is challenging as there are no familiar properties such as coordinate systems, vector space structure, or shift invariance.

**Graph/Geometric Deep Learning** is an umbrella term for emerging techniques attempting to generalize deep neural networks to non-Euclidean domains such as graphs and manifolds [[Bronstein *et al.*, 2017](https://arxiv.org/abs/1611.08097)].
We are interested to designing neural networks for graphs of arbitrary topologies and structures in order to solve generic graph problems, such as vertex classification, graph classification, graph regression, and graph generation.
These Graph Neural Network (GNN) architectures are used as backbones for challenging domain-specific applications in chemistry, social networks or graphics.

![GNN Layer](gnn-layer.png)
*GNNs iteratively build representations of graphs through recursive neighborhood aggregation (or message passing), where each graph node gathers features from its neighbors to represent local graph structure.*