---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Free-hand Sketches"

summary: "Representation learning for drawings via graphs with geometric and temporal information."

authors: [chaitanya.joshi, peng.xu, xavier.bresson]

tags: [Deep Learning, Computer Vision, Graph Neural Networks, Applications, Sketches]

categories: [Applications]

date: 2020-01-14T16:19:27+08:00

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

## Representation Learning for Sketches

Human beings have been creating free-hand sketches, *i.e.*, drawings without precise instruments, since [time immemorial](https://en.wikipedia.org/wiki/Cave_painting).
Due to the popularity of touchscreen interfaces, machine learning using sketches has emerged as an interesting problem with a myriad of applications:
If we consider sketches as 2D images, we can throw them into off-the-shelf [Convolutional Neural Networks (CNNs)](https://arxiv.org/abs/1501.07873).
While CNNs are designed for *static* collections of pixels with *dense* colors and textures,
sketches are usually an extremely *sparse* sequences of strokes which capture high-level abstractions and ideas. [Recurrent Neural Networks (RNNs)](https://ai.googleblog.com/2017/04/teaching-machines-to-draw.html) stick out as a natural architecture for capturing this temporal nature of sketches.

>*Structure vs. temporal order: can we have the best of both worlds?*

## Sketches as Graphs

We are working on a novel representation of free-hand sketches as **sparsely-connected graphs**. 
We assume that sketches are sets of curves and strokes, which are discretized by a set of points representing the graph nodes.
Each node encodes spatial, temporal and semantic information.
Thus, representing sketches with graphs offers a universal representation that can make use of both the sketch structure (like images) as well as temporal information (like stroke sequences).
To exploit these graph structures, we are developing **Graph Neural Networks (GNNs)** based on the Transformer model [[*Vaswani et al.*, 2017]](https://arxiv.org/abs/1706.03762). 
