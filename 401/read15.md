
# Trees
a *collection of nodes*, where each node is a data structure consisting of a value and a list of references to nodes. The start of the tree is the `root node` and the reference nodes are the `children`

![tree](https://cdn-images-1.medium.com/max/975/1*PWJiwTxRdQy8A_Y0hAv5Eg.png)


## A Binary Tree
A binary tree has the benefits of both an ordered array and a linked list as search is as quick as in a sorted array and insertion or deletion operation are as fast as in linked list.
 
it contains following parts:
1. Data
2. Pointer to left child
3. Pointer to right child

## Tree terms :
1. **Node** - A Tree node is a component which may contain it’s own values, and references to other nodes
2. **Root** - The root is the node at the beginning of the tree
3. **K**- A number that specifies the maximum number of children any node may have in a k-ary tree. In a binary tree, k = 2.
4. **Left** - A reference to one child node, in a binary tree
5. **Right** - A reference to the other child node, in a binary tree
6. **Edge** - The edge in a tree is the link between a parent and child node
7. **Leaf** - A leaf is a node that does not have any children
8. **Height** - The height of a tree is the number of edges from the root to the furthest leaf

## Traversal categories:
* Depth First : going through the depth (height) of the tree first and it is have three methods for depth first traversal:
    - Pre-order: `root >> left >> right`
    - In-order: `left >> root >> right`
    - Post-order: `left >> right >> root`

* Breadth First : iterates through the tree by going through each level of the tree node-by-node.


## K-ary Trees 
is a rooted tree in which each node has no more than m children

![k-tree](https://www.tutorialspoint.com/assets/questions/media/41120/k_ary_tree.jpg)
