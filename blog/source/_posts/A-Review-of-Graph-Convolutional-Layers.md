---
title: A Review of Graph Convolutional Layers
date: 2021-12-31 12:29:28
tags: Study Notes
categories: Study Notes
---

# ChebConv
$$H^{l+1}=\sum_{k=1}^{K}{Z^{(k)}\cdot \theta^{(k)}}$$
# GCNConv
$$
H^{l+1} = \sigma(\tilde{D}^{-\frac{1}{2}}\tilde{A}\tilde{D}^{-\frac{1}{2}}H^{l}W^{l})
$$
## Explanation: 
Adding node features from neighboring nodes into central nodes
# SAGEConv
Perform node sampling in every neighborhood to procude $f(\mathcal{N}(i))$, where $f(\cdot)$ is a sampling function
# GraphConv
Paper: [arxiv](https://arxiv.org/abs/1810.02244)
$$x_i^′=\theta_1 x_i+\theta_2 \sum_{j\in\mathcal{N}(i)}{e_{j,i}\cdot x_j}$$
where $e_{j,i}$   denotes the edge weight from source node $j$ to target node $i$ (default: 1)
## Explanation: 
`GraphConv` multiplies features in neighboring nodes by their corresponding edge weights


# EdgeConv
Paper: [arxiv](https://arxiv.org/abs/1801.07829)

$$x_i′=\sum_{j\in\mathcal{N}(i)}{h_\theta (x_i||(x_j−x_i))}$$
## Explanation: 
Adding feature difference $x_j−x_i$  from neighboring nodes into central nodes $x_i$.

# GATConv
$$x_i^′=\alpha_{i,j}x_i+ \sum_{j\in\mathcal{N}(i)}{\alpha_{i,j}\cdot \theta x_j}$$
where $α_{i.j}$  is the attention coefficient
## Notes:
Similar to `GraphConv`. The difference is in `GraphConv`, edge weight is predefined. In `GATConv`, edge weights are replaced by attention coefficients
# GATv2Conv
Different to GATConv in terms of the computation of attention coefficients $α_{i.j}$.

# TransformerConv

 

