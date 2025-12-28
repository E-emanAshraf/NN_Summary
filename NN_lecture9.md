### **1. Why Graph Neural Networks?**

Traditional neural networks are designed for "Grid-Structured Data":

* **MLPs**: Handle tabular data.
* **CNNs**: Handle 2D grids (images).
* **RNNs**: Handle 1-D sequences (text/audio).

However, many real-world data types are **Non-Euclidean** and are best represented as **Graphs** (nodes and edges), such as:

* **Social Networks**: People (nodes) and their friendships (edges).
* **Molecules/Chemistry**: Atoms connected by chemical bonds.
* **Recommender Systems**: Users and items.
* **Knowledge Graphs**: Concepts and their relationships.

### **2. Fundamentals of GNNs**

A graph  consists of a set of vertices (nodes) and edges. GNNs aim to learn a state embedding  for each node that contains information about its neighborhood.

* **Aggregate and Update**: The core operation of a GNN involves:
1. **Aggregating** features from a node's neighbors.
2. **Updating** the node's own representation based on this aggregated information.


* **Graph Convolution**: Similar to how a CNN slides a filter over pixels, a GNN "convolves" over the neighbors of a node.

### **3. Key Architectures Compared**

The lecture details three primary types of GNNs, each evolving in complexity:

| Model | Mechanism | Best Use Case |
| --- | --- | --- |
| **GCN (Graph Convolutional Network)** | Treats all neighbors equally using a mean/sum aggregation. | Efficient for medium-sized, simple graphs. |
| **GAT (Graph Attention Network)** | Uses an **Attention Mechanism** to assign different weights (importance) to different neighbors. | High-relational data like social networks or knowledge graphs. |
| **Graph Transformer** | Uses global attention to capture long-range dependencies between nodes, not just immediate neighbors. | Complex structures where distant nodes are related (e.g., protein folding). |

### **4. Challenges in GNNs**

* **Over-smoothing**: A common issue in deep GNNs where, after many layers of aggregation, the representations of all nodes become nearly identical, making them indistinguishable.
* **Computational Cost**: While GCNs are fast, GATs and Transformers have much higher compute requirements ( for Transformers).

### **5. Tasks Performed by GNNs**

* **Node Classification**: Predicting the label of a node (e.g., is this user a bot?).
* **Link Prediction**: Predicting if an edge should exist between two nodes (e.g., "People you may know").
* **Graph Classification**: Categorizing an entire graph (e.g., is this molecule toxic?).