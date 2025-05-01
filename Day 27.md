Day 27 of 30 Days Challenge (CCD)

**PROBLEM:** Overlapping SubIntervals.

**LINK:** https://www.geeksforgeeks.org/batch/gfg-160-problems/track/sorting-gfg-160/problem/overlapping-intervals--170633.

**DESCRIPTION:** 
Given an array of Intervals arr[][], where arr[i] = [starti, endi]. The task is to merge all of the overlapping Intervals.

**SAMPLE INPUT & OUTPUT:**
Input: arr[][] = [[1,3],[2,4],[6,8],[9,10]]
Output: [[1,4], [6,8], [9,10]]
Explanation: In the given intervals we have only two overlapping intervals here, [1,3] and [2,4] which on merging will become [1,4]. Therefore we will return [[1,4], [6,8], [9,10]].

**CODE:**

```cpp
class Solution {
  public:
    vector<vector<int>> mergeOverlap(vector<vector<int>>& arr) {
        // Code here
        vector<vector<int>> result;
        sort(arr.begin(),arr.end());
        for(int i=0;i<arr.size();i++)
        {
            if(result.empty() || arr[i][0]>result.back()[1])
            result.push_back(arr[i]);
            
            else
            result.back()[1]=max(result.back()[1],arr[i][1]);
        }
        return result;
    }
};
