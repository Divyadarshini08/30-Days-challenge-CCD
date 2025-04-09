Day 6 of 30 days challenge (CCD)

**PROBLEM:** Move all Zeroes to End.
**LINK:** https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/move-all-zeroes-to-end-of-array0751

**DESCRIPTION:**
You are given an array arr[] of non-negative integers. 
Your task is to move all the zeros in the array to the right end while maintaining the relative order of the non-zero elements. 
The operation must be performed in place, meaning you should not use extra space for another array.

**SAMPLE INPUT & OUTPUT:**
Input: arr[] = [1, 2, 0, 4, 3, 0, 5, 0]
Output: [1, 2, 4, 3, 5, 0, 0, 0]

**APPROACH:**
1. Initialize count = 0 (to track position for non-zero elements).
2. Traverse the array from start to end:
      If the current element is non-zero:
      Swap the current element with the element at index count.
      Increment count by 1.
3. All zeros are moved to the end.

**CODE:**

```cpp
// User function template for C++
class Solution {
  public:
    void pushZerosToEnd(vector<int>& arr) {
        // code here
        int i=0,j=1;
        while(j<arr.size())
        {
            if(arr[i]==0 && arr[j]!=0)
            {
                int temp=arr[i];
                arr[i]=arr[j];
                arr[j]=temp;
                i++;
                j++;
                
            }
            else if(arr[j]==0 && arr[i]==0)
            {
                while(j<arr.size() && arr[j]==0)
                j++;
            }
            
            else{
                i++;j++;
            }
        }
    }
};
