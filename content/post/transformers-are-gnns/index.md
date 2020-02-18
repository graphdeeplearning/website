---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Transformers are Graph Neural Networks"
subtitle: ""
summary: ""

authors: [chaitanya.joshi]

tags:
- Deep Learning
- Graph Neural Networks
- Transformer

categories: []

date: 2020-02-12T16:08:39+08:00
lastmod: 2020-02-12T16:08:39+08:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects:
- spatial-convnets
---

<!-- 
Research friends ask: what are some success stories of GNNs being practical? Besides the usual recommender systems and drug design, a slightly nuanced application is the Transformer architecture, an architecture which has seen rapid adoption in NLP for its advantages over RNNs.

Bataglia 
Dgl tutorials and papers from team
Our graph transformer paper

Are fc graphs the best representation
Is working on fc graphs somehow akin to learning the graph structure, and thus discovering syntax (link to chris manning work, google brain work)

What choice of attention mechanisim is best (Luong investigated this years ago, but not in context of multi head models)
What are multiple heads doing? Do they help with bad init, or do they look at different aspects or facilitate different types of messages to propogate?
What is the overparameterized FC layer? Why is that the only place where they use non-linearities?
Can we use ideas such as MHA and Pw-FF in designing more powerful GNNs? E.g. can we benefit from encoding graph features such as node degree akin to position encodings in text? E.g.2. can we use BERT style special tokens at each layer to build represenations of sub-graphs/graphs?
Why did they decide on a particular way of doing batch norm after residual conex? And is that why we need warmup?


Here are some nice resources to get you started w/ Graph Transformers!

 

In the context of NLP and Machine Translation
Original paper: https://arxiv.org/abs/1706.03762
Helpful blogpost: http://nlp.seas.harvard.edu/2018/04/03/attention.html
http://jalammar.github.io/illustrated-transformer/
https://github.com/sannykim/transformers
Helpful YouTube video: https://www.youtube.com/watch?v=iDulhoQ2pro&t=3s
Generic mathematical/graph formulation as ‘attention on fully-connected graphs’
Arthur Szlam’s talk: https://ipam.wistia.com/medias/1zgl4lq6nh
Graph Attention Network: https://arxiv.org/abs/1710.10903


 -->