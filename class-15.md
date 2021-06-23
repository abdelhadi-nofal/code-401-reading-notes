# Trees 


## Common Terminology
  > Node - A Tree node is a component which may contain it’s own values, and references to other nodes
    Root - The root is the node at the beginning of the tree
    K - A number that specifies the maximum number of children any node may have in a k-ary tree. In a binary tree, k = 2.
    Left - A reference to one child node, in a binary tree
    Right - A reference to the other child node, in a binary tree
    Edge - The edge in a tree is the link between a parent and child node
    Leaf - A leaf is a node that does not have any children
    Height - The height of a tree is the number of edges from the root to the furthest leaf

### How to traverse "Trees"?
 - > traversing a tree allows us to search for a node, print out the contents of a tree, and much more!
 -  Recursion is the most common way to traverse trees
 - **Categories of traversals**:
   - _Depth First:_ prioritize goiing to depth first
     **Methods**
      - Pre-order: root >> left >> right
        >   ALGORITHM preOrder(root)

            OUTPUT <-- root.value

            if root.left is not NULL
                preOrder(root.left)

            if root.right is not NULL
               preOrder(root.right)

      - In-order: left >> root >> right
       > ALGORITHM inOrder(root)
        // INPUT <-- root node
        // OUTPUT <-- in-order output of tree node's values

            if root.left is not NULL
                inOrder(root.left)

            OUTPUT <-- root.value

            if root.right is not NULL
                inOrder(root.right)

      - Post-order: left >> right >> root
      > ALGORITHM postOrder(root)
        // INPUT <-- root node
        // OUTPUT <-- post-order output of tree node's values

            if root.left is not NULL
                postOrder(root.left)

            if root.right is not NULL
                postOrder(root.right)

            OUTPUT <-- root.value

   - _Breadth First:_ 
     - > Breadth first traversal iterates through the tree by going through each level of the tree node-by-node
     - > breadth first traversal uses a queue (instead of the call stack via recursion) 
     - >   ALGORITHM breadthFirst(root)
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

## Binary Trees
- only have two children 
- no specific sorting order 

## Binary Search Trees
- > A Binary Search Tree (BST) is a type of tree that does have some structure attached to it. In a BST, nodes are organized in a manner where all values that are smaller than the root are placed to the left, and all values that are larger than the root are placed to the right

## K-ary Trees
- nodes can have more than two children
