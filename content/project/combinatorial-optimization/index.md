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
  preview_only: true

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


**[Operations Research (OR)](https://en.wikipedia.org/wiki/Operations_research)** started in the first world war as an initiative to use mathematics and computer science to assist military planners in their decisions.
Today, combinatorial optimization algorithms developed in the OR community form the backbone of the most important modern industries including transportation, logistics, scheduling, finance and supply chains.

OR Problems are formulated as integer constrained optimization, *i.e.*, with integral or binary variables (called decision variables).
While not all such problems are hard to solve (*e.g.*, finding the shortest path between two locations), we concentrate on **[Combinatorial (NP-Hard) problems](https://en.wikipedia.org/wiki/Combinatorial_optimization)**. 
NP-Hard problems are *impossible* to solve optimally at large scales as exhaustively searching for their solutions is beyond the limits of modern computers.
The [Travelling Salesman Problem (TSP)](https://en.wikipedia.org/wiki/Travelling_salesman_problem) and the [Minimum Spanning Tree Problem (MST)](https://en.wikipedia.org/wiki/Minimum_spanning_tree) are two of the most popular examples for such problems defined using graphs.

![TSP GIF](tsp-gif.gif)
*TSP asks the following question: Given a list of cities and the distances between each pair of cities, what is the shortest possible route that visits each city and returns to the origin city? Formally, given a graph, one needs to search the space of permutations to find an optimal sequence of nodes, called a tour, with minimal total edge weights (tour length).*

---

## Neural Combinatorial Optimization

Solvers and heuristic algorithms developed in the OR community are able to solve classical problems such as TSP with up to millions of variables.
However, designing powerful and robust optimization algorithms requires significant **specialized knowledge** and years of **trial-and-error**, especially for understudied but high-impact problems arising in [scientific discovery](https://arxiv.org/abs/2003.11755) or [computer architecture](https://arxiv.org/abs/1911.05289).
The state-of-the-art TSP solver, [Concorde](http://www.math.uwaterloo.ca/tsp/concorde.html), leverages [over 50 years of research](https://www.youtube.com/watch?v=q8nQTNvCrjE) on linear programming, cutting plane algorithms and branch-and-bound.

{{% alert note %}}
At our lab, we're working on **automating** and **augmenting** such expert intuition through Machine Learning [[Bengio *et al.*, 2018](https://arxiv.org/abs/1811.06128)].
{{% /alert %}}

Since most problems are highly structured, heuristics take the form of rules or policies to make sequential decisions, *e.g.*, determine the TSP tour one city at a time. 
Our research uses deep neural networks to parameterize these policies and train them directly from problem instances.
In particular, **Graph Neural Networks** are the perfect fit for the task because they naturally operate on the graph structure of these problems.

![End-to-end pipeline](pipeline.png)
*A generic five-stage pipeline for end-to-end learning of combinatorial problems on graphs*

---

## Why study TSP in particular?

(1) The problem has an amazing history of serving as an **engine of discovery** for applied mathematics, with several [legendary](https://en.wikipedia.org/wiki/John_von_Neumann) [computer](https://en.wikipedia.org/wiki/Richard_E._Bellman) [scientists](https://en.wikipedia.org/wiki/George_Dantzig) and [mathematicians](https://en.wikipedia.org/wiki/Edsger_W._Dijkstra) having a crack at it. Here's an [amazing talk](https://www.youtube.com/watch?v=q8nQTNvCrjE) by William Cook, the co-inventor of the current state-of-the-art Concorde TSP solver.

(2) TSP has been the focus of intense research in the combinatorial optimization community. If you come up with a new solver, *e.g.*, a learning-driven solver, you *need* to benchmark it on TSP. TSP’s **multi-scale nature** makes it a challenging graph task which requires reasoning about both local node neighborhoods as well as global graph structure.

(3) Learning-based approaches for heuristic algorithms have the potential to be a breakthrough for OR if they are able to  learn efficiently on small scale problems and then generalize robustly to larger instances. 
However, such *scale-invariant* generalization is an exciting and unsolved challenge, not just for TSP, but for machine learning as a whole. 
**Update:** We explore this in our [latest paper](https://arxiv.org/abs/2006.07054)!

![XKCD:TSP](https://imgs.xkcd.com/comics/travelling_salesman_problem.png)

---

At the same time, the more *profound* motivation of using deep learning for combinatorial optimization is not to outperform classical approaches on well-studied problems. 
Neural networks can be used as a general tool for tackling previously *un-encountered* NP-hard problems, especially those that are **non-trivial to design heuristics for** [[Bello *et al.*, 2016](https://arxiv.org/abs/1611.09940)].
We are excited about recent applications of neural combinatorial optimization for [accelarating drug discovery](https://deepmind.com/blog/article/AlphaFold-Using-AI-for-scientific-discovery), [optimizing operating systems](https://arxiv.org/abs/1910.01578) and [designing computer chips](https://arxiv.org/abs/2004.10746).

---

**P.S.** XB is organizing an exciting workshop at IPAM titled ["Deep Learning and Combinatorial Optimization"](http://www.ipam.ucla.edu/programs/workshops/deep-learning-and-combinatorial-optimization/).

