Day 28 of 30 Days Challenge CCD

**PROBLEM:** Insert Interval.

**LINK:** https://www.geeksforgeeks.org/batch/gfg-160-problems/track/sorting-gfg-160/problem/insert-interval-1666733333

**DESCRIPTION:** 
Geek has an array of non-overlapping intervals intervals where intervals[i] = [starti, endi] represent the start and the end of the ith event and intervals is sorted in ascending order by starti. 
He wants to add a new interval newInterval= [newStart, newEnd] where newStart and newEnd represent the start and end of this interval.
Help Geek to insert newInterval into intervals such that intervals is still sorted in ascending order by starti and intervals still does not have any overlapping intervals (merge overlapping intervals if necessary).

**INPUT & OUTPUT:**
Input: intervals = [[1,3], [4,5], [6,7], [8,10]], newInterval = [5,6]
Output: [[1,3], [4,7], [8,10]]
Explanation: The newInterval [5,6] overlaps with [4,5] and [6,7].

**CODE:**
```cpp
class Solution {
  public:
    vector<vector<int>> insertInterval(vector<vector<int>> &intervals,
                                       vector<int> &newInterval) {
        // code here
        vector<vector<int>> result;
        intervals.push_back(newInterval);
        sort(intervals.begin(),intervals.end());
        for(int i=0;i<intervals.size();i++)
        {
            if(result.empty() || result.back()[1]<intervals[i][0])
            result.push_back(intervals[i]);
            
            else
            result.back()[1]=max(result.back()[1],intervals[i][1]);
        }
        return result;
    }
};
