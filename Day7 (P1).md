Day 7 of 30 Days Challenge

**PROBLEM:** Reverse an Array.
**LINK:** https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/reverse-an-array.

**DESCRIPTION:** You are given an array of integers arr[]. Your task is to reverse the given array.

**SAMPLE INPUT & OUTPUT:**
Input: arr = [1, 4, 3, 2, 6, 5]
Output: [5, 6, 2, 3, 4, 1]

**APPROACH:**
1. Initialize two pointers
    i = 0 (start of the array)
    j = arr.size() - 1 (end of the array)
2. Check condition
    While i < j, do the following steps.
        Swap elements
        Swap arr[i] and arr[j].
3. Move pointers
    Increment i by 1 (i++)
    Decrement j by 1 (j--)
4. Repeat
    Continue steps 2 to 4 until i >= j.
5. The array is now reversed!


**CODE:**

```cpp
class Solution {
  public:
    void reverseArray(vector<int> &arr) {
        // code here
        int i=0,j=arr.size()-1;
        while(i<j)
        {
            int temp=arr[i];
            arr[i]=arr[j];
            arr[j]=temp;
            
            i++;
            j--;
        }
    }
};
