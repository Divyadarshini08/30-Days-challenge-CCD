Day 17 of 30 Days Challenge

**PROBLEM:** Smallest Positive Missing Number.

**LINK:** https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/smallest-positive-missing-number-1587115621.

**DESCRIPTION:** 
You are given an integer array arr[]. Your task is to find the smallest positive number missing from the array.
Note: Positive number starts from 1. The array can have negative integers too.

**INPUT & OUTPUT:**
Input: arr[] = [2, -3, 4, 1, 1, 7]
Output: 3
Explanation: Smallest positive missing number is 3.

**APPROACH:**
1. Initialize a variable n = 1 (the smallest positive integer to check).
2. Sort the array in ascending order.
3. Traverse the array from start to end.
4. For each element, if it equals n, increment n by 1.
5. Ignore elements less than n or duplicates.
6. After the loop, return n — this is the smallest missing positive number.

**CODE:**
```java
class Solution {
    // Function to find the smallest positive number missing from the array.
    public int missingNumber(int[] arr) {
        // Your code here
        Arrays.sort(arr);
        int small=1;
        for(int i=0;i<arr.length;i++)
        if(arr[i]==small)
        small++;
        
        return small;
    }
}


