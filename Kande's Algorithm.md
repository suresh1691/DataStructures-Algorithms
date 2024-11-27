Kadane's algorithm is a dynamic programming approach used to find the contiguous subarray within an array that has the largest sum. It's a classic problem in algorithm design and has various applications in fields like signal processing, financial analysis, and bioinformatics.   

How it works:
==========

**Initialization:**

max_so_far: Stores the maximum sum encountered so far.

max_ending_here: Stores the maximum sum of the subarray ending at the current position.

**Iterating through the array:**

For each element num in the array:

**Update max_ending_here:**

If max_ending_here is positive, add num to it.

Otherwise, start a new subarray with num.

**Update max_so_far:**

If max_ending_here is greater than max_so_far, update max_so_far.

**Return the result:**

After iterating through the entire array, max_so_far will hold the maximum sum of any contiguous subarray.

**Key points:**

Time complexity: O(n)

Space complexity: O(1)   

Efficiency: It's a highly efficient algorithm for solving the maximum subarray problem.

Simplicity: The algorithm is easy to understand and implement.   

**Example:**

Consider the array: [-2, 1, -3, 4, -1, 2, 1, -5, 4]

max_so_far = -2, max_ending_here = -2

num = 1: max_ending_here = 1, max_so_far = 1

num = -3: max_ending_here = -2, max_so_far = 1

num = 4: max_ending_here = 2, max_so_far = 2

... and so on

After iterating through the entire array, the max_so_far will be 6, which is the maximum sum of the subarray [4, -1, 2, 1].

Applications:
============

Stock Trading: Calculate maximum profit from price differences.

Weather Data: Analyze longest streaks of increasing/decreasing temperatures.

Game Development: Determine optimal paths or moves in grid-based challenges.


Psudocode:
========
        
        public void int findMaxContinuosSubArray(int arr){
        int s=0; int start ,end =0;
        int max_end =0, max_so_far =0;
                
                for(int i=0; i<arr.length; i++){
                        if(max_end<0){
                        max_end =arr[i];
                        s =i
                        }else {
                        max_end += arr[i]; 
                        }
                        if(max_so_far < max_end){
                        max_so_far = max_end;
                        start = s;
                        end =i;
                        }
                }
        }
