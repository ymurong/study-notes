- [Table of Content](#table-of-content)
  - [B tree](#b-tree)



# Table of Content

## B tree
1. balanced m-way tree (m -> order of tree -> maximum number of children per node)
2. generalization of BST in which a node could have more than one key and more than 2 children
3. maintains sorted data (ascending)
4. all leaf node must be at the same level
5. B-tree of order m has the following properties
   1. every node has maximum m children
   2. min children: leaf->0, root->2, internal node-> ceiling(m/2)
   3. every node has max (m-1) keys
   4. min keys: root -> 1, all other nodes -> ceiling(m/2)-1

## B+ tree
1. variation of B tree where all values stored in the leaf nodes
2. internal nodes has maximum m children.
3. internal nodes has minimum ceiling (m/2) children
4. leaf nodes has at most L elements
5. leaf nodes has at least ceiling(L/2) elements
6. elements in B+ tree ordered from least to most
7. keys in the internal nodes contains the smallest values in each of the children, starting from the second one