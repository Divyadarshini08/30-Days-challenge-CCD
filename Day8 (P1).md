Day 8 of 30 Days Challenge CCD

**PROBLEM:** Next Permutation Possible

**LINK:** https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/next-permutation5226

**DESCRIPTION:**
Given an array of integers arr[] representing a permutation, implement the next permutation that rearranges the numbers into the lexicographically next greater permutation. 
If no such permutation exists, rearrange the numbers into the lowest possible order (i.e., sorted in ascending order). 

**INPUT & OUTPUT:**
Input: arr = [2, 4, 1, 7, 5, 0]
Output: [2, 4, 5, 0, 1, 7]

**APPROACH:**
1. Start from the end and find the first index i such that arr[i] < arr[i + 1].
2. If no such index is found, the array is in descending order — reverse it to get the first permutation.
3. Otherwise, find the smallest number greater than arr[i] to the right of it.
4. Swap arr[i] with that number.
5. Reverse the subarray to the right of i

**CODE:**
```cpp
class Solution {
  public:
    void nextPermutation(vector<int>& arr) {
        // code here
        int i;
        for(i=arr.size()-2;i>=0;i--)
        {
            if(arr[i]<arr[i+1])
                break;
        }
        
        if(i<0)
        {
            sort(arr.begin(),arr.end());
        }
        else{
            
            for(int j=arr.size()-1;j>=0;j--)
            {
                if(arr[j]>arr[i])
                {
                    int temp=arr[j];
                    arr[j]=arr[i];
                    arr[i]=temp;
                    
                    break;
                }
            }
            reverse(arr.begin()+i+1,arr.end());
        }
    }
};

