<h1 align="center">👋 BST in C# </h1>

## 🧐 Problem 1: Find Closest Value In BST.

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
                else
                {
			break;
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


</br></br>




## 🧐 Problem 2: Branch Sums In BST.

<div class="html">
<p>
  Write a function that takes in a Binary Tree and returns a list of its branch
  sums ordered from leftmost branch sum to rightmost branch sum.
</p>
<p>
  A branch sum is the sum of all values in a Binary Tree branch. A Binary Tree
  branch is a path of nodes in a tree that starts at the root node and ends at
  any leaf node.
</p>
<p>
  Each <span>BinaryTree</span> node has an integer <span>value</span>, a
  <span>left</span> child node, and a <span>right</span> child node. Children
  nodes can either be <span>BinaryTree</span> nodes themselves or
  <span>None</span> / <span>null</span>.
</p>
<h3>Sample Input</h3>
<pre><span class="CodeEditor-promptParameter">tree</span> =     1
        /     \
       2       3
     /   \    /  \
    4     5  6    7
  /   \  /
 8    9 10
</pre>
<h3>Sample Output</h3>
<pre>[15, 16, 18, 10, 11]
<span class="CodeEditor-promptComment">// 15 == 1 + 2 + 4 + 8</span>
<span class="CodeEditor-promptComment">// 16 == 1 + 2 + 4 + 9</span>
<span class="CodeEditor-promptComment">// 18 == 1 + 2 + 5 + 10</span>
<span class="CodeEditor-promptComment">// 10 == 1 + 3 + 6</span>
<span class="CodeEditor-promptComment">// 11 == 1 + 3 + 7</span>
</pre>
</div>

## Solution: 
O(n) time | O(n) space - where n is the number of nodes in the Binary Tree


 	public static void CalculateBracnchSum(BST tree, int runningSum, List<int> sums)
        {
            if (tree == null)
            {
                return;
            }

            runningSum = runningSum + tree.value;
            if (tree.left == null && tree.right == null)
            {
                sums.Add(runningSum);
            }

            CalculateBracnchSum(tree.left, runningSum, sums);
            CalculateBracnchSum(tree.right, runningSum, sums);

        }
