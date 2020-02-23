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
  preview_only: true

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects:
- spatial-convnets

markup: mmark
---


Engineer friends often ask me: Graph Deep Learning sounds great, but are there any big compercial success stories? Is it being deployed in practical applications?

Besides the obvious ones--recommendation systems at [Pinterest](https://medium.com/pinterest-engineering/pinsage-a-new-graph-convolutional-neural-network-for-web-scale-recommender-systems-88795a107f48), [Alibaba](https://arxiv.org/abs/1902.08730) and [Twitter](https://blog.twitter.com/en_us/topics/company/2019/Twitter-acquires-Fabula-AI.html)--a slightly nuanced success story is the [**Transformer architecture**](https://arxiv.org/abs/1706.03762), which has [taken](https://openai.com/blog/better-language-models/) [the](https://www.blog.google/products/search/search-language-understanding-bert/) [NLP](https://www.microsoft.com/en-us/research/project/large-scale-pretraining-for-response-generation/) [industry](https://ai.facebook.com/blog/roberta-an-optimized-method-for-pretraining-self-supervised-nlp-systems/) [by](https://blog.einstein.ai/introducing-a-conditional-transformer-language-model-for-controllable-generation/) [storm](https://nv-adlr.github.io/MegatronLM).

Through this post, I want to establish links between [Graph Neural Networks (GNNs)](({{<ref "/project/spatial-convnets/index.md">}})) and Transformers.
I'll talk about the intuitions behind model architectures in the NLP and GNN communities, make connections using equations and figures, and discuss how we could work together to drive progress.

Let's start by talking about the purpose of model architectures--*representation learning*.

---

### Representation Learning for NLP

At a high level, all neural network architectures build *representations* of input data, which encode useful statistical and semantic information about the data.
These *latent* or *hidden* representations can then be used for performing something useful, such as classifying an image or translating a sentence.
The neural network can then *learn* to build better-and-better representations by recieving feedback, usually via error/loss functions.    

For Natural Language Processing (NLP), conventionally, **Recurrent Neural Networks** (RNNs) build representations of each word in a sentence in a sequential manner, *i.e.*, **one word at a time**. 
Intuitively, we can imagine an RNN layer as a conveyor belt, with the words being processed on it *autoregressively* from left to right.
At the end, we get a hidden feature for each word in the sentence, which we pass to the next RNN layer or use for our NLP tasks of choice.

> *I highly recommend Chris Olah's legendary blog for recaps on [RNNs](http://colah.github.io/posts/2015-08-Understanding-LSTMs/) and [representation learning](http://colah.github.io/posts/2014-07-NLP-RNNs-Representations/) for NLP.*

![RNNs/Transformers for NLP tasks](rnn-transf-nlp.jpg)

Initially introduced for machine translation, **Transformers** has gradually replaced RNNs in mainstream NLP. 
The architecture takes a fresh approach to representation learning: Doing away with recurrence entirely, Transformers build features of each word using an *[attention](https://distill.pub/2016/augmented-rnns/) [mechanism](https://lilianweng.github.io/lil-log/2018/06/24/attention-attention.html)* to figure out how important **all the other words** in the sentence are w.r.t. to the aforementioned word.
Knowing this, the word's updated features are simply the sum of linear transformations of the features of all the words, weighted by their importace. 

> *Back in 2017, this idea sounded very radical, because the NLP community was so used to the sequential--one-word-at-a-time--style of processing text with RNNs. The title of the paper probably added fuel to the fire! 
For a recap, Yannic Kilcher made an excellent [video overview](https://www.youtube.com/watch?v=iDulhoQ2pro).*

---

### Breaking down the Transformer

Translating the previous paragraph into the language of mathematical symbols and vectors, we update the hidden feature $h$ of the $i$'th word in a sentence $\mathcal{S}$ from layer $\ell$ to layer $\ell+1$ as follows:

$$
h_{i}^{\ell+1} = \text{Attention} \left( Q^{\ell} h_{i}^{\ell} \;, K^{\ell} h_{j}^{\ell} \;, V^{\ell} h_{j}^{\ell} \right), \\
i.e.,\;\ h_{i}^{\ell+1} = \sum_{j \in \mathcal{S}} w_{ij} \left( V^{\ell} h_{j}^{\ell} \right), \\ 
\text{where} \;\ w_{ij} = \text{softmax}_j \left( Q^{\ell} h_{i}^{\ell} \cdot  K^{\ell} h_{j}^{\ell} \right), 
$$

where $Q^{\ell}, K^{\ell}, V^{\ell}$ are learnable linear weights (denoting the **Q**uery, **K**ey and **V**alue for the attention computation, respectively).
The attention mechanism is performed parallely for each word in the sentence to obtain their updated features in *one shot*--another plus point for Transformers over RNNs, which update features word-by-word.

We can understand the attention mechanism better through the following pipeline:

{{< figure src="attention-block.jpg" title="" lightbox="true" width="350px">}}
> *Taking in the features of the word $h_{i}^{\ell}$ and the set of other words in the sentence $\{ h_{j}^{\ell} \;\ \forall j \in \mathcal{S} \}$, we compute the attention weights $w_{ij}$ for each pair $(i,j)$ through the dot-product, followed by a softmax across all $j$'s. Finally, we produce the updated word feature $h_{i}^{\ell+1}$ for word $i$ by summing over all $\{ h_{j}^{\ell} \}$'s weighted by their corresponding $w_{ij}$. Each word in the sentence parallely undergoes the same pipeline to update its features.*

#### Multi-head Attention mechanism

Getting this dot-product attention mechanism to work proves to be tricky--bad random initializations can de-stabilize the learning process. 
We can overcome this by parallely performing multiple *'heads'* of attention and concatenating the result (with each head now having separate learnable  weights):

$$
h_{i}^{\ell+1} = \text{Concat} \left( \text{head}_1, \ldots, \text{head}_K \right) O^{\ell}, \\
\text{head}_k = \text{Attention} \left(  Q^{k,\ell} h_{i}^{\ell} \;, K^{k, \ell} h_{j}^{\ell} \;, V^{k, \ell} h_{j}^{\ell} \right),
$$

where $Q^{k,\ell}, K^{k,\ell}, V^{k,\ell}$ are the learnable weights of the $k$'th attention head and $O^{\ell}$ is a down-projection to match the dimensions of $h_i^{\ell+1}$ and $h_i^{\ell}$. 
Multiple heads allow the attention mechanism to essentially *'hedge its bets'*, looking at different transformations or aspects of the hidden features from the previous layer.
We'll talk more about this later.

#### Scale issues and the Feed-forward sub-layer

A key issue motivating the final Transformer architecture is that the features for words *after* the attention mechanism might be at **different scales** or **magnitudes**:
(1) Some words may have very sharp or very distributed attention weights $w_{ij}$ when summing over the features of the other words.
(2) At the individual feature/vector entries level, concatenating across multiple attention heads--each of which might output values at different scales--can lead to the entries of the final vector $h_{i}^{\ell+1}$ having a wide range of values. 
Following conventional ML wisdom, it seems reasonable to add a [normalization layer](https://nealjean.com/ml/neural-network-normalization/) into the pipeline.

Transformers overcome issue (2) with [**LayerNorm**](https://arxiv.org/abs/1607.06450), which normalizes and learns an affine transformation at the feature level. 
Additionally, **scaling the dot-product** attention by the square-root of the dimension of the feature vectors involved helps counteract issue (1).

Finally, the authors propose another *'trick'* to control the scale issue: **a position-wise 2-layer MLP** with a very special structure. 
After the multi-head attention, they project $h_i^{\ell+1}$ to a (absurdly) higher dimension by a learnable weight, where it undergoes the ReLU non-linearity, and is then projected back to its original dimension followed by another normalization:

$$
h_i^{\ell+1} = \text{LN} \left( \text{MLP} \left( \text{LN} \left( h_i^{\ell+1} \right) \right) \right)
$$

> *To be honest, I'm not sure what the exact intuition behind the over-parameterized feed-forward sub-layer was and, frankly, nobody seems to be asking questions about it, too! I suppose LayerNorm and scaled dot-products didn't completely solve the issues highlighted, thus the big MLP is a sort of hack to re-scale the feature vectors independently of each other.*

> *[Email me](mailto:chaitanya.joshi@ntu.edu.sg) if you know more.*

The final picture of a Transformer layer looks like this:

{{< figure src="transformer-block.jpg" title="" lightbox="true" width="380px">}}

The Transformers architecture is also extremely ammenable to very deep networks, enabling the NLP community to *[scale](https://arxiv.org/abs/1910.10683) [up](https://arxiv.org/abs/2001.08361)* in terms of both model parameters and, by extension, data. 
**Residual connections** between the inputs and outputs of each multi-head attention sub-layer and the feed-forward sub-layer are key for stacking Transformer layers (but ommited from the diagram for clarity). 

---

### GNNs build representations of graphs

Let's take a step back: Graph Neural Networks (GNNs) or Graph Convolutional Networks (GCNs) build representations of nodes and edges in graph data. 
They do so through **neighborhood aggregation** (or message passing), where each node gathers features from its neighbors to update its represention of the *local* graph structure around it.
Stacking several GNN layers enables the model to propagate each node's features over the entire graph--from its neighbors to the neighbors' neighbors, and so on.

![GNNs for social network applications](gnn-social-network.jpg)
> *Take the example of this emoji social network: The node features produced by the GNN can be used for predictive tasks such as identifying the most influential members or proposing potential connections.*

In their most basic form, GNNs update the hidden features $h$ of node $i$ (for example, :laughing:) at layer $\ell$ via a non-linear transformation of the node's own features $h_i^{\ell}$ added to the aggreagation of features $h_j^{\ell}$ from each neighboring node $j \in \mathcal{N}(i)$:

$$ 
h_{i}^{\ell+1} =  \sigma \Big( U^{\ell} h_{i}^{\ell} + \sum_{j \in \mathcal{N}(i)} \left( V^{\ell} h_{j}^{\ell} \right)  \Big),
$$

where $U^{\ell}, V^{\ell}$ are learnable weight matrices of the GNN layer and $\sigma$ is a non-linearity such as ReLU.
In the example, $\mathcal{N}(\text{:laughing:}) = \{\text{:kissing_heart:, 😎, :stuck_out_tongue_winking_eye:, 🤩}\} $.

The summation over the neighborhood nodes $j \in \mathcal{N}(i)$ can be replaced by other input size-invariant **aggregation functions** such as simple mean/max or something more powerful, such as a weighter sum via [an attention mechanism](https://petar-v.com/GAT/).

Does that sound familiar?

Maybe a pipeline will help make the connection:

{{< figure src="gnn-block.jpg" title="" lightbox="true" width="320px">}}

> *If we were to do multiple parallel heads of neighborhood aggregation and replace summation over the neighbors $j$ with the attention mechanism, i.e., a weighted sum, we'd get the <b>Graph Attention Network</b>. Add normalization and the feed-forward MLP, and voila, we have a <b>Graph Transformer</b>!*

---

### Sentences are fully-connected word graphs

To make the connection more explicit, consider a sentence as a fully-connected graph, where each word is connected to every other word.
Now, we can use a GNN to build features for each node (word) in the graph (sentence), which we can then perform NLP tasks with. 

![GNNs for NLP tasks](gnn-nlp.jpg)

Broadly, this is what Transformers are doing: they are **GNNs with multi-head attention** as the neighborhood aggregation function. 

<!-- 
Are fc graphs the best representation - chosky linguists worked on tres/ which are als graph structs
-- dgl sparse transformer can be faster, maybe we don't need to do full attention

Is working on fc graphs somehow akin to learning the graph structure, and thus discovering syntax (link to chris manning work, google brain work)


What choice of attention mechanisim is best (Luong investigated this years ago, but not in context of multi head models)

What are multiple heads doing? Do they help with bad init, or do they look at different aspects or facilitate different types of messages to propogate?
-- how can they hellp in gnns
-- why we don't need them in gnns other than gat?
-- can we then use other simpler aggre fucntions for nlp, too?

What is the overparameterized FC layer? Why is that the only place where they use non-linearities?

Can we use ideas such as MHA and Pw-FF in designing more powerful GNNs? E.g. can we benefit from encoding graph features such as node degree akin to position encodings in text? 

E.g.2. can we use BERT style special tokens at each layer to build represenations of sub-graphs/graphs?

Why did they decide on a particular way of doing batch norm after residual conex? And is that why we need warmup?
--we do it differrently for gnns and we are able to stack many layers, too

 -->


---

### Diving Deeper

To dive deep into the Transformer architecture from an NLP perspective, check out these amazing blog posts: [The Illustrated Transformer](http://jalammar.github.io/illustrated-transformer/) and [The Annotated Transformer](http://nlp.seas.harvard.edu/2018/04/03/attention.html).
Also, this blog isn't the first to link GNNs and Transformers:
Here's [an excellent talk](https://ipam.wistia.com/medias/1zgl4lq6nh) by Arthur Szlam on the history and connection between Attention/Memory Networks, GNNs and Transformers.
Similarly, DeepMind's [star-studded position paper](https://arxiv.org/abs/1806.01261) introduces the *Graph Networks* framework, unifying all these ideas.

For a code walkthrough, the DGL team has [a nice tutorial](https://docs.dgl.ai/en/latest/tutorials/models/4_old_wines/7_transformer.html) on seq2seq as a graph problem and building Transformers as GNNs.
**In our next post, we'll be doing the reverse: using GNNs as Transformers (using [🤗's library](https://github.com/huggingface/transformers)).**

Finally, we wrote [a recent paper]({{<ref "/publication/xu-2019-multi/index.md">}}) applying Transformers to sketch graphs. Do check it out!
