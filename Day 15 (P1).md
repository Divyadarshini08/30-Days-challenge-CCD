Day 15 of 30 Days Challenge.

**PROBLEM:** Maximum Product Subarray
**LINK:** https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/maximum-product-subarray3604

**DESCRIPTION:** 
Given an array arr[] that contains positive and negative integers (may contain 0 as well).
Find the maximum product that we can get in a subarray of arr[].

**INPUT & OUTPUT:**
Input: arr[] = [-2, 6, -3, -10, 0, 2]
Output: 180
Explanation: The subarray with maximum product is {6, -3, -10} with product = 6 * (-3) * (-10) = 180.

**APPROACH:**
1. Initialize prefprod, sufprod as 1 and maxi as the smallest possible integer.
2. Traverse the array from left to right:
      Multiply current element to prefprod and update maxi with the maximum of prefprod and maxi.
      If prefprod becomes 0, reset it to 1.
3. Traverse the array from right to left:
      Repeat the same steps with sufprod.
4. Return the maximum value stored in maxi.

**CODE:**
```java
class Solution {
    // Function to find maximum product subarray
    int max(int a,int b)
    {
        return a>b?a:b;
    }
    int maxProduct(int[] arr) {
        // code here
        int prefprod=1,sufprod=1,maxi=Integer.MIN_VALUE;
        for(int i=0;i<arr.length;i++)
        {
            prefprod=prefprod*arr[i];
            maxi=max(prefprod,maxi);
            if(prefprod==0)
            prefprod=1;
        }
        for(int i=arr.length-1;i>=0;i--)
        {
            sufprod=sufprod*arr[i];
            maxi=max(sufprod,maxi);
            if(sufprod==0)
            sufprod=1;
        }
        return maxi;
    }
}
