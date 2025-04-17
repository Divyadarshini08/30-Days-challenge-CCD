Day 14 of 30 Days challenge.

**PROBLEM:** Maximum Subarray Sum.
**LINK:** https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/kadanes-algorithm-1587115620

**DESCRIPTION:**
Given an integer array arr[]. You need to find the maximum sum of a subarray.

**INPUT & OUTPUT:**
Input: arr[] = [2, 3, -8, 7, -1, 2, 3]
Output: 11
Explanation: The subarray {7, -1, 2, 3} has the largest sum 11.

**APPROACH:**
1. We initialize maxSum to INT_MIN to handle negative numbers.
2. sum keeps track of the running sum of the subarray.
3. For each number, we decide whether to add it to the current subarray or start fresh with the current number.
4. We update maxSum with the maximum value between maxSum and the current sum.
5. Return the maxSum as the result.


**CODE:**
```cpp
class Solution {
    int maxi(int a,int b)
    {
        return a>b?a:b;
    }
  public:
    int maxSubarraySum(vector<int> &arr) {
        // Your code here
        int max=INT_MIN,sum=0;
        for(int i=0;i<arr.size();i++)
        {
            sum=sum+arr[i];
            max=maxi(sum,max);
            if(sum<0)
            sum=0;
        }
        return max;
    }
};
