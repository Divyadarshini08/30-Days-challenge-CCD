Day 16 of 30 Days Challenge

**PROBLEM:** MAX CIRCULAR SUBARRAY SUM

**LINK:** https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/max-circular-subarray-sum-1587115620

**DESCRIPTION:** Given an array of integers arr[] in a circular fashion. Find the maximum subarray sum that we can get if we assume the array to be circular.

**INPUT & OUTPUT:**
Input: arr[] = [8, -8, 9, -9, 10, -11, 12]
Output: 22
Explanation: Starting from the last element of the array, i.e, 12, and moving in a circular fashion, we have max subarray as 12, 8, -8, 9, -9, 10, which gives maximum sum as 22.

**APPROACH:**
1. Initialize: total sum, max sum, min sum, current max, current min.
2. Traverse the array.
3. At each step, update current max (Kadane's) and max sum.
4. Update current min (Kadane's for min) and min sum.
5. Add current element to total sum.
6. Return max of (max sum, total sum − min sum), unless all elements are negative—in that case, return max sum.

**CODE:**
```java
class Solution {

    // a: input array
    // n: size of array
    // Function to find maximum circular subarray sum.
    int maximum(int a,int b)
    {
        return a>b?a:b;
    }
    int minimum(int a,int b)
    {
        return a<b?a:b;
    }
    public int circularSubarraySum(int arr[]) {
         // Your code here
        int sum=0,minsum=0,maxsum=0,MaxKadane=Integer.MIN_VALUE,MinKadane=Integer.MAX_VALUE;
        
        for(int i=0;i<arr.length;i++){
            sum=sum+arr[i];
            
            maxsum=maxsum+arr[i];
            if(maxsum<0)
            maxsum=0;
            MaxKadane=maximum(MaxKadane,maxsum);
            
            minsum=minsum+arr[i];
            if(minsum>0)
            minsum=0;
            MinKadane=minimum(MinKadane,minsum);
        }
        return maximum(MaxKadane,sum-MinKadane);
    }
}
