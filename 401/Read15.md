# Trees

Common Terminology

* Node - A Tree node is a component which may contain it’s own values, and references to other nodes
* Root - The root is the node at the beginning of the tree
* K - A number that specifies the maximum number of children any node may have in a k-ary tree. In a binary tree, k = 2.
* Left - A reference to one child node, in a binary tree
* Right - A reference to the other child node, in a binary tree
* Edge - The edge in a tree is the link between a parent and child node
* Leaf - A leaf is a node that does not have any children
* Height - The height of a tree is the number of edges from the root to the furthest leaf

![tree](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/BinaryTree1.PNG)

## Traversals

An important aspect of trees is how to traverse them. Traversing a tree allows us to search for a node, print out the contents of a tree, and much more! There are two categories of traversals when it comes to trees:

* Depth First
* Breadth First

### Depth First

Depth first traversal is where we prioritize going through the depth (height) of the tree first. There are multiple ways to carry out depth first traversal, and each method changes the order in which we search/print the `root`

* Pre-order: root >> left >> right
* In-order: left >> root >> right
* Post-order: left >> right >> root

#### Pre-order

Let’s break down the pre-order traversal. Here is the pseudocode for this traversal method:

    ALGORITHM preOrder(root)

    OUTPUT <-- root.value

    if root.left is not NULL
        preOrder(root.left)

    if root.right is not NULL
        preOrder(root.right)

![preOrder](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/DepthTraversal1.PNG)

#### in-Order

    ALGORITHM inOrder(root)
    // INPUT <-- root node
    // OUTPUT <-- in-order output of tree node's values

        if root.left is not NULL
            inOrder(root.left)

        OUTPUT <-- root.value

        if root.right is not NULL
            inOrder(root.right)

#### Post-order

    ALGORITHM postOrder(root)
    // INPUT <-- root node
    // OUTPUT <-- post-order output of tree node's values

        if root.left is not NULL
            postOrder(root.left)

        if root.right is not NULL
            postOrder(root.right)

        OUTPUT <-- root.value

### Breadth First

Breadth first traversal iterates through the tree by going through each level of the tree node-by-node.

![breadth-first](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/tree-example.png)

#### Pseudocode
Here is the pseudocode, utilizing a built-in queue to implement a breadth first traversal.

    ALGORITHM breadthFirst(root)
    // INPUT  <-- root node
    // OUTPUT <-- front node of queue to console

    Queue breadth <-- new Queue()
    breadth.enqueue(root)

    while breadth.peek()
        node front = breadth.dequeue()
        OUTPUT <-- front.value

        if front.left is not NULL
        breadth.enqueue(front.left)

        if front.right is not NULL
        breadth.enqueue(front.right)

## Binary Tree Vs K-ary Trees

In all of our examples, we’ve been using a Binary Tree. Trees can have any number of children per node, but Binary Trees restrict the number of children to two (hence our left and right children).

### Binary Tree

![binary](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/BinaryTree2.PNG)

### K-ary Trees

If Nodes are able have more than 2 child nodes, we call the tree that contains them a K-ary Tree. In this type of tree we use K to refer to the maximum number of children that each Node is able to have.

#### Breadth First Traversal

Traversing a K-ary tree requires a similar approach to the breadth first traversal. We are still pushing nodes into a queue,

![breadth](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/KaryTree1.png)

#### Pseudocode

    ALGORITHM breadthFirst(root)
    // INPUT  <-- root node
    // OUTPUT <-- front node of queue to console

    Queue breadth <-- new Queue()
    breadth.enqueue(root)

    while breadth.peek()
        node front = breadth.dequeue()
        OUTPUT <-- front.value

        for child in front.children
            breadth.enqueue(child)

#### Adding a node

Because there are no structural rules for where nodes are “supposed to go” in a binary tree, it really doesn’t matter where a new node gets placed.

One strategy for adding a new node to a binary tree is to fill all “child” spots from the top down. To do so, we would leverage the use of breadth first traversal. During the traversal, we find the first node that does not have all it’s children filled, and insert the new node as a child. We fill the child slots from left to right.

#### Big O

The Big O time complexity for inserting a new node is O(n). Searching for a specific node will also be O(n). Because of the lack of organizational structure in a Binary Tree, the worst case for most operations will involve traversing the entire tree. If we assume that a tree has n nodes, then in the worst case we will have to look at n items, hence the O(n) complexity.

### Binary Search Trees

A Binary Search Tree (BST) is a type of tree that does have some structure attached to it. In a BST, nodes are organized in a manner where all values that are smaller than the root are placed to the left, and all values that are larger than the root are placed to the right.

![search](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/BST1.PNG)