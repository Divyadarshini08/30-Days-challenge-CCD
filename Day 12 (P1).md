Day 12 of 30 Days Challenge

**PROBLEM:** Stock Buy and Sell – Max one Transaction Allowed.

**PROBLEM LINK:** https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/buy-stock-2

**DESCRIPTION:** 
Given an array prices[] of length n, representing the prices of the stocks on different days.
The task is to find the maximum profit possible by buying and selling the stocks on different days when at most one transaction is allowed. 
Here one transaction means 1 buy + 1 Sell. If it is not possible to make a profit then return 0.

**INPUT & OUTPUT:**
Input: prices[] = [7, 10, 1, 3, 6, 9, 2]
Output: 8
Explanation: You can buy the stock on day 2 at price = 1 and sell it on day 5 at price = 9. Hence, the profit is 8.

**APPROACH:**
1. Initialize min = arr[0], maxProfit = 0
2. Loop from i = 1 to n - 1
3. If arr[i] < min, update min = arr[i]
4. Else, calculate profit = arr[i] - min
5. Update maxProfit = max(maxProfit, profit)
6. Return maxProfit

**CODE:**
```java
class Solution {
    int maximum(int a,int b)
    {
        return a>b?a:b;
    }
    public int maximumProfit(int arr[]) {
        // Code here
        int i=0,j=1,max=0,min=arr[0];
        while(j<arr.length)
        {
            if(arr[j-1]>arr[j])
            {
                max=maximum(max,(arr[j-1]-arr[i]));
            }
            if(arr[j]<min){
                    min=arr[j];
                    i=j;
                }
            j++;
        }
        max=maximum(max,(arr[j-1]-min));
        return max;
    }
}
