# Data Stracture - Recursion in C#

## Problem 1: Find Factorial Value of N number.

Write a function that gives Factorial of a number 'n'. For example, the factorial of 4 is 4×3×2×1, which is equal to 24..

#### Sample Input: 4
#### Sample Output: 24

## Solution: 


        public static int Factorial(int n)
        {
            if (n == 1)                           // Base Case
                return 1;
            else
                return n * Factorial(n - 1);     // Recursive Procedure
        }
        
 
### Debugging: Recursive Procedure and Base Case finding tricks - 
 
Factorial 1 = 1                                 // If there no recursive calling found, you can consdier that as a Base Case.                      
 
Factorial 2 = 2 * Factorial(1) = 2
 
Factorial 3 = 3 * Factorial(2) = 6
 
Factorial 4 = 4 * Factorial(3) = 24
 

 
