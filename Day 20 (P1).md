Day 20 of 30 Days challenge CCD

**PROBLEM:** Power of 2

**LINK:** https://www.geeksforgeeks.org/problems/power-of-2-1587115620/1

**DESCRIPTION:** Given a non-negative integer n. The task is to check if it is a power of 2. 

**INPUT & OUTPUT:**
Input: n = 8
Output: true
Explanation: 8 is equal to 2 raised to 3 (2^3 = 8).

**APPROACH:**
1. Check if the number n is greater than 0; if not, return false.
2. Perform a bitwise AND operation between n and 𝑛−1. If the result is 0, the number is a power of two, so return true.
3. If the result of the bitwise AND is not 0, return false.
   
**CODE:**
```cpp
class Solution {
  public:
    // Function to check if given number n is a power of two.
    bool isPowerofTwo(int n) {
        // code here
        
        if(n==1)
        return true;
        else if(n%2!=0)
        return false;
        
        return isPowerofTwo(n/2);
    }
};
