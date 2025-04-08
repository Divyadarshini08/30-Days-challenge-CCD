Day 5 of 30 Days Challenge

**PROBLEM:** Minimum Number of Operations to Make Elements in Array Distinct.
**PROBLEM LINK: **https://leetcode.com/problems/minimum-number-of-operations-to-make-elements-in-array-distinct/description/?envType=daily-question&envId=2025-04-08

Given an integer array nums. You need to ensure that the elements in the array are distinct. To achieve this, you can perform the following operation any number of times:
Remove 3 elements from the beginning of the array. If the array has fewer than 3 elements, remove all remaining elements.

**Note** that an empty array is considered to have distinct elements. Return the minimum number of operations needed to make the elements in the array distinct.

**INPUT:** nums = [1,2,3,4,2,3,3,5,7]
**OUTPUT:** 2

**APPROACH:**
1. Start from index i = 0.
2. In steps of 3, check if the subarray from i to end has unique elements.
3. If yes, return the number of steps taken so far.
4. If no, keep going until the end.


**CODE**
```cpp
class Solution {
int oper( vector<int> &nums,int n)
{
     vector<int> seen(101,0);
    for(int i=n;i<nums.size();i++)
    {
        if(seen[nums[i]])
        return false;
        
        seen[nums[i]]=true;
    }
    return true;
}
public:
    int minimumOperations(vector<int>& nums) {
       
        int ans=0;
        for(int i=0;i<nums.size();i=i+3,ans++)
        {
            if(oper(nums,i))
            return ans;
        }
        return ans;
    }
};
