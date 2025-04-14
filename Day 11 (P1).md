Day 11 of 30 Days Challenge CCD

**PROBLEM:** Stock Buy and Sell – Multiple Transaction Allowed
**LINK:** https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/stock-buy-and-sell2615

**DESCRIPTION:**
The cost of stock on each day is given in an array price[]. 
Each day you may decide to either buy or sell the stock i at price[i], you can even buy and sell the stock on the same day. 
Find the maximum profit that you can get.
Note: A stock can only be sold if it has been bought previously and multiple stocks cannot be held on any given day.

**INPUT & OUTPUT:**
Input: prices[] = [4, 2, 2, 2, 4]
Output: 2
Explanation: Buy the stock on day 3 and sell it on day 4 => 4 – 2 = 2. Maximum Profit = 2.

**APPROACH:**
1. Initialize i, j, and sum to 0.
2. Traverse the prices array with j to find profit windows.
3. If the current price drops (prices[j] > prices[j+1]), sell at prices[j] and move i to j+1.
4. After the loop, sell at the last price if still holding stock.
5. Return the total accumulated sum (profit).

**CODE:**
```java
class Solution {
    public int maximumProfit(int prices[]) {
        // code here
        int i=0,j=0,sum=0;
        while(j<prices.length-1)
        {
            if(prices[j]>prices[j+1])
            {
                sum=sum+(prices[j]-prices[i]);
                i=j+1;
            }
            j++;
        }
        if(j==prices.length-1)
        {
            sum=sum+(prices[j]-prices[i]);
        }
        return sum;
    }
}
