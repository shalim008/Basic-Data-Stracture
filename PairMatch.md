<h1 align="center">👋 Sales by Match in C# </h1>

## 🧐 Problem 1: Sales by Match.

There is a large pile of socks that must be paired by color. Given an array of integers representing the color of each sock, determine how many pairs of socks with matching colors there are.



#### Example

Input: n=7   ar = [1,2,1,2,1,3,2]

####### Output = 2

There is one pair of color 1 and one of color 2. There are three odd socks left, one of each color. The number of pairs is 2.


Code: 

     public static int sockMerchant(int n, List<int> ar)
        {

            if (ar.Count == 0) return 0;
            n = 0;
            List<int> uniqueNumbers = new List<int>();
            for (int i = 0; i < ar.Count; i++)
            {
                if (!uniqueNumbers.Contains(ar[i]))
                {
                    uniqueNumbers.Add(ar[i]);
                }
                else
                {
                    n++;
                    uniqueNumbers.Remove(ar[i]);
                }
            }
            return n;
        }
