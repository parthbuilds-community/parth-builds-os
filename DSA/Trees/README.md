# Trees

Trees are non-linear data structures used to represent hierarchical relationships between different entities. A tree consists of a collection of nodes connected by edges, with one node designated as the root.

## Basic Terminology

* **Node:** Fundamental unit of a tree that stores data.
* **Root:** The topmost node of a tree.
* **Edge:** Connection between two nodes.
* **Parent:** A node that has one or more children.
* **Child:** A node directly connected below another node.
* **Leaf Node:** A node that has no children.
* **Sibling:** Nodes that share the same parent.
* **Depth:** Number of edges from the root to a node.
* **Height:** Number of edges on the longest path from a node to a leaf.
* **Subtree:** A tree formed by a node and all of its descendants.
* **Ancestor:** Any node present on the path from the root to a given node.
* **Descendant:** Any node present in the subtree of a given node.

## Properties of Trees

* A tree with `N` nodes contains exactly `N - 1` edges.
* There is exactly one path between any two nodes in a tree.
* A tree does not contain cycles.
* Every node except the root has exactly one parent.
* A tree can be empty or can have a single root node.

## Types of Trees

### 1. Binary Tree

A binary tree is a tree in which each node has at most two children.

```text
        1
       / \
      2   3
     / \
    4   5
```

### 2. Full Binary Tree

Every node has either `0` or `2` children.

```text
        1
       / \
      2   3
     / \
    4   5
```

### 3. Complete Binary Tree

All levels are completely filled except possibly the last level, and the last level is filled from left to right.

```text
        1
       / \
      2   3
     / \  /
    4  5 6
```

### 4. Perfect Binary Tree

All internal nodes have exactly two children, and all leaf nodes are at the same level.

```text
        1
       / \
      2   3
     / \ / \
    4  5 6  7
```

### 5. Binary Search Tree (BST)

A binary tree where:

* Left subtree contains values smaller than the node.
* Right subtree contains values greater than the node.

```text
        8
       / \
      4   12
     / \  / \
    2  6 10 14
```

### 6. Balanced Binary Tree

A tree where the heights of the left and right subtrees remain approximately balanced.

Examples include:

* AVL Tree
* Red-Black Tree

### 7. Skewed Tree

A tree where every node has only one child.

```text
1
 \
  2
   \
    3
     \
      4
```

## Tree Traversal Algorithms

Tree traversal means visiting every node of a tree in a specific order.

### Depth First Traversal

DFS-based traversals visit nodes by exploring one branch before moving to another.

#### Inorder Traversal

* Order: Left → Root → Right
* Commonly used with Binary Search Trees
* Produces sorted order for a BST

```text
4 2 5 1 3
```

#### Preorder Traversal

* Order: Root → Left → Right
* Useful for copying or serializing a tree

```text
1 2 4 5 3
```

#### Postorder Traversal

* Order: Left → Right → Root
* Useful when deleting or processing child nodes before their parent

```text
4 5 2 3 1
```

### Breadth First Traversal

#### Level Order Traversal

* Uses a Queue
* Visits nodes level by level
* Useful for processing a tree based on its depth

```text
1 2 3 4 5
```

## Important Tree Algorithms

* Inorder Traversal
* Preorder Traversal
* Postorder Traversal
* Level Order Traversal
* Height of a Tree
* Diameter of a Tree
* Lowest Common Ancestor (LCA)
* Binary Search Tree Operations
* Tree Insertion
* Tree Deletion
* Tree Searching
* Tree Balancing
* Tree Serialization and Deserialization

## Common Binary Search Tree Operations

### Search

Search for a value by comparing it with the current node.

**Average Time Complexity:** O(log N)

**Worst Case Time Complexity:** O(N)

### Insertion

Insert a new value while maintaining the BST property.

**Average Time Complexity:** O(log N)

**Worst Case Time Complexity:** O(N)

### Deletion

Remove a node while maintaining the BST property.

**Average Time Complexity:** O(log N)

**Worst Case Time Complexity:** O(N)

## Common Applications

* File Systems
* Database Indexing
* HTML/XML Document Structure
* Expression Parsing
* Searching and Sorting
* Priority Queues
* Decision Trees
* Autocomplete Systems
* Artificial Intelligence
* Hierarchical Data Representation

## Problem Sets

* Set 1: Inorder, Preorder and Postorder Traversal
* Set 2: Level Order Traversal and Height of a Tree
* Set 3: Binary Search Tree Operations
* Set 4: Diameter and Lowest Common Ancestor
* Set 5: Advanced Tree Problems
