---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Combinatorial Optimization"

summary: "Scalable deep learning systems for practical NP-Hard combinatorial problems such as the TSP."

authors: [chaitanya-joshi, xavier-bresson]

tags: [Deep Learning, Graph Neural Networks, Applications, Operations Research, Combinatorial Optimization]

categories: [Applications]

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


## Operations Research and Combinatorial Problems

**[Operations Research (OR)](https://en.wikipedia.org/wiki/Operations_research)** started in the first world war as an initiative to use mathematics and computer science to assist military planners in their decisions. Nowadays it is widely used in the industry, including but not limited to transportation, supply chain, energy, finance, and scheduling.

OR Problems are formulated as integer constrained optimization, *i.e.*, with integral or binary variables (called decision variables).
While not all such problems are hard to solve (*e.g.*, finding the shortest path between two locations), we concentrate on **[Combinatorial (NP-Hard) problems](https://en.wikipedia.org/wiki/Combinatorial_optimization)**. 
NP-Hard problems are *impossible* to solve optimally at large scales as exhaustively searching for their solutions is beyond the limits of modern computers.
The [Travelling Salesman Problem (TSP)](https://en.wikipedia.org/wiki/Travelling_salesman_problem) and the [Minimum Spanning Tree Problem (MST)](https://en.wikipedia.org/wiki/Minimum_spanning_tree) are two of the most popular examples for such problems defined using graphs.

![TSP GIF](tsp-gif.gif)
*TSP asks the following question: Given a list of cities and the distances between each pair of cities, what is the shortest possible route that visits each city and returns to the origin city? Formally, given a graph, one needs to search the space of permutations to find an optimal sequence of nodes, called a tour, with minimal total edge weights (tour length).*

---

## Neural Combinatorial Optimization

Although handcrafted heuristic algorithms are able to solve problems such as TSP with up to a million variables,
designing good heuristics often requires significant specialized knowledge and years of trial-and-error.
The state-of-the-art TSP solver, [Concorde](http://www.math.uwaterloo.ca/tsp/concorde.html), leverages [over 50 years of research](https://www.youtube.com/watch?v=q8nQTNvCrjE) on linear programming, cutting plane algorithms and branch-and-bound.
At our lab, we're working on **automating** and **augmenting** such expert intuition through Machine Learning [[Bengio *et al.*, 2018](https://arxiv.org/abs/1811.06128)].

Since most problems are highly structured, heuristics take the form of rules or policies to make sequential decisions, *e.g.*, determine the TSP tour one city at a time. 
Our research uses deep neural networks to parameterize these policies and train them directly from problem instances.
In particular, **Graph Neural Networks** are the perfect fit for the task because they naturally operate on the graph structure of these problems.

![End-to-end pipeline](pipeline.png)
