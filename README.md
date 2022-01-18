# Data Stracture C#

## Problem: Find Closest Value In BST.

Write a function that takes in a Binary Search Tree (BST) and a target integer value and returns the closest value to that target value contained in the BST. 
You can assume that there will only be one closest value.

<pre><span class="CodeEditor-promptParameter">tree</span> =   10
       /     \
      5      15
    /   \   /   \
   2     5 13   22
 /           \
1            14

<span class="CodeEditor-promptParameter">target</span> = 12
</pre>

#### Sample Output: 13


## Solution: 


       public static int FindClosestValueInBst(BST tree, int target)
        {
            int closest = tree.value;
            BST currentNode = tree;
            while (currentNode != null)
            {
                if (Math.Abs(target - closest) > Math.Abs(currentNode.value - target))
                {
                    closest = currentNode.value;
                }

                if (target > currentNode.value && currentNode.right != null)
                {
                    currentNode = currentNode.right;
                }
                else if (target < currentNode.value && currentNode.left != null)
                {
                    currentNode = currentNode.left;
                }
            }
            
            return closest; 
        }
