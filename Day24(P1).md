**PROBLEM: SORT 0s 1s 2s**

**DESCRIPTION:**
Given an array arr[] containing only 0s, 1s, and 2s. Sort the array in ascending order.
You need to solve this problem without utilizing the built-in sort function.

**CODE:**
```cpp
class Solution {
  public:
    void sort012(vector<int>& arr) {
        // code here
        int c1=0,c2=0,c3=0;
        for(int i=0;i<arr.size();i++)
        {
            if(arr[i]==0)
            c1++;
            if(arr[i]==1)
            c2++;
            if(arr[i]==2)
            c3++;
        }int j=0;
        for(int i=0;i<c1;i++)
        { 
            arr[j++]=0;
        }
        for(int i=0;i<c2;i++)
        {
            arr[j++]=1;
        }
        for(int i=0;i<c3;i++)
        {
            arr[j++]=2;
        }
    }
};

