- [1.1 Why Graph?](#11-why-graph)
  - [What is Graph?](#what-is-graph)
  - [Many Types of Data and Graphs](#many-types-of-data-and-graphs)
  - [Why it is hard?](#why-it-is-hard)
  - [Supervised ML vs Representation Lifecycle](#supervised-ml-vs-representation-lifecycle)
  - [Covered subjects](#covered-subjects)
- [1.2 Applications of Graph ML](#12-applications-of-graph-ml)
  - [Classic Graph ML Tasks](#classic-graph-ml-tasks)
  - [Examples](#examples)
- [1.3 Choice of Graph Representation](#13-choice-of-graph-representation)
  - [Directed vs Undirected](#directed-vs-undirected)
  - [Node Degrees](#node-degrees)
  - [Bipartite Graph](#bipartite-graph)
  - [Graph Representations](#graph-representations)
    - [Adjacency Matrix](#adjacency-matrix)
    - [Edge list](#edge-list)
    - [Adjacency list](#adjacency-list)
  - [Node and Edge Attributes](#node-and-edge-attributes)
  - [More types of Graphs](#more-types-of-graphs)
  - [Connectivity](#connectivity)

## 1.1 Why Graph?
Graphs are the new frontier of deep learning / representation learning.

* Input: Network
* Output: Predictions on Node labels, New links, Generated graphs and subgraphs


### What is Graph?

Graphs are a general language for describing and analyzing entities with relations/interactions.

### Many Types of Data and Graphs

- Event Graph
- Social Networks
- Communication and Transactions Networks
- Knowledge Graphs
- Biomedicine, Molecules
- Brain connections

Complex domains have a rich relational structure, which can be represented as a relational graph. By explicitely modeling relationships we achieve better performance.

### Why it is hard? 
- Arbitrary size and complex topological structure (no spatial locality like grids)
- No fixed nodes ordering or reference point
- Often dynamic and have multimodal features

### Supervised ML vs Representation Lifecycle
* Feature Engineering vs Automatically learn the features
* Map nodes to d-dimentional embeddings such that similar nodes in the network are embedded close together

### Covered subjects
* Traditional methods: Graphlets, Graph Kernels
* Methods for node embeddings: DeepWalk, Node2Vec
* Graph Neural Networks: GCN, GraphSAGE, GAT, Theory of GNNs
* Knowledge graphs and reasoning: TransE, BetaE
* Deep generative models for graphs
* Applications to Biomedicine, Science, Industry


## 1.2 Applications of Graph ML
### Classic Graph ML Tasks
* Node Classification: Predict a property of a node. Ex: Categorize online users/items
* Link prediction: Predict whether there are missing links between two nodes. Ex: Knowledge graph completion
* Graph classification: Categorize different graphs. Ex: Molecule property prediction
* Clustering: Detect if nodes from a community. Ex: Social circle detection
* Graph generation: drug discovery
* Graph evolution: physical simulation

### Examples
User interacts with items
* watch movies, buy merchandise, listen to music
* Nodes: Users and items
* Edges: User-item interactions
* Goal: Recommend items users might like

Recommend related pins to users
* Task: Learn node embeddings such that we found closest nodes


Biomedical Graph Link Prediction
* Drug Sides effects
* Nodes: Drugs & Proteins
* Edges: Interactions

## 1.3 Choice of Graph Representation
* Objects: nodes, vertices -> N
* Interactions: links, edges -> E
* System: network, graph -> G(N,E)


### Directed vs Undirected
* Undirected (Collaborations)
* Directed (Twitter Following)
  
### Node Degrees
*  Node degree, $k_i$: the number of edges adjacent to node i
*  Avg. degree: $\overline{k} = <k> = \frac{1}{N} \sum_{N}^{i=1}k_i = \frac{2E}{N}$

> For directed graph, the total degree of a node is the sum of in-and out-degrees. $\overline{k_{in}}=\overline{k_{out}}$
* Source: Node with $k_{in}$ = 0
* Sink: Node with $k_{out}$ = 0

### Bipartite Graph
Bipartite graph is a graph whose nodes can
be divided into two disjoint sets U and V such that every link connects a node in U to one in V; that is, U and V are independent sets

* Authors-to-Papers (they authored)
* Actors-to-Movies (they appeared in)
* Users-to-Movies (they rated)
* Recipes-to-Ingredients (they contain)

> Folded/Projected Bipartite Graphs  

### Graph Representations
#### Adjacency Matrix
* adjacency matrix for directed graph is not symmetric
* adjacency matrix are sparse
* most real-world networks are sparse
#### Edge list
#### Adjacency list
* easier to work with if network is large/sparse
* allows to quickly retrive all neighbours of a given node

### Node and Edge Attributes
Possible options
* Weight (frequency of communication)
* Ranking (best friend, second best friend)
* Type (friend, relative, co-worker)
* Sign: Friend vs Fow, Trust vs. Distrust
* Properties depending on the structure of the rest of the graph: nb of common friends

### More types of Graphs
* Unweighted vs Weighted
* self-edges (self-loops) (undirected)
* Multigraph (undirected) -> financial transactions
* Connected graph vs Disconnected Graphs
> A disconnected graph is made up by two or more connected components

### Connectivity

The adjacency matrix of a network with several
components can be written in a block- diagonal
form, so that nonzero elements are confined to
squares, with all other elements being zero

* Strongly conected directed graph has a path from each node to every other node and vice versa (e.g., A-B path and B-A path)
* Weakly conected directed graph is connected if we disregard the edge directions