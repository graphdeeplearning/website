---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Spatial Graph ConvNets"

summary: "Graph Neural Network architectures for inductive representation learning on arbitrary graphs."

authors: [chaitanya-joshi, vijay-dwivedi, xavier-bresson]

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
We are interested to designing neural networks for graphs of arbitrary topologies and structures in order to solve *generic* graph problems, such as vertex classification, graph classification, graph regression, and graph generation.

These Graph Neural Network (GNN) architectures are used as backbones for challenging domain-specific applications in a myriad of domains, including chemistry, social networks, recommendations and computer graphics.

---

## Basic Formalism

Each GNN layer computes $d$-dimensional representations for the nodes/edges of the graph through recursive neighborhood diffusion (or message passing), where each graph node gathers features from its neighbors to represent local graph structure.
Stacking $L$ GNN layers allows the network to build node representations from the **$L$-hop neighborhood** of each node.

![GNN Layer](gnn-layer.png)

Let $h_i^{\ell}$ denote the feature vector at layer $\ell$ associated with node $i$.
The updated features $h_i^{\ell+1}$ at the next layer $\ell+1$ are obtained by applying non-linear transformations to the central feature vector $h_i^{\ell}$ and the feature vectors $h_{j}^{\ell}$ for all nodes $j$ in the neighborhood of node $i$ (defined by the graph structure). 
This guarantees the transformation to build local reception fields, such as in standard ConvNets for computer vision, and be invariant to both graph size and vertex re-indexing.

Thus, the most generic version of a feature vector $h_i^{\ell+1}$ at vertex $i$ at the next layer in the graph network is:
\begin{equation} 
    h_{i}^{\ell+1} =  f \left( \ h_i^{\ell} \  , \ \{ h_{j}^{\ell}: j \rightarrow i \}  \ \right) ,
\end{equation}
where $\{ j \rightarrow i \}$ denotes the set of neighboring nodes $j$ pointed to node $i$, which can be replaced by $\{ j \in \mathcal{N}_i \}$, the set of neighbors of node $i$, if the graph is undirected. In other words, a GNN is defined by a mapping $f$ taking as input a vector $h_i^{\ell}$ (the feature vector of the center vertex) as well as an un-ordered set of vectors $\{ h_{j}^{\ell}\}$ (the feature vectors of all neighboring vertices). 

The arbitrary choice of the mapping $f$ defines an instantiation of a class of GNNs, *e.g.*, [GraphSage](https://arxiv.org/abs/1706.02216), [MoNet](https://arxiv.org/abs/1611.08402), [GAT](https://arxiv.org/abs/1710.10903), etc.
For an illustration, here's a simple-yet-effective Graph ConvNet from [Sukhbaatar *et al.*, 2016](https://arxiv.org/abs/1605.07736):
\begin{equation}
    h_{i}^{\ell+1} = \text{ReLU} \Big( U^{\ell} h_{i}^{\ell} + \sum_{j \in \mathcal{N}_i} V^{\ell} h_{j}^{\ell} \Big),
\end{equation}
where $U^{\ell}, V^{\ell} \in \mathbb{R}^{d \times d}$ are the learnable parameters.
