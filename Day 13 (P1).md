Day 13 of 30 Days challenge CCD

**PROBLEM:** Minimize the Heights I
**LINK:** https://www.geeksforgeeks.org/problems/minimize-the-heights-i/1

**DESCRIPTION:**
Given a array arr[] and positive integer k denoting heights of towers, you have to modify the height of each tower either by increasing or decreasing them by k only once.
Find out what could be the possible minimum difference of the height of shortest and longest towers after you have modified each tower.

**INPUT & OUTPUT:**
Input: arr[] = [1, 5, 8, 10], k = 2
Output: 5
Explanation: The array can be modified as [3, 3, 6, 8]. The difference between the largest and the smallest is 8 - 3 = 5.

**APPROACH:**
1. Sort the array.
2. Initialize ans = arr[n-1] - arr[0].
3. Let smallest = arr[0] + k, largest = arr[n-1] - k.
4. For each i from 0 to n-2:
5. Calculate min_height = min(smallest, arr[i+1] - k) and max_height = max(largest, arr[i] + k).
6. Update ans = min(ans, max_height - min_height).



**CODE:**
```cpp
class Solution {
  public:
    int getMinDiff(vector<int> &arr, int k) {
        // code here
        sort(arr.begin(),arr.end());
        if (arr.size() == 1) return 0;
        int min_height,smallest=arr[0]+k,ans= arr[arr.size() - 1] - arr[0];
        int max_height,largest=arr[arr.size()-1]-k;
        for(int i=0;i<arr.size()-1;i++)
        {
            min_height = min(smallest, arr[i+1] - k);
            max_height = max(largest, arr[i] + k);
            
            ans = min(ans, max_height - min_height);
        }
        return ans;
    }
};
