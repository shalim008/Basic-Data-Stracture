#  Recursion in C#

## Problem 1: Find Factorial Value of N number.

Write a function that gives Factorial value of a number N. For example, the factorial of 4 is 4×3×2×1, which is equal to 24..

#### Sample Input:   4
#### Sample Output: 24

#### Solution: 


        public static int Factorial(int n)
        {
            if (n == 1)                           // Base Case
                return 1;
            else
                return n * Factorial(n - 1);     // Recursive Procedure
        }
        
 
#### Debugging: Recursive Procedure and Base Case finding tricks - 
 
👉 Factorial 1 = 1                                 // If there no recursive calling found, you can consdier that as a Base Case.           

👉 Factorial 2 = 2 * Factorial(2-1) = 2

👉 Factorial 3 = 3 * Factorial(3-1) = 6

👉 Factorial 4 = 4 * Factorial(4-1) = 24


</br></br>

## Problem 2: Nth Fibonacci.
<div class="html">
<p>
  The Fibonacci sequence is defined as follows: the first number of the sequence
  is <span>0</span>, the second number is <span>1</span>, and the nth number is the sum of the (n - 1)th
  and (n - 2)th numbers. Write a function that takes in an integer
  <span>n</span> and returns the nth Fibonacci number.
</p>
<p>
  Important note: the Fibonacci sequence is often defined with its first two
  numbers as <span>F0 = 0</span> and <span>F1 = 1</span>. For the purpose of
  this question, the first Fibonacci number is <span>F0</span>; therefore,
  <span>getNthFib(1)</span> is equal to <span>F0</span>, <span>getNthFib(2)</span>
  is equal to <span>F1</span>, etc..
</p>
<h3>Sample Input #1</h3>
<pre><span class="CodeEditor-promptParameter">n</span> = 2
</pre>
<h3>Sample Output #1</h3>
<pre>1 <span class="CodeEditor-promptComment">// 0, 1</span>
</pre>
<h3>Sample Input #2</h3>
<pre><span class="CodeEditor-promptParameter">n</span> = 6
</pre>
<h3>Sample Output #2</h3>
<pre>5 <span class="CodeEditor-promptComment">// 0, 1, 1, 2, 3, 5</span>
</pre>
</div>

#### Solution: O(2^n) time | O(n) space

        
        public static int GetNthFib(int n)
        {            
            if (n == 2)
                return 1;
            else if (n == 1)
                return 0;
            else
                return GetNthFib(n-1) + GetNthFib(n - 2);
        }

#### Debugging: Fibonacci Recursive Procedure and Base Case finding tricks - 

👉 Fibonacci 1 = 0                                 // If there no recursive calling found, you can consdier that as a Base Case.    

👉 Fibonacci 2 = 1

👉 Fibonacci 3 = Fibonacci(3-1) + Fibonacci(3-2) = 1 + 0 = 1

👉 Fibonacci 4 = Fibonacci(4-1) + Fibonacci(4-2) = 1 + 1 = 2

👉 Fibonacci 5 = Fibonacci(5-1) + Fibonacci(5-2) = 2 + 1 = 3

👉 Fibonacci 6 = Fibonacci(6-1) + Fibonacci(6-2) = 3 + 2 = 5


