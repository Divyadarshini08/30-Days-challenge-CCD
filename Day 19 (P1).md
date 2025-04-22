Day 19 of 30 Days Challenge CCD

**PROBLEM:** UNIQUE NUMBER 1

**LINK:** https://www.geeksforgeeks.org/problems/find-unique-number/1.

**DESCRIPTION:** Given a unsorted array arr[] of positive integers having all the numbers occurring exactly twice, except for one number which will occur only once. Find the number occurring only once.

**INPUT & OUTPUT:**
Input: arr[] = [1, 2, 1, 5, 5]
Output: 2
Explanation: Since 2 occurs once, while other numbers occur twice, 2 is the answer.

**APPROACH:**
1. Initialize sum = 0.
2. For each element x in the array:
      Perform sum = sum ^ x.
3. Return sum, which will be the unique element.

**CODE:**
```cpp
class Solution {
  public:
    int findUnique(vector<int> &arr) {
        // code here
        int sum=0;
        for(int i=0;i<arr.size();i++)
        sum=sum^arr[i];
        
        return sum;
    }
};
