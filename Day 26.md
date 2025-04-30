Day 26 of 30 Days challenge

**PROBLEM:** Count Inversions.

**LINK:** https://www.geeksforgeeks.org/batch/gfg-160-problems/track/sorting-gfg-160/problem/inversion-of-array-1587115620.

**DESCRIPTION:** 
Given an array of integers arr[]. Find the Inversion Count in the array.
Two elements arr[i] and arr[j] form an inversion if arr[i] > arr[j] and i < j.

Inversion Count: For an array, inversion count indicates how far (or close) the array is from being sorted. If the array is already sorted then the inversion count is 0.
If an array is sorted in the reverse order then the inversion count is the maximum. 

**SAMPLE INPUT & OUTPUT:**
Input: arr[] = [2, 4, 1, 3, 5]
Output: 3
Explanation: The sequence 2, 4, 1, 3, 5 has three inversions (2, 1), (4, 1), (4, 3).

**APPROACH:**

1. **Divide** the array recursively into two halves until each subarray has one element.  
2. **Merge** the sorted halves while comparing elements from both sides.  
3. **Count** inversions when an element from the right half is placed before one from the left half — it means all remaining left-side elements form inversions.  
4. **Store** merged elements in a temporary array and copy back to the original.  
5. **Return** the total count of inversions after completing the merge process.  

**CODE:**
```cpp
class Solution {
    int cnt=0;
    void merge(vector<int> &arr,int low,int mid,int high)
    {
        vector<int> temp;
        int left=low;
        int right=mid+1;
        while(left<=mid && right<=high)
        {
            if(arr[left]<=arr[right])
            temp.push_back(arr[left++]);
            
            else{
                cnt=cnt+(mid-left+1);
                temp.push_back(arr[right++]);
            }
        }
        while(left<=mid)
        temp.push_back(arr[left++]);
        
        while(right<=high)
        temp.push_back(arr[right++]);
        
        for(int i=low;i<=high;i++)
        arr[i]=temp[i-low];
    }
    void mergesort(vector<int>& arr,int low,int high)
    {
        if(low>=high)return;
        int mid=(low+high)/2;
        mergesort(arr,low,mid);
        mergesort(arr,mid+1,high);
        merge(arr,low,mid,high);
    }
  public:
    // Function to count inversions in the array.
    int inversionCount(vector<int> &arr) {
        // Your Code Here
        mergesort(arr,0,arr.size()-1);
        return cnt;
    }
};
