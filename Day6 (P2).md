Day 6 of 30 days challenge (CCD)

**PROBLEM:** Minimum Operations to Make Array Values Equal to K.
**PROBLEM LINK:** https://leetcode.com/problems/minimum-operations-to-make-array-values-equal-to-k/description/?envType=daily-question&envId=2025-04-09

**DESCRIPTION**
You are given an integer array nums and an integer k.
An integer h is called valid if all values in the array that are strictly greater than h are identical.
For example, if nums = [10, 8, 10, 8], a valid integer is h = 9 because all nums[i] > 9 are equal to 10, but 5 is not a valid integer.
You are allowed to perform the following operation on nums:
    Select an integer h that is valid for the current values in nums.
    For each index i where nums[i] > h, set nums[i] to h.
Return the minimum number of operations required to make every element in nums equal to k. If it is impossible to make all elements equal to k, return -1.

**INPUT && OUTPUT:**
Input: nums = [5,2,5,4,5], k = 2
Output: 2

**APPROACH:**
1. Check if it's possible:
      If any number in nums is less than k, return -1 (because you can only decrease numbers).
2. Count unique numbers > k:
      Collect all unique numbers greater than k.
      The number of unique numbers greater than k is the answer.
   Why?
      In each operation, you can "eliminate" the current highest number by lowering it to the next lower unique number.
      Do this until you reach k.
3. Return the count.

**CODE:**
```cpp
class Solution {
public:
    int minOperations(vector<int>& nums, int k) {
        map<int,int> mp;
        int count=0;
        for(int i=0;i<nums.size();i++)
        {
            if(nums[i]<k)
            return -1;

            else
            mp[nums[i]]++;
        }
        for(auto it=mp.begin();it!=mp.end();it++)
        {
            if(it->first>k)
            count++;
        }

        return count;
    }
};
