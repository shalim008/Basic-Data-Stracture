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

To create a tree - 

    public class BST
    {
        public int value;
        public BST left;
        public BST right;

        public BST(int value)
        {
            this.value = value;
        }
    }
    
    
     static void Main(string[] args)
     {
            var root = new BST(10);
            root.left = new BST(5);
            root.left.left = new BST(2);
            root.left.left.left = new BST(1);
            root.left.right = new BST(5);
            root.right = new BST(15);
            root.right.left = new BST(13);
            root.right.left.right = new BST(14);
            root.right.right = new BST(22);                    
            var actual = Program.FindClosestValueInBst(root, 12);
            Console.WriteLine(actual);
            Console.ReadLine();
      }
