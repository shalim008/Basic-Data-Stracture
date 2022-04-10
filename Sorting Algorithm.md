<h1 align="center">👋 Bubble Sort in C# </h1>

<div class="_3ujpThEtqc2woOs6g2RNC2 ae-workspace-dark"><div class="html">
<p>
  Write a function that takes in an array of integers and returns a sorted
  version of that array. Use the Bubble Sort algorithm to sort the array.
</p>
<p>
  If you're unfamiliar with Bubble Sort, we recommend watching the Conceptual
  Overview section of this question's video explanation before starting to code.
</p>
<h3>Sample Input</h3>
<pre><span class="CodeEditor-promptParameter">array</span> = [8, 5, 2, 9, 5, 6, 3]
</pre>
<h3>Sample Output</h3>
<pre>[2, 3, 5, 5, 6, 8, 9]
</pre>
</div></div>


## Solution: 


      public static int[] BubbleSort(int[] array) 
      {

          int temp, count=0;
          while (count < array.Length)
          {
              for (int j = 0; j < array.Length - 1-count; j++)
              {
                  if (array[j] > array[j + 1])
                  {
                      temp = array[j];
                      array[j] = array[j + 1];
                      array[j + 1] = temp;
                  }
              }
              count++;    
          }
          return array;
	    }


<h1 align="center">👋 Insertion Sort in C# </h1>
<div class="_3ujpThEtqc2woOs6g2RNC2 ae-workspace-dark"><div class="html">
<p>
  Write a function that takes in an array of integers and returns a sorted
  version of that array. Use the Insertion Sort algorithm to sort the array.
</p>
<p>
  If you're unfamiliar with Insertion Sort, we recommend watching the Conceptual
  Overview section of this question's video explanation before starting to code.
</p>
<h3>Sample Input</h3>
<pre><span class="CodeEditor-promptParameter">array</span> = [8, 5, 2, 9, 5, 6, 3]
</pre>
<h3>Sample Output</h3>
<pre>[2, 3, 5, 5, 6, 8, 9]
</pre>
</div></div>

## Solution: 

		public static int[] InsertionSort(int[] input) 
		{
		
			int temp;		
			for (int i =1; i < input.Length; i++)
			{
					int j = i;
					while (j >0 && input[j]<input[j-1])
					{
							temp = input[j];
							input[j] = input[j - 1];
							input[j - 1] = temp;
							j--;
					}
			}
			return input;
		}
