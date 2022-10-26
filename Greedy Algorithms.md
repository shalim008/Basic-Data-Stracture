
## 🧐 Find Minimum Waiting Time.

<div  ae-workspace-dark"><div class="html">
<p>
  You're given a non-empty array of positive integers representing the amounts
  of time that specific queries take to execute. Only one query can be executed
  at a time, but the queries can be executed in any order.
</p>
<p>
  A query's <b>waiting time</b> is defined as the amount of time that it must
  wait before its execution starts. In other words, if a query is executed
  second, then its waiting time is the duration of the first query; if a query
  is executed third, then its waiting time is the sum of the durations of the
  first two queries.
</p>
<p>
  Write a function that returns the minimum amount of total waiting time for all
  of the queries. For example, if you're given the queries of durations
  <span>[1, 4, 5]</span>, then the total waiting time if the queries were
  executed in the order of <span>[5, 1, 4]</span> would be
  <span>(0) + (5) + (5 + 1) = 11</span>. The first query of duration
  <span>5</span> would be executed immediately, so its waiting time would be
  <span>0</span>, the second query of duration <span>1</span> would have to wait
  <span>5</span> seconds (the duration of the first query) to be executed, and
  the last query would have to wait the duration of the first two queries before
  being executed.
</p>
<p>Note: you're allowed to mutate the input array.</p>
<h3>Sample Input</h3>
<pre><span class="CodeEditor-promptParameter">queries</span> = [3, 2, 1, 2, 6]
</pre>
<h3>Sample Output</h3>
<pre>17
</pre>
</div></div>

## Solution: 

		// Write your code here.

       	public int MinimumWaitingTime(int[] queries) 
        {
            Array.Sort(queries);
            int i = 0, sum = 0, temp = 0, totalWaitingTime=0;
            for (i = 0; i < queries.Count(); i++)
            {
                if (i == 0) { sum = 0; }
                sum = temp + sum;
                totalWaitingTime += sum;
                temp = queries[i];
            }
     
		return totalWaitingTime;
	 }






## 🧐 Class Photos
<p>
  It's photo day at the local school, and you're the photographer assigned to
  take class photos. The class that you'll be photographing has an even number
  of students, and all these students are wearing red or blue shirts. In fact,
  exactly half of the class is wearing red shirts, and the other half is wearing
  blue shirts. You're responsible for arranging the students in two rows before
  taking the photo. Each row should contain the same number of the students and
  should adhere to the following guidelines:
</p>
<ul>
  <li>All students wearing red shirts must be in the same row.</li>
  <li>All students wearing blue shirts must be in the same row.</li>
  <li>
    Each student in the back row must be strictly taller than the student
    directly in front of them in the front row.
  </li>
</ul>
<p>
  You're given two input arrays: one containing the heights of all the students
  with red shirts and another one containing the heights of all the students
  with blue shirts. These arrays will always have the same length, and each
  height will be a positive integer. Write a function that returns whether or
  not a class photo that follows the stated guidelines can be taken.
</p>
<p>Note: you can assume that each class has at least 2 students.</p>
<h3>Sample Input</h3>
<pre><span class="CodeEditor-promptParameter">redShirtHeights</span> = [5, 8, 1, 3, 4]
<span class="CodeEditor-promptParameter">blueShirtHeights</span> = [6, 9, 2, 4, 5]
</pre>
<h3>Sample Output</h3>
<pre>true <span class="CodeEditor-promptComment">// Place all students with blue shirts in the back row.</span>
</pre>

<h3>Code:</h3>

	using System.Collections.Generic;
	using System;


	public class Program {

		public bool ClassPhotos(List<int> redShirtHeights, List<int> blueShirtHeights) {
			redShirtHeights.Sort();
			blueShirtHeights.Sort();
			string frontRow = "";

			if (redShirtHeights[0] < blueShirtHeights[0])
			{
				frontRow = "RED";
				for (int i = 0; i < redShirtHeights.Count; i++)
				{
					if (redShirtHeights[i] >= blueShirtHeights[i])
					{
						 return false;
					}
				}
				return true;
			}
			else 
			{
				frontRow = "BLUE";
				for (int i = 0; i < blueShirtHeights.Count; i++)
				{
					if (blueShirtHeights[i] >= redShirtHeights[i])
					{
					 return false;
					}
				}
				return true;
			}


		}
	}






## 🧐 Tandem Bicycle

<p>
  A tandem bicycle is a bicycle that's operated by two people: person A and
  person B. Both people pedal the bicycle, but the person that pedals faster
  dictates the speed of the bicycle. So if person A pedals at a speed of
  <span>5</span>, and person B pedals at a speed of <span>4</span>, the tandem
  bicycle moves at a speed of <span>5</span> (i.e.,
  <span>tandemSpeed = max(speedA, speedB)</span>).
</p>
<p>
  You're given two lists of positive integers: one that contains the speeds of
  riders wearing red shirts and one that contains the speeds of riders wearing
  blue shirts. Each rider is represented by a single positive integer, which is
  the speed that they pedal a tandem bicycle at. Both lists have the same
  length, meaning that there are as many red-shirt riders as there are
  blue-shirt riders. Your goal is to pair every rider wearing a red shirt with a
  rider wearing a blue shirt to operate a tandem bicycle.
</p>
<p>
  Write a function that returns the maximum possible total speed or the minimum
  possible total speed of all of the tandem bicycles being ridden based on an
  input parameter, <span>fastest</span>. If <span>fastest = true</span>, your
  function should return the maximum possible total speed; otherwise it should
  return the minimum total speed.
</p>
<p>
  "Total speed" is defined as the sum of the speeds of all the tandem bicycles
  being ridden. For example, if there are 4 riders (2 red-shirt riders and 2
  blue-shirt riders) who have speeds of <span>1, 3, 4, 5</span>, and if they're
  paired on tandem bicycles as follows: <span>[1, 4], [5, 3]</span>, then the
  total speed of these tandem bicycles is <span>4 + 5 = 9</span>.
</p>
<h3>Sample Input</h3>
<pre><span class="CodeEditor-promptParameter">redShirtSpeeds</span> = [5, 5, 3, 9, 2]
<span class="CodeEditor-promptParameter">blueShirtSpeeds</span> = [3, 6, 7, 2, 1] 
<span class="CodeEditor-promptParameter">fastest</span> = true
</pre>
<h3>Sample Output</h3>
<pre>32
</pre>

<h3>Code:</h3>

	using System;


	public class Program {

	public int TandemBicycle(int[] redShirtSpeeds, int[] blueShirtSpeeds, bool fastest) {

	Array.Sort(redShirtSpeeds);
	Array.Sort(blueShirtSpeeds);
	int sum = 0;
	if (fastest)
	{
	    int j = 0;
	    for (int i = redShirtSpeeds.Length - 1; i >= 0; i--)
	    {
		if (redShirtSpeeds[i] > blueShirtSpeeds[j])
		{
		    sum += redShirtSpeeds[i];
		}
		else
		{
		    sum += blueShirtSpeeds[j];
		}

		j++;
	    }

	}
	else
	{

		    for (int i = redShirtSpeeds.Length - 1; i >= 0; i--)
		    {
			if (redShirtSpeeds[i] > blueShirtSpeeds[i])
			{
			    sum += redShirtSpeeds[i];
			}
			else
			{
			    sum += blueShirtSpeeds[i];
			}        
		    }   

	}
			return sum;
	}
	}



