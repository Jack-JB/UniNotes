# Tree and Graph Data Structures

## Tree data structures: Terminology

For a tree data structure:

- The tree is **hierarchical.** Every link goes from one node to a subordinate node. There is only one path from the root to any of the nodes in the tree. No link goes back up again. In particular, there are **no cycles**
- There is exactly one node, the **root** node, from which all nodes can be reached. Each node is either a **leaf**, or it is a root for its own (sub-)tree.
- In a tree, the number of "children" (subordinate nodes) of a node is called its **degree**. in a **binary tree,** all nodes have degree two or lower

![image-20211130161052993](C:\src\UniNotes\Year 2\CO2509 - Mobile Computing\images\image-20211130161052993.png)

A **search tree** is inherently sorted; data items stored at each node and within each of its subtrees have a clearly specified order. To **search for an element** or **insert a new element**, links have to be found downward.

A search tree is **balanced** if its **depth scales with O(log n)** where `n` is the size of the tree. In particular, that is the case if the data structure ensures that at each node, the ratio between the size of its largest and its smallest subtree never exceeds a specified constant value. **Then searching takes O(log n) time.**

## Graph Data Structures

### Generalisation from trees to graphs

For many applications, these **restrictions** are unsuitable. A linked data structure where any node can be connected to any node is called a **graph.**

A node in a graph is also often called a **vertex.**

The links between the nodes (or vertices) in a graph are called **edges.**

### Typical Use Cases

Modern knowledge bases represent knowledge about the state of affairs as **knowledge graphs.** These graphs are understood as part of one **semantic web.**

### Traversal of a binary search tree

**Visiting the nodes** in a binary search tree in ascending order by value of their data items, can be done in O(n) time, given that **the tree is inherently sorted.**

### Breadth-first and depth-first search: Basic idea

The two most common traversal strategies for linked data structures that are not inherently sorted, and generally for graphs, are breath-first searches (BST) and depth-first search (DFS).