- [2. Tranditional Feature-based Methods](#2-tranditional-feature-based-methods)
  - [2.1 Node-Level Prediction](#21-node-level-prediction)
    - [Node features](#node-features)
    - [Different ways to model importance](#different-ways-to-model-importance)
    - [Clustering Coefficient](#clustering-coefficient)
    - [Graphlet Degree Vector](#graphlet-degree-vector)
  - [2.2 Link-Level Prediction](#22-link-level-prediction)
    - [Link features](#link-features)
  - [2.3 Graph-Level predictions](#23-graph-level-predictions)
    - [TODO](#todo)

# 2. Tranditional Feature-based Methods
 [Slides Link](http://web.stanford.edu/class/cs224w/slides/02-tradition-ml.pdf)

Traditional ML Pipeline
* Design feature for nodes/links/graphs
* Obtain features for all training data


## 2.1 Node-Level Prediction

### Node features

Importance-based features (useful for predicting influential nodes in a graph)

* Node Degree: counts the neighboring nodes without capturing their importance. It counts the #(edges) that a node touches
* Node centrality: takes the node importance in a graph into account
  
Structure-based features (useful for predicting role a node plays in a graph)
* Node Degree
* Clustering coefficient
* Graphlet Degree Vector

### Different ways to model importance
* Eigenvector centrality
  
  A node v is important if surrounded by important neighboring nodes. The leading eigenvector is used for centraility.

* Betweenness centrality
  
  A node is important if it lies on many shortest paths between other nodes.
  $$
  c_v  = \sum_{s\neq{v}\neq{t}}\frac{\#shortest\ paths\ between\ s\ and\ t\ that\ contain\ v}{\#shortest\ paths\ between\ s\ and\ t}
  $$

* Closeness centrality
  
  A node is important if it has small shortest path lengths to all other nodes.
  $$
  c_v  = \sum_{u\neq{v}}\frac{1}{\#shortest\ paths\ between\ u\ and\ v}
  $$
  
### Clustering Coefficient
  
  Measures how connnected v's neighboring nodes are. It counts #(triangles) that a node touches. 

$$
e_v  = \frac{\#(edges\ among\ neighboring\ nodes)}{\begin{pmatrix} k_v\\2 \end{pmatrix}_{\#node\ pairs\ among\ k_v\  neighboring\ nodes}} \in [0,1]
$$

  > 0 means none of your friends know each other while 1 means all of your friends know each other

### Graphlet Degree Vector

  Rooted connected non-isomorphic subgraphs

  - Graphlet Degree Vector (GDV): Graphlet-base features for nodes
  - GDV counts #(graphlets) that a node touches
  - GDV provides a measure of a node's local noetwork topology
  
> Considering graphlets on 2 to 5 nodes we get: 1) vector of 73 (1! + 2! + 3! + 4!) coordinates is a signature of a node that describes the topology of node's neighborhood 2) captures its interconnectivities out to a distance of 4 hops


## 2.2 Link-Level Prediction

### Link features 

* Distance-based feature
  
  Shortest-path distance between two nodes. However, this does not capture the degree of neighborhood overlap. 

* Local neighborhood overlap
  
  Capture # neighboring nodes shared between two nodes v_1 and v_2

  - Common neighbors 
  - Jaccard's coefficient
  - Adamic-Adar index

> Limitation: metric is always zero if the two nodes do not have any neighbors in common. however, the two nodes may still potentially be connected in the future.

* Global neighborhood overlap
  
  Katz index: counts the number of paths of all lengths between a pair of nodes

$$
S_{v_1v_2} = \sum_{l=1}^{\infty}\beta{^l}{A^l_{v_1v_2}}
$$
$$
\beta \in (0,1): discount\ factor
$$

## 2.3 Graph-Level predictions
### TODO





